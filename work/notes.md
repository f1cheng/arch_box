
## Activator:
0 main thread / listener thread /worker thread  
1 main thread do all work, and then goes to wait state  
2 listener thread if listener thread having excepiton, it will send mutex signal to main thread  

listener thread--> listen socket/accept=receive socket-->  
-->put msg to one task --> add task to thread pool(tasks threads)->  
-->signal-->  
thread in run--> receive condition-> execute()  
(RequestTask::execute() real action here, main execute after msg from ldap server)--->  
--> _eventReceiver->deleteRequest.....  
                    AddRequest.....  
                    
                    
## Validator Activator executing order
Validator register to master ldap  
Activator register to local ldap  
And during the commit the transaction, it first check master's behavior(to slave and to validator), then local's.  
So first Validator firstly be called ,then Activator.  

For Slave only, it will notify to slaves to store it only.  and then end_tx will call commit, 
but it will skip to store if it's already committed.  

When activation failure, it will rollback, but as the data was already commited/stored.  
And our rollback means that for transaction subscriber rollback, which is the inform flag, but not the real data from DB rollback.  


## docker
docker start c0b  
docker exec -it c0b /bin/bash  