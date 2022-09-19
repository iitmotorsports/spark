# Git Onboarding

Git is a free and open source software tool used for version control. 

## Create a GitHub Account

If you already have a GitHub account, please skip to [Apply for a Student Developer Pack](#apply-for-a-github-student-license).

[Create a GitHub Account](https://github.com/signup){ .md-button target=_blank }

!!! tip
    You will likely continue to use a GitHub account after graduation as a portfolio or in the industry. We recommend the use of a personal email and an appropriate username as this account will be public.

## Apply for a GitHub student license

As a university student, you get access to a ton of solid software resources. The GitHub Student Developer pack includes industry-standard tools for free. We use many of these tools in development for IIT Motorsports.

[Apply for a Student Developer Pack](https://education.github.com/pack){ .md-button target=_blank }

## Join the IIT Motorsports Organization

We work out of the [IIT Motorsports Organization](https://github.com/iitmotorsports) to keep our repositories organized. It's crucial that you have access to this organization in order to utilize elctrical and software resources.

**Ping the electrical team lead with your github username to get access to the organization.**

## Install Git
The Git software is used to interact with git repositories, such as those stored on GitHub.

### Installation

??? tip "**Recommended: ** Install Git using a package manager"
    A package manager makes it easy to install and update software packages with a single command. We recommend the use of the following package managers to install git:
    
    === "Chocolatey (Windows)"
        ```
        choco install git
        ```

    === "Scoop (Windows)"
        ```
        scoop install git
        ```

    === "Winget (Windows)"
        ```
        winget install -e --id Git.Git
        ```

    === "Brew (MacOS)"
        ```
        brew install git
        ```

    === "APT (Debian / Ubuntu)"
        ```
        sudo apt install git-all
        ```

    === "DNF (RHEL / CentOS)"
        ```
        sudo dnf install git-all
        ```

???+ note "Install Git manually"
    Navigate to [https://git-scm.com/downloads](https://git-scm.com/downloads) and follow the guide for your operating system.

### Configuration

Git needs to be configured to use your new GitHub account. Use the following steps to set your account username and email:

1. Open Git Bash (or equivelent terminal)
2. Set a git username:
```
git config --global user.name "Insert Name here"
```
3. Set a git email:
```
git config --global user.email "insert.email@here.com"
```