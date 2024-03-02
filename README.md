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
- Choose an Amazon Machine Image (AMI), preferably Ubuntu.
- Select an instance type.
- Configure instance details.
- Add storage.
- Configure security groups (ensure that port 25 for SMTP is open).
- Review and launch the instance.
