# Task 01: Set Up Jenkins Server

## Objective

The DevOps team at xFusionCorp Industries is initiating the setup of CI/CD pipelines and has decided to utilize Jenkins as their server. Execute the task according to the provided requirements:



1. Install `Jenkins on` the jenkins server using the `apt` utility only, and start it using the `service` command.

- If you face a timeout issue while starting the Jenkins service, first check the service status with `service jenkins status`
- Then review the logs in `/var/log/jenkins/jenkins.log` to identify the cause.
  
2. Jenkin's admin user name should be `theadmin`, password should be `Adm!n321`, full name should be `Kirsty` and email should be `kirsty@jenkins.stratos.xfusioncorp.com.`

## Solution

Jenkins requires Java to run. keep an eye on this *not all java versions are compatible* with Jenkins

```bash
apt update
apt install fontconfig openjdk-21-jre
java -version
# Output
openjdk version "21.0.12" 2026-07-21
OpenJDK Runtime Environment (build 21.0.12+8-1-24.04-Ubuntu)
OpenJDK 64-Bit Server VM (build 21.0.12+8-1-24.04-Ubuntu, mixed mode, sharing)
```

Now let's download the GPG key and install Jenkins

```bash
wget -O /etc/apt/keyrings/jenkins-keyring.asc \
> https://pkg.jenkins.io/debian-stable/jenkins.io-2026.key
echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
> https://pkg.jenkins.io/debian-stable binary/ | sudo tee \se
> /etc/apt/sources.list.d/jenkins.list > /dev/null
apt update
apt install jenkins
```
We start the service

```bash
service jenkins start
# Output
 * Starting Jenkins Automation Server jenkins                                                                                   Setting up max open files limit to 8192
```
Now let's copy the initialAdminPassword from the following path

```bash
cat /var/lib/jenkins/secrets/initialAdminPassword
```

and paste here
<img width="1008" height="969" alt="image" src="https://github.com/user-attachments/assets/abb002af-bd62-4670-85b3-5c1a1ad76c25" />

If you don't want to struggle with deciding which plugins to install, go with "Install suggested plugins"
<img width="1008" height="969" alt="image" src="https://github.com/user-attachments/assets/db96d8ad-6b64-4d01-a216-867d988b47a4" />

Now we can create our first admin user
<img width="1006" height="962" alt="image" src="https://github.com/user-attachments/assets/c52baee3-a946-4d41-82c5-71690ab4529a" />

and we're done
<img width="1006" height="962" alt="image" src="https://github.com/user-attachments/assets/da8249c4-0298-43c4-a4ec-0e76a31528b9" />

