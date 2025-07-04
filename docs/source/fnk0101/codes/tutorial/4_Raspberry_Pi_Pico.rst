##############################################################################
Chapter 4 Raspberry Pi Pico
##############################################################################

The Freenove Breakout Board is compatible with a variety of development boards. However, please note that the distance width between the header pins on both sides of the development board should be between 600mil and 1000mil. If the development board does not meet the installation requirements, do not force the installation, as this may cause damage to the Freenove Breakout Board or your development board.

+-------------------+---------------------+---------------------+
| Raspberry Pi Pico | Raspberry Pi Pico W | Raspberry Pi Pico 2 |
|                   |                     |                     |
| |Chapter04_00|    | |Chapter04_01|      | |Chapter04_02|      |
+-------------------+---------------------+---------------------+

.. |Chapter04_00| image:: ../_static/imgs/4_Raspberry_Pi_Pico/Chapter04_00.png
.. |Chapter04_01| image:: ../_static/imgs/4_Raspberry_Pi_Pico/Chapter04_01.png
.. |Chapter04_02| image:: ../_static/imgs/4_Raspberry_Pi_Pico/Chapter04_02.png

Resources for Raspberry Pi Pico
****************************************

:red:`This section will use the Raspberry Pi Pico W as an example; the usage method is the same for other development boards.`

Regarding the programming process of the Raspberry Pi Pico, we will not delve into it here. If you are interested in learning about the Raspberry Pi Pico, Raspberry Pi Pico W, or Raspberry Pi Pico 2, the following resource links can assist you in your learning journey:

https://freenove.com/fnk0058/

Or you can visit our github to download: 

https://github.com/Freenove/Freenove_Ultimate_Starter_Kit_for_Raspberry_Pi_Pico

Regarding the programming instructions for the Freenove Raspberry Pi Pico, we won't delve into them here. 

If you're interested, please refer to the following resources:

For For C Programming Tutorial, you can check 

**Freenove_Ultimate_Starter_Kit_for_Raspberry_Pi_Pico\\C\\C_Tutorial.pdf**

For Python Programming Tutorial, you can refer to 

**Freenove_Ultimate_Starter_Kit_for_Raspberry_Pi_Pico\\Python\\Python_Tutorial.pdf**

For Processing Programming Tutorial, you can refer to

**Freenove_Ultimate_Starter_Kit_for_Raspberry_Pi_Pico\\Processing\\Processing_Tutorial.pdf**

Installing Raspberry Pi Pico
*************************************

Step1: Select the Power Input and GND Pins for the Microcontroller
=========================================================================

Regardless of the type of development board, it typically features external power input pins, which are commonly situated near the data line connection area on the board. It is important to note that when both VIN/VCC/5V and 3.3V power options are present on the development board, it is advisable to prioritize the use of VIN/VCC/5V for powering the board. 

Taking the Raspberry Pi Pico W as an example, this board is marked with both 5V and 3.3V silk screen labels. This indicates the presence of a voltage regulator circuit on the board that steps down the 5V input to a 3.3V output. Generally, the 3.3V is intended for use as an output power supply, while the 5V serves as the input power supply. Consequently, when powering the board, the 5V pin should be used as the positive terminal of the input power supply, and the GND pin should be used as the negative terminal. This is illustrated in the figure below.

.. image:: ../_static/imgs/4_Raspberry_Pi_Pico/Chapter04_03.png
    :align: center

Step2: Power the Development Board
==========================================

In the first step, the Freenove ESP32 WROVER Board utilizes 5V for the positive power supply terminal and GND for the negative power supply terminal. Consequently, it is necessary to set VC1 to 5V.

.. image:: ../_static/imgs/4_Raspberry_Pi_Pico/Chapter04_04.png
    :align: center

As illustrated below:

Conect the yellow header aligned with the 5V pin of the microcontroller to the red header. 

Connect the yellow header aligned with the GND pin of the microcontroller to the black header.

.. image:: ../_static/imgs/4_Raspberry_Pi_Pico/Chapter04_05.png
    :align: center

:red:`Please note: The red header pin represents the positive power terminal, and the black header pin represents the negative power terminal. During use, under no circumstances should the red and black header pins be short-circuited, as doing so will damage the Freenove Breakout Board.`

Step3: Power Supply Precautions
=============================================

Freenove Breakout Board DC005 Jack
----------------------------------------------

The interface for external power supply to Freenove Breakout board is a DC005 interface, whose size is 5.5x2.1mm. Please pay attention to its positive and negative terminals, as shown in the figures below.

.. image:: ../_static/imgs/4_Raspberry_Pi_Pico/Chapter04_06.png
    :align: center

:red:`The Freenove Breakout Board features a reverse power protection circuit. This design ensures that the board is safeguarded from damage in the event of an improperly connected external power supply. If, after connecting the external power, the Freenove Breakout Board fails to power the development board, it is likely due to a polarity mismatch in the DC interface being used. The positive and negative terminals may be reversed. It is crucial to verify the specifications of the DC interface to confirm that it is correctly aligned with the board's requirements.`

If the external power supply is connected correctly, the signal indicator on the breakout board will light up. 

.. image:: ../_static/imgs/4_Raspberry_Pi_Pico/Chapter04_07.png
    :align: center

1.	During experiments, if the development board is connected to USB for power supply or code downloading, and the Freenove Breakout Board is powered by an external power source, we recommend that you disconnect the positive connection between the development board and the Freenove Breakout Board. This can better protect your development board. As shown in the figure below.

.. image:: ../_static/imgs/4_Raspberry_Pi_Pico/Chapter04_08.png
    :align: center

2.	If you are powering the development board using only a data cable, be aware that the combined power consumption of the Raspberry Pi Pico W and any external circuits should not be excessive. Generally, a computer's USB port can only supply 5V at 0.5A to 1A. If your total power consumption exceeds the USB port's capacity, it may cause the development board to operate abnormally or even damage your computer's USB port.

3.	If you are using an external power source to power the development board, ensure that the positive and negative terminals of the development board are correctly connected to the Freenove Breakout Board.

4.	Each pin on the Freenove Breakout Board is equipped with an indicator LED, which is used to indicate the voltage level state of the development board's pins. If you control a pin to output high or low voltage levels, the indicator LED will change accordingly. Similarly, if some pins on your development board are not in use, they will be in a floating state, which could be either high or low voltage. The corresponding indicator LED on the board will light up or turn off accordingly. If you do not want the indicator LED to light up or turn off, you can control it to output a high or low voltage level through programming.

:red:`If you need any support, please feel free to contact us via:` support@freenove.com