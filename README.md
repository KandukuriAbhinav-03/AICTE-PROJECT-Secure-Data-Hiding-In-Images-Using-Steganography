# Secure Data Hiding In Images Using Steganography  
     

 
A simple Python-based steganography project that hides a secret message and passcode in an image using Least-Significant-Bit (LSB) encoding, and later retrieves the message securely.

# Overview
 
This project uses robust LSB steganography to embed a secret message along with a passcode into an image.Steganography is the technique of concealing data or information within a carrier medium, such as an image, audio, or video, so that the hidden message is not detectable to the human eye or ear.  

# Key Concepts:
Steganography vs Cryptography:

**Cryptography** encrypts the data, making it unreadable to unauthorized parties but does not hide the fact that data is being sent.

**Steganography**, on the other hand, hides the existence of the message itself, making it ideal for scenarios where confidentiality needs to be maintained without drawing attention.

**Image as a Carrier Medium:** Images are commonly used as the carrier medium for steganography. By modifying the pixel values in a way that is not visible to the human eye, we can embed data without altering the image’s appearance significantly.

# Security in Steganography:

 **Confidentiality:** The hidden data should be encrypted before embedding in the image to avoid unauthorized access in case the image is intercepted.

**Imperceptibility:** The hidden data should not be noticeable in the image. To achieve this, the data is embedded in the least significant bits (LSB) of the image pixels.

**Capacity:** The amount of data that can be hidden within the image is important. This capacity should be balanced with imperceptibility and security.



# Features
* **Encryption:** Embeds a secret message and passcode into mypic.jpg and saves the result as encrypted.png.

* **Decryption:** Retrieves the hidden message from encrypted.png when the correct passcode is provided.

* **User-Friendly GUI:** Easy-to-use interfaces for both encryption and decryption processes.

* **Robust Data Storage:** Uses a header to store the lengths of the passcode and message for accurate extraction.

 

 

# Requirements

* Python 3.x

* NumPy

* OpenCV

* VS code


# Installation

* Clone the repository.
  
* Install the required libraries:pip install opencv-python numpy
 
Place an image mypic.jpg in project directory


# Advantages of Using Steganography in Images:
#### 1. Security 
#### 2. Stealth 
#### 3. Versatility 



# PROJECT  EXECUTION 


**Step 1:** Install Python
1. Go to the official Python download page: https://www.python.org/downloads/
2. Click on the "Download Now" button for the latest version of Python.
3. Follow the installation instructions to install Python on your computer.

**Step 2:** Install VS Code
1. Go to the official VS Code download page: https://code.visualstudio.com/download
2. Click on the "Download" button for the latest version of VS Code.
3. Follow the installation instructions to install VS Code on your computer.

**Step 3:** Install OpenCV
1. Open VS Code.
2. Open the terminal in VS Code by pressing `Ctrl + `` (backtick) or by navigating to "View" > "Terminal".
3. Type the following command to install OpenCV using pip: pip install opencv-python
4. Press Enter to run the command.

**Step 4:** Create a New File
1. In VS Code, click on "File" > "New File" or press Ctrl + N.
2. Save the file with a .py extension (e.g., steganography.py).

**Step 5:** Copy and Paste the Code
1. Copy the following Steganography code:

import cv2

import os

import string


**#Read the image**

img = cv2.imread("mypic.jpg")


**#Get the secret message and password from the user**

msg = input("Enter secret message: ")

password = input("Enter a passcode: ")


**#Create dictionaries for character-to-ASCII and ASCII-to-character mappings**

d = {}

c = {}

for i in range(255):

d[chr(i)] = i

c[i] = chr(i)


**#Initialize variables for embedding the message**

m = 0

n = 0

z = 0


**#Embed the message into the image**

for i in range(len(msg)):

img[n, m, z] = d[msg[i]]

n = n + 1

m = m + 1

z = (z + 1) % 3


**#Save the encrypted image**

cv2.imwrite("encryptedImage.jpg", img)


**#Open the encrypted image**

os.system("start encryptedImage.jpg")


**#Get the passcode for decryption**

pas = input("Enter passcode for Decryption: ")


**#Decrypt the message if the passcode is correct**

if password == pas:

message = ""

n = 0

m = 0

z = 0

for i in range(len(msg)):

message = message + c[img[n, m, z]]

n = n + 1

m = m + 1

z = (z + 1) % 3

print("Decryption message: ", message)

else:

print("YOU ARE NOT authorized")

2. Paste the code into the steganography.py file.

**Step 6:** Run the Code
1. Make sure you have an image file named mypic.jpg in the same directory as the steganography.py file.
2. Open the terminal in VS Code by pressing `Ctrl + `` (backtick) or by navigating to "View" > "Terminal".
3. Type the following command to run the code: python steganography.py
4. Press Enter to run the command.

That's it! The code should now run and prompt you to enter a secret message and passcode. then it generates the Encrypted image known as Steganography.
