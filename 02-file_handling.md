# Python File Handling

Authors: Sueyvid José

Date: July 26, 2025

## Stages
- ~~Read and understand~~
- ~~Write in your structure~~
- ~~Review with Anki~~
- Watch a video
- Create a slide
- Record a video or an audio

## File Handling

Python has several functions for creating, reading, updating, and deleting files.

The open() function takes two parameters; filename, and mode.

There are four different methods (modes) for opening a file:

- `"r"` - Read - Default value. Opens a file for reading, error if the file does not exist
- `"a"` - Append - Opens a file for appending, creates the file if it does not exist
- `"w"` - Write - Opens a file for writing, creates the file if it does not exist
- `"x"` - Create - Creates the specified file, returns an error if the file exists

In addition you can specify if the file should be handled as binary or text mode:

- `"t"` - Text - Default value. Text mode
- `"b"` - Binary - Binary mode (e.g. images)

To open a file for reading it is enough to specify the name of the file:

```python
f = open("demofile.txt")
```

The code above is the same as:

```python
f = open("demofile.txt", "rt")
```

Because "r" for read, and "t" for text are the default values, you do not need to specify them.

**Note:** Make sure the file exists, or else you will get an error.

## Open a File

To open the file, use the built-in `open()` function.

The `open()` function returns a file object, which has a `read()` method for reading the content of the file:

```python
f = open("demofile.txt")
print(f.read()) 
```

Open a file on a different location:

```python
f = open("D:\\myfiles\welcome.txt")
print(f.read()) 
```

## Using the with statement

You can also use the `with` statement when opening a file:

```python
with open("demofile.txt") as f:
  print(f.read()) 
```

Then you do not have to worry about closing your files, the `with` statement takes care of that.

## Close files

It is a good practice to always close the file when you are done with it.

If you are not using the with statement, you must write a close statement in order to close the file:

```python
f = open("demofile.txt")
print(f.readline())
f.close() 
```

**Note**: You should always close your files. In some cases, due to buffering, changes made to a file may not show until you close the file.

## Read Only Parts of the File

By default the `read()` method returns the whole text, but you can also specify how many characters you want to return:

Return the 5 first characters of the file:

```python
with open("demofile.txt") as f:
  print(f.read(5)) 
```

## Read Lines

You can return one line by using the `readline()` method:

```python
with open("demofile.txt") as f:
  print(f.readline()) 
```

By calling readline() two times, you can read the two first lines:

```python
with open("demofile.txt") as f:
  print(f.readline())
  print(f.readline()) 
```

By looping through the lines of the file, you can read the whole file, line by line:

```python
with open("demofile.txt") as f:
  for x in f:
    print(x) 
```

## Write to an Existing File

To write to an existing file, you must add a parameter to the `open()` function:

- `"a"` - Append - will append to the end of the file
- `"w"` - Write - will overwrite any existing content

Open the file "demofile.txt" and append content to the file:

```python
with open("demofile.txt", "a") as f:
  f.write("Now the file has more content!")

#open and read the file after the appending:
with open("demofile.txt") as f:
  print(f.read()) 
```

## Overwrite Existing Content

To overwrite the existing content to the file, use the `w` parameter:

```python
with open("demofile.txt", "w") as f:
  f.write("Woops! I have deleted the content!")

#open and read the file after the overwriting:
with open("demofile.txt") as f:
  print(f.read()) 
```

**Note**: the "w" method will overwrite the entire file.

## Create a New File

To create a new file in Python, use the `open()` method, with one of the following parameters:

- `"x"` - Create - will create a file, returns an error if the file exists
- `"a"` - Append - will create a file if the specified file does not exists
- `"w"` - Write - will create a file if the specified file does not exists

Create a new file called "myfile.txt":

```python
f = open("myfile.txt", "x") 
```

Result: a new empty file is created.

**Note**: If the file already exist, an error will be raised.

## Delete a File

To delete a file, you must import the OS module, and run its `os.remove()` function:

```python
import os
os.remove("demofile.txt") 
```

## Check if File exist:

To avoid getting an error, you might want to check if the file exists before you try to delete it:

```python
import os
if os.path.exists("demofile.txt"):
  os.remove("demofile.txt")
else:
  print("The file does not exist") 
```

## Delete Folder

To delete an entire folder, use the `os.rmdir()` method:

```python
import os
os.rmdir("myfolder") 
```

**Note**: You can only remove *empty* folders.

## References

- [w3schools - Python File Handling](https://www.w3schools.com/python/python_file_handling.asp)
