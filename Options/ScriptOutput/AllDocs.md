Snippets\File Handling\01 File Upload.md
```md
## Image Upload
### Basic Image upload  
```python
from google.colab import files
from PIL import Image
import matplotlib.pyplot as plt

# Upload image
uploaded = files.upload()  # opens file chooser

# Get the first uploaded file name
img_path = next(iter(uploaded))

# Open and display
img = Image.open(img_path)
plt.imshow(img)
plt.axis('off')  # hide axes
plt.show();
```  
##### Preview:  
![](../../z_images/001/09.png)  
### Image upload & tabular data
```python
from google.colab import files
from PIL import Image
import pandas as pd
import io
import matplotlib.pyplot as plt

# 1️⃣ Upload image
uploaded = files.upload()
img_name = next(iter(uploaded))  # get the first file name

# 2️⃣ Open image from bytes
img = Image.open(io.BytesIO(uploaded[img_name]))

# 3️⃣ Preview image
plt.imshow(img)
plt.axis('off')
plt.show()

# 4️⃣ Gather image info
info = {
    "Property": ["Filename", "Format", "Mode", "Width", "Height", "Size (bytes)"],
    "Value": [
        img_name,
        img.format,
        img.mode,
        img.width,
        img.height,
        len(uploaded[img_name])  # actual size in bytes
    ]
}

# 5️⃣ Display info as table
df = pd.DataFrame(info)
df
```  
##### Preview:  
![](../../z_images/001/10.png)
```

Snippets\Info\GPU available or not.md
```md
```python
import torch

if torch.cuda.is_available():
    print("✅ GPU available:", torch.cuda.get_device_name(0))
else:
    print("❌ No GPU");
```  
#### Output: if GPU not available  
```console
❌ No GPU
```  
#### Output: if GPU available    
```console
✅ GPU available: Tesla T4
```
```
