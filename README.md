Ransomware Challenge - Lucas Pontes

Overview

This document outlines the steps required to complete the ransomware challenge, including setting up the environment, handling dependencies, running the encryption and decryption scripts, and troubleshooting installation issues.

Prerequisites

Kali Linux

Python 3.12

Pip (Python package manager)

pyaes library

Steps

1. Gain Root Access

sudo su

2. Create and Navigate to Project Directory

mkdir projecto-ransomware
cd projecto-ransomware

3. Create and Modify a Test File

touch teste.txt
nano teste.txt

4. Verify the Presence of Scripts

Ensure that encrypter.py and decrypter.py are in the directory:

ls

5. Run encrypter.py

Attempt to execute the encryption script:

python encrypter.py

If you see an error:

ModuleNotFoundError: No module named 'pyaes'

then pyaes needs to be installed.

6. Install pyaes

Since the environment is externally managed, follow these steps:

6.1 Check Python and Pip Versions

python3 --version
pip3 --version

6.2 Install pyaes Using Pip with --break-system-packages

pip install pyaes --break-system-packages

7. Run encrypter.py Again

python encrypter.py

This will create an encrypted file with .ransomwaretroll extension:

ls

Expected output:

decrypter.py  encrypter.py  teste.txt.ransomwaretroll

8. Verify Encrypted File

Open the encrypted file:

nano teste.txt.ransomwaretroll

9. Run decrypter.py

python decrypter.py

10. Verify Decryption

Ensure that the original file is restored:

ls

Notes

Running Pip as the root user may cause system issues. Using a virtual environment is recommended for better package management.

If you face permission errors, ensure you are running commands with appropriate privileges.

The encryption script renames files, so be cautious when testing in directories with important data.

Reference Links

Kali Linux Python Packages

PEP 668 - Externally Managed Environments
