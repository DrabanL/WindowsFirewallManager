# Windows Firewall Manager
A library that simpifies programmatic management of Windows Firewall.

You can set various firewall settings (see <code>FirewallManagerSettings</code>) such as EdgeTraversal, IcmpTypesAndCodes, etc.

The library will also take care of IPs limit per rule and will generate new rules as needed.

## Usage

Its pretty simple and straightforward:

```
using RabanSoft.WindowsFirewallManager;
using RabanSoft.WindowsFirewallManager.Models;

...

var _firewallRef = new FirewallManager(new FirewallManagerSettings()
            {
                RuleName = "Application Blocked IPs",
                Protocol = NetFwIPProtocols.TCP,
                LocalPorts = "46332,44332",
            });

...

_firewallRef.Add("54.66.122.1");

...

_firewallRef.Remove("54.66.122.1");

...

_firewallRef.Clear();
```

## Nuget package
Install-Package RabanSoft.WindowsFirewallManager

or

dotnet add package RabanSoft.WindowsFirewallManager

or

https://www.nuget.org/packages/RabanSoft.WindowsFirewallManager
