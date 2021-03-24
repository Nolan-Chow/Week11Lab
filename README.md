# Week11Lab

1) To clone the this repository onto your Linux machine, run the following command:
    "git clone https://github.com/Nolan-Chow/Week11Lab.git"
   Tip: after running the command above, use the "ls" command to confirm that a folder containing this repository's contents has appeared

2) To access the contents of the repository, run the following command:
    "cd Week11Lab"
    
3) Access wttr_script.service to work on your current machine using the following command:
    "vim wttr_script.service"
    
    After the above command has been ran, find the line containing "ExecStart" and perform the following changes:
        ExecStart=/home/vagrant/week11/wttr_script -> ExecStart=/home/<insert the path to your home directory>/Week11Lab/wttr_script
  
    Then find the line containing "WorkingDirectory" and perform the following changes:
        WorkingDirectory=/home/vagrant/week11 -> WorkingDirectory=/home/<insert the path to your home directory>/Week11Lab
  
    Finally, save the file
   
4) Move the service and timer files to the /etc/systemd/sytem folder using the following commands:
    "mv wttr_script.service /etc/systemd/system" and "mv wttr_script.timer /etc/systemd/system"
    
5) Enable the two scripts using the following command:
    "sudo systemctl enable wttr_script.service" and "sudo systemctl enable wttr_script.timer"
    
6) Lastly, reload the daemon list using the following command:
    "sudo systemctl daemon-reload"
    
After the six steps have been completed, a file containing the weather should appear in the Week11Lab folder on bootup. This file, called wttr, will update hourly displaying the weather accurate to the hour.
