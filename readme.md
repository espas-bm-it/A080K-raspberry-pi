# Start
Hello World

This is the new Raspberry PI scanning system. 

# Requirements 
- Raspbian Buster (2019)
- NxpRdLib
- EXPLORE-NFC Element14 
- MySQL Database
- Active Internet Connection (only to send Data)

# Installation
1. clone repository into `nfc` folder
2. `sudo bash ./install.sh` installs missing Python libraries, installs chronos_scanner.service and creates the .env file.

## Database
Import the structure of `database.sql` into your preferred database.

# After installation
## .env
modify `.env` to your needs and file locations.

## CronTab
Following scripts require Sudo CronTab:
- chronos_sender.py `* 5-19 * * 1-5 /usr/bin/python3 /home/pi/nfc/chronos_sender.py >> /var/log/chronos_sender.log 2>&1 | logger -t chronos`
- chronos_deleter.py `0 18 * * 1-5 /usr/bin/python3 /home/pi/nfc/chronos_deleter.py >> /var/log/chronos_deleter.log 2>&1 | logger -t chronos`

