# Lab4_Path_Following

Justin Beiriger, Adam Davis, Gareth, Surag

In this lab, we wrote 3 ROS nodes to interact in order to provide the demonstrated functionality. First, we reused our LIDAR alarm code which detecs object that are within a "corridor" in front of the robot. Then, we wrote an action-client, action-server pair of nodes. The client node builds the initial path goal and sends it to the server. If the LIDAR alarm goes off, then the client commands the server to halt the robot and wait for more path commands. If the path execution is suspended, the robot waits until the LIDAR alarm is no longer sounding, and the client then resends the path goal, beginning where the robot was interrupted. 

The biggest change that we had to make to this lab was deciding where to check for the cancelled goal within the action server node. At first, we were only checking for the alarm in between each subgoal along the path (in the main function), but that was not effective. So, we had to check for the alarm in the do_move and do_spin functions, while the robot is in the middle of its subgoals. After making this change, we observed the functionality in the video - when the alarm sounds, the robot halts and then the new path message is sent to the server to be executed when the alarm has been turned off (the person has moved from the robot's path). 
