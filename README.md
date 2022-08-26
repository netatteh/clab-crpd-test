# cRPD deployment test

## Initialization

1. Clone this repository
2. Run `clab dep`

## Expected result

Lab get deployed, and each device EXCEPT CE1 and CE2 get startup configuration from the defined `startup-config` file. CE1 and CE2 don't have that defined, so they should get the default configuration.

The configuration files have differing ISO addresses on the `lo` interface, which reflect their management address. This can be used to find out which config file got deployed to the device.

## Actual result

All the nodes deployed with `startup-config`get deployed properly. CE1 and CE2 devices get configuration randomly from one of the devices with `startup-config` defined. The configurations used change every time `sudo clab destroy --cleanup` and `sudo clab deploy` are run.
