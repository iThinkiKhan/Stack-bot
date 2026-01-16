# Stack-bot
 
I decided to upgrade the brain and display of the bot, primarily. I also wanted to use common parts and 3d prints I could order from the local library. 

**Hardware**
Brain - Lonely Binary ESP32-S3 N16R8. 16MB flash, 8MB octal PSRAM. Powerful little chip by esp32 standards. We need it to drive all the functions.

Display - 2.8" IL19341 Touch Screen. SPI interface (important to keep cables down) 320x240 resolution. This should enable us to display all kinds of data effectively, or act as a button, etc. This also gives us an SD slot.

Movement - 2x SG90 Servos. Can be upgraded to x6 for walking version.

**_Warning_** -Some of the pins on this board are used for the extra RAM. Do not use those pins. 

**3D Printing & Assembly**

Head - Case for 2.8" IL19341, bottom power by DorffMeister
  Body_-_Bottom_Power.stl
  Lid_-_Bottom_Power.stl

  Body - Standard StackChan repo from meganataaan 
    feet_SG90.stl
    bracket_SG90_b.stl

These do not fit together. Rough up the horns and superglue em.

**Software**
Development Environment
IDE: VS Code + PlatformIO
Framework: Arduino

The "Dual Brain" System
The firmware is designed to be model-agnostic, allowing hot-swapping between AI providers via a preprocessor flag (#define USE_GEMINI).

_Primary Brain (Google Gemini)_:

Model: gemini-1.5-flash
Cost: Free Tier
Role: Daily driver

_Backup Brain (OpenAI)_:

Model: ChatGPT
Cost: Paid API
Role: Fallback or complex reasoning tasks.

Secrets Management
API keys and WiFi credentials are stored in a non-tracked src/Secrets.h file to prevent accidental leaks.


