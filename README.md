[![CircleCI](https://circleci.com/gh/heleport/ardupilot/tree/visualpos.svg?style=svg)](https://circleci.com/gh/heleport/ardupilot/tree/visualpos)

# Automated builds

Builds are done on CircleCI, firmware is uploaded to `s3://heleport-dev/ardupilot/<branchname>`, eg:
* https://s3-us-west-1.amazonaws.com/heleport-dev/ardupilot/visualpos/ArduCopter-v2.px4
* https://s3-us-west-1.amazonaws.com/heleport-dev/ardupilot/visualpos/ArduCopter-ubuntu.elf

# Load new firmware

## Update firmware

* `scp ArduCopter-v2.px4 solo:/firmware`
* Restart the solo

## Connect with mavlink

* `pip install mavproxy`
* `mavproxy.py —master 0.0.0.0:14550`

## Set params

* `param set EK2_GPS_TYPE 0`
* `param set LOG_BACKEND_TYPE 1`
* `param set LOG_BITMASK 131070`
* `param set LOG_DISARMED 1`
* `param set LOG_REPLAY 1`