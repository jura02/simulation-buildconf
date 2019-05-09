## Quick Instructions
    First of all we need to Install MARS Environment:
    But Before That we need to update our manifest file.
    Just chage it to: "github: rock-core/compilerspeedup-package_set"
    in your manifest 
    And then perform the following steps without usings sudo (No Root file will be generated)
    Now Open The Terminal or Command Prompt and follow the following steps:
    apt-get update
    apt-get install -y build-essential ruby ruby-dev sudo wget
    
    wget http://rock-robotics.org/autoproj_bootstrap
    # If you have no write access to this repository: (If you don't have the SSH key)
    ruby autoproj_bootstrap git https://github.com/jura02/simulation-buildconf.git branch=envireMars
    # If you have write access: (It means if you have already generated the SSH key)
    ruby autoproj_bootstrap git git@github.com:jura02/simulation-buildconf.git branch=envireMars
    # Answer "whether C++11 should be enabled for Rock packages [false]" with "true" and the
    # other with default (just hit enter)
    
    
    #Sometimes you may face the problems like "No Access Rights to your repository".
    #Make sure you have corrected generated the SSH Key for both GitLab and GitHub
    
    
    
    
    source env.sh
    autoproj update
    #While checking out Models Evironment and Models Robots the program stucks.
    #To Complete the installation we have to install separately individually each robot/environment.
    #Let say  we need to install spacebot_cup robot.
    #Todo so use autoproj update models/environments/spacebot_cup
    #Similarly do for other robots like asguard_v4 etc
    #After doing this for all the robots Now move to the next step. 

    autoproj build             
    #This step will start building Everything.
    #Maybe you get an error "CMake fails to compile the simple test".
    #There are two possibilites 
    #1st install build essential using command sudo apt install build-essential
    #Still you are havig the same error then remove the ccache and install that again because we don't need ccache.
    #And during installation we had disabled the ccache but somehow he is still looking for ccache.
    #So by removig the ccache file and installing again it will remove this error.
    #After removing this error again send autoproj build command.
    #This time it will build everything.
    
    mars_app
    #To launch the mars application.
    #If you are facing problem launching the application.
    #Like its says command not found.
    #Then install mars_app separately using 
    autoproj build simulation/mars/app/
    
    
    #This will install the mars_app
    #Now by writing mars_app in terminal and after pressing enter it will open mars_app.
    #Here you can load different environments and robots of your chioce.
    
    
    

