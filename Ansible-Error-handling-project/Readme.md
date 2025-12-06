--- This project explains about how to handle errors in ansible ---

- In general if any errors occur while excecuting tasks...it wont execute next task..anible will stop all remaining tasks ...to over come this issue using below modules

using - ignore_errors

   ---  if we use ignore_errors: yes ,  in any task ..even if that task failed..it wont effect remaining tasks, all the taks will execute as usual

using block-rescue-always

    ----if we use block and rescue module  , if any task in block module is failed..tasks in rescue mode getting started executing...if tall tasks in block module succed succesfully,
        then rescue module skips execting its tasks ,But in both cases if you use always module..tasks in that will always execute successfully

 Using Fail

  ---- This will instruct ansible to stop executing tasks...if it find condition matches


    
