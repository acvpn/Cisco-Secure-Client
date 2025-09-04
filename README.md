# Cisco Secure Client

* [Installation](#installation)
* [Deploying Cisco Secure Client](#deploying-cisco-secure-client)
* [Cisco Secure Client Deployment Methods](#cisco-secure-client-deployment-methods)
* [Predeploying Cisco Secure Client](#predeploying-cisco-secure-client)
* [Configuring Cisco Secure Client Modules](#configuring-cisco-secure-client-modules)

## Installation

After the download finishes, use the following steps to install the client:

* Run the installer and follow the on-screen instructions.
* Provide administrator privileges if prompted to continue.
* Once installed, launch Cisco Secure Client and configure your VPN connection.
* Ensure any configuration profiles from your IT team are applied correctly for stable connectivity.

## Deploying Cisco Secure Client

Previously called AnyConnect, Cisco Secure Client provides secure remote access for end users. It merges strong security capabilities with dependable enterprise network connectivity. This guide details how to deploy, configure, and troubleshoot the client effectively.

## Cisco Secure Client Deployment Methods

The deployment approach depends on your organization’s infrastructure and operational requirements:

> **Predeployment**: Installed manually or via enterprise software distribution systems such as SMS.

> **Web Deployment**: Automatically installs when a user connects to supported devices like Secure Firewall ASA, ISE, or Threat Defense.

> **Cloud Management Deployment**: Managed and deployed through the Cisco Secure Client Cloud Management platform.

Each method offers distinct advantages and prerequisites, described in the following sections.

## Predeploying Cisco Secure Client

Predeployment entails installing Cisco Secure Client manually or using enterprise management tools.

### Predeployment Steps:

1. **Download the Predeployment Package**

   * Available via Cisco’s official software portal.

2. **Install the Required Modules**

   * VPN
   * Network Access Manager
   * ISE Posture
   * Network Visibility Module

3. **Distribute Configuration Profiles**

   * Maintain profile consistency between client devices and headend systems (ASA, ISE).

4. **Deploy via SCCM or Similar Platforms**

   * Use distribution tools like SCCM for a smooth deployment.

5. **Verify Installation**

   * Ensure the client is installed properly and fully operational.

## Web Deploying Cisco Secure Client

Web deployment enables Cisco Secure Client to install automatically when users access a headend appliance such as ASA or ISE.

### Web Deployment Procedure:

1. **Upload the installer package to ASA or ISE.**
2. **Configure deployment policies and settings on the headend device.**
3. **Users log in to the headend web portal to initiate the download.**
4. **Installation completes automatically once the session begins.**

> \[!info] **Note:** Web deployment requires an active internet connection and access to the headend device.

## Updating Cisco Secure Client Software and Profiles

Keeping Cisco Secure Client up to date is crucial for compatibility, stability, and security.

### Update Methods:

* **Automatic Update via ASA or ISE**

  * Updates are applied during VPN sessions.

* **Manual Update**

  * Users download and install the latest package directly from Cisco’s website.

* **Enterprise Software Distribution Update**

  * Updates are delivered centrally via an SMS platform.

## Configuring Cisco Secure Client Modules

Cisco Secure Client includes several modules configurable to align with your organization’s security policies.

### Available Modules:

* **VPN Module**: Provides secure access to enterprise networks.
* **Network Access Manager**: Manages and enforces network access.
* **ISE Posture**: Validates endpoint security compliance.
* **Network Visibility Module (NVM)**: Collects telemetry for monitoring and analysis.
* **Umbrella Roaming Security Module**: Adds DNS-layer protection via Cisco Umbrella.

### VPN Module Configuration:

```xml
<VPNProfile>
    <ServerList>
        <HostEntry>
            <HostName>vpn.company.com</HostName>
            <HostAddress>192.168.1.1</HostAddress>
        </HostEntry>
    </ServerList>
</VPNProfile>
```

## Managing Profiles and Policies

Profiles and policies govern how Cisco Secure Client enforces organizational security standards.

### Profile Management:

* **VPN Profiles**: Contain server addresses and authentication methods.
* **ISE Posture Profiles**: Define compliance rules for endpoints.
* **Network Visibility Profiles**: Specify telemetry collection settings.

### Policy Management:

* Managed via **ASA, ISE, or Cisco Secure Client Cloud Management**.
* Policies control authentication, access, and security enforcement.

## Security and Compliance Considerations

Cisco Secure Client incorporates features to protect both devices and enterprise networks.

### Key Security Features:

* **Multi-factor Authentication (MFA)**: Adds an additional identity verification step.
* **Endpoint Compliance Checks**: Ensures devices meet required security standards.
* **Encrypted Connections**: SSL and IPsec safeguard data in transit.

> \[!important] **Allow VPN access only for devices compliant with your organization’s security requirements.**

## Troubleshooting Cisco Secure Client

If problems occur, start with these basic troubleshooting steps:

### Common Issues & Solutions:

* **Cannot Connect to VPN**

  * Verify the correct configuration profile is applied.
  * Check firewall or proxy settings.

* **Authentication Errors**

  * Confirm login credentials.
  * Ensure the authentication server is reachable.

* **Update Failures**

  * Restart the client and attempt the update again.
  * Confirm the update server is accessible.

### Logs and Diagnostic Tools:

Cisco Secure Client provides the **Diagnostic and Reporting Tool (DART)** for collecting logs and diagnostic data.

```shell
c:\Program Files (x86)\Cisco\Cisco Secure Client\DART\dartcli.exe -log
```

## Cisco Secure Client System Requirements

Before installing, confirm that your system satisfies the necessary specifications.

### Supported Operating Systems:

* **Windows**: Windows 10, 11
* **macOS**: macOS 11 or newer
* **Linux**: Ubuntu, Red Hat Enterprise Linux

### Hardware Requirements:

* **CPU**: 64-bit Intel or AMD processor
* **RAM**: Minimum 2GB
* **Disk Space**: At least 200MB available

### Network Prerequisites:

* **Internet Connection**: Required for web deployment and updates
* **Firewall Permissions**: VPN traffic must be permitted

> \[!note] **Ensure your operating system and security patches are current for optimal performance.**
