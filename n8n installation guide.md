<img width="2880" height="1800" alt="Screenshot (470)" src="https://github.com/user-attachments/assets/e9f9256d-001e-4b9f-9d78-0de08fca59eb" />
Follow through a step by step process of installing n8n for AI automation.

## Pre-requisite
Before we proceed, the following are pre-requisite required.
1. Kali Linux Virtual machine. (Please note this can be done on any other host machine.)
2. Docker desktop installed. To view how I installed Docker desktop on my Kali [view here](https://youtu.be/LefBKOtGZwo "link to video demo").

## Installation

Step 1: Confirm Docker is successfully installed on Machine
`docker -v`

Step 2: confirm status of Docker Daemon
`systemctl status docker`
this must show active running, else you will have to run
`systemctl enable docker`
`systemctl start docker`

Step 3: Pull n8n Image
``docker.n8n.io/n8nio/n8n:latest``

step4: Verify Image Pulled successfully
``docker images``

Step 5: Create persistent volume for data storage
``docker volume create n8n_data``

Step 6: Run n8n Container
This references the image pulled and the volume created

``sudo docker run -d --name n8n -p 5678:5678 -v n8n_data:/home/node/.n8n docker.n8n.io/n8nio/n8n:latest``

Step 7: verify Docker container is running
``docker ps``

For a video demo of these process, watch my walkthrough [view here](https://youtu.be/LefBKOtGZwo "link to video demo").

Step 8: Launch n8n dashboard on your localhost via the browser
From browser, type 
``localhost:5878``

Step 9: Set up you n8n profile if you haven't yet done so previously
