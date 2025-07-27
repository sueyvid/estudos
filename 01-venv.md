# Python Virtual Environment

Authors: Sueyvid José

Date: July 25, 2025

## Stages
- ~~Read and understand~~ 
- ~~Write in your structure~~
- ~~Review with Anki~~
- ~~Watch a video~~
- Create a slide
- Record a video or an audio

## What is a venv?
venv is an isolated environment on your computer, where you can run and test your Python projects.

It allows you to manage project-specific dependencies without interfering with other projects or the original Python installation.

Properties:
- Has its own Python interpreter
- Has its own set of installed packages
- Is isolated from other virtual environments
- Can have different versions of the same package

Utility:
- It prevents package version conflicts between projects
- Makes projects more portable and reproducible
- Keeps your system Python installation clean
- Allows testing with different Python versions

## Creating a venv

open the command prompt > navigate to the folder of your project > type this command:

Windows or macOS/Linux:
```shell
python -m venv myfirstproject 
```

This will set up a virtual environment, and create a folder named "myfirstproject" with subfolders and files.


## Activate venv

To use the virtual environment, you have to activate it with this command:

Windows:
```shell
myfirstproject\Scripts\activate 
```

macOS/Linux:
```shell
source myfirstproject/bin/activate 
```

After activation, your prompt will change to show that you are now working in the active environment:

```
(myfirstproject) ...
```

## Install packages

Once your virtual environment is activated, you can install packages in it, using `pip`.

We will install a package called 'cowsay' in the venv:

Windows or macOS/Linux:
```shell
pip install cowsay 
```

## Using package

Create a file called test.py on your computer.

You can place it wherever you want, but I will place it in the same location as the `myfirstproject` folder.

Open the file and insert these four lines in it:

```python
# test.py
import cowsay

cowsay.cow("Good Mooooorning!")
```

Then, try to execute the file while you are in the virtual environment:

Windows or macOS/Linux:
```shell
python test.py  
```

## Deactivate venv

To deactivate the virtual environment use this command:

Windows or macOS/Linux:
```shell
deactivate  
```

As a result, you are now back in the normal command line interface:

Windows or macOS/Linux:
```shell
  
```

If you try to execute the test.py file outside of the virtual environment, you will get an error because 'cowsay' is missing.

It was only installed in the virtual environment.

**Note**: The virtual environment `myfirstproject` still exists, it is just not activated. If you activate the virtual environment again, you can execute the `test.py` file, and the diagram will be displayed.

## Delete venv

To delete a virtual environment, you can simply delete its folder with all its content.

Windows:
```shell
rmdir /s /q myfirstproject 
```

macOS/Linux:
```shell
rm -rf myfirstproject 
```

## Saving dependencies

To export our entire environment we can simply save a list of all of the dependencies we used into a requirement txt file.

```shell
pip freeze > requirements.txt
```

## Importing dependencies

You can install all of dependencies using the `requirements.txt` file.

```shell
pip install -r requirements.txt
```

`-r`: stands for install from a file.

To see all of installed packages:

```shell
pip list
```

## References

- [w3schools - Python VirtualEnv [Doc]](https://www.w3schools.com/python/python_virtualenv.asp)
- [Tech With Tim - Python Virtual Environments [Video]](https://www.youtube.com/watch?v=Y21OR1OPC9A)
