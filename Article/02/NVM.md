NvRam Manager provides many services for NvM user , and I will focus on the services commonly used :  
- Read block
- Write block
- Restore defaults
- Invalidate Nv Block
- Erase Block
- Read All
- Write All

There are 3 executors running in NvM layer to process the service request from NvM user:<br />
- Task
- Main Job
- Sub Job <br />

And they are scheduled in cascade:<br />
![](Relationship_between_Task_MainJob_SubJob.png)
  
## NvM - Task 
NvM user requests service by push service to a queue.
Task takes responsibility to pop service from queue and starts the job to process the service request  .<br />
![Main Task State](NVM_State_Diagram-MainTaskState.png)<br />
If the request is to process only one block ，the **Normal Job** will be executed ,otherwise the **Multi block job** will be executed.

## NvM - Job 
### Normal Priority Job <br />
- Read Block<br />
![](NVM_State_Diagram-READ_BLOCK.png) <br />
- Write Block <br />
![](NVM_State_Diagram-WRITE_BLOCK.png) <br />
- Restore Default <br />
![](NVM_State_Diagram-RESTORE_DEFAULTS.png)<br />
- Invalidate Nv Block <br />
![](NVM_State_Diagram-INVALIDATE_NV_BLOCK.png) <br />
- Erase Block
![](NVM_State_Diagram-ERASE_BLOCK.png) <br />

### Multi block job <br />
- Read All <br />
 ![](NVM_State_Diagram-READ_ALL.png) <br />

- Write All  <br />
![](NVM_State_Diagram-WRITE_ALL.png) <br />

