# Overture PCB

Overture is a custom ESP32-C6 control board designed to drive a NEMA 17 stepper motor while handling NFC reading, a small display, and physical user inputs. Everything is powered through a single USB-C Power Delivery connection.

## Hardware Specs

* **Microcontroller:** ESP32-C6-WROOM-1
* **Motor Driver:** TMC2208/TMC2209 setup driving a JST-XH port, sized for a NEMA 17 stepper.
* **Peripheral Headers:** Broken out pins for an ST7789 TFT screen, a PN532 NFC module, 3 push buttons, and a rotary encoder.
* **Power Delivery:** Uses an STUSB4500 PD controller to negotiate 20V directly from a USB-C wall adapter.
* **Power Regulation:** A TPS54308DDCT buck converter steps the 20V down to 3.3V (up to 2A max) to power the ESP32 and logic peripherals.
* **Programming:** Features a secondary USB-C port dedicated strictly to flashing and serial output.

## Power and Flashing

The board uses a dual USB-C port design to separate power and data. 

To power the motor and board, plug a compatible USB-C PD charger into the main power port. The STUSB4500 handles the 20V negotiation automatically. 

To flash the ESP32, use the secondary USB-C port. Note that the primary power port does not route data lines to the ESP32 and will not show up as a COM port on your machine.

## Exports

The exports folder contains all the file for production:
* hw1-bom.csv - is the Bill of Materials (formatted for JLCPCB)
* hw1-top-pos.csv - is the Components Position File for PCB-A (formatted for JLCPCB)
* Gerber_Archived.zip - has all the Gerber and Drill files needed for production
