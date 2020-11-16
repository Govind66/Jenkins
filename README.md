# Jenkins

## Red Hat / CentOS
* You can install Jenkins through yum on Red Hat Enterprise Linux, CentOS, and other Red Hat based distributions. You need to choose either the Jenkins Long Term Support release or the Jenkins weekly release.

### Long Term Support release
* A LTS (Long-Term Support) release is chosen every 12 weeks from the stream of regular releases as the stable release for that time period. It can be installed from the redhat-stable yum repository.
```
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
```
```
sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
```
```
sudo yum upgrade
```
```
sudo yum install jenkins java-1.8.0-openjdk-devel
```
```
sudo systemctl daemon-reload
```
### Start Jenkins
* You can start the Jenkins service with the command:
```
sudo systemctl start jenkins
```
* You can check the status of the Jenkins service using the command:
```
sudo systemctl status jenkins
```
* If everything has been set up correctly, you should see an output like this:
```
Loaded: loaded (/etc/rc.d/init.d/jenkins; generated)
Active: active (running) since Tue 2018-11-13 16:19:01 +03; 4min 57s ago
...
```
### Unlocking Jenkins
* When you first access a new Jenkins instance, you are asked to unlock it using an automatically-generated password.

* Browse to http://localhost:8080 (or whichever port you configured for Jenkins when installing it) and wait until the Unlock Jenkins page appears.
* From the Jenkins console log output, copy the automatically-generated alphanumeric password (between the 2 sets of asterisks).
* The command: sudo cat /var/lib/jenkins/secrets/initialAdminPassword will print the password at console.

### Customizing Jenkins with plugins
* After unlocking Jenkins, the Customize Jenkins page appears. Here you can install any number of useful plugins as part of your initial setup.

* Click one of the two options shown:

* Install suggested plugins - to install the recommended set of plugins, which are based on most common use cases.

* Select plugins to install - to choose which set of plugins to initially install. When you first access the plugin selection page, the suggested plugins are selected by default.

### Creating the first administrator user
* Finally, after customizing Jenkins with plugins, Jenkins asks you to create your first administrator user.

* When the Create First Admin User page appears, specify the details for your administrator user in the respective fields and click Save and Finish.

* When the Jenkins is ready page appears, click Start using Jenkins.
Notes:

* This page may indicate Jenkins is almost ready! instead and if so, click Restart.

* If the page does not automatically refresh after a minute, use your web browser to refresh the page manually.

* If required, log in to Jenkins with the credentials of the user you just created and you are ready to start using Jenkins!.
