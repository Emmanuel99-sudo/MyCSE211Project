# CSE211s Final Project - Embedded System with RTC and Voltage Display

This project was developed for the **CSE211s - Introduction to Embedded Systems** course at **Ain Shams University**, Spring 2025.  
It demonstrates an embedded application running on an STM32 NUCLEO-F401RE board using **Mbed OS**, interfaced with an Arduino multifunction shield.

---

## 📌 Features

- **Real-Time Clock (RTC)**  
  - Displays elapsed time in `MMSS` format on a 4-digit 7-segment display.  
  - Starts from 00:00 at power-up and increments every second.  
  - Pressing **S1** resets the timer to zero.

- **Analog Voltage Display**  
  - Reads voltage from a potentiometer using the on-board ADC.  
  - Pressing **S3** shows the voltage on the display in `X.XX` format.  
  - Tracks and stores the minimum and maximum observed voltages.

---

## 🛠️ Hardware Requirements

- STM32 NUCLEO-F401RE Board  
- Arduino Multifunction Shield  
- USB cable  
- Optional: oscilloscope or multimeter for voltage measurement

---

## 📂 Project Structure

- `main.cpp` – Core logic: timekeeping, voltage reading, 7-segment display control  
- `startup_stm32f401xe.s` – (Reference only) Assembly startup file from STM32, not used in Mbed build

---

## 🧠 How It Works

- Uses **Mbed Ticker** for 1-second RTC updates  
- 7-segment display driven via shift registers (latch, clock, data pins)  
- Potentiometer value scaled from 0–3.3V  
- Pushbuttons are active-low with internal pull-ups

---

## 🔌 Circuit Overview

- **D4**: Latch  
- **D7**: Clock  
- **D8**: Data  
- **A0**: Potentiometer input  
- **A1 (S1)**: Reset timer  
- **A3 (S3)**: Voltage display toggle

---

## 🚀 Getting Started with Mbed

1. Import this project into the [Mbed Compiler](https://os.mbed.com/compiler).
2. Select target board: **NUCLEO-F401RE**.
3. Compile and flash the `.bin` file to your board via USB drag-and-drop.
4. Open a terminal (e.g., Tera Term) if needed for debug prints (optional).

---

## 📎 Notes

### ✅ About the Startup File

This repository includes a reference startup file:  
`startup_stm32f401xe.s`  

🛑 **This file is NOT used in the Mbed OS build**. Mbed manages all low-level initialization automatically.  
The file is provided **for educational purposes only** to show what startup code looks like in bare-metal STM32 development.

---

## 📽️ Demonstration

You can watch a video demonstration of the project in action here:  
🎥 [Watch the Demo Video](https://your-video-link-here.com)

This video shows the timer display, voltage reading from the potentiometer, and the system’s response to the S1 and S3 buttons.

---

## 📚 License

This project is for academic and educational use.  
Please credit the author if reused in coursework or documentation.

---

## 👤 Author

**Emmanuel**  
Ain Shams University – Mechatronics Engineering  
Spring 2025  
