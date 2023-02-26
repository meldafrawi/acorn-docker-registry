# Running docker private registry as acorn app 

Run k3s cluster.
`curl -sfL https://get.k3s.io | sh -`

Install Acorn with enabled lets-encrypt
`acorn install --lets-encrypt enabled --lets-encrypt-tos-agree --lets-encrypt-email <ENTER_YOUR_EMAIL_HERE>`

Build acorn app:

`acorn build -t acorn-docker-registry:v0.0.0`

Run acorn app

`acorn run acorn-docker-registry:v0.0.0`

Get endpoint URI:

`acorn apps | grep acorn-docker-registry:v0.0.0` 

Login to private registry:  

`docker login <ENTRYPOINT_URI>`  # registry has no authentication, enter any username and password to login


