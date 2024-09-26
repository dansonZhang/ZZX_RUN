中文博客：https://blog.csdn.net/qq_45153670/category_11762617.html

# ZZX_RUN V1.0

Show:

	in RVIZ:
  	roslaunch zzx_run_description display_xacro.launch
  
  	in GAZEBO:
  	roslaunch zzx_run_description gazebo.launch
  
  	arbotix+rviz:
  	roslaunch zzx_run_description arbotix.launch
  	roslaunch zzx_run_teleop zzx_run_robot_teleop.launch
  
  
Mapping:

	with Gmapping:
  	roslaunch zzx_run_gazebo zzx_run_gazebo.launch 
  	roslaunch zzx_run_navigation gmapping_slam.launch
  	roslaunch zzx_run_teleop zzx_run_robot_teleop.launch 
  	rosrun map_server map_saver -f ${map_name}
   
  	with hector:
  	roslaunch zzx_run_gazebo zzx_run_gazebo.launch
  	roslaunch zzx_run_navigation hector_slam.launch
  	roslaunch zzx_run_teleop zzx_run_robot_teleop.launch
  	rosrun map_server map_saver -f ${map_name}
  
  	explore with gmapping:
  	roslaunch zzx_run_gazebo zzx_run_gazebo.launch
  	roslaunch zzx_run_navigation exploring_gmapping_slam.launch
  	rosrun zzx_run_navigation exploring_slam.py
  	rosrun map_server map_saver -f ${map_name}
  
Navigation:

  	arbotix+rviz:
  	roslaunch zzx_run_bringup fake_zzx_run_robot.launch
  	roslaunch zzx_run_navigation fake_navigation.launch

  	arbotix+rviz+random:
  	roslaunch zzx_run_bringup fake_zzx_run_robot.launch
  	roslaunch zzx_run_navigation fake_navigation.launch
  	rosrun zzx_run_navigation random_navigation.py
  
  	ros_control+gazebo:
  	roslaunch zzx_run_gazebo zzx_run_gazebo.launch
  	roslaunch zzx_run_navigation real_navigation.launch
  
  	ros_control+gazebo+random:
  	roslaunch zzx_run_gazebo zzx_run_gazebo.launch
  	roslaunch zzx_run_navigation real_navigation.launch
  	rosrun zzx_run_navigation random_navigation.py
