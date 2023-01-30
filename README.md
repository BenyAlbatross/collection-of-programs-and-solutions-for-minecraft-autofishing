<h1>A list of autofishing programs for Minecraft 1.16+</h1>
<p align='center'>
  <em>Because every repo name is a permutation of "mine", "auto" and "fish" and my downloads folder is now a fish farm</em>
</p>
<p>
  This document contains <b>autofishers on Github categorised by type, and evaluated on its OS compatibility, reliability, and ease of use</b>. Readers with little technical knowledge looking for an autofisher to get going immediately, please check out the recommendations in summary and instructions at the bottom.
</p>

## Summary
- In 1.16+, minecraft fish farms do not work. New autofishers need to detect when the fishing bobber goes underwater, (right click) reel in, and (right click) cast out again. 
- Caption template matching works the best, and I recommend elias123tre's script. Requires python knowledge. (I may fork and provide an updated executable download in the future)
- If you want to run the autofisher without having to leave minecraft up on the screen, I recommend MrKinau's fishing bot. However, you won't be able to tell if anyone is nearby - making you very vulnerable to bans. Jar file available to run without technical knowledge needed.

## Glossary
- Executable: A program that can be run just by double clicking on it, with all the necessary components included inside or in the same folder. For example: .exe, .jar, .app, and UNIX Executable Files. Runs just like an app.
- Script: A file containing text lines of code. Requires installation of the programming language to your computer, so that the script can be interpreted. Requires knowledge of the terminal to install libraries, specify the language interpreter to be used, and the location of the file, and hence less user-friendly. 
- [**See end of document for instructions on running a python script**](#how-to-run-a-python-script-for-complete-beginners)
## Table of autofishers for Minecraft 1.16+



[Caption Template Image Matching](#matches-a-template-image-of-the-"fishing-bobber-splashes"-caption-to-a-screenshot-of-minecraft)\
[Autofishers that are Minecraft clients](#autofishers-that-are-minecraft-clients---takes-action-when-the-server-tells-the-client-that-the-fishing-bobber-has-splashed)\
[Fishing bobber color detectors](#fishing-bobber-color-detectors)\
[OCR](#using-optical-character-recognition-ocr-to-detect-if-the-"fishing-bobber-splases"-caption-appears-on-screen)\
[Future Testing](#using-optical-character-recognition-ocr-to-detect-if-the-"fishing-bobber-splases"-caption-appears-on-screen)


### Caption Template Image Matching: Checks whether the "Fishing Bobber Splashes" caption appears on your screen by matching your screen to a reference image
| Link  | How it works  | Executable or Script?  | Win  | Mac  | Linux  | Reliability  | Notes  |
|---|---|---|---|---|---|---|---|
| [elias123tre](https://github.com/elias123tre/minecraft-auto-fisher)  | Template matching: Checks if any part of **the whole screen** matches a template image of the "Fishing Bobber Splashes" caption (pyautogui.locateOnScreen)| Python script. The provided windows executable does not work, you have to compile it yourself using pyinstaller  | :white_check_mark:  | :white_check_mark:  | :white_check_mark:  | Very reliable and extremely easy to use. Minecraft window shouldn't be so small such that chat obscures captions. If fishing bobber splashes another time within a short duration, less reliable. | Very easy to use because the program uses a screenshot of the entire screen and no selection is required. The template is a image of the caption in English only. You could edit the python file to use your own image of a caption in a different language. Additionally, it requires an internet connection as the reference image is downloaded from imgur.  |
|[xxu-mzwyt](https://github.com/xxu-mzwyt/Minecraft-Auto-Fishing)   | Template matching: Checks if any part of a **selected part of the screen** matches a screenshot of the "Fishing Bobber Splashes" caption (cv2.BGR2GRAY on template and screenshot. cv2.matchTemplate). | Python Script | :white_check_mark:  | :white_check_mark:  | :white_check_mark:  | Very reliable. Minecraft window shouldn't be so small such that chat obscures captions. If fishing bobber splashes another time within a short duration, less reliable.  | Program UI text is in Chinese. English and Chinese (Simplified) template caption images are provided. Capturing and matching a smaller part of the screen might reduce processor workload, untested. However, this means that the selection needs to be repositioned if the Minecraft window is moved. |
### Autofishers that are Minecraft Clients - Takes action when the server tells the client that the fishing bobber has splashed
| Link  | How it works  | Executable or Script?  | Win  | Mac  | Linux  | Reliability  | Notes  | 
|---|---|---|---|---|---|---|---|
| [MrKinau's FishingBot](https://github.com/MrKinau/FishingBot)   | Background autofisher. The user has to position the minecraft player over water with fishing rod in hand, then log out and start the script. The program is a minecraft client.  | Jar executable  | :white_check_mark:  | :white_check_mark:  | :white_check_mark:  | Very reliable  |  Has a nice GUI, and shows a tally of loot collected.  |
| [Amund211](https://github.com/Amund211/autofish)  | Backgrond autofisher. The user has to position the minecraft player over water with fishing rod in hand, then log out and start the script. The program is a minecraft client. When the server instructs the client/script to play the "fishing bobber splashes" sound, the client detects the instruction and sends 2 right click commands | Python script  | :white_check_mark:  | :white_check_mark:  | :white_check_mark:  | Does not support Microsoft authentication, untested  |   | 
| [Nitro1231](https://github.com/Nitro1231/MineFish), [Nitro1231-Beta3](https://github.com/Nitro1231/MineFish-Beta3)  |   |   |   |   |   | I have not tested this  |   |

### Fishing Bobber Color Detectors
| Link  | How it works  | Executable or Script?  | Win  | Mac  | Linux  | Reliability  | Notes  |
|---|---|---|---|---|---|---|---|
|[kirb3](https://github.com/kirb3/minecraft-fisher)   | Detects changes in red intensity around the bobber. User indicates a window around the bobber  | Python script  | :white_check_mark:  | :white_large_square:  | :white_large_square:  | Did not work for me  | Uses windows specific libraries to capture the screen, so does not work on mac/linux  |
|[prerikoth](https://github.com/prerikoth/Minecraft-Auto-Fisher)   | Variation on kirb3's autofisher. Detects changes in red intensity around the bobber. User indicates a window around the bobber  | Python script  | :white_check_mark:  | :white_check_mark:  | :white_check_mark:  | Did not work for me  | Uses windows specific libraries to capture the screen, so does not work on mac/linux  |
|[bionoren](https://github.com/bionoren/autofishing)   | Assumes the fishing bobber is in the middle of the screen, takes a screenshot around that area, and detects if the change in red in the screenshot exceeds a threshold | Go script  | :white_check_mark:  | :white_check_mark:  | :white_check_mark:  | I have not tested this  |   |
|[JohnAJimenez](https://github.com/JohnAJimenez/random-stuff/blob/master/game-related/minecraft/minecraft-autofishing.ahk)  |  | AutoHotKey script  | :white_check_mark:  | :white_large_square:  | :white_large_square:  | I have not tested this  |   |

### Using Optical Character Recognition (OCR) to detect if the "Fishing Bobber Splases" Caption appears on screen
Link  | How it works  | Executable or Script?  | Win  | Mac  | Linux  | Reliability  |   | 
|---|---|---|---|---|---|---|---|
| [Xechorizo](https://github.com/Xechorizo/McFishy)  |   | AutoHotKey Script  | :white_check_mark:  | :white_large_square:  | :white_large_square:  | I have not tested this | Could potentially work with Minecraft in the background?? |
| [mc-autofisher](https://pypi.org/project/mc-autofisher/) | | Python Script  | :white_check_mark:  | :white_check_mark:  | :white_check_mark:  | I have not tested this |  |

### For Future Testing
Link  | How it works  | Executable or Script?  | Win  | Mac  | Linux  | Reliability  |   | 
|---|---|---|---|---|---|---|---|
| [comjar](https://github.com/comjar/minecraft-autofish/blob/master/minecraft_autofish.py)  |  | Python Script  | :white_check_mark:  | :white_check_mark:  | :white_check_mark:  | I have not tested this  |  |
| [ruby3141](https://github.com/ruby3141/AFKFishing) |  | AutoHotKey Script | :white_check_mark:  | :white_large_square:  | :white_large_square:  | I have not tested this | Could potentially work with Minecraft in the background?? |

## How to run a python script for complete beginners
### Windows [Mac/Linux](#maclinux)
Download and install python from https://www.python.org/. Install using default settings. As of today, you will have installed python version 3.10 to your computer and added it to your computer's PATH. This means that python.exe is saved somewhere on your computer, and typing `python` into the command prompt means that you are automatically referring to the python.exe saved somewhere in the depths of your applications.

(Some programs may request a specific version of python. It does not matter for most scripts. If you need to install multiple versions of python on your computer and specify which version to use, it is outside the scope of this tutorial, check out miniconda, anaconda, and pyenv.)

Win 10 and below: Open Powershell

Win 11: Open terminal, and select Powershell

Next, we are going to copy the folder containing the files that you want to run from github onto your computer. I will use elias' repository as an example. cd means 'to go into'. **Press enter after each line.** **Replace username with your username (check file explorer), which will never have a space in it, unlike the Microsoft Account usernames**

```ps
PS C:\Users\username> cd (Drag the folder you want the github folder to reside in here)
```
For example, I want elias' repo to be in my Documents folder

```ps
PS C:\Users\username> cd C:\Users\myusername\Documents
```
OR
```ps
PS C:\Users\username> cd Documents (because Documents is a folder in C:\Users\username)
```

To copy elias' repo, press the big green 'Code' button at the top and copy the website

```ps
PS C:\Users\username\Documents> git clone https://github.com/elias123tre/minecraft-auto-fisher.git
```
A folder named minecraft-auto-fisher will be created in Documents. Enter the folder using cd. Then list all the files using ls. Press enter before typing the next line; each line is one command.

```ps
PS C:\Users\username\Documents> cd minecraft-auto-fisher
PS C:\Users\username\Documents\minecraft-auto-fisher> ls
```
We will now create a virtual python environment inside of the minecraft-auto-fisher folder. This allows us to download libraries (helper tools) that only this virtual python can access, rather than downloading libraries for the python 3.10 to use anywhere. This allows us to have multiple versions of the same library for different projects, because some libraries require specific versions of other libraries, and python allows us to have installed 1 version of a library at a time.

We then run activate to activate this virtual env

```ps
PS C:\Users\username\Documents\minecraft-auto-fisher> python3 -m venv name_of_this_venv
C:\Users\username\Documents\minecraft-auto-fisher> name_of_this_venv\Scripts\activate
```
You may come across an error here, where Windows is preventing you from running the activate.ps1 script due ot security reasons. You can temporarily disable this. **Launch powershell in administrator mode**. (You don't have to cd anywhere as it is affected powershell in general and not a specific file)

```ps
Set-ExecutionPolicy Unrestricted
```
You should see this bracketed thing in the terminal, indicating that the virtual environment has been activated

```ps
(name_of_this_venv) C:\Users\username\Documents\minecraft-auto-fisher> 
```
Now, we install all the libraries needed for this script using the helpful requirements.txt file, going through all the entires recursively (-r)

```ps
(name_of_this_venv) C:\Users\username\Documents\minecraft-auto-fisher> pip install -r requirements.txt 
```
Now, the setup is done. To run a python script, we write the following to tell the computer to use the python program that we installed earlier to understand how to run the fishing.py file. As the fishing.py file runs, it imports libraries that it needs stored inside the virtual environment.

```ps
(name_of_this_venv) C:\Users\username\Documents\minecraft-auto-fisher> python3 fishing.py
```
To make it easier for future use, run the following. An .exe file will be created.
```ps
(name_of_this_venv) C:\Users\username\Documents\minecraft-auto-fisher> pyinstaller --onefile fishing.py
```

Remember to reapply the restriction on the use of .ps1 powershell scripts if you wish. 
```ps
Set-ExecutionPolicy Restricted
```
Deactivate the virtual environment if you will be activating another virtual environment.
```ps
(name_of_this_venv) C:\Users\username\Documents\minecraft-auto-fisher> deactivate
```

When you want to use this script again, you must remember to activate the virtual environment, or else there will be no libraries available to the script. Activating the virtual environment involves running the activate.ps1 script located in minecraft-suto-fisher\name_of_venv\Scripts. As such, you must make sure that you use cd until your terminal is accessing the right folder. For example, if you have cd'ed into the Scripts folder, you simply need to run activate. You may use drag and drop to help.

```ps
C:\Users\username\Documents\minecraft-auto-fisher\name_of_this_venv\Scripts> activate
```

### Mac/Linux
Python is preinstalled on your computer. This means that the python application is saved somewhere on your computer, and typing `python` into the command prompt means that you are automatically referring to the python application saved somewhere in the depths of your computer.

(Some programs may request a specific version of python. It does not matter for most scripts. If you need to install multiple versions of python on your computer and specify which version to use, it is outside the scope of this tutorial, check out miniconda, anaconda, and pyenv.)

Open terminal

Next, we are going to copy the folder containing the files that you want to run from github onto your computer. I will use elias' repository as an example. The terminal will show some text before the % or $ sign to indicate what folder the terminal is pointing to and what files it can access. 

On older macs. Stuff before the : indicates user. ~ indicates the folder you are in, ~ is the root directory. **Type the indicated code after % or $ sign and press enter**
```bash
username@mac:~$
```
On newer macs.
```zsh
username@mac ~ %
```

cd means 'to go into'. **Press enter after each line.**

```zsh
~ % cd (Drag the folder you want the github folder to reside in here, or type the subfolder)
```
For example, I want elias' repo to be in my Documents folder

```zsh
~ % cd ~/Documents
```
OR
```zsh
~ % cd Documents (because Documents is a subfolder in ~)
```
To copy elias' repo, press the big green 'Code' button at the top and copy the website

``zsh
~/Documents % git clone https://github.com/elias123tre/minecraft-auto-fisher.git
```
A folder named minecraft-auto-fisher will be created in Documents. Enter the folder using cd. Then list all the files using ls. Press enter before typing the next line; each line is one command.

```zsh
~/Documents % cd minecraft-auto-fisher
~/Documents/minecraft-auto-fisher % ls
```
We will now create a virtual python environment inside of the minecraft-auto-fisher folder. This allows us to download libraries (helper tools) that only this virtual python can access, rather than downloading libraries for the python 3.10 to use anywhere. This allows us to have multiple versions of the same library for different projects, because some libraries require specific versions of other libraries, and python allows us to have installed 1 version of a library at a time.

We then run activate to activate this virtual env

```zsh
~/Documents/minecraft-auto-fisher % python3 -m venv name_of_this_venv
~/Documents/minecraft-auto-fisher % source name_of_this_venv/bin/activate
```
You should see this bracketed thing in the terminal, indicating that the virtual environment has been activated

```zsh
(name_of_this_venv) ~/Documents/minecraft-auto-fisher % 
```
Now, we install all the libraries needed for this script using the helpful requirements.txt file, going through all the entires recursively (-r)

```zsh
(name_of_this_venv) ~/Documents/minecraft-auto-fisher %  pip install -r requirements.txt 
```
Now, the setup is done. To run a python script, we write the following to tell the computer to use the python program that we installed earlier to understand how to run the fishing.py file. As the fishing.py file runs, it imports libraries that it needs stored inside the virtual environment.

```zsh
(name_of_this_venv) ~/Documents/minecraft-auto-fisher % python3 fishing.py
```
To make it easier for future use, run the following. An unix executable file will be created.
```zsh
(name_of_this_venv) ~/Documents/minecraft-auto-fisher % pyinstaller --onefile fishing.py
```
Deactivate the virtual environment if you will be activating another virtual environment.
```zsh
(name_of_this_venv) ~/Documents/minecraft-auto-fisher % deactivate
```

When you want to use this script again, you must remember to activate the virtual environment, or else there will be no libraries available to the script. Activating the virtual environment involves running the activate.ps1 script located in minecraft-suto-fisher\name_of_venv\Scripts. As such, you must make sure that you use cd until your terminal is accessing the right folder. For example, if you have cd'ed into the Scripts folder, you simply need to run activate. You may use drag and drop to help.

```ps
~/Documents/minecraft-auto-fisher/name_of_this_venv/bin % source activate
```


