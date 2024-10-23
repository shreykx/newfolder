# Setting up Twenty (STEPS + IMAGES + COMMON MISTAKES)

> **Alryy! Let's do it.**


## Useful URLs
- Repo link: **https://github.com/twentyhq/twenty** (Contains code+some more docs)
- For the official guide refer: **https://twenty.com/developers/local-setup** (Refer)
- Twenty Discord invites: **https://discord.com/invite/cx5n4Jzs57** (Ask queries related to setup here)
- Twenty Demo: **https://demo.twenty.com/** (test out twenty's use-case in a crisp manner)

## Before we begin
### Overview
This document serves as a resource for setting up your **Big Twenty Localhost Project**. It provides the essential steps but may not cover every aspect you might want to explore. This guide is part of the **oss.gg** contribution for **Hacktoberfest**.
### Prerequisites

- **Git**: Ensure Git is installed and configured on your local machine.  
  [Download Git](https://git-scm.com/downloads)

- **Node.js**: Install the latest LTS version of Node.js.  
  [Download Node.js](https://nodejs.org/en/download/)

- **Package Manager**: npm or Yarn should be available.  
  [npm Documentation](https://docs.npmjs.com/) | [Yarn Documentation](https://yarnpkg.com/getting-started)

- **Code Editor**: A code editor like VSCode.  
  [Download VSCode](https://code.visualstudio.com/)

- **Browser**: A modern web browser (e.g., Chrome, Firefox).  
  [Download Chrome](https://www.google.com/chrome/) | [Download Firefox](https://www.mozilla.org/firefox/)

- **Terminal**: Access to a terminal or command line tool.  
  [Using the Terminal on Windows](https://docs.microsoft.com/en-us/windows/terminal/) | [Mac Terminal Guide](https://support.apple.com/guide/terminal/welcome/mac)

- **Basic Knowledge**: Understanding of Git, CLI commands, and JavaScript.  
  [Git Documentation](https://git-scm.com/doc) | [JavaScript Guide](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)


### Assumptions

- **Familiarity with Git**: You know how to clone, commit, and push code.  
  [Git Basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics](https://git-scm.com/doc))
![image](https://github.com/user-attachments/assets/1df44e4c-b88f-4e8c-8590-1f0666cdfde3)

- **Basic Command Line Skills**: You can navigate directories and run commands in a terminal.  
  [Command Line Crash Course](https://learnpythonthehardway.org/book/appendixa.html)

- **Node.js and npm Knowledge**: You understand how to install and manage packages.  
  [npm Getting Started Guide](https://docs.npmjs.com/getting-started)
  ![image](https://github.com/user-attachments/assets/608e6ab6-7b3a-49a3-8b8f-e06934e0891f)
  
- **Understanding of JavaScript**: Since most of twenty is written in **Typescript (Javascript with types)**.  
  [JavaScript Basics](https://developer.mozilla.org/en-US/docs/Web/JavaScript/A_re-introduction_to_JavaScript)

### Estimated time
A streamlined workflow of this type could take **~10 minutes** for the first time.

## Steps

### Clone the official **[Twenty Github Repo](https://github.com/twentyhq/twenty/)**.
Here's what the repo looks like as per **22-10-2024**
![image](https://github.com/user-attachments/assets/e1b179a7-397d-4938-9046-699bc02bcb89)

We'll be using **SSH** for all our **use-cases**, however, as an alternative you may use **HTTPS** (not recommended), which may require **external steps**.

To clone the repo all you need to do is follow these clicks:
![image](https://github.com/user-attachments/assets/86bbab9f-cefa-4291-bcb4-f38f546285c6)
Yay! Here are the final steps to get **TwentyCRM** in your local setup...
![image](https://github.com/user-attachments/assets/80c5633e-a4a3-4265-930e-56bc65f19c8e)
In the above steps, we've navigated to the repositories where you want the Twenty project folder to be created. It does not mean you're going to get the files in that folder, there will be a separate folder created.

And,

- Run : `git clone git@github.com:twentyhq/twenty.git`
![image](https://github.com/user-attachments/assets/b1bf2959-27c6-4401-8955-49d0df719c31)

- Run : `cd twenty`, this will take you to the project's root (the parentest folder present in the setup)
![image](https://github.com/user-attachments/assets/4f68cbba-09e3-4c76-8a60-13ee022b67eb)

If you see the circled name `twenty` like this in your terminal, Congratulations! You have the base setup 🎉.
> If you're using any terminal other than the `Win-11` one, you might have a different look but the basics remain the same.

Confirm the files with a simple command - `dir` on **Windows**, `ls` on **Mac/Linux**
![image](https://github.com/user-attachments/assets/68fe19c7-6df8-4f46-924c-c055bc279b54)

