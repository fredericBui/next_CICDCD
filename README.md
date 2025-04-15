Install dependencies and build the app for production
```
npm install
npm run build
npm run start
```

Build the image and run as container
```
docker build -t next_cicdcd .
docker run --name next_cicdcd_container -p 3000:3000 next_cicdcd
```
# html_CICDCD ANOTHER PROJECT

CICDCD in Docker environment

Require :
- Docker Engine instal

If not already done start an instance of jenkins_master
```
docker run --name jenkins -p <choose_a_port>:8080 jenkins/jenkins
```

Then build and start an instance of a jenkins_agent

```
cd Jenkins-agent
docker build -t jenkins-agent-with-docker .
docker run --init --name jenkins-agent-next-with-docker_container -v /var/run/docker.sock:/var/run/docker.sock jenkins-agent-next-with-docker -url http://172.17.0.2:8080 589952531d8a3b9b9f3750db6836e765607c9cc1120103c46b02b1efa75d9731 jenkins-agent-next-with-docker
```

Want to try the entire CICD on your own repository and registry ?
Fork this project and use the jenkinsfile inside Custom folder