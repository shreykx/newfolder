# Setting up Twenty (STEPS + IMAGES + COMMON MISTAKES)

> **Alryy! Let's do it.**


## Useful URLs
- Repo link: **https://github.com/twentyhq/twenty** (Contains code+some more docs)
- For the official guide refer: **https://twenty.com/developers/local-setup** (Refer)
- Self-hosting: **https://twenty.com/developers/section/self-hosting** (Refer)
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
- **Docker**: Containerizing application.
  [Docker](https://www.docker.com/)
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
  
- **Following skills** - Pay attention to the details.
### Estimated time
A streamlined workflow of this type could take **~10 minutes** for the first time.

## Steps

### 1) Clone the official **[Twenty Github Repo](https://github.com/twentyhq/twenty/)**.
Here's what the repo looks like as per **22-10-2024**
![image](https://github.com/user-attachments/assets/e1b179a7-397d-4938-9046-699bc02bcb89)

We'll be using **SSH** for all our **use-cases**, however, as an alternative you may use **HTTPS** (not recommended), which may require **external steps**.

To clone the repo all you need to do is follow these clicks:
![image](https://github.com/user-attachments/assets/86bbab9f-cefa-4291-bcb4-f38f546285c6)
Yay! Here are the final steps to get **TwentyCRM** in your local setup...
![image](https://github.com/user-attachments/assets/80c5633e-a4a3-4265-930e-56bc65f19c8e)
In the above steps, we've navigated to the repositories where you want the Twenty project folder to be created. It does not mean you're going to get the files in that folder, there will be a separate folder created.

And,

- Run: `git clone git@github.com:twentyhq/twenty.git`
![image](https://github.com/user-attachments/assets/b1bf2959-27c6-4401-8955-49d0df719c31)
It took me approx. 10 seconds to get the whole clone ready, time may vary as per your machine's specs, so don't panic.

- Run: `cd twenty`, this will take you to the project's root (the parentest folder present in the setup)
![image](https://github.com/user-attachments/assets/4f68cbba-09e3-4c76-8a60-13ee022b67eb)

If you see the circled name `twenty` like this in your terminal, Congratulations! You have the base setup 🎉.
> If you're using any terminal other than the `Win-11` one, you might have a different look but the basics remain the same.

Confirm the files with a simple command - `dir` on **Windows**, `ls` on **Mac/Linux**
![image](https://github.com/user-attachments/assets/68fe19c7-6df8-4f46-924c-c055bc279b54)

### 2) Open up the project in your favorite Editor.
You can open your project in your favorite editor. I'm a Cursor user, so I'll type the command `cursor .` in the `root dir` to open it.

![image](https://github.com/user-attachments/assets/99a8917b-08a7-468e-92c7-522343281c3d)
Here's how it looks on my machine!

### 3) Setting Postgres inside WSL (for Windows machines, OPTIONAL)
This is going to set up Postgres from scratch in your WSL, however, an easier way of just retrieving the **DOCKER** image locally is better for many users.

Well, just giving you an overview, WSL stands for `Windows Subsystem for Linux`, making a Linux environment, in your Windows machine! We use it for ease of development as Linux is the default system developers could rely on. If you're on Mac, the steps for setting this up would vary. Linux users, stay chill, you need not do anything, just start with the commands.
I opened the Cursor-integrated terminal and WSLed via it.
![image](https://github.com/user-attachments/assets/cf53a72a-480f-4e87-b7f6-e84540aa6ce8)

**Resource : [Setup Postgres on WSL](https://harshityadav95.medium.com/postgresql-in-windows-subsystem-for-linux-wsl-6dc751ac1ff3)**

![image](https://github.com/user-attachments/assets/42f0d14a-bf1e-4a04-bb5b-51107b2fa4c9)
Postgres installed.

### 4) Twenty's database localized!
Just follow the commands inside WSL after you set Postgres-
- `psql postgres -c "CREATE DATABASE \"default\";" -c "CREATE DATABASE test;" -c "CREATE USER twenty PASSWORD 'twenty';" -c "ALTER ROLE twenty superuser;"` (If you installed Postgres yourself)
  or 
- `docker run \
    --name twenty_postgres \
    -e POSTGRES_USER=postgres \
    -e POSTGRES_PASSWORD=postgres \
    -e POSTGRES_DB=default \
    -v twenty_db_data:/var/lib/postgresql/data \
    -p 5432:5432 \
    twentycrm/twenty-postgres:latest` (If you prefer going on with Docker)

  I would just prefer going on with **Docker** as it makes the whole process a lot more efficient whilst reducing steps.
  **Resource : [Official Docker guide to set it up on Ubuntu, is the same for WSL 2](https://docs.docker.com/engine/install/ubuntu/)**
  > Pro tip: If docker is installed correctly, you may use this command to check with a demo pull!
  > ![image](https://github.com/user-attachments/assets/7716767e-54e5-4053-8205-bc0544c8e35d)

If you're confused about what we did with the above steps, in summary, the Twenty team did a great job setting us up a **snapshot** of the kind of Postgres database setup they would like their open-source contributors to have, the **snapshot** is all we're copying through Docker, in fact copying **snapshots** is mostly what Docker does.

What setting up **Postgres** for **20** would look like on WSL 2 using Docker? 
![image](https://github.com/user-attachments/assets/57143811-af6a-4b6b-be01-c13931aa6cf4)


### 5) Setting up Redis (for Twenty, using Docker)

Redis is a [caching database](https://en.wikipedia.org/wiki/Database_caching).

Run
- `docker run -d --name my-redis-stack -p 6379:6379 redis/redis-stack-server:latest` to pull the Redis image from twenty locally.
![image](https://github.com/user-attachments/assets/5441d69e-9b7b-4f1d-ba15-77d017660d62)

### 6) Environment Variables

Environment variables here would contain some important strings- may it be keys, API endpoints, etc. They're mostly stored inside a common file, often named `.env`
We'll also set our `.env` file so our app is fully functional.

#### Steps to setup env vars:

- `touch .env` on WSL/Linux would create a `.env` file
- copy all the parameters you need for a complete environment from the `.env.example` file present at both the `twenty-front/` (for frontend) and `twenty-server` (for backend) directory. You can do this manually or just use the command - `cp ./packages/twenty-front/.env.example ./packages/twenty-front/.env &&
cp ./packages/twenty-server/.env.example ./packages/twenty-server/.env` in a WSL/Linux machine.
- On WSL, since you won't have direct control over your Linux terminal, you could simply replace `cp` with `cat` and then manually do the next step.
- paste everything in `.env`

or

- `cat ./packages/twenty-front/.env.example ./packages/twenty-front/.env ./packages/twenty-server/.env.example ./packages/twenty-server/.env > .env`

![image](https://github.com/user-attachments/assets/ebe16f47-120b-4b0d-9471-52a8fbbaedd3)

### 7) Setting Dependencies

Dependencies are basically what all packages this setup would require. Docker manages this all but since we're doing this whole setup manually, we would be using `nvm` or **Node Version Manager**.

#### What does `nvm` do?
It has the version of node (or more) that we've to use for our local setup in the `.nvmrc` file.
Use these commands to setup Node to its correct version using the `.nvmrc` file.
![image](https://github.com/user-attachments/assets/359a68f2-fc5f-4d15-8225-725b919d687f)

Yarn is a package manager for node, run `yarn install` as the final step.

  
### Run Application

- `npx nx database:reset twenty-server` ![image](https://github.com/user-attachments/assets/63a00de7-f4b7-4ff4-9fd5-621771704108)
- `npx nx start twenty-server`
- `npx nx start twenty-front`
- and finally `npx nx start`

Congratulations 🎉 Your **Twenty** setup is ready!


### FAQs (& handling issues)


- #### Issue - ![image](https://github.com/user-attachments/assets/9efcd5a0-d42b-4c10-9f5d-da7954c41ed4)
Try running `yarn install`
![image](https://github.com/user-attachments/assets/b3cc4297-dba3-437f-8d9c-1ebaded8ca6b)
![image](https://github.com/user-attachments/assets/78b734e9-affa-4548-a258-4d78ccad07e7)

- #### Should I use `yarn` or `npm`?

Use `yarn`, using npm here means **re-inventing the wheel**. 

- #### Can TwentyCRM see my setup?

No. It's all on your personal machine



