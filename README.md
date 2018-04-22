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


## Pros and Cons


- For the running up and down motion detection, I coupling the accelerometer data with the altimeter data.
Altimeter is used for detect going up and down and the altimeter for detect running. The problem is that the altimeter has a low frequency update. So when you going up and begin to going down, the altimeter hasn't yet get the altitude reached. So with my solution, you have to wait the altimeter update to the right altitude and after move the phone to enable accelerometer and detect this motion.

## TODO

- Protect sdk code from viewing.

- Add private to deep functions and variables.

- Coupling gyroscope with accelerometer on bicep curl detection, detect a rotation ~= 90 degrees.

- Use delegate to let user get motion detection.
