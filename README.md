Homework 7 – Docker QR Code Generator App
This was actually fun to build! For this assignment, I created a Python program that generates a QR code and runs completely inside a Docker container. It takes any URL, turns it into a QR code image, and logs the results. I used my own GitHub profile link for the demo. Everything’s done with environment variables, and the image gets saved to a shared volume. 

What the App Does
Takes a URL from command-line or default env

Creates a .png QR code file with it

Uses custom fill and background color from .env

Saves the image inside the /qr_codes folder

Logs the status using logging (no print statements)

All this runs from inside a Docker container

I built the Docker image using:
docker build -t qr-code-generator .

Then I ran the container like this:
docker run --rm qr-code-generator

My QR Code Image: 
![My GitHub QR Code](qr_codes/QRCode_20250714225843.png)

Log Output (Terminal)
This was the log message printed to the terminal when I ran the app: 
2025-07-14 22:58:16,125 - INFO - QR code saved to /app/qr_codes/QRCode_20250714225816.png

My Project structure:
improved-qr-docker-2024/
│
├── Dockerfile
├── docker-compose.yml
├── .env
├── .gitignore
├── .dockerignore
├── requirements.txt
├── main.py
├── logs/
│   └── (log output if redirected here)
├── qr_codes/
│   └── QRCode_20250714225816.png
