# Raspberry Pi Workshop

## Initial Kickstart Learning Resources

### Setup for First-time

- **Setup Headless Mode** - [Youtube](#)

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

This example project provides a hands-on experience in setting up a Python environment, installing libraries, and creating a simple script for the DHT11 sensor on a Raspberry Pi.
