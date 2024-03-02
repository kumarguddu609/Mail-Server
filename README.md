# Mail Server Project

This project is a simple mail server implemented using Node.js and the `smtp-server` Node package. It allows you to send and receive emails using SMTP protocol.

## Features

- Send and receive emails

## Requirements

- Node.js
- npm

## Installation

1. Clone the repository:

```bash
git clone https://github.com/kumarguddu609/Mail-Server.git
```

2. Install dependencies

```bash
cd mail-server
npm install
```

## AWS EC2 Deployment

1. Sign in to AWS Console: Sign in to your AWS account.

2. Launch an Instance:

- Go to EC2 Dashboard.
  ![alt text](/resources/EC2.png)
- Click on "Launch Instance".
  ![alt text](/resources/launch.png)
- Choose Name of Server and an Amazon Machine Image (AMI), preferably Ubuntu Free tier.
  ![alt text](/resources/1.mp4)
- Select an instance type.
  t2.micro Free tier
  ![alt text](/resources/instance.png)
- Configure instance details and create a new key-pair.
  ![alt text](/resources/2.mp4)
- Click Launch Instances.
- Go to EC2 Dashboard and see instances.
- Configure security groups (ensure that port 25 for SMTP is open).
  ![alt text](/resources/3.mp4)
- Review, save and start connection.
  ![alt text](/resources/4.mp4)

3. Install Node.js and npm:

- Install curl:

```bash
sudo apt install curl
```

- Retrieve installation script using curl

```bash
curl -sL https://deb.nodesource.com/setup_18.x -o /tmp/nodesource_setup.sh
```

- Run the installation script

```bash
sudo bash /tmp/nodesource_setup.sh
```

- Install NodeJs

```bash
sudo apt install nodejs
```

- check installation:

```bash
node -v
```
