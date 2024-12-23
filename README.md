# RVC-Copy
Copy of the [RVC-Project](https://github.com/RVC-Project) modified for compatibility with Windows 11

## Usage

After following the instructions of original-README.md for RVC WebUI, Open your terminal or PowerShell in the project directory, then run:

```powershell
& "C:\Users\'UserName'\AppData\Local\pypoetry\Cache\virtualenvs\rvc-beta-mNhLC9aH-py3.10\Scripts\Activate.ps1"
poetry install
python infer-web.py

## Changes Made

# infer-web.py
Line 57 device = torch.device("cuda" if torch.cuda.is_available() else "CPU")

# Activate.ps1
$env:Path += ";$env:APPDATA\Python\Scripts"
$env:CUDA_HOME = "C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.7"
$env:PATH += ";C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.7\bin"

ensures GPU is always used if available

# C:\Users\'UserName'\AppData\Local\pypoetry\Cache\virtualenvs\rvc-beta-mNhLC9aH-py3.10\Scripts\Activate.ps1
Runs Activate.ps1 script directly, which":

Stores script path and base directory
Defines deactivation function to restore original environment
Sets up virtual environment variables
Creates environment prompt ('rvc-beta-py3.10')
Backs up original PATH
CUDA Management
Adds virtual environment Scripts folder to PATH
Adds Python user scripts directory
Modifies command prompt to show virtual env name


