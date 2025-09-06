```python
from datetime import datetime
import pytz  # pip install pytz if not available

def generate_timestamp_ist():

    ist = pytz.timezone('Asia/Kolkata')
    now = datetime.now(ist)
    return now.strftime("%I-%M%p_%d-%B_%Y")

# Example usage
timestamp = generate_timestamp_ist()
print(timestamp)  # e.g., 07-00AM_06-September_2025
# use like this: filename = generate_timestamp_ist() + ".extension"
```  
#### Output:  
```console
12-34PM_06-September_2025
```  