Unofficial test build of FastECU, not a FastECU release. It's built from
[miikasyvanen/FastECU](https://github.com/miikasyvanen/FastECU) master plus the fix that makes the new protocol show
up in the protocol list. It adds a read-only protocol for the 2019+ Subaru 2.0 DIT ECUs (Hitachi SH72544R, 2.5 MB of
flash).

**Not yet tested on a car.** It only reads; nothing is written to the ECU.

### Which zip

* **`FastECU-@TAG@-windows-i686.zip` (32-bit): use this one with a Tactrix OpenPort 2.0.** The OpenPort's J2534
  driver is 32-bit, and a 64-bit program can't load it.
* `FastECU-@TAG@-windows-x86_64.zip` (64-bit): for comparison only; it most likely can't use the OpenPort.

### How to read

1. Unzip and run `FastECU.exe`.
2. If you've run FastECU 0.1.0-beta.5 before, close it and rename
   `%LOCALAPPDATA%\FastECU\0.1.0-beta.5\config\protocols.cfg` (for example to `protocols.cfg.old`). FastECU keeps
   its old protocol list otherwise, and the new entry won't appear.
3. Select the protocol **"Subaru 2019+ 2.0 DIT CAN (Hitachi SH72544R/2.5MB), read only"** and read the ECU.
4. A complete read is exactly **2,621,440 bytes**. Please open an issue with your ECU's calibration ID and the result,
   good or bad.

### Source

Built from commit @SHA@ on branch `hitachi-sh72544-2.5mb`. FastECU is GPL-3.0; the license is in each zip and the
source is in this repository.
