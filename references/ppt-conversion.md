# PPT Conversion

## Workflow
1. Extract text, images, and notes from `.pptx`.
2. Present extracted structure to user for confirmation.
3. Select style (guided or direct).
4. Generate HTML deck preserving order and assets.

## Extraction Baseline (python-pptx)

```python
from pptx import Presentation
import os

def extract_pptx(file_path, output_dir):
    prs = Presentation(file_path)
    slides_data = []

    assets_dir = os.path.join(output_dir, 'assets')
    os.makedirs(assets_dir, exist_ok=True)

    for slide_num, slide in enumerate(prs.slides):
        slide_data = {
            'number': slide_num + 1,
            'title': '',
            'content': [],
            'images': [],
            'notes': ''
        }

        for shape in slide.shapes:
            if shape.has_text_frame:
                if shape == slide.shapes.title:
                    slide_data['title'] = shape.text
                else:
                    slide_data['content'].append({'type': 'text', 'content': shape.text})

            if shape.shape_type == 13:
                image = shape.image
                image_name = f"slide{slide_num + 1}_img{len(slide_data['images']) + 1}.{image.ext}"
                image_path = os.path.join(assets_dir, image_name)

                with open(image_path, 'wb') as f:
                    f.write(image.blob)

                slide_data['images'].append({'path': f"assets/{image_name}"})

        if slide.has_notes_slide:
            slide_data['notes'] = slide.notes_slide.notes_text_frame.text

        slides_data.append(slide_data)

    return slides_data
```

## Confirmation Template

```text
I extracted the following:
- Slide 1: <title>, text blocks: <count>, images: <count>
- Slide 2: <title>, text blocks: <count>, images: <count>
...

Does this structure look correct before I style and generate HTML?
```

## Preservation Rules
- Preserve slide sequence.
- Preserve all extracted images unless user asks to drop/replace.
- Preserve speaker notes as comments or separate companion output.
- Keep generated HTML viewport-safe using the viewport fitting rules.
