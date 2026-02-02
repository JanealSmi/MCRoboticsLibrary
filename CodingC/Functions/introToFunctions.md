Functions act as a useful and necessary tool to learn, not only to make coding easier to write, but also to read.
Hard coding, while reliable in some part, is difficult and makes writing the repeptitive lines of code simpler.

To write functions we must know how to both write and "call" them, using:
  `void "name"(int variables){ }
  "name"(variable #);`

`Void` acts as a "return type" telling the code it does not have to return information in the function, other return types like `int` and `float` can return information, however will not be used often for basic functions like motors or servo functions.

When writing a function for these actions we must choose a `name` for the function in order to call it later on, for movement we can use drive as an example.

`int variables` specifies the actions within the function that will be input when called. 

We can then write a function to move the motors however it is important to note that functions themselves are not written in the `int main(){}` and are place above it after the `includes`

For example:

    #include <stdio.h>  
    #include <kipr/wombat.h>
    
    //functions go here \/
    
    void drive(int power,int time){ //<-- determine what the independent and dependent variables are
    // Write as normal with required variable names that would change like time and power or for servos degree
      motor(0,power);
      motor(3,power);
      msleep(time);
    }
    
    int main(){
    //Functions do not go here!
    return 0;
    }

While functions go above the int main, they are still acknowledged but do not allow the bot to do the actions specified in them unless called

To call a function is much simpler, after writing a function and placing it above the `int main` you may call that function as much as you want using its `name` and inputting all the dependent variables that would need to be specified by the coder.

This would look like this:

    #include <stdio.h>  
    #include <kipr/wombat.h>
    
    void drive(int power, int time){
      motor(0,power);
      motor(3,power);
      msleep(time);
    }
    
    int main(){
    drive(100,5000);
    
    return 0;
    }

Here we see the robot would drive for 5 seconds at 100 power in both wheels, and this is done only with one line of code in the `int main()`

The same can be done for servos and just about any function needed for these two parts like turning or even specified motions using mechano wheels,

    #include <stdio.h>  
    #include <kipr/wombat.h>
    
    void claw(int degrees){  <-- named claw to control the open or closed position
      enable_servos();
      set_servo_position(0, degrees); <-- servo port is constant while the degree/position can be changed
      msleep(100); <-- time in servos is pretty irrelevant but required to work
      disable_servos(); <-- turning off to conserve power
    }
    
    int main(){
    claw(2000); <-- sets the claw to the position at 2000
    
    return 0;
    }
