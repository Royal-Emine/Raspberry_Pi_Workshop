# Raspberry Pi Workshop

## Initial Kickstart Learning Resources

### Setup for First-time

- **Setup Headless Mode** - [Youtube](https://youtu.be/AlM8O01QY9c)

During this process, install the following software:
  - [VNC Viewer](https://www.realvnc.com/en/connect/download/viewer/)
  - [PuTTY](https://www.putty.org/) (For Windows users, Mac/Linux users need to enable SSH)

  > PuTTY is an SSH and telnet client. Mac/Linux users, enable SSH using [Reference](https://osxdaily.com/2022/07/08/turn-on-ssh-mac/) and [Reference](https://www.cyberciti.biz/faq/ubuntu-linux-install-openssh-server/). Connect to Raspberry Pi through SSH using the command: `ssh pi@192.168.x.x` (Default Username: pi, Password: raspberry)

To enable VNC Server on Raspberry Pi:

1. Open PuTTy and connect to Raspberry Pi over SSH.
2. Enter the command: `sudo raspi-config`
3. Select Interfacing Options and press Enter.
4. Select VNC and press Enter.
5. Enable VNC Server by selecting Yes.
6. Select Ok and then Finish to return to the terminal.

For Windows users:

1. Open PuTTy and connect to Raspberry Pi over SSH.
2. Enter the command: `sudo apt install xrdp`
3. On your main Windows machine, type `Remote Desktop Connection` in the search bar.
4. Enter the IP address of the Raspberry Pi in the Computer field.
5. Click Connect.
6. Confirm by clicking YES (for first-time connection).
7. At the login screen, enter Raspberry Pi's Username/Password and click OK.

> Supportable for all OS: Windows, MacOS, Linux. Internet connectivity is crucial for the initial setup.

### Enabling Ports and Protocols

To enhance connectivity with other Raspberry Pi Hats or electronic modules, it's crucial to enable specific ports and protocols. This step ensures seamless communication between your Raspberry Pi and external devices.

1. **Enabling Ports and Protocols:**

To facilitate better communication with other Raspberry Pi Hats or electronic modules, you need to ensure that specific ports and protocols are enabled. Follow these steps to enable the necessary configurations:

   - Identify the Ports: Determine which ports are required for your specific Raspberry Pi project or module. This information is often available in the documentation provided with the module.

   - Access Router Settings: Log in to your router's settings page. You can usually access this by entering your router's IP address in a web browser. Refer to your router's manual for guidance on accessing settings.

   - Port Forwarding: Locate the port forwarding section in your router settings. Add a new port forwarding rule for each required port. Specify the Raspberry Pi's IP address as the destination for these ports.

   - Firewall Configurations: Check if there are any firewalls (on your Raspberry Pi or router) that might block incoming or outgoing connections on the specified ports. Adjust firewall settings accordingly.

   - Test Connectivity: Once the port forwarding and firewall settings are configured, test the connectivity between your Raspberry Pi and the external device or module. This can be done using specific commands or tests relevant to your project.

   > Note: Always ensure that you are aware of the security implications of opening specific ports, and only enable those that are necessary for your project. Regularly update and review security measures to safeguard your Raspberry Pi.

These detailed instructions will vary based on the specific ports and protocols required for your project. Refer to the documentation of your Raspberry Pi Hats or electronic modules for precise information on port configurations.

### *Enabling VNC* (Virtual Network Computing) 
on your Raspberry Pi over SSH using PuTTY involves a few steps. Follow these instructions:

1. **Connect to Raspberry Pi:**
   - Open PuTTY and enter the IP address of your Raspberry Pi.
   - Click "Open" to initiate the SSH connection.
   - Log in with your Raspberry Pi username and password.

2. **Open the Raspberry Pi Configuration Tool:**
   - In the SSH terminal, type the following command and press Enter:
     ```bash
     sudo raspi-config
     ```

3. **Navigate to Interfacing Options:**
   - In the Raspberry Pi Configuration Tool, use the arrow keys to navigate to "Interfacing Options."
   - Press Enter to select it.

4. **Enable VNC:**
   - In the "Interfacing Options" menu, navigate to "VNC" and press Enter.
   - You will be prompted to enable VNC Server. Select "Yes" and press Enter.

5. **Finish Configuration:**
   - After enabling VNC, use the arrow keys to select "Finish."
   - Press Enter to exit the configuration tool.

6. **Restart Your Raspberry Pi:**
   - To apply the changes, restart your Raspberry Pi:
     ```bash
     sudo reboot
     ```

7. **Connect Using VNC Viewer:**
   - Once your Raspberry Pi has restarted, open VNC Viewer on your computer.
   - Enter the IP address of your Raspberry Pi in VNC Viewer.
   - Click "Connect" to establish the VNC connection.

8. **Authenticate:**
   - Enter your Raspberry Pi username and password when prompted.
   - You should now have access to the Raspberry Pi's desktop environment through VNC Viewer.

**Note:**
- Ensure that your Raspberry Pi and the computer running VNC Viewer are on the same network.
- VNC Server is now enabled, allowing you to remotely access the graphical interface of your Raspberry Pi.

These steps should guide you through the process of enabling and using VNC Server on your Raspberry Pi over SSH using PuTTY.

### Setup Environment in Python (its a good practice)

Sure thing! To create a virtual environment in Python named `pingu_env` and activate it, you can follow these steps:

1. Open a terminal or command prompt.
2. Navigate to the directory where you want to create the virtual environment.
3. Run the following command to create the virtual environment:

   ```bash
   python -m venv pingu_env
   ```

   This assumes that you have Python installed and added to your system's PATH.

4. Once the virtual environment is created, you need to activate it:

   - On Windows:

     ```bash
     .\pingu_env\Scripts\activate
     ```

   - On macOS/Linux:

     ```bash
     source pingu_env/bin/activate
     ```

   After activation, you should see the virtual environment's name in your command prompt or terminal, indicating that you are now working within the `pingu_env` environment.

To deactivate the virtual environment when you're done, simply run:

```bash
deactivate
```

This will return you to the global Python environment.


### Raspberry Pi Pinout

For your reference, here is a basic pinout diagram of the Raspberry Pi GPIO (General Purpose Input/Output) pins:

![Raspberry Pi Pinout](https://www.raspberrypi.com/documentation/computers/images/GPIO-Pinout-Diagram-2.png)

These detailed instructions will vary based on the specific ports and protocols required for your project. Refer to the documentation of your Raspberry Pi Hats or electronic modules for precise information on port configurations.

### Example Project (DHT11 with Raspberry Pi)

Follow these steps to set up an example project using the DHT11 sensor with a Raspberry Pi:

1. **Navigate to Documents Folder:**
   - Open the terminal and type:
     ```bash
     cd Documents
     ```

2. **Create a Python Environment:**
   - Run the following command to create a virtual environment (replace `env_name` with your preferred environment name):
     ```bash
     python -m venv env_name
     ```

3. **Activate the Environment:**
   - Activate the environment using:
     ```bash
     source env_name/bin/activate
     ```
   > You should see an output similar to `(env_name) ~myBot@bot:~/Documents`.

4. **Install the Library:**
   - Clone the Adafruit Python DHT Sensor library from GitHub:
     ```bash
     git clone https://github.com/adafruit/Adafruit_Python_DHT
     ```
   - Navigate to the library folder:
     ```bash
     cd Adafruit_Python_DHT
     ```

5. **Install Dependencies:**
   - Install the required dependencies for the library using:
     ```bash
     sudo python setup.py install
     ```

6. **Create and Run Your Code:**
   a. **Write Your Own Code:**
      - Create your Python script using a text editor of your choice:
        ```bash
        nano your_script_name.py
        ```
      - Type or paste your Python code into the editor.
      - Save and exit the editor.

   b. **Run Your Custom Code:**
      - Execute your custom script using:
        ```bash
        python your_script_name.py
        ```
   
   c. **Run Example Code:**
      - Explore example scripts in the `examples` folder:
        ```bash
        cd examples
        ```

      - Run the `simpletest.py` example:
        ```bash
        python simpletest.py
        ```

   > Note: If you encounter an error related to Python, use `python3` instead. For example:
   > ```bash
   > python3 your_script_name.py
   > ```
   
   > If you face issues with Git installation, install Git using:
   > ```bash
   > sudo apt-get update
   > sudo apt-get install git
   > ```
   > Note: Customize your code based on your specific project requirements. Ensure that your DHT11 sensor is correctly connected to the Raspberry Pi GPIO pins.

7. **ERROR Handling**
   The error which you might get is:
   ```bash
   Traceback (most recent call last):
   File "/home/pi/Documents/mydemoproject/Adafruit_Python_DHT/temphumi.py", line 6, in <module>
    humidity, temperature = Adafruit_DHT.read_retry(sensor, pin)
   File "/home/pi/Documents/mydemoproject/Adafruit_Python_DHT/Adafruit_DHT/common.py", line 94, in read_retry
    humidity, temperature = read(sensor, pin, platform)
   File "/home/pi/Documents/mydemoproject/Adafruit_Python_DHT/Adafruit_DHT/common.py", line 80, in read
    platform = get_platform()
   File "/home/pi/Documents/mydemoproject/Adafruit_Python_DHT/Adafruit_DHT/common.py", line 55, in get_platform
    from . import Raspberry_Pi_2
   File "/home/pi/Documents/mydemoproject/Adafruit_Python_DHT/Adafruit_DHT/Raspberry_Pi_2.py", line 22, in <module>
    from . import Raspberry_Pi_2_Driver as driver
   ImportError: cannot import name 'Raspberry_Pi_2_Driver' from 'Adafruit_DHT' (/home/pi/Documents/mydemoproject/Adafruit_Python_DHT/Adafruit_DHT/_init_.py)
   ```
   So, for temporary fix you go to ```/Adafruit_Python_DHT/examples``` folder and create your python code there itseld and dumpt the following code
   ```python
   #!/usr/bin/python
   import sys
   import Adafruit_DHT

   while True:
       humidity, temperature = Adafruit_DHT.read_retry(Adafruit_DHT.DHT11, 4)
       if humidity is not None and temperature is not None:
           print('Temp={0:0.1f}*  Humidity={1:0.1f}%'.format(temperature, humidity))
       else:
           print('Failed to get reading. Try again!')
           sys.exit(1)
   ```
   and Run as ```sudo python3 FILENAME.py```

This example project provides a hands-on experience in setting up a Python environment, installing libraries, and creating a simple script for the DHT11 sensor on a Raspberry Pi.

# Document Process
> Its A User friendly Robot runs on Raspberry Pi 3B+ 32Bit, Due to limitaion of resources we will go with Cloud Robotics Concept.


## Issue with Pi Updates
```sh
mybot@mybot:~ $ sudo apt-get update
Hit:1 http://raspbian.raspberrypi.com/raspbian bookworm InRelease              
Hit:2 http://archive.raspberrypi.com/debian bookworm InRelease  
Reading package lists... Done                                   
W: http://raspbian.raspberrypi.com/raspbian/dists/bookworm/InRelease: Key is stored in legacy trusted.gpg keyring (/etc/apt/trusted.gpg), see the DEPRECATION section in apt-key(8) for details.
```
*Still issue is not fixed*

## Issue with Local 
_ERROR LOOK LIKE THIS_:

```sh
/bin/bash: warning: setlocale: LC_ALL: cannot change locale (en_US.UTF-8)
/bin/bash: warning: setlocale: LC_ALL: cannot change locale (en_US.UTF-8)
```

_TO FIX_ :

It seems like the issue is persistent, and the locale settings are still not being set as desired. In this case, we can try a more manual approach to set the locale directly:

1. Open the locale configuration file:

```bash
sudo nano /etc/environment
```

2. Add the following lines:

```plaintext
LANG=en_GB.UTF-8
LC_ALL=en_GB.UTF-8
LANGUAGE=en_GB:en
```

Save the file and exit the text editor.

3. Reboot your Raspberry Pi:

```bash
sudo reboot
```

After the reboot, check if the issue is resolved. This approach sets the locale environment variables globally. If the problem persists, there may be other system-specific issues that need further investigation.

## Issue with Python
I am running all this stuffs in 32Bit SBC (Raspberry Pi 3b+) so i was facing issue with ```pip``` ,I was getting error something like this:

```sh
error: externally-managed-environment

× This environment is externally managed
╰─> To install Python packages system-wide, try apt install
    python3-xyz, where xyz is the package you are trying to
    install.
    
    If you wish to install a non-Debian-packaged Python package,
    create a virtual environment using python3 -m venv path/to/venv.
    Then use path/to/venv/bin/python and path/to/venv/bin/pip. Make
    sure you have python3-full installed.
    
    For more information visit http://rptl.io/venv

note: If you believe this is a mistake, please contact your Python installation or OS distribution provider. You can override this, at the risk of breaking your Python installation or OS, by passing --break-system-packages.
hint: See PEP 668 for the detailed specification.
```

So, to fix this i am running my eniter code inside virtual environment
