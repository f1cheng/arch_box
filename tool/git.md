
1. git merge branch_name(to current checked out branch: e.g: master)  --git reset --merge  
**Understand When & Why a Conflict Happens**  
Conflicts occurs when the same file was changed in contradictory ways.
The most common situation when it cannot do this is 
when the exact same lines were edited in that file.   
In that case, Git has no way of knowing 
what's correct - you'll have to look at the changes and decide how you want the file to finally look.