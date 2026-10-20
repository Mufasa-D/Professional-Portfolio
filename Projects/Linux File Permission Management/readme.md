# 📎 **Project description**
This project demonstrates the use of Linux file permissions to enforce appropriate access controls within a research environment.

The objective was to inspect existing file and directory permissions, identify access that violated organizational security requirements, and modify those permissions using Linux commands.

## Scenario

A research team stores project files under:

```bash
/home/researcher2/projects
```

As part of a security review, file and directory permissions needed to be examined to ensure that users had only the access required for their roles.

The goal was to identify excessive permissions and remove unauthorized access.

Please view the current file permissions by clicking the link below⬇️ <br>
[View Current file permissions](https://docs.google.com/document/d/1q5OS7J1tIArAUB6QhWBMDkPn3150b5iH/edit?usp=drive_link&ouid=102961763573972563230&rtpof=true&sd=true)

---

# Inspecting Permissions

__NB:__ Screenshot links are provided during each step. 

1. The first step was to inspect the directory:

```bash
ls -la /home/researcher2/projects
```
[View Screenshot](../../Screenshots/1.png)

---

2. According to the organizations security policies, none of the files should allow the "other" users to write to files. Hence I had to make that change.
The file **project_k.txt**'s permissions had to be changed. 

```bash
chmod o-w project_k.txt
```
[View Screenshot](../../Screenshots/2.png)

---

3. There was a hidden file which needed to have only "read" permissions for user and group. I made the required change.

```bash
chmod u=r,g-r .project_x.txt
```
[View Screenshot](../../Screenshots/3.png)

---

<!--Check file and directory details
[Add content here.]
Describe the permissions string
[Add content here.]
Change file permissions
[Add content here.]
Change file permissions on a hidden file
[Add content here.]
Change directory permissions
[Add content here.]
Summary
[Add content here.]

