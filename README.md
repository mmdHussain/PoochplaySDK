# PoochplaySDK
BLE project to track acitvity.
# PoochPlay BLE(Bluetoothy low energy) device Integration & device details.
An iOS library that solves Poochplay iOS Bluetooth Low Energy problems. 
Class exposes high level API for connecting and communicating with Bluetooth LE peripherals.
The API is clean and easy to read.

## Features (Version 0.0.1)

1. Connecting with bluetooth devices.
2. Poochplay device battery percentage, Total step counts, Total calories burn.

#### Central
- Scan for remote peripherals for a given time interval.
- Continuously scan for remote peripherals for a give time interval, with an in-between delay until interrupted.
- Connect to remote peripherals with a given time interval as time out.
- Receive any size of data without having to worry about chunking.

#### Peripheral
- Start broadcasting with only a single function call.
- Send any size of data to connected remote centrals without having to worry about chunking.


To integrate PoochplaySDK into your Xcode project using CocoaPods, specify it in your `Podfile`:
```
```ruby
source 'https://github.com/CocoaPods/Specs.git'
platform :ios, '8.0'
use_frameworks!

pod 'BluetoothKit', '~> 0.2.0'
```

Then, run the following command:

```bash
$ pod install
```


## How to Use this module after seting up all gradle.

First we need to Initialize SDK into ViewCOntroller , And for getting call back of every method, We need to implement **Protocol**

    let pooch = Poochplay()
    
    pooch.poochplayDelegate = self
    
    
To establish the connection between your App and framework you need to connect with below method by passing CBCentralMAnager object and peripherral object with identifier to whom you want to connect.

    pooch.connectWithBle(uuid:"PERIPHERAL_UUIDSTRING",periferal:CBPeripheral, manager: CBCentralManager)

After Implementing  **Protocol** you will start getting callback in below methods:- 

    func getBigData(_ bigDataDic: [AnyHashable : Any]!, andDevice bleDevice: Any!) {
            // To get all untracked data in bulk
    }
    
    func getRealTimeStepsData(_ stepsDic: [AnyHashable : Any]!, andDevice bleDevice: Any!, macId idString: String!, batterlyLevel btLevel: Int32) {
                    // event emit in every seconds.
    }
    
## Version 0.0.1

The BLE library v 0.0.1 is supported.
