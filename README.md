# Locust Installation & Testing Guide (Linux / macOS / Windows)

------------------------------------------------------------
# 1. INSTALL LOCUST
------------------------------------------------------------

## LINUX

Install Python:
---
sudo apt update
sudo apt install python3 python3-pip
---
Install Locust:
---
pip3 install locust
---
Verify:
---
locust -V
---
If “locust command not found”:
---
nano ~/.bashrc
Add at end of file:
---
export PATH="$HOME/.local/bin:$PATH"
---
3. Save + exit
4. Run
--- source ~/.bashrc
locust -V ---

## MACOS

Install Homebrew (if not installed):
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

Install Python:
brew install python

Install Locust:
pip install locust

Verify:
locust -V

If “locust command not found”:
1. python3 -m site --user-base
   Example: /Users/yourname/Library/Python/3.9
2. Scripts dir:
   /Users/yourname/Library/Python/3.9/bin
3. Add to PATH:
   nano ~/.zshrc
4. Add:
   export PATH="$HOME/Library/Python/3.9/bin:$PATH"
5. Apply:
   source ~/.zshrc
6. Test:
   locust -V

## WINDOWS

Install Python:
Download from https://www.python.org/downloads/windows/
Check “Add Python to PATH”

Install Locust:
pip install locust

Verify:
locust --version

If not working:
1. python -m site --user-site
2. Find Scripts folder:
   C:\Users\YourName\AppData\Roaming\Python\Python311\Scripts
3. Add to PATH:
   Environment Variables → PATH → Add new
4. Restart terminal
5. locust --version



------------------------------------------------------------
# 2. ADD THE API FOR SEQUENTIAL TESTING
------------------------------------------------------------

Download sample project:
https://github.com/visionsDe/devops

Go to folder:
devops-master/sequences_test

Check file example (sequence_test.py):

------------------------------------------------------------
# 3. RUN THE TEST (All Operating Systems)
------------------------------------------------------------

Run Locust:
locust -f sequence_test.py --host https://api-ng.barsys.com

Open Locust UI:
http://localhost:8089

Start the test:
• Enter number of users
• Enter spawn rate
• Click “Start Swarming”

------------------------------------------------------------
# SUMMARY
------------------------------------------------------------

Linux: Install via apt + pip3
macOS: Install via Homebrew + pip
Windows: Install via Python installer + pip
Run test (all OS):
locust -f sequence_test.py --host <API>
Open: http://localhost:8089
