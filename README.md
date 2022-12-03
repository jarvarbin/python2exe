# python2exe

Here is a simple example of how to write a Python program that converts a Python script to an executable file (.exe) in Windows:

```
import os
import sys

# Check if the required arguments were provided
if len(sys.argv) != 3:
  print("Usage: python_to_exe.py <input_file> <output_file>")
  sys.exit(1)

# Set the input and output file paths
input_file = sys.argv[1]
output_file = sys.argv[2]

# Check if the input file exists
if not os.path.exists(input_file):
  print("Error: Input file does not exist")
  sys.exit(1)

# Set the command to convert the input file to an executable
command = f"pyinstaller -F {input_file}"

# Run the command and check for errors
if os.system(command) != 0:
  print("Error: Failed to convert the file to an executable")
  sys.exit(1)

# Rename the output file to the specified name
os.rename("dist/main.exe", output_file)

# Print a success message
print(f"Successfully converted {input_file} to {output_file}")

```

This code uses the os and sys modules in Python to convert a Python script to an executable file using the pyinstaller command. The os.path.exists() function is used to check if the input file exists, and the os.system() function is used to run the pyinstaller command and convert the input file to an executable. The os.rename() function is then used to rename the output file to the specified name.

To run this code, you will need to install the pyinstaller module using pip:
```
$ pip install pyinstaller
```
Then, you can save the code to a file and run it using the python command with the input and output file paths as arguments:

```
$ python python_to_exe.py input.py output.exe
```
This will convert the input.py script to an executable file called output.exe. Note that this code is just an example and may not work on all systems. It is also important to mention that the pyinstaller module may require some additional dependencies to be installed on your system for this code to work correctly.
