Servos are similar to motors in the fact they look the same and both turn, however servos only turn to a set degrees rather than in rotations like a motor. 

The code used in a servo is:
`enable_servos();
 set_servos_position(port,degree);
 ao();
 disable_servos();
 msleep(time);`

 Servos aren't automatically on when you start the bot, they must be turned on via the code to allow them to function. This is why we use `enable_servos();` and `disable_servos();`, this is to conserve the battery of the bot and is highly recommended so your bot doesn't die mid-code.

`ao();` also works in a similar manner to `disable_servos();` however this stops the function of all servos, motors and sensors, you can use this to also conserve battery or halt the working of everything when used in a function.

`set_servo_position(port,degree);` tells the bot at what position between 0 and 2047 to set the arm of the bot. 

`msleep();` is used to give the servo a set time to operate within, this does not change the speed of the bot but is necessary for the operation of it.
Remember time is measured in milliseconds, so 1 second = 1000 milliseconds

Using all this together you can get something like:

    #include <stdio.h>    
    #include <kipr/wombat.h>
    
    int main(){
    enable_servos();
    set_servos_position(0,1000);
    msleep(1000);
    ao();
    
    return 0;
    }
or

    #include <stdio.h>    
    #include <kipr/wombat.h>
    
    int main(){
    enable_servos();
    set_servos_position(0,1000);
    msleep(1000);
    disable_servos();
    
    return 0;
    }
