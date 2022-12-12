This part of the coursework is very limited, due to mc issues and time issues i found this area especially difficult, additionally i ran into issues i could not remedy. As a result of this i have only a single model, my weapon, inserted into the scene. In order to import it required me to strip textures upon export. When i did not remove textures everything imported as a single black rectangle from origin. Additionally i couldnt grasp fixing this in openGL or lighting items. 

Irregardless, i managed to import my model, and then code both camera operations, and an interaction. My camera works on a simple calculation based on the lookAt matrix you provided and can be utilised with keys wasd. Secondly i developed a small interaction, as the gun was my item i was performing this interaction with, i decided to code the recoil and then compensation back to starting point. 

This was slightly more complex and the development is discussed below:

Firstly i believed it was as simple as just using a key being pressed, rotate backward, then rotate back to start point. When i attemped this i ran into the issue that due to commands in code being so fast to run, it was impossible to see the first action after pressing, you would only see the return to start position, hence nothing visually happened. 

To remedy this i tried to implement sleep() but this seemd to be of no use and threw issues. 

I then to troubleshoot tried to implement just press and release. Press rotating the gun backwards, release rotating the gun forwards back to start. This worked in terms of the recoil and recentering of the gun but it also removed the ability to move the object as the release state was always active when the key was not pressed. Hence the object could not be rotated on the axis in which the interaction occured when my solution was in this state.

Finally to complete my solution i utilised a boolean to allow for the remedying of the above issue. I acomplished this by intitialising a bool Pressed as false, this allowed for the operation below.

if (glfwGetKey(window, GLFW_KEY_Q) == GLFW_RELEASED && Pressed == true) {

This allows for my issue of release being constantly on until button is pressed to be fixed as release now relies and only will turn on, after the exact pressing of the button. This allows me to move my model, move my camera, and perform the interaction. 

FOR CAMERA MOVEMENT I FOUND THIS LINK OF GREAT EXACT USE. https://learnopengl.com/Getting-started/Camera
