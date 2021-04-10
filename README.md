# asus-FX50J
Set fancontrol on asus FX50J, lubuntu   
  
I spent some time on this because my laptop is very noisy. I would buy a new one if money would not be a problem.   
anyway!  
  
The problem today is solved by using the following commads:

$sensors-detect     #and accept and add all the module  
$sensors            #use this command for trobleshooting and debugging to check the temperature of the sensors    
$pwmconfig          #create /etc/fancontrol via a guided process   
$sudo service fancontrol restart   
$sudo service fancontrol status    #if it outputs Error reading Fan value from /sys/class/hwmon/hwmon4/fan1_input   

if you see the above error:   
modify /etc/fancontrol and remove FCFANS line or comment it out   
example:  
FCFANS= hwmon4/pwm1=hwmon4/fan1_input       ----->      #FCFANS= hwmon4/pwm1=hwmon4/fan1_input  
