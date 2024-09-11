Campaigns enable automatic configuration to simplify an engagement, with automatic report generation.

---
## Campaign Modes

#### Reconnaissance - Monitor Only

Passively monitor client device and access point activity within a defined region of the WiFi environment.

#### Client Device Assessment - Passive

Identify client devices susceptible to basic rogue access points or evil twin attacks. Uses a passive PineAP mode to mimic access points only upon direct request. Depending on filter configuration, client devices may be allowed to associate with the WiFi Pineapple.

#### Client Device Assessment - Active

Identify client devices susceptible to advanced rogue access points or evil twin attacks. Uses an active PineAP mode to broadcast an SSID pool, mimicking all access points listed. New access points may be dynamically added to the pool. Depending on filter configuration, client devices may be allowed to associate with the WiFi Pineapple.

---
## Campaign Design

Campaigns should be designed in order to not capture any unrelated SSIDs or clients. Allow/block lists should be leveraged, i.e. only allow MP networks and deny everything else. This will avoid any data captured from nearby networks that are susceptible to attack. Public WiFi and commercial organizations may have open networks which the Pineapple WILL capture and create unnecessary data collection. 

Campaigns will generate a report, in either JSON or HTML format that will be stored locally on the Pineapple. 