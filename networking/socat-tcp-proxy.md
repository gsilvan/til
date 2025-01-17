# TCP proxy using socat

```bash
#!/bin/bash

sudo socat TCP4-LISTEN:502,fork TCP:192.168.178.28:502
```
