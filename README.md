# The Toothpaste Cap Reminder Study

## Setting up

```sh
Running cells with 'c:\Users\timof\AppData\Local\Programs\Python\Python310\python.exe' requires the ipykernel package.
Run the following command to install 'ipykernel' into the Python environment. 
Command: 'c:/Users/timof/AppData/Local/Programs/Python/Python310/python.exe -m pip install ipykernel -U --user --force-reinstall'
```

The command shown fixes this.

```sh
---------------------------------------------------------------------------
ModuleNotFoundError                       Traceback (most recent call last)
Cell In[1], line 1
----> 1 import pandas as pd
      2 import matplotlib.pyplot as plt
      4 # Step 1: Upload the Excel File
      5 # Replace this step with the code to read your Excel file locally
      6 # For example:
   (...)
      9 
     10 # Step 3: Read the Excel File into a Pandas DataFrame

ModuleNotFoundError: No module named 'pandas'
```

To fix the above run this command: ```python -m pip install pandas```

```sh
---------------------------------------------------------------------------
ModuleNotFoundError                       Traceback (most recent call last)
Cell In[2], line 2
      1 import pandas as pd
----> 2 import matplotlib.pyplot as plt
      4 # Step 1: Upload the Excel File
      5 # Replace this step with the code to read your Excel file locally
      6 # For example:
   (...)
      9 
     10 # Step 3: Read the Excel File into a Pandas DataFrame
     11 dataFrame = pd.read_excel('toothpaste-data.xlsx')  # Replace 'path_to_your_file.xlsx' with the actual file path

ModuleNotFoundError: No module named 'matplotlib'
```

```sh
python -m pip install pandas
```

```sh
---------------------------------------------------------------------------
ModuleNotFoundError                       Traceback (most recent call last)
Cell In[3], line 2
      1 import pandas as pd
----> 2 import matplotlib.pyplot as plt
      4 # Step 1: Upload the Excel File
      5 # Replace this step with the code to read your Excel file locally
      6 # For example:
   (...)
      9 
     10 # Step 3: Read the Excel File into a Pandas DataFrame
     11 dataFrame = pd.read_excel('toothpaste-data.xlsx')  # Replace 'path_to_your_file.xlsx' with the actual file path

ModuleNotFoundError: No module named 'matplotlib'
```

```sh
python -m pip install matplotlib
```

```sh
import pandas as pd
import matplotlib.pyplot as plt

# Step 1: Upload the Excel File
# Replace this step with the code to read your Excel file locally
# For example:
# file_path = 'path_to_your_file.xlsx'
# dataFrame = pd.read_excel(file_path)

# Step 3: Read the Excel File into a Pandas DataFrame
dataFrame = pd.read_excel('toothpaste-data.xlsx')  # Replace 'path_to_your_file.xlsx' with the actual file path

# Step 4: Convert 'Forgot' and 'Remembered' columns to numeric, treating non-numeric values as NaN
dataFrame['Forgot'] = pd.to_numeric(dataFrame['Forgot'], errors='coerce')
dataFrame['Remembered'] = pd.to_numeric(dataFrame['Remembered'], errors='coerce')

# Step 5: Fill NaN values with zeros and calculate the 'Forgot Percentage' cumulatively
dataFrame['Forgot'] = dataFrame['Forgot'].fillna(0)
dataFrame['Remembered'] = dataFrame['Remembered'].fillna(0)

# Calculate the 'Forgot Percentage' cumulatively for each row
dataFrame['Forgot_Cumulative'] = dataFrame['Forgot'].cumsum()
dataFrame['Remembered_Cumulative'] = dataFrame['Remembered'].cumsum()
dataFrame['Forgot_Percentage'] = (dataFrame['Forgot_Cumulative'] / (dataFrame['Remembered_Cumulative'] + dataFrame['Forgot_Cumulative'])) * 100

# Step 6: Plot the Data
plt.figure(figsize=(10, 6))
plt.plot(dataFrame['Forgot_Percentage'], marker='o', linestyle='-')
plt.title('Forgot Percentage Cumulative Over Rows')
plt.xlabel('Row Number')
plt.ylabel('Forgot Percentage')
plt.grid(True)
plt.show()
```

```sh
python -m pip install openpyxl
```
