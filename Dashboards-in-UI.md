# Introduction
To provide overview about the server, FOSSology provides following dashboards in the UI.

![Dashboard menu](https://user-images.githubusercontent.com/18077542/195010556-b2692787-eb67-4b9a-bb6a-dbf2a170781f.png)

### All jobs
The "Status - all server jobs" dashboard is accessible for all users with at least read permission. It provides following information:

![All jobs dashboard](https://user-images.githubusercontent.com/18077542/195010804-4c1eb22b-bfe3-49e6-90f7-c592f854e600.png)

1. The status of scheduler
    - Users can check the scheduler here.
    - The status will show "Running" if the scheduler daemon is running, otherwise status will be "Stopped" and the scheduler needs to be restarted.
2. Running status of all agents
    - The following table shows the running status of all agents in the server.
    - The column "Agent name" displays the agent for which the stats are pulled.
    - The column "Running" displays the count of instances of the agent running/scanning.
    - The column "Pending" displays the count of instances of the agent which are waiting to be scheduled or paused.
    - The column "ETA" displays the estimated time to finish the running agents.

### Overview
The "Overview Dashboard" is accessible only for administrators as it provides system information.

![Overview Dashboard](https://user-images.githubusercontent.com/18077542/195012812-2b0818cc-9537-4ca6-8671-ad86d1dc96bd.png)

The dashboard provides following tables:
1. Database contents:
    - It displays useful information about critical tables.
    - Keeping an eye on "Last Analyze" can provide helpful information if server response is slow.
    - The [maintenance agent](https://github.com/fossology/fossology/wiki/Maintenance-Agent) should be used to Vacuum/Analyze the tables at regular intervals.
2. Database Metrics:
    - The table shows metrics of Postgres database.
    - It includes the total size of database, version of database server and active connections to the database.
3. Active FOSSology queries:
    - The table shows active queries/connections open by FOSSology on the database.
    - In case a query is stuck, it can be identified from here and [killed from database server](https://www.postgresql.org/docs/current/functions-admin.html#FUNCTIONS-ADMIN-SIGNAL).
4. PHP Info:
    - The table shows version information of PHP running the frontend as well as list of loaded extensions.
5. Disk Space:
    - The table provides list of mounted file systems and their usage.
    - If the usage on any mounted FS goes above 90%, it gets highlighted in red color.
6. Note:
    - At the bottom of page, other helpful locations are displayed.

### Statistics Dashboard
The "Statistics Dashboard" is designed to provide statistics about the FOSSology server. It currently displays the total count of scheduling for each agent.

![Statistics Dashboard](https://user-images.githubusercontent.com/18077542/195014865-2ed57a9e-f8ef-4373-a327-71a970861793.png)