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

On your browser open `http://localhost` port:80 to run DVWA Application

  username: admin
  password: password

## View the dashboard

 On your browser open `http://localhost:8080` to view the live activity metrics from your N+ instance
 Creds for Dashbaord:
`user1:Welcome@user1`
`user2:Welcome@user2`

### Dashboard - Metrics available under HTTP Upstream Tab
Following are the metrics available when you have enabled the "zone" directive in the upstream context:

<img width="1493" alt="http_upstreams" src="https://user-images.githubusercontent.com/52437445/130018076-a0f9acd4-ef31-41d0-91cb-b11d115a8b7a.png">


### Dashboard - Metrics available under HTTP Zones Tab
Following are the metrics available when you have status_zone directive enabled in your location/server context:

<img width="1488" alt="http_zones" src="https://user-images.githubusercontent.com/52437445/130018095-732ee65b-465d-4b2c-8256-d9264f81b409.png">


## Testing LIVENESS of DoS

It is configured via nginx.conf and can be accessed via browswer:

```http://dvwa.example.com:8090/liveness```

- Where expected response should be "Alive"
                                                                                                                                                     
## Testing Some Security Features:

Command Injection - <url>/vulnerabilities/exec/
Stored Cross Site Scripting - Dataguard - <url>/vulnerabilities/xss_s/
 


### Possible Additions - will review them in future

- You can add self-signed certificate in the nginx.conf file 
- Include multiple policy files as required for specific end-points
- Export logs to ELK or write to local drive
