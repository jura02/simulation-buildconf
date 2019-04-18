## Quick Instructions (also works for ubuntu:latest docker container from dockerhub.com):
    First of all we need to Install MARS Environment:
    So Open The Terminal or Command Prompt and follow the following steps:
    apt-get update
    apt-get install -y build-essential ruby ruby-dev sudo wget
    
    wget http://rock-robotics.org/autoproj_bootstrap
    # If you have no write access to this repository:
    ruby autoproj_bootstrap git https://github.com/jura02/simulation-buildconf.git branch=envireMars
    # If you have write access:
    ruby autoproj_bootstrap git git@github.com:jura02/simulation-buildconf.git branch=envireMars
    # Answer "whether C++11 should be enabled for Rock packages [false]" with "true" and the
    # other with default (just hit enter)
    
    source env.sh
    autoproj update
    autoproj build

