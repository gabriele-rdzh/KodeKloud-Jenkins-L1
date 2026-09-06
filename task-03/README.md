# Task 03: Configure Jenkins User Access

## Objective

The Nautilus team is integrating Jenkins into their CI/CD pipelines. After setting up a new Jenkins server, they're now configuring user access for the development team, Follow these steps:



1. Click on the Jenkins button on the top bar to access the Jenkins UI. Login with username `admin` and password `Adm!n321`.

2. Create a jenkins user named `jim` with the password `YchZHRcLkL`. Their full name should match `Jim`.

3. Utilize the `Project-based Matrix Authorization Strategy` to assign `overall read` permission to the `jim` user.

4. Remove all permissions for `Anonymous` users (if any) ensuring that the `admin` user retains overall `Administer` permissions.

5. For the existing job, grant `jim` user only `read` permissions, disregarding other permissions such as Agent, SCM etc.

## Solution

First, let's go to the Jenkins server to log in.
<img width="1393" height="515" alt="image" src="https://github.com/user-attachments/assets/62646f76-6fdb-4f89-80e2-433776602d5f" />

Once we've logged in, go to "manage Jenkins" and then to "System Configuration" to install the plugin `Matrix Authorization Strategy`.
<img width="1832" height="278" alt="image" src="https://github.com/user-attachments/assets/c2f754b0-5581-474e-bf81-feb7a5565c0b" />

<img width="1920" height="331" alt="image" src="https://github.com/user-attachments/assets/6871635a-9e9a-4617-ae83-3ccc4cf2eb03" />

Once th plugin is installedand Jenkins has been restarted, go to the security section under "Manage Jenkins".
Go to "Users" to create a user for `Jim`
<img width="907" height="199" alt="image" src="https://github.com/user-attachments/assets/5b34e446-f4e0-4b58-9648-e399e88c5f09" />

<img width="1610" height="250" alt="image" src="https://github.com/user-attachments/assets/2d8b169d-6424-476b-8705-b2285f7f802e" />

<img width="1920" height="400" alt="image" src="https://github.com/user-attachments/assets/9e41212d-334e-48cc-8543-9383ed3344d9" />

Now we're heading back to security section and go to Security, unader "Authorization", we select "Project-based Strategy" and add the `admin` user and `Jim` user
<img width="1622" height="643" alt="image" src="https://github.com/user-attachments/assets/30c9e5e5-e762-46fb-bfc5-ec560a0def87" />

<img width="1622" height="643" alt="image" src="https://github.com/user-attachments/assets/23a9d03d-bac6-4ab7-a80c-0b4174698a4a" />

Now we'll  grant Jim global read permissions, grant admin global administration permissions, and verify that anonymous users do not have any permissions.
<img width="1619" height="753" alt="image" src="https://github.com/user-attachments/assets/24aed8a8-9721-4edc-a17c-12769da8b406" />

<img width="1628" height="926" alt="image" src="https://github.com/user-attachments/assets/6c077f1e-48fd-4621-8d93-56e4d0b5004d" />

Now let's go to the Jenkins home page and select the job
<img width="1919" height="400" alt="image" src="https://github.com/user-attachments/assets/2534e42f-2d1a-461d-8f41-b93808836a5b" />

We're going to configurations

<img width="682" height="558" alt="image" src="https://github.com/user-attachments/assets/b1b0ec62-3853-44ae-8d99-be2e5a5a4393" />

In general, we're going to add Jim and grant him read permissions in the Job section, save and we're done

<img width="1710" height="877" alt="image" src="https://github.com/user-attachments/assets/7071bff1-1ec2-4d1b-84f3-de792bf1d83a" />

<img width="1748" height="864" alt="image" src="https://github.com/user-attachments/assets/2a62295e-5e27-411d-87c5-5a4e9f241964" />

<img width="1690" height="991" alt="image" src="https://github.com/user-attachments/assets/5f8f02f1-6be5-4b2c-bfa2-cc8b62b3ec8c" />
