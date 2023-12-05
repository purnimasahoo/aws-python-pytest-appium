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

## Starting the server
-----
A server to be run on the local host. Other servers include Saucelabs and Browserstack, but for our purposes, we will be running this server locally. This server needs to be up and running when either running appium specific driver code or using the inspector. Currently, this is only being supported on your local terminal.

### Launch terminal, run the following line of code, and keep it running.
`appiumps -p 4723`

# The Inspector
-----
The Appium desktop application, which we installed earlier, allows us to use the Inspector. Once running, this will give you a view of the devkit and the object tree, which you can run through. This allows you to find elements.

## Set Desired Information
When starting the session, we have to use the same desired information as we used earlier. In addition to this, we will need to set the port to use port 4723 or whatever we run the local Appium server on.

Run the Appium and Appium Inspector to create the local session.

##### Desired Capabilities

In order to start a remote session, we have to provide information.

appium_conf_content = """\
{
    "options": {
        "capabilities": [{
            "appium:deviceName": "Pixel_3_API_28",
            "platformName": "Android",
            "appium:platformVersion": "11",
            "appium:app": "C:\\Users\\purni\\OneDrive\\Documents\\Downloads\\SwipeListView Demo_v1.13_apkpure.com.apk",
            "avd": "Pixel_3_API_28"
        }]
    }
    
}
"""
with open("appium.conf", "w") as appium_conf:
    appium_conf.writelines(appium_conf_content)

print("appium.py created")

###### Starting session

Once the desired capabilities are defined, we have to start a session with this information.

url = 'http://127.0.0.1:4723/wd/hub'
driver = webdriver.Remote(url, desired_caps, keep_alive=True)

######  Running tests on AWS Device Farm

Step 1: Navigate into your workspace project directory and activate the virtualenv.
$ source bin/activate
Step 2: Package your tests.
$ ./package_tests.sh
Step 3: Upload to AWS Device Farm.
Follow these instructions and upload test_bundle.zip on Step 9.


