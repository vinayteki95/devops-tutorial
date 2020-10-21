# devops-tutorial

    An implementation tutorial ( ever growing ) to understand and utilize the concepts including and not limiting to unit testing, integration testing, UAT, container orchestration, configuration management, CI/CD and Monitoring.

## Introduction

    Honestly, I've never written an article neither did I explicitly work as a Dev-Ops engineer ever.
    So why am I doing this?
        I often search for resources to understand the ins and outs of a new/confusing topic and start implementing these technologies or concepts that very day. And I often get them as far as they are simple and well established narrow concepts. But apparently that same strategy doesn't apply if you are trying to learn an entire culture of Dev-Ops in a day. And the most frustrating part of it all is, it's almost impossible to implement from ground zero when you have almost no expertice, no application in hand that you are constantly working on in a work environment where you slowly discover problems in different stages of development and deployment operations first and then make up your mind to solve it and then stumble upon the ideas of devops and realise that this is something you've been searching for and you learn them.
        Almost every Dev-Ops engineer story I've heard has been around the same narrative. I've been in that situation and year and a half ago but that was a start-up and I certainly was a newbie and everything grew very organically. I've never even had a name for the technological transformations that were taking place. We were building pipelines but the distinction is they were job-pipelines or one might even say data-pipelines because everything we did was machine learning and deep learning on tons of images. We went from the process of making things work to slowly discovering technologies that would work at a long term. Even then most of the times we chose to build these data pipelines on our one, obviously for multiple reasons which were relevant like cost and time optimisation.

        I don't want to bore you with the details of my mundane story any more, I'll get into the crux of it all in just a minute.

        I've worked with docker and kubernetes in my previous job positions and worked on GCP and AWS sufficiently enough to stumble and figure out solutions. This is exactly how I've learnt everything so far. I was in a situation and I had to figure out these different technologies so that I can solve the problem effiently. And being in a start up made me into a implement first and think later kind of guy mostly because of the pace at which we were working (I've nothing against it, I've learnt everthing so far from start ups all along). So I've always lacked the academic knowledge that goes under all these technologies, I have a good intuition to formulate a wage understanding of these technologies but obviously one would miss the true details.

        I decided to be a Dev-Ops engineer ( ignore why for now because it isn't relevant right now ).
        I searched for tutorials and youtube videos to learn devops but either they were an eagles eye view of the whole concept of devops and ci/cd which are not always comprehensive of all the parts of it or they are long courses with specific technologies a little slow and expensive.

        That's when I've realised there is a need for this content. People who wants to learn the whole idea of devops and see how it plays out in real world while learning the technologies to use and to have a coherent mental model to think in terms of devops is just not available sadly.

        So I'm going to start this article or may be a series of articles where I can learn everything about devops from ground zero which is where I am currently.

        Note: I might not be spending much time on explaining literally all the features of a technology that comes up because what do I know. But the important thing is I'm going to document every piece of the technology that I use in building this large scale devops pipeline / project so that you can see how one might go about discovering technologies and thier features.

        Note2: I'm going to adopt an iterative learning methodology here. I'm going to start of by building a very minial application with almost no devops intelligence in the application and slowly grow it into a robust system by introducing discovered / learned problems in the current system and treating with some devops related technologies so that we understand the use case of all of these technolgies.

## Iteration 1

### The application

    I'm going to take a stupid application to kick us off as quickly as possible and slowly introduce tougher and more varied applications as we go along.

#### Setting up environment to work

    Environment: Ubuntu 20.04

```BASH
    # Install basic packages
    sudo apt install python3-pip
    sudo apt install python3-venv  # let's not be any more stupid than we are

    # Setup virtual environment
    cd devops-tutorial/applications/ microservice
    python3 -m venv virtualenv

    # Activate environment
    source virtualenv/bin/activate
    # To deactivate just run:::: > deactive

    # pip and pip3 in this environment are same. Better check this
    pip --version
    pip3 --version
    # the results are the same from both the commands above. Awesome.

    # Install flask to run a simple http server - microservice in our case
    pip install flask   # make sure your virtualenv is activated
```

#### The Application

    The application is pretty simple. I did not focus much on the complexity and structure of the application for now as this is only a first iteration. We'll make the application more sofisticated over time.

    The application has two main goals
        1. respond to a number by factorial of it
        2. respond to a number by the total number of prime factors
    
    Forget about the logic for now, these are simple algorithms which you can find explanations to virtually on any coding platform.

    We'll also make a distinct of unit tests and integration tests in an oversimplified fashion for now.

    [TODO] Elaborate on the details of application

#### Unit Testing

    We've written some unit tests for the routes and the functions we have in the repository.
    Currently I've setup a simple git-hook to run these tests locally first before making a commit. We'll also replicate the same unit tests and also add some integration tests in a CI/CD pipeline later because these git-hooks are local objects. They are not shared to the remote repository and also these hooks can easily by passed with commands like `git commit -m "random commit message" -n `. The '-n' option takes care of this.

    There is a second option called the server-side hooks. This is not possible on shared github because obviously github would not want to let it's users run random scripts on thier servers.

    [TODO] Elaborate on unit testing and integration testing and how these test scripts are written