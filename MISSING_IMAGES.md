# Missing Equipment Images for Eta.html

The following image files are referenced in Eta.html but are not currently present in the repository:

## Required Images

1. **tiller.png** - Icon for tiller equipment
2. **blade.png** - Icon for blade equipment  
3. **tracks.png** - Icon for tracks equipment
4. **finisher.png** - Icon for cross-country tracks equipment

## Image Specifications

These images should match the style and dimensions of existing equipment icons:
- Recommended size: 64x64 pixels (or larger, as they will be scaled)
- Format: PNG with transparency
- Style: Should match the existing groomer.png and charger.png icons

## Fallback Behavior

The current implementation includes fallback handling:
- If an image file is missing, the code will automatically display a generic emoji (📦) instead
- This ensures the application continues to function even without the image files

## Adding Images

To add these images:
1. Create or obtain appropriate icon images
2. Save them with the exact filenames listed above
3. Place them in the root directory of the project (same location as groomer.png and charger.png)

The images will be automatically picked up by the application once they are in place.
