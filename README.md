# Image-stegnography
Using LSB algorithm
# prerequisites:
1. Python Environment:
Ensure you have Python installed. The script should work with Python 3.x.
2. Pillow Library:
The script uses the PIL module, which is part of the Pillow library (a modern fork of the original Python Imaging Library).
You can install it via pip:

    pip install Pillow

3. NumPy Library:
The script imports the array function from the numpy library, although it's not directly used in the provided code. If you need to use NumPy, install it via pip:

    pip install numpy

    If you don't intend to use NumPy, you can remove the line from numpy import array.

4. Input Image:
You need an image file (preferably in PNG format) to encode data into. The image should be located in the same directory as the script or you must provide the correct path to the image when prompted.

6. Python IDE/Editor:
Use any Python-compatible IDE or text editor (like PyCharm, VSCode, or even IDLE) to run the script.

8. Basic Understanding of Command Line:
The script runs in a command-line interface (CLI) and prompts the user for input. Basic familiarity with running Python scripts and entering data via the command line is helpful.

## Encoding_Decoding.py:
This Python script implements a simple text encryption and decryption tool using substitution ciphers. The script defines two byte translation tables: encrypt_table for encrypting messages and decrypt_table for decrypting them. The encryption replaces each letter in the input message with a corresponding letter from the encrypted string, while decryption reverses this process using the decrypted string. The script repeatedly prompts the user to either encrypt, decrypt, or exit the program. Depending on the user's choice, the script either encrypts the entered message and displays the result or decrypts a given message. If the user inputs anything other than '1', '2', or '0', the program notifies them of the invalid input and prompts them to try again. The loop continues until the user chooses to exit by entering '0'.
## Encoding_Decoding_with_key.py 
This Python script allows users to encrypt and decrypt messages using a pseudo-random substitution cipher. It generates a list of printable ASCII characters and shuffles them based on a user-provided seed. For encryption, each character in the input message is replaced with its corresponding character from the shuffled list. During decryption, the same seed is used to recreate the shuffled list, allowing the original message to be restored by mapping each encrypted character back to its original counterpart. The process ensures that using the same seed for both encryption and decryption yields consistent and reversible results. The program continues to prompt the user until they choose to exit.
## Imagesteg.py
This Python script implements a basic form of steganography, allowing users to hide data within an image or extract hidden data from an image. It modifies the least significant bits (LSBs) of the pixel values to encode the binary representation of the input data.

# How It Works:
Data Encoding:

genData(data): Converts the input data into a list of binary strings, each representing a character in the data.

modPix(pix, data): Iterates through the pixels of the image and modifies the LSBs to match the binary data. The function ensures that each bit of the data is encoded into the image pixels. If the data bit is 0, it ensures the LSB is even, and if it's 1, the LSB is made odd.

encode_enc(newimg, data): Embeds the modified pixel values back into the image, scanning row by row.

encode(): The main function that prompts the user for an image file and data, then encodes the data into a copy of the image and saves the new image.

Data Decoding:

decode(): Iterates through the image pixels, extracting the binary data from the LSBs. It reconstructs the original message by converting these binary values back into characters. The process continues until it detects a stopping condition embedded in the last pixel's LSB.

Main Program:

main(): Presents the user with a menu to either encode data into an image or decode data from an image. The appropriate function is then called based on the user's input.
This steganography method is straightforward and hides data within an image in a way that is not easily noticeable, although it is limited by the amount of data that can be stored based on the image size.
