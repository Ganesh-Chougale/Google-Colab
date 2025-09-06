### 1. Create a new notebook  
crete a new notebook & give it a name `CSV_JSON_Converter`  
### 2. inject core snippet  
```python
import os

# Mount Google Drive
from google.colab import drive
drive.mount('/content/drive')

# Define paths
input_dir = "/content/drive/MyDrive/Colab Notebooks/Projects/CSV_JSON_Converter/Files/Input"
output_dir = "/content/drive/MyDrive/Colab Notebooks/Projects/CSV_JSON_Converter/Files/Output"

# Create folders if they don't exist
os.makedirs(input_dir, exist_ok=True)
os.makedirs(output_dir, exist_ok=True)

print("Input folder:", input_dir)
print("Output folder:", output_dir)
```  
#### Output:  
```console
Mounted at /content/drive
Input folder: /content/drive/MyDrive/Colab Notebooks/Projects/CSV_JSON_Converter/Files/Input
Output folder: /content/drive/MyDrive/Colab Notebooks/Projects/CSV_JSON_Converter/Files/Output
```  
can also check these folder are created into drive  