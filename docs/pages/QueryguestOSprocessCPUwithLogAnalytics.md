## Query guest OS process CPU with Log Analytics

1. Log into Azure portal
2. Open your Log Analytics Space (create one if you do not have). [Add agent performance counter](https://docs.microsoft.com/en-us/azure/azure-monitor/agents/data-sources-performance-counters)
    - Click Agents configuration
    - Click Linux performance counters
    - Click Add performance counter. 
    - Select Pct User Time
    - Click Apply
    ![image](../images/AgentConfiguration.jpg)
3. Connect VM into the Log Analytics Workspace
    a. Click **Virtual machines**
    b. Select the VM you want to monitor, for example: cent78-1
    c. Click Connect
    ![image](../images/ConnectWorkspace.jpg)
4. Simulate high CPU in VM
    a. SSH into VM
    b. Load stress
    `[leon@cent78-1 ~]$ sudo yum install stress -y`
    `[leon@cent78-1 ~]$ stress –cpu 1`
    c. Open another SSH session to check CPU consumption
    `[leon@cent78-1 ~]$ top`
    ![image](../images/StressCPU.jpg)
5. Query CPU consumption
    a. Open VM in Azure portal
    b. Click Logs
    c. Query the CPU consumption
    ![image](../images/QueryCPUConsumption.jpg)



