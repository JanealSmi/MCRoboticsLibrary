Turning using motors is something any bot needs to know how to do, however there are two methods of turning, a wide turn and a pivot turn.

The code we use when turning is the same as when driving forward (https://github.com/JanealSmi/MCRoboticsLibrary/blob/34aae890eac1349688f4ee1cd80f8eef8ca82ba4/CodingC/Motors/DrivingForward.md)

When driving we usually set both wheels to the same power, when turning the wheel must have a difference in power, one having less than the other in order to create a turn for example:

    int main(0){

    motor(0,50);
    motor(3,100);
    
    msleep(5000);

    return 0;
    }

Here the bot will turn in the direction motor 0 is on because the power on that side is less than the power output of motor 3

This creates a wide turn that shifts the bot forward out of it's position.
However a piviot turn does not shift the bot, keeping it in the same spot as it turns.

This is because on power is negative while the other is positive. This allows the bot to turn in place versus a wide turn, for example:

    int main(0){

    motor(0,-100);
    motor(3,100);

    msleep(5000);
    return 0;
    }

A pivot turn is great for exact or precise turns that are less likely to interfere with other things or the alignment of the bot.


