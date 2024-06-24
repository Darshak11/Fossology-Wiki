# 1. Status - all server jobs

![image](https://github.com/fossology/fossology/assets/9692764/45617229-50d7-475e-94ca-a0e98d342684)

This status page gives you the information about the load of the system in color coding (green, yellow and red).
It tells you also if the scheduler is running and which agents are running or pending.

# 2. Folder and Upload dashboard

![image](https://github.com/fossology/fossology/assets/9692764/4bc465fe-f268-4664-9c39-52b9b074b434)

In this dashboard you can see all uploads with the respective size of the upload. It is also possible to search for an upload or to sort it.
If the clearing management information is entered, also the clearing duration is calculated.

In addition the size of a specific folder shown.

# 3. Overview Dashboard

![overview-dashboard](https://github.com/fossology/fossology/assets/9692764/7cab63f0-e9f2-46e7-b2eb-acea7c5b9b70)

### 3.1 Database Contents

all numbers are taken on a specific date and time: last Analyze
?? what means 'last vacuum?'??

* Users: Number of users in the system
* Uploads: Number of uploads
* Unique files referenced in repository: ?? what is the difference to the individual files?? unique, because there are duplicate files??
* Individual files: all files of all uploads (with license information, or really all files??)
* Discovered Licenses: all discovered licenses (by the agents or the users???) in all files in the system.
* Copyrights/URLs/Emails: all findings of the copyright agent (of by the user??)

### 3.2 Active FOSSology Queries
???

### 3.3 Disk Space
Disk space available for different filesystems, the usage, availability and percentage of usage is shown.
If the disk space is over the threshold of ??? percent, there is a color coding in red.
?? are these always the some filesystem names?

### 3.4 Database Metrics
* FOSSology DB size: Size of the overall DB
* Postgres Version
* Active DB connections: ?? to where??

### 3.5 PHP Info
* PHP Version
* loaded extensions

# 4. Statistics
Overall statistics of all agents in FOSSology and the number of jobs run by the agent.
?? when is the reference point, when does it start?
?? Why are there some agents mentioned several times?
?? What does it mean if there is just 'null'

![image](https://github.com/fossology/fossology/assets/9692764/c5aa0115-2897-4757-ab12-cf633244030b)

![image](https://github.com/fossology/fossology/assets/9692764/3794bbde-c832-45a7-97e4-ff2164d46330)

