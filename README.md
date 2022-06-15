# dual_iiwa Dual-Arm ROS Packages

![dual_iiwa](https://fastly.jsdelivr.net/gh/lyh458/ImageRepo@main/image/16552861679241655286167663.png)

- **dual_iiwa_description**: a URDF for a KUKA LBR IIWA robot and a universal robot (default: iiwa7 and ur5).
- **dual_iiwa_moveit_config**: a MoveIt! package to work with the robot description just defined.
~~- **dual_iiwa_bringup**: a package to bringup the iiwa and ur union.~~
~~- **dual_iiwa_gazebo**: a package simulate motion in gazebo for the union.~~

## Dependencies

- [iiwa_stack](https://github.com/IFL-CAMP/iiwa_stack): ROS integration for the KUKA LBR IIWA R800/R820 (7/14 Kg).

## Supported ROS Distribution

ROS Melodic and Noetic (tested).

## Usages

After installing all the dependencies, you can:

- Only visualize in RVIZ:

  ```xml
  roslaunch dual_iiwa_moveit_config demo.launch
  ```

~~- Real robot control:~~

  - please make sure that iiwa and ur are in the same subnet. eg. iiwa: `172.31.1.147`, ur: `172.31.1.12`.

  - roslaunch the integrated launch file

    ```xml
    roslaunch dual_iiwa_moveit_config moveit_planning_execution.launch sim:=false ur_ip:=<your_ur_ip>
    ```

~~The rqt_graph:~~

![rqt_graph_real](https://cdn.jsdelivr.net/gh/lyh458/ImageRepo@main/image/1628570846470-1628570846458-dual_iiwa_moveit_real_robot_seperated_namespace.png)

~~- Simulate in Gazebo:~~

  ```xml
  roslaunch dual_iiwa_moveit_config moveit_planning_execution.launch sim:=true
  ```

~~The rqt_graph:~~

![rqt_graph_sim](https://cdn.jsdelivr.net/gh/lyh458/ImageRepo@main/image/1628571178979-1628571178961-dual_iiwa_moveit_gazebo_seperated_namespace.png)

**some other options may be used**:

- `-use_pedestal`： if true, use pedestal instead of simple robot, default `true`.

More options info can be checked in launch files.

~~## Other Branches~~

This branch `master` holds iiwa and ur in two different namespace, if you prefect a unified namespace version, you can try this branch [all-in-one-namespace](https://github.com/lyh458/dual_iiwa/tree/all-in-one-namespace), whose almost all nodes and topics are included in a same namespace, `dual_arm` by default.

## References

- [dual_ur](https://github.com/Liuyvjin/shixi_dual_ur)