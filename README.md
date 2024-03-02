# Mail Server Project

This project is a simple mail server implemented using Node.js and the `smtp-server` Node package. It allows you to send and receive emails using SMTP protocol.

## Features

- Send and receive emails

## Requirements

- Node.js
- npm

## Installation

1. **Clone the repository:**

```bash
git clone https://github.com/kumarguddu609/Mail-Server.git
```

2. **Install dependencies:**

```bash
cd mail-server
npm install
```

## AWS EC2 Deployment

1. **Sign in to AWS Console: Sign in to your AWS account.**

2. **Launch an Instance:**

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

3. **Install Node.js and npm:**

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

4. **Clone the repository:**

```bash
git clone https://github.com/kumarguddu609/Mail-Server.git
```

5. **Install packages on Ubuntu Machine:**

```bash
cd Mail-Server
npm install
```

5. **Run the server**

```bash
sudo node server.js
```

6. **Get the public IP for access the address of the SMTP Server**
7. **Get a domain or use pre-exiting domain:**

- Add 'A' in DNS setting naming mail of the domain with the IP address of Server with root
- Add 'MX' in DNS. e.g mail.guddu.in
- You can add SPF and DKIM or DMARC records also for secruity purpose.

8. **Check the server**

- Send a mail from google or any mail account to domain you have used
- AWS Ubuntu Sever will able to receive your mail.

9. **Mail get received as:**

```bash
onConnect cfxafrcwoddahpga
onMailFrom kumarguddu082002@gmail.com [Function (anonymous)]
onRcptTo guddu@outfitnation.in cfxafrcwoddahpga
onData Received: by mail-ed1-f50.google.com with SMTP id 4fb4d7f45d1cf-565a3910f86so4660896a12.3
        for <guddu@outfitnation.in>; Sat, 02 Mar 2024 02:24:20 -0800 (PST)
DKIM-Signature: v=1; a=rsa-sha256; c=relaxed/relaxed;
        d=gmail.com; s=20230601; t=1709375058; x=1709979858; darn=outfitnation.in;
        h=to:subject:message-id:date:from:mime-version:from:to:cc:subject
         :date:message-id:reply-to;
        bh=qi1kFkxYzmHarWCzk+rjR8M6tXlBlNYW34esdMNVPXM=;
        b=iy0Wvug7V2airNKsOAqRm9s6Y8UcJZhS6VmSTo3sfzFTOQfQCvopcsLxHdxfYmQXo/
         6B58rI7dDOSY0bESbRTD9lf/D/YrzzJesovSjTlvLSBjXIUXiGiO1OsDaJaiASQUI8LJ
         xtCyX3SS51ebU6eRjMw4yiNQHaSAB2i3L3zS0zfP/niunnZ3efXu4Vu3A4QKECHECb/p
         RFr75WEkvv5+AxgEZn30h9a3CQJX2UrT13KNuGy3hro1FtzpHg+1i7UxS8qPP+QotFmj
         TDWC4huopwY2Wl1XM7/2qLdsfs/8atx1aq2Hg7jOQdAeWOcU90l13mfUf6y5SvP0+DNA
         cShQ==
X-Google-DKIM-Signature: v=1; a=rsa-sha256; c=relaxed/relaxed;
        d=1e100.net; s=20230601; t=1709375058; x=1709979858;
        h=to:subject:message-id:date:from:mime-version:x-gm-message-state
         :from:to:cc:subject:date:message-id:reply-to;
        bh=qi1kFkxYzmHarWCzk+rjR8M6tXlBlNYW34esdMNVPXM=;
        b=m3HyH3oflEmrzkIOFPCIVSuhqtbSJPhhyxrOHJPcS6Gg1bfVpLWaeIEriMelrvNUIc
         o1ybSAOFY+JH79tlOYOONTwikrKQvVMFfJXNUJs7NrORTqDSRqwYFPtxeBvG4QFPZiQ1
         QGU01FLEGyui6i1X9/VAz6BzNIA+
onData AHbDW85aTOUweOGU8TzGKa71moOuPdBj9DjAx107
         7lwi+bTdYzp7/6x38ja8Gig65XaIYlIa4+nw3OXkRJ5dovdH7a7g7ARbR6kW/CK1UWvi
         977IlPlIysi4zN59qluDgJBPvLSwGldgg2BxyIcQbFm77rrtbqX4acuj0KX5s0Iv+HlN
         S1vg==
X-Gm-Message-State: AOJu0YzZkef8J1jXmBa50W8Pqzo2ZpMB6+xFRA9b6CS8oJL4N6buZs+0
        FFLySvTfEDXGoqILWPiN2nb5QyvNT50XAQXQ5MDe2rURHOaNAvSYnOxv0boGFmBTDFUTb8Y8ct9
        lVD0WsaMbNveuHRCBBa7xaCGiIssmOSwnU7ItqA==
X-Google-Smtp-Source: AGHT+IEHVYY82pr/Rn5f/g4zLFpJEZQ4I8E3g8BbEBaTHtGwaE/UwYlG7g5BuMlxK9ZQS8P8XPm9HagpPCeDZmkC+Ek=
X-Received: by 2002:a17:906:c411:b0:a44:e3c:c4dd with SMTP id
 u17-20020a170906c41100b00a440e3cc4ddmr3046659ejz.48.1709375058467; Sat, 02
 Mar 2024 02:24:18 -0800 (PST)
MIME-Version: 1.0
From: Guddu Kumar <kumarguddu082002@gmail.com>
Date: Sat, 2 Mar 2024 15:54:07 +0530
Message-ID: <CAHms3HWb-gQ4PTvD1c_X+Dwi8GDh1sw_FDvrK_e+_uYWoMGMCA@mail.gmail.com>
Subject: mail Sever check
To: guddu@outfitnation.in
Content-Type: multipart/alternative; boundary="00000000000025e2550612aae530"

--00000000000025e2550612aae530
Content-Type: text/plain; charset="UTF-8"

Hello from google

--00000000000025e2550612aae530
Content-Type: text/html; charset="UTF-8"

<div dir="ltr">Hello from google<br></div>

--00000000000025e2550612aae530--
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contribute

Feel free to contribute and improve this project! If you have any questions or issues, please open an [issue](https://github.com/guddu/mail-server/issues).
