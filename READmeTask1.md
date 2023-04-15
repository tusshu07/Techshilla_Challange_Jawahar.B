Download the python file of submission : "Submission.py" in your local device.
Install the pyinstaller package using pip by running the following command in the terminal:

```
pip install pyinstaller
```

Navigate to the directory where your Python script is located.

Run the following command in the terminal to create a standalone executable file:
```
pyinstaller --onefile Submission.py
```
Replace Submission.py with the name of your Python script.

Wait for the process to complete. Once done, you will see a new dist folder created in the same directory as your Python script.

Inside the dist folder, you will find the executable file with the same name as your Python script. This file can be moved to your desktop or anywhere else, and double-clicking on it will run your Python script.
Note: If your script has any dependencies, such as external packages or modules, you will need to include them using the --hidden-import option when running the pyinstaller command. For example, if your script uses the requests package, you can include it using the following command:
```
pyinstaller --onefile --hidden-import requests your_script_name.py
```
This will install the executable file of Submission file in the dist folder
Double click on this executable application file.
It will run the two windows simultaneously : one of GUI Application and other one will be command window.
Enter the number of drones,plane and draw the shape in the grid area in pink. Click on download and quit button.
It will generate the 2-D drone coordinates in the txt file.This file will be saved as 3D_drone_coordinates.txt in the dist folder.


Drive link to download the .exe Application file of Submssion: https://drive.google.com/file/d/1qCl8kElsF3wp2GAsMB0I2SxN-Td8BVbR/view?usp=sharing
