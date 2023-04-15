Install the pyinstaller package using pip by running the following command in the terminal:

```
pip install pyinstaller
```

Navigate to the directory where your Python script is located.

Run the following command in the terminal to create a standalone executable file:
```
pyinstaller --onefile your_script_name.py
```
Replace your_script_name.py with the name of your Python script.

Wait for the process to complete. Once done, you will see a new dist folder created in the same directory as your Python script.

Inside the dist folder, you will find the executable file with the same name as your Python script. This file can be moved to your desktop or anywhere else, and double-clicking on it will run your Python script.
Note: If your script has any dependencies, such as external packages or modules, you will need to include them using the --hidden-import option when running the pyinstaller command. For example, if your script uses the requests package, you can include it using the following command:
```
pyinstaller --onefile --hidden-import requests your_script_name.py
```
