### The problem
By default, `raspbian` writes log files and other temporary files onto the SD card. This eventually leads to card failure, or the dreaded `kernel panic, can't boot` message(s).

### RO rootfs to the rescue
Some use cases allow for a readonly system that boots to same state everytime. All temporary files are written to `tmpfs`, and are lost on reboot. It's certainly possible to save these or any other system information onto a 2nd disk or to a network mounted storage.

### Basic steps
* Mount the raspbian `img` file
* Edit in `chroot` environment
* Test locally with `qemu`
* Write updated `img` to SD card
* Use on a raspberry pi

