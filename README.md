# ROS Web Gamepad

This is a simple web application that uses the browser [Gamepad API][] and [roslibjs][] to publish gamepad (joystick / game controller) input to ROS via a [rosbridge][], without installing anything.

[Gamepad API]: https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API
[roslibjs]: https://wiki.ros.org/roslibjs
[rosbridge]: https://wiki.ros.org/rosbridge_suite

As an alternative, you might want to use the [joy][] package.

[joy]: https://wiki.ros.org/joy


# Usage

Navigate to https://whoigit.github.io/ros-web-gamepad/?rosbridge-websocket-url=ws://127.0.0.1:9090 (insert the correct address for your rosbridge), connect a gamepad to your computer, and press any gamepad button.


# Notes and Limitations

Your browser's security settings may prevent the page from connecting to the rosbridge. In this case, download the HTML file and open it locally.

The application publishes [`sensor_msgs/Joy`][sensor_msgs/Joy] messages to the `/joy` topic at 10 Hz.

Most browsers support the Gamepad API, but Safari's support seems buggy. At the time of writing, Chrome works well.

This has been tested against ROS Melodic. It probably does not work with ROS2.

The appearance of the gamepad indicators is derived from [`ipywidgets`][ipywidgets].

[sensor_msgs/Joy]: https://github.com/ros/common_msgs/blob/noetic-devel/sensor_msgs/msg/Joy.msg
[ipywidgets]: https://github.com/jupyter-widgets/ipywidgets
