## Quick Instructions
    First of all we need to Install MARS Environment:
     
    We need to perform the following steps without usings sudo (To avoid generating files and folders owned by root)
    Now Open The Terminal or Command Prompt and follow the following steps step-by-step:
    
     
      1)Basic Initial Steps: 
      
          apt-get update
          apt-get install -y build-essential ruby ruby-dev sudo wget
          
      
    
      2)Download the autoproj bootstrap script:
      
          wget http://rock-robotics.org/autoproj_bootstrap
          
    
      3) Run the boostrap script and provide the repository address:
      
          ruby autoproj_bootstrap git git@github.com:jura02/simulation-buildconf.git branch=envireMars          
    #The user has to set up his/her keys in the github and gitlab account and use the correspondent command:
       
    #If the user has not generated the SSH key in his/her github and gitlab account then use the correspondent command: 
    
        ruby autoproj_bootstrap git https://github.com/jura02/simulation-buildconf.git branch=envireMars
        

    # Answer "whether C++11 should be enabled for Rock packages [false]" with "true" and the
    # other with default (just hit enter)
    
    #Sometimes you may face the problems like "No Access Rights to your repository".
    #Make sure you have corrected generated the SSH Key for both GitLab and GitHub
    
    #Similarly sometimes you don't have access to the specific Repository forexample:
    "No Access Rights to git@git.hb.dfki.de/models-environments" 
    #In this case you have to make a access request to the maintainer/owner of that Repository. 
  
    
      4)Source Your Environment: 
      
          source env.sh
      
      5)Checking Out Updates:
      
          autoproj update
          
      6)Check Your Installation:
      
          autoproj build               
    #This step will start building Everything.
    
      7)Open The Application: 
      
          mars_app          
    #To launch the mars application.
    #Here you can load different environments and robots of your chioce.
    
 ## TroubleShooting Section:
    1- PROGRAM STUCKS AFTER ENTERING " autoproj update "
    If you are on step NO:05 and your program got stuck: 
    #While checking out Models Environment and Models Robots.
    Now you have to install each robot/environment separately to overcome this problem.
    #Let say  we need to install spacebot_cup robot.
    #Todo so use:
    
        autoproj update models/environments/spacebot_cup
              
    #Similarly do same for all the other robots like asguard_v4 etc
    #After doing this for all the robots.
    #Now move to the next step. 
    
    2- AFTER ENTERING " autoproj build ".
    #Maybe you get an error "CMake fails to compile the simple test".
    There are two possibilites to overcome this problem. 
    #First of all install build essential using the correspondent command:
    
        sudo apt install build-essential
              
    #If you are still having the same error then remove the ccache because we don't need ccache using " apt-get ".
    #Because during installation we had disabled the ccache but somehow he is still looking for ccache.
    #So by removig the ccache file this error will be removed.
    

