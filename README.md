# VMware Horizon Client

* [Installation](#installation)
* [System Requirements and Setup](#system-requirements-and-setup)
* [Installing and Updating Horizon Client](#installing-and-updating-horizon-client)
* [Configuring Horizon Client](#configuring-horizon-client)
* [Connecting to Remote Desktops and Applications](#connecting-to-remote-desktops-and-applications)

## Installation

Once the download finishes, double-click the installer to launch the setup wizard. Follow the on-screen instructions to select your preferred options—for instance, enabling smart card login, adjusting display settings, or optimizing performance. After installation concludes, open the client and log in using your account credentials.
If you experience connection difficulties, review your network configuration or consult your IT support team.

### System Requirements and Setup

#### Hardware and Software Prerequisites

Before starting the installation, ensure your device meets these minimum specifications:

* **Processor**: x86-64 with SSE2 support (800 MHz or higher)
* **RAM**: Minimum 1 GB
* **Supported Operating Systems**:

  * Windows 11 (64-bit: Versions 22H2, 21H2)
  * Windows 10 (64-bit: Versions 22H2, 21H2, 20H2, LTSC 2021/2019)
  * Windows Server 2012 R2, 2016, 2019

### Authentication and Security Options

Horizon Client accommodates several authentication methods, including:

* **Smart Card Login**
* **Client Certificate Sign-In**
* **Two-Factor Authentication (RSA, RADIUS)**
* **Integration with Windows Hello for Business**

> \[!note]
> Certain methods may require additional configuration on the Horizon Server.

### Supported Operating Systems

The Windows edition of VMware Horizon Client is compatible with a broad range of desktop and server versions. Refer to VMware’s official documentation for comprehensive compatibility details.

## Installing and Updating Horizon Client

### Installation Steps

1. Download the installer from [VMware’s GitHub](*).
2. Execute the `.exe` file and follow the guided setup.
3. Select either **Typical (Standard)** or **Custom (Advanced)** installation mode.
4. Accept the license terms and click **Agree & Install**. Restart the computer if prompted.

### Silent Installation Parameters

For automated installations, run:

```sh
VMware-Horizon-Client.exe /silent /install
```

To enable FIPS-compliant encryption:

```sh
VMware-Horizon-Client.exe VDM_FIPS_ENABLED=1
```

### Updating or Removing the Client

* To update, navigate to **Options > Software Updates** in the client.
* To uninstall, execute:

```sh
VMware-Horizon-Client.exe /uninstall
```

## Configuring Horizon Client

### Setting Up the Server Connection

Ensure the server-side configuration includes:

* **Correct IP address or DNS name**
* **Secure Tunnel enabled**, if necessary
* **Multi-Factor Authentication enabled**, when required

### Common Ways to Configure

Horizon Client settings can be adjusted via:

* **Group Policy Objects (GPOs)**
* **Windows Registry modifications**
* **Command-line options**

> \[!info]
> Advanced settings can be found under the registry path:
> `HKLM\Software\VMware, Inc.\Horizon Client`

## Connecting to Remote Desktops and Applications

### Sign-In and Authentication

1. Launch Horizon Client.
2. Enter the **Connection Server** address.
3. Provide your **Username and Password**.
4. Choose your **Target Desktop or Application** to initiate the session.

### Session Management and Reconnection

* Enable **Auto-Reconnect** to resume sessions without logging in manually.
* Use **Session Persistence** to maintain unsaved work during disconnects.

### Quick Access and Auto-Connect

* Create a **Desktop Shortcut** for faster access.
* Activate **Auto-Connect to Last Session** in preferences for convenience.

## Using Remote Desktops and Applications

### File and Clipboard Sharing

Enable **Clipboard Redirection** to copy text or data between your local and virtual environments. Drag-and-drop supports file transfers between desktops.

### Display and Input Adjustments

Adjust your session layout and interactions with:

```sh
vmware-view://desktopName?desktopLayout=fullscreen
```

### Performance Optimization Tips

* Opt for **VMware Blast** protocol for improved rendering and responsiveness.
* Close unused applications to free up system resources.

## Using External Devices

### Multi-Monitor Setup

* **Extend Displays** to span sessions across multiple monitors.
* **Assign Specific Monitors** for remote usage only.

### USB and Peripheral Access

Enable USB redirection with:

```sh
vmware-view://server?connectUSBOnStartup=true
```

### Audio and Camera Integration

* Improve online meetings with **Real-Time Audio-Video (RTAV)**.
* Choose your **Preferred Audio Input and Output Devices** for better clarity.

## Security and Authentication Features

### Smart Card and Certificate Access

* Ensure **Smart Card Drivers** are installed and current.
* Use **Certificate-Based Authentication** to strengthen security.

### Setting Up Two-Factor Authentication

Activate this in **Horizon Console > Security Settings** to add an extra authentication layer.

## Troubleshooting and Logs

### Frequent Problems and Solutions

* **Black screen on connection?** Try changing the display protocol.
* **Connection issues?** Check firewall and proxy settings.

### Viewing Log Files

Access log files here:

```sh
C:\Users\<Username>\AppData\Local\VMware\VDM\Logs
```
