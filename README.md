# ICOM.py

The iCOM application provides minimal control of an iCOM IC-7610 radio. This program is written in Python and allows control 
of a few key radio functions that are needed for my remote radio control setup. This control app does not provide frequency 
or band selection, these functions are performed using N1MM+. The spectrum display and tuning built into N1MM+ provide very 
nice visualization and frequency selection. This application is needed to provide a few critical capabilities:

  -	On/Off control of the transceiver
  -	Mode selection
  -	Filter selection
  -	RF gain control
  -	Power output control
  -	Break-in control
  -	CAT passthrough


The CAT passthrough allows the use of Virtual Serial Port Driver to create a connected pair of com ports. The iCOM app then 
pass all the traffic from the CAT passthrough port to the CAT port on the transceiver. This allows N1MM+ and this app to use 
the one CAT transceiver port. All the N1MM+ traffic to passed to and from the transceivers CAT port.

The baud rate is fixed at 115,200. This speed is required for the spectrum display mode of N1MM+.  The com ports for the CAT 
interface and the CAT passthrough can be selected by pulling the bottom of the interface dialog down to expose selection 
boxes for the two ports. After you select the desired port then press Connect to make the connections. This app will save 
the settings in a configuration file and automatically load them and connect on startup.
 
The iCOM app is written in Python 3.7 using the pycharm IDE and uses Tkinter for the GUI and the pyserial library for 
com port control. The application contains a class that supports radio functions, an object is created for each control. 
Additional controls can be easily added by creating additional objects for the desired functions.

I am primarily a CW operator and use this app both when operating remotely and when in my shack. My logging software 
(N1MM+, or SKCClogger, or AC log) all connect to this app’s passthrough port. I only use N1MM+ when operating remotely because 
it provides the spectrum display and tuning interface.

