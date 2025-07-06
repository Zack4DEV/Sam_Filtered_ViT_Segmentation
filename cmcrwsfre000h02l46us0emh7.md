---
title: "Customized Cloud Usage — Why Using A devContainer.json ?"
datePublished: Sat Jul 06 2024 16:00:24 GMT+0000 (Coordinated Universal Time)
cuid: cmcrwsfre000h02l46us0emh7
slug: customized-cloud-usage-why-using-a-devcontainer-json-f48507f32b6c

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1751820657835/79d1984e-cb4d-4f11-a551-b00f5819d99b.jpeg)

Nowadays Cloud Images are familiary used .so Why Customize them ?

<! — — — — — Benefits — — — →  
Using a devContainer.json file in a CodeSpace or a similar setup is beneficial for several reasons, even when containers, pods, Docker images, and similar technologies are commonly used. Here’s why customizing them can be advantageous:

1-Consistency Across Development Environments:

\-Ensures all team members work in the same environment.  
\-Avoiding “works on my machine” issues by standardizing development setups.

2-Pre-configured Tools and Dependencies:

\-Includes all necessary tools, libraries, and dependencies in the container.  
\-Saves time on setting up environments for new team members or new machines.

3-Isolation of Development Environment:

\-Keeps the development environment isolated from the host machine.  
\-Prevents conflicts between different projects or different versions of tools.

4-Reproducibility:

\-Ensures that the same environment can be reproduced anywhere.  
\-Facilitates CI/CD processes by ensuring builds and tests run in the same environment as development.

5-Portability:

\-Enables developers to switch between different machines or environments seamlessly.  
\-Facilitates remote development setups like Github Codespaces.

6-Customization for Specific Needs:

\-Switch the environment to the specific needs of the project.  
\-Allows customization of IDE settings, extensions, and configurations.

<! — — — — — devContainer.json Components Key — — — →

1-Base Image:

\-Defines the Docker image to be used as the base environment.  
/\*\*  
“image”: “mcr.microsoft.com/vscode/devcontainers/base:0-alpine-3.12”  
\*/

2-Extensions:

\-Specifies VS Code extensions to be installed in the container.  
/\*\*  
“extensions”: \[  
 “ms-python.python”,  
 “dbaeumer.vscode-eslint”  
\]  
\*/

3-Settings:

\-Configures settings for the development environment.  
/\*\*  
“settings”: {  
 “terminal.integrated.shell.linux”: “/bin/bash”  
}  
\*/

4-Post-Create Commands:

\-Runs scripts or commands after the container is created.  
/\*\*  
“postCreateCommand”: “npm install”  
\*/

5-Mounts and Volumes:  
\-Specifies file mounts and volumes for the container.  
/\*\*  
“mounts”: \[  
 “source=/path/on/host,target=/path/in/container,type=bind”  
\]  
\*/  
<! — — — — — devContainer.json Example — — — →  
/\*\*  
{  
 “name”: “Node.js & TypeScript”,  
 “image”: “mcr.microsoft.com/vscode/devcontainers/typescript-node:0–12”,  
 “settings”: {  
 “terminal.integrated.shell.linux”: “/bin/bash”  
 },  
 “extensions”: \[  
 “dbaeumer.vscode-eslint”,  
 “esbenp.prettier-vscode”  
 \],  
 “postCreateCommand”: “npm install”,  
 “mounts”: \[  
 “source=/path/on/host,target=/path/in/container,type=bind”  
 \]  
}

\*/

Customizing development environments using devcontainer.json offers numerous advantages, including consistency, reproducibility, and ease of setup. It helps ensure that all developers have a unified and well-configured environment