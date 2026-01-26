# MacOS X Notes

### Bluetooth corruption on 2013 Macbook Pro
Reload the Bluetooth kext!
> `sudo kextunload -b com.apple.iokit.BroadcomBluetoothHostControllerUSBTransport`  
> `sudo kextload -b com.apple.iokit.BroadcomBluetoothHostControllerUSBTransport`
