## PineAP Capabilities

PineAP enables some of the core functionality of the WiFi Pineapple:

- Control access with Filters Limit your engagement by configuring access by filters. Limit to specific clients or SSIDs, or exclude specific clients or SSIDs.    
- Impersonate APs Explicitly advertise lists of access points to instigate clients into connecting to previously saved networks.    
- Open AP Serve a basic, unencrypted Open access point, or automatically impersonate _any_ Open access point requested by a client.    
- Evil WPA Serve a new WPA network, or copy an existing WPA network. Capture partial handshakes to crack the WPA keys of unknown networks.    
- Evil Enterprise Serve a WPA-Enterprise network with optional key exchange degradation. Coupled with automatic authorization of all accounts, identify misconfigured enterprise clients and capture credentials.    

## PineAP Settings

**PineAP** offers three basic operation modes:

1. **Passive** Collect information about nearby access points, and add them to the list of potential APs to advertise. Accept connections to the Open, WPA, and Enterprise SSIDs (if enabled) Do _not_ advertise other access points, and it will not answer for other SSIDs.
    
2. **Active** Collect information about nearby access points. Actively advertise all SSIDs from the Impersonated AP Pool (if enabled) Respond to all client requests for any network which is permitted by the filters.
    
3. **Advanced** All PineAP features can be individually configured; mix and match the features you need
![](Resources/Pineap.png)
**Notifications**

Create a notification in the WiFi Pineapple UI when a client connects or disconnects from any of the WiFi Pineapple access points.
**SSID Pool Capture**

Automatically add SSIDs to the SSID Pool for advertising. SSIDs are collected from probe requests made by clients and nearby access points observed by recon mode.

When "Capture SSIDs to Pool" is enabled, SSIDs seen passively (observed probe requests) and through recon mode are automatically added to the pool of target SSIDs.

Additional configuration can be found under the "Impersonation" tab.
**Broadcast SSID Pool**

SSIDs from the SSID Pool can be advertised; this will cause the SSIDs to be visible in the network list of nearby devices, and may be useful for collecting client information.

Additional configuration can be found under the "Impersonation" tab.

SSIDs can be impersonated from a single BSSID, or from a pseudo-random BSSID for each SSID.

---
### OpenAP

OpenAP is an open access point that can be enabled to allow for connections to capture data. Be sure to allow your Open SSID in the filter rules; it must be in the list if filters are set to "Allowed", and must not be in the list if filters are set to "Deny".

When "Impersonate All Networks" is enabled, the WiFi Pineapple will answer for _all_ SSIDs which are permitted by the filter configuration!

Filters can be used to tune the responses for your engagement, by either allowing all SSIDs in the filter list, or denying all SSIDs _not_ in the filter list.![](Resources/openap.png)

---
### Evil WPA

The Evil WPA access point is used to impersonate a WPA (or WPA2) PSK network. It can also be used to collect partial handshakes for use with external cracking tools when the PSK is not known. As before, be sure to include your "Evil" WPA to the filter to allow connection attempts.![](Resources/evilwpa.png)

---
### Impersonation

Some WiFi clients will not attempt to connect to a network unless they observe an advertisement; in addition to responding as any network when "Impersonate All Networks" is enabled, the WiFi Pineapple can advertise additional SSIDs using the SSID Impersonation Pool.

These networks will be visible in the network lists of nearby devices. Combined with "Impersonate All Networks", this can capture clients which otherwise would not connect to the WiFi Pineapple.

Networks advertised from the SSID Impersonation Pool can come from any BSSID (that of the WiFi Pineapple Open access point, or any other MAC address), or from a pseudo-random BSSID which is unique to each impersonated SSID, and can be sent to the broadcast address (default), or a single client address.

To allow connections to a SSID from the impersonation pool, be sure it is allowed by your filter configuration and "Impersonate All Networks" is enabled.
![](Resources/impersonation.png)

---
### Filtering

The filtering page is designed for Allow/Deny lists for both specific clients and SSIDs. The "Allow" column will only allow clients/SSIDs on the list to be impersonated or connect to the PineAP. The "Deny" column will deny clients/SSIDs on the list. 

In order to take advantage of OpenAP, EvilWPA or Evil Enterprise APs, the filter mode should be set to Deny. If it is set to Allow, clients/SSIDs must explicity be entered. 