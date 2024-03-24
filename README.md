# The Toothpaste Cap Reminder Study

This is a basic data science project.

It aims to answer the question: "how many times do I have to remind you?".

It is based on an initial [Google Colab project](https://colab.research.google.com/drive/1r9bKIuGanhqMT_pjLlirAoXo2Erb0CSS?authuser=0#scrollTo=m3-BN8saYbXU).

This relied on some environment specific libraries such as ```from google.colab import files``` which allow you to upload a file on your local system for use in the notebook in the cloud.  Running locally it is replaced by the Pandas ```dataFrame = pd.read_excel('toothpaste-data.xlsx')``` function.

## The rules of the study

The initial study was done using my daughter's forgetting to put the cap back on the toothpaste.  I collected the data according to the following rules.

- every time my daughter leaves to top off the toothpaste, I reminder to put the cap back on after using it.
- every time she remembers to put the cap on the toothpaste after using it, I put a one in the remember column.
- So for the data model, there are three columns, including an index.

## Setting up

VSCode has some good [tutorials](https://code.visualstudio.com/docs/datascience/overview) on working with Jupyter notebooks.

When setting up a Jupyter notebook to run locally, the first time you may see errors like this indicating missing dependencies.

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

If you have Python installed on your system and reachable via the command prompt, you can just install packages using pip like this:

To fix the above run this command: ```python -m pip install pandas```

```sh
---------------------------------------------------------------------------
ModuleNotFoundError                       Traceback (most recent call last)
Cell In[3], line 2
      1 import pandas as pd
----> 2 import matplotlib.pyplot as plt
      4 # Step 1: Upload the Excel File


ModuleNotFoundError: No module named 'matplotlib'
```

```sh
python -m pip install matplotlib
```

I also had to install this:

```sh
python -m pip install openpyxl
```
