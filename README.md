## Python Scripts

```python
import os
from PIL import Image, ImageDraw, ImageFont

# Dimensions for KDP (8.625 x 11.25 inches @ 300 DPI)
DPI = 300
WIDTH_PX = int(8.625 * DPI)
HEIGHT_PX = int(11.25 * DPI)

# Generate Page 2
canvas = Image.new("L", (WIDTH_PX, HEIGHT_PX), 255)
draw = ImageDraw.Draw(canvas)

# Drawing elements (Tiko & Egg)
draw.ellipse((800, 900, 1500, 1600), outline=0, fill=255, width=8)
draw.ellipse((1350, 1600, 2150, 2600), outline=0, fill=255, width=10)

# Save image
os.makedirs("raw_images", exist_ok=True)
canvas.save("raw_images/page_02.png", dpi=(DPI, DPI))
print("Page 02 generated!")
