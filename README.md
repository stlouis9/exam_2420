# exam_2420

## Q1
<p>sudo apt update</p>
<p>sudo apt upgrade</p>

## Q2
<p>/1 to get to -eq 1; del to delete 1, i to insert 0; esc to normal mode</p>
<p>/eco ; right arrow then insert an h; / to repeat cmd for the other 2 eco; esc to normal mode</p>
<p>/V to get to [f|v|k]; del then insert C; / to repeat cmd, replace the other V with C</p>
<p>/num to get to [numbs]; del then insert digit</p>
<p>:wq to save and quit</p>


![](/images/Q2.png)

## Q3
![](/images/q3boot.png)
![](/images/q3Json.png)
![](/images/q3priority.png)
![](/images/q3output.png)

## Q4
![](/images/q4useradd.png)
    
    #!/bin/bash

    printf "%s\n" "Regular users on the system are:" "$(grep -E [1-2][0-9]{3} /etc/passwd)" "" "Users currently logged in are:" "$(who | awk '{print $1}')" > /etc/motd
<p> I placed this script in /opt/find_users

## Q5

<p> I placed my service file in /etc/systemd/system</p>

![](/images/Q5service.png)


    [Unit]
    Description=Prints the regular users on the system as well as the users logged in

    [Service]
    Type=oneshot
    ExecStart=/opt/find_users/find_users

    [Install]
    WantedBy=multi-user.target


## Q6

![](/images/q6timer.png)

    [Unit]
    Description=Timer to start find_user script when the system starts

    [Timer]
    OnBootSec=1min
    OnUnitActiveSec=24h

    [Install]
    WantedBy=timers.target




