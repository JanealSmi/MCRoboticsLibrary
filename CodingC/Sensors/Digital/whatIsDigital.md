Digital acts as a condition with the only datd it can receive being 1 or 0 (true or false)

Sensors like a button have only two states/values, is it or is it not pressed

for example using and if statement we can create a condition where a button being pressed will run a line of code:]

    int main(0){
    if (digital(0) == 1){
    
    motor(0,100);
    motor(3,100);
    
    msleep(5000);
    return 0;
    }
    
This allows for things like initiating code as show or safeguards to get out of a loop (while and if loops)
Sensors like the bump, or even the built in buttons on the IED and bot can be used!
