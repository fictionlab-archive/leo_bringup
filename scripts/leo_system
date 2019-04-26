#!/usr/bin/env python 

import rospy
import os


from std_msgs.msg import Empty


def rebootCallback(x): 
    rospy.logerr("reboot")
    os.system("reboot")

def shutdownCallback(x): 
   rospy.logerr("shutdown")
   os.system("shutdown -r now")


if __name__=="__main__":
    try:
        rospy.init_node('leo_system', anonymous=True)
        pose_sub=rospy.Subscriber("/system/shutdown", Empty, shutdownCallback)
        pose_sub=rospy.Subscriber("/system/reboot", Empty, rebootCallback)
        rospy.loginfo("Leo system node is working!...be gentle using shutdown and reboot command!")
    except rospy.ROSInterruptException as e:
        rospy.logerr(e)

    rospy.spin()







