# MotionDetection
MotionDetection is an iOS framework which use sensor to detect motion.

## Installation

- Install [CocoaPods](http://cocoapods.org).

- Open Terminal and go to your project directory.

- Create a Podfile with the command :

```ruby
pod init
```

- In the Podfile created, add the line :

```ruby
pod 'MotionDetection', :git => 'https://github.com/quentindnl/MotionDetection', :tag => '2.0.0'
```

- Use the command below to install the framwork :

```ruby
pod install
```

-MotionDetection is now available in your project.

## Usage

- First import the framework with :

```ruby
import MotionDetection
```

- Create an instance of the class "Detection" :

```ruby
let myInstance = Detection()
```

- Start the motion detection with :

```ruby
myInstance.startMotionDetection()
```

- Now you can call variable to know motion status:


bool    isRunningDownDetected

bool    isRunningUpDetected

bool    isRunningUpDownDetected

bool    isRunningDownUpDetected

bool    isDeviceInPocket
        
int    bicepCurlCounter

int    starJumpCounter

- A example to call motion status variables :

```ruby
@objc func update() {
        if (isRunningDownDetected==true) {myLabel.text = "Detection running down"}
    }
```

```ruby
_ = Timer.scheduledTimer(timeInterval: 1, target: self, selector: #selector(update), userInfo: nil, repeats: true)
    }
```


