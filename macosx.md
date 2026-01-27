# MacOS X Notes

### Bluetooth corruption on 2013 Macbook Pro
Bluetooth mouse (and everything Bluetooth) had a habit of dying now and then, at least in El Capitan. Reload the Bluetooth kext!  
`sudo kextunload -b com.apple.iokit.BroadcomBluetoothHostControllerUSBTransport`  
`sudo kextload -b com.apple.iokit.BroadcomBluetoothHostControllerUSBTransport`
