# Setup your DVWA - Damn Vulnerable Web Application Application with NGINX App Protect 

## Step 1 - Create APP Protect Image on your Host

 Create App Protect Image with Attack Signatures & Threat Campaigns
  (Ensure you copy your .crt & .key in the same directory)
  
  `docker build --no-cache -t app-protect .`

Test Step 1: 

`docker images`

Ensure that you can now view the newly created image

## Step 2 - Run Docker Compose

`docker-compose up -d`

Test Step 2:

`docker ps`

Ensure that you are now able to view two running containers

## Run the Applicaiton

On your browser open `localhost` port:80 to run DVWA Application

  username: admin
  password: password
  
  
## Testing Some Security Features:



### Possible Additions - will review them in future

- You can add self-signed certificate in the nginx.conf file 
- Include multiple policy files as required for specific end-points
- Export logs to ELK or write to local drive
