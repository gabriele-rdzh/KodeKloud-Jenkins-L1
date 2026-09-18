# Task 05: Configure Jenkins Job for Package Installation

## Objective

Some new requirements have come up to install and configure some packages on the Nautilus infrastructure under Stratos Datacenter. The Nautilus DevOps team installed and configured a new Jenkins server so they wanted to create a Jenkins job to automate this task. Find below more details and complete the task accordingly:



1. Access the Jenkins UI by clicking on the `Jenkins` button in the top bar. Log in using the credentials: username `admin` and password `Adm!n321`.


2. Create a new Jenkins job named `install-packages` and configure it with the following specifications:


- Add a string parameter named `PACKAGE`.

- Configure the job to install a package specified in the `$PACKAGE` parameter on the `storage server` (Stratos Datacenter).


Build the job at least once (e.g. with parameter `PACKAGE=vim-enhanced`) so the package is installed on the Storage server and can be verified.

## Solution

On the home page, go to `New Job`
<img width="1920" height="620" alt="image" src="https://github.com/user-attachments/assets/3a256bcc-4984-49d3-bb47-50073466abb3" />


Enter the name and click ok
<img width="1920" height="509" alt="image" src="https://github.com/user-attachments/assets/4ede76d6-4d88-45fb-986f-69aa5cb8a51e" />


select Build with Parameters and select the String parameter
<img width="1904" height="992" alt="image" src="https://github.com/user-attachments/assets/9966a1a6-f89a-4b84-a5df-4e730abc11e7" />

Let's use the following command; just change whatever needs to be changed and save it
`sshpass -p "PASSWORD" ssh -o StrictHostKeyChecking=no USER@SERVER "sudo echo 'PASSWORD' | sudo -S dnf install -y $PACKAGE"`

<img width="1905" height="990" alt="image" src="https://github.com/user-attachments/assets/2543ebf9-3663-4ee2-8322-aaf71b7b8b8c" />

Now select Build with Parameters and enter the package name
<img width="1919" height="569" alt="image" src="https://github.com/user-attachments/assets/4e4f81e3-8b09-4231-9aab-7e29ca984a74" />


and we're done
<img width="1920" height="715" alt="image" src="https://github.com/user-attachments/assets/b68378f9-14df-432b-a4be-34b9a9fef8ab" />

*I made a typo in the command, which is why there are more builds; the error is no longer in the previous command :P
