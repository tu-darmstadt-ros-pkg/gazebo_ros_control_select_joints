# gazebo_ros_control_select_joints
Gazebo ros_control plugin that allows for selecting the controlled joints (unlike the standard [gazebo_ros_control](https://github.com/ros-simulation/gazebo_ros_pkgs/tree/indigo-devel/gazebo_ros_control) which grabs all transmissions available in the model)

## Usage
The usage of this plugin is very similar to the original [gazebo_ros_control](https://github.com/ros-simulation/gazebo_ros_pkgs/tree/indigo-devel/gazebo_ros_control) plugin, which documentation can be found [here](https://classic.gazebosim.org/tutorials?tut=ros_control)

To use the plugin, add the following to your robot's URDF:
```xml
  <gazebo>
    <plugin name="gazebo_ros_control_select_joints" filename="libgazebo_ros_control_select_joints.so">
      <robotNamespace>NAMESPACE</robotNamespace>
      <joints>joint_1 joint_2 joint_3</joints>
    </plugin>
  </gazebo>
```

with `<joint>` tag being the feature brought by this package. It expects a space separated list of joint names.

If no `<joint>` tag is specified, or if the list is empty, the plugin simply grabs all transmissions available in the model (as the standard gazebo_ros_control would do).