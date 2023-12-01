#python-pytest-appium
Pytest Appium Tests

# Appium
Appium is a framework that allows for both running tests that manipulate the unit and running tests that verify what users are seeing on the screen. This is done by setting up a server for the unit to communicate with, either through the command line or through a UI. It also supports automating smart TV and Windows/macOS-based desktop applications.


# Tutorials

### Installation
--------
Requirements for the setup:

Appium and Appium inspector

Latest edition of Python and JAVA

Android Studio

Emulators

Plugins installation

IDE (VS Code or PyCharm)

Sample test run

Make sure to activate the virtual environment in the terminal.

To install the Appium server, run the following command on your terminal

!pip3 install appium-python-server

Install appium-ps

!pip3 install appium-python-client-ps

## Starting the server
-----
A server to be run on the local host. Other servers include Saucelabs and Browserstack, but for our purposes, we will be running this server locally. This server needs to be up and running when either running appium specific driver code or using the inspector. Currently, this is only being supported on your local terminal.

### Launch terminal, run the following line of code, and keep it running.
`appiumps -p 4723`
