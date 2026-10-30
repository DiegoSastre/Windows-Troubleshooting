# DNS & DHCP Troubleshooting

## Objective

Troubleshoot common DNS and DHCP issues on a Windows client using standard Windows networking tools.

The lab focuses on identifying how the computer receives its network configuration, how DNS resolution works, and how to refresh DHCP and DNS information during troubleshooting.

## Scenario

A user reports that they are having problems accessing websites and resolving network resources.

As a Help Desk technician, the goal is to determine whether the issue is related to:

- DHCP configuration
- DNS configuration
- DNS cache
- Network configuration

## Environment

- Windows 11
- Wi-Fi network connection
- Command Prompt
- PowerShell
- Windows networking tools

## Tools Used

- `ipconfig`
- `nslookup`
- `ping`
- `ipconfig /displaydns`
- `ipconfig /flushdns`
- `ipconfig /release`
- `ipconfig /renew`

---

## 1. Review DHCP and DNS Configuration

The first step is to identify the network configuration assigned to the Windows client.

The following information is reviewed:

- IPv4 address
- Subnet Mask
- Default Gateway
- DHCP Server
- DNS Servers
- DHCP status

### Command

```cmd
ipconfig /all
```

### Evidence

![DHCP and DNS Configuration](./screenshots/01-dns-dhcp-config.png)

---

## 2. Inspect the DNS Resolver Cache

Windows temporarily stores DNS information in the local DNS resolver cache.

This can help determine whether previously resolved domains are being stored locally.

### Command

```cmd
ipconfig /displaydns
```

### Evidence

![DNS Resolver Cache](./screenshots/02-dns-cache.png)

---

## 3. Test DNS Resolution

`nslookup` can be used to test whether the configured DNS server can resolve a domain name.

### Command

```cmd
nslookup google.com
```

### Evidence

![DNS Query](./screenshots/03-dns-query.png)

---

## 4. Clear the DNS Resolver Cache

If cached DNS information is suspected to be incorrect or outdated, the local DNS resolver cache can be cleared.

### Command

```cmd
ipconfig /flushdns
```

### Evidence

![Flush DNS Cache](./screenshots/04-flushdns.png)

---

## 5. Release the DHCP Configuration

The current DHCP configuration can be released from the network adapter.

### Command

```cmd
ipconfig /release
```

### Evidence

![DHCP Release](./screenshots/05-dhcp-release.png)

---

## 6. Renew the DHCP Configuration

After releasing the configuration, Windows can request a new DHCP configuration from the DHCP server.

### Command

```cmd
ipconfig /renew
```

### Evidence

![DHCP Renew](./screenshots/06-dhcp-renew.png)

---

## 7. Verify the Final Configuration

The network configuration is checked again after renewing the DHCP lease.

### Command

```cmd
ipconfig /all
```

### Evidence

![Final Network Configuration](./screenshots/07-final-config.png)

---

## Findings

_To be completed after performing the troubleshooting exercises._

## Troubleshooting Relevance

This lab demonstrates basic client-side troubleshooting commonly performed by a Help Desk or IT Support technician when a user reports problems accessing websites or network resources.

The troubleshooting process focuses on separating DHCP-related problems from DNS-related problems instead of assuming that every connectivity issue has the same cause.

## Conclusion

_To be completed after the troubleshooting exercises._
