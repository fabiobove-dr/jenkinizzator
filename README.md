# Jenkinizzator️🤵🎩

# Instructions

## Jenkins Master
1. **Run Jenkins**<br>In the same directory as the docker-compose.yml file, run the following command:
   `docker-compose up -d`
2. **Access Jenkins**<br>Open a browser and navigate to http://localhost:8080. The initial setup requires an unlock key,
   which can be found in the Jenkins container logs: `docker logs jenkins`
   <br>You can also run the `jenkins/get_jenkins_token.sh` script that generates the file `initialAdminPassword` with the unlock key.
4. **Persist Jenkins Data**<br>The `jenkins_home` volume ensures that Jenkins data (e.g., jobs, plugins, configuration)
   is stored persistently on your machine. You can adjust the volumes mount
4. **Install Plugins and Setup Jobs**<br>Once inside Jenkins, you can install necessary plugins and start setting up
   your jobs.

## Jenkins Agent
The docker-compose automatically builds the Agent `jenkins-agent`.
It's important to register the agent. Once it is configured you can obtain the secret and palace in the .env
so it can connect to the `jenkins-master`.