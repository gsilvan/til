# Enable Multicast DNS (mDNS) on esp8266

```cpp
#include <ESP8266mDNS.h>

const char *dns_name = "solarboy";

void setup() {
    if (MDNS.begin(dns_name)) {
        Serial.println("mDNS responder started");
        Serial.println("http://" + String(dns_name) + ".local/");
    }
}

void loop() {
    MDNS.update();
}
```

## Linux configuration

https://wiki.archlinux.org/title/Avahi

