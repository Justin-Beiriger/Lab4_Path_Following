# Lab4_Path_Following

Justin Beiriger, Adam Davis, Gareth, Surag

In this lab, we wrote 3 ROS nodes to interact in order to provide the demonstrated functionality. First, we reused our LIDAR alarm code which detecs object that are within a "corridor" in front of the robot. Then, we wrote an action-client, action-server pair of nodes. The client node builds the initial path goal and sends it to the server. If the LIDAR alarm goes off, then the client commands the server to halt the robot and wait for more path commands. If the path execution is suspended, the robot waits until the LIDAR alarm is no longer sounding, and the client then resends the path goal, beginning where the robot was interrupted. 
