
1. Unit Testing based on function's requirement, black box testing, as inside function, 
code style like if/while entries are different by programers. Specially for legacy code.
2. Testing the function which uses internal functions  
   mock the internal function and using macro to distinguish the production code and mock function code.
   - test.cpp file
   ```
    #define TESTING
   ```
   
   - production code
   ```
   #ifndef TESTING
   internal function
   #endif
   ```  
  
3. To skip the test, add the prefix(DISABLED_) for the test name:  
TEST_F(MarsTesting, DISABLED_turn_left__move_from_east_to_north)
   
   
  
