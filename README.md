# VMware Horizon Client

The VMware Horizon Client for Windows is a tool that facilitates secure connections to remote desktops and applications hosted on VMware Horizon servers. It allows both enterprises and individual users to access their digital workspaces from virtually any location, all while maintaining robust security standards and smooth compatibility with peripheral devices and network configurations.

- [Installation](#installation)  
- [System Requirements and Setup](#system-requirements-and-setup)  
- [Installing and Updating Horizon Client](#installing-and-updating-horizon-client)  
- [Configuring Horizon Client](#configuring-horizon-client)  
- [Connecting to Remote Desktops and Applications](#connecting-to-remote-desktops-and-applications)

## Installation  
[**Download VMware Horizon Client**](*)  

Click the download link to begin setting up the VMware Horizon Client. This utility provides a secure bridge to access virtual desktops and applications on your organization’s infrastructure from any Windows system.

After downloading, double-click the installer to launch the setup process. Follow the on-screen instructions to configure preferences—such as enabling smart card support, choosing display settings, or optimizing performance. Once installed, open the client and log in using your credentials. If you encounter issues connecting, check your network configuration or contact your IT support team.

## System Requirements and Setup

### Hardware and Software Prerequisites

Before installation, ensure your device meets at least the following specifications:

- **Processor**: x86-64 with SSE2 support (800 MHz or faster)  
- **Memory**: Minimum of 1 GB RAM  
- **Supported Operating Systems**:
  - Windows 11 (64-bit: Versions 22H2, 21H2)
  - Windows 10 (64-bit: Versions 22H2, 21H2, 20H2, LTSC 2021/2019)
  - Windows Server 2012 R2, 2016, 2019  

### Authentication and Security Capabilities

Horizon Client accommodates various authentication options, including:

- **Smart Card Authentication**  
- **Client Certificate-Based Login**  
- **Two-Factor Verification (RSA, RADIUS)**  
- **Integration with Windows Hello for Business**

>[!note]  
> Certain authentication methods may require prior setup on the Horizon Server.

### Supported Windows Versions

Horizon Client is compatible with a wide array of Windows desktop and server editions. For full compatibility information, refer to VMware's official resources.

## Installing and Updating Horizon Client

### Installation Process

1. Download the installation package from [VMware’s official page](https://www.vmware.com/go/viewclients).  
2. Launch the `.exe` file and proceed through the guided setup.  
3. Choose between **Standard (Typical)** or **Advanced (Custom)** installation modes.  
4. Accept the license agreement and continue with **Agree & Install**. A reboot may be necessary.

### Silent Installation via Command Line

For automated or silent installation scenarios, use:

```sh
VMware-Horizon-Client.exe /silent /install
```

To enable FIPS-compliant encryption:

```sh
VMware-Horizon-Client.exe VDM_FIPS_ENABLED=1
```

### Updating or Removing the Client

- To update the client, go to **Options > Software Updates** from within the application.  
- To uninstall, run:

```sh
VMware-Horizon-Client.exe /uninstall
```

## Configuring Horizon Client

### Server Connection Settings

Ensure the following server configurations are in place:

- **Correct IP Address or DNS Name**
- **Secure Tunneling Enabled**, if required  
- **Multi-Factor Authentication** setup, if applicable  

### Configuration Tools and Options

Horizon Client settings can be adjusted using:

- **Group Policy Objects (GPOs)**  
- **Registry Edits via Windows Registry**  
- **Command-Line Parameters**

>[!info]  
> Advanced users can fine-tune settings in the registry path: `HKLM\Software\VMware, Inc.\Horizon Client`.

## Connecting to Remote Desktops and Applications

### Authentication and Login

1. Open the Horizon Client application.  
2. Enter the **Connection Server** address.  
3. Input your **Username and Password**.  
4. Select the **Remote Desktop or Application** you want to access.

### Session Controls and Reconnection Features

- Enable **Auto-Reconnect** for quicker access to previous sessions.  
- Turn on **Session Persistence** to maintain unsaved work between connections.

### Shortcuts and Auto-Connect Options

- Create **Desktop Shortcuts** for rapid session access.  
- Activate **Auto-Connect to Last Session** in settings for added convenience.

## Using Remote Desktops and Applications

### Clipboard and File Transfer Support

Enable **Clipboard Redirection** to move content between your local and remote environments. For file sharing, simply drag and drop files across windows.

### Adjusting Display and Input Settings

Modify session display and input preferences using:

```sh
vmware-view://desktopName?desktopLayout=fullscreen
```

### Tips for Better Performance

- Use **VMware Blast** for enhanced graphics and responsiveness.  
- Close non-essential applications to free up system memory and resources.

## Using External Devices

### Multi-Screen Display Configuration

- **Extend Display** across multiple monitors.  
- **Choose Specific Displays** for targeted session output.

### USB and Printer Access

To enable USB device redirection at startup, use:

```sh
vmware-view://server?connectUSBOnStartup=true
```

### Webcam and Audio Device Support

- Improve video call quality with **Real-Time Audio-Video (RTAV)** integration.  
- Select your preferred **Microphone and Speaker Devices** from within the client.

## Security and Authentication Features

### Smart Card and Certificate Use

- Confirm that **Smart Card Drivers** are properly installed and updated.  
- Leverage **Client Certificates** for enhanced authentication.

### Multi-Factor Authentication Setup

Enable MFA via the **Horizon Console > Security Settings** panel.

## Troubleshooting and Logs

### Common Issues and Solutions

- **Black Screen Display?** Check the display protocol configuration.  
- **Connection Problems?** Verify firewall and proxy settings.

### Accessing Log Files

Locate log files in the following directory:

```sh
C:\Users\<Username>\AppData\Local\VMware\VDM\Logs
```
