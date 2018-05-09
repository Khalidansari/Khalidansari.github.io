---
layout: default
---
# Adhoc Tricks

## Run JD decompiler on mac

CD to the directory with the JD jar and then run the following command:

> java --add-opens java.base/jdk.internal.loader=ALL-UNNAMED --add-opens jdk.zipfs/jdk.nio.zipfs=ALL-UNNAMED -jar jd-gui-1.4.0.jar


## Enable unidentified apps to run, enable Anywhere option in MAC:

> sudo spctl --master-disable
> sudo spctl --master-enable