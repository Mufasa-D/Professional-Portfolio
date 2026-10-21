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
[View Current file permissions📷](https://docs.google.com/document/d/1q5OS7J1tIArAUB6QhWBMDkPn3150b5iH/edit?usp=drive_link&ouid=102961763573972563230&rtpof=true&sd=true)

---

# 🕵️‍♂️ Inspecting Permissions

__NB:__ Screenshot links are provided during each step. 

__1.__ The first step was to inspect the directory:

```bash
ls -la /home/researcher2/projects
```
[View Screenshot📷](../../Screenshots/1.png)

The `-l` option displays detailed file information, including permissions, ownership, group membership, file size, and modification information.

The `-a` option also displays hidden files.

## 🌠 Understanding Linux Permissions

Consider:

```text
-rw-rw-rw-
```

Linux permissions can be divided into four sections:

```text
- | rw- | rw- | rw-
    │      │      │
    │      │      └── Others
    │      └───────── Group
    └──────────────── User / Owner
```

The first character describes the object type:

```text
- = regular file
d = directory
l = symbolic link
```

The remaining characters represent:

```text
r = read
w = write
x = execute
- = permission not granted
```

Therefore:

```text
-rw-rw-rw-
```

means:

| Identity | Read | Write | Execute |
|---|---|---|---|
| Owner | Yes | Yes | No |
| Group | Yes | Yes | No |
| Others | Yes | Yes | No |

---

---

__2.__ According to the organizations security policies, none of the files should allow the "other" users to write to files. Hence I had to make that change.
The file **project_k.txt**'s permissions had to be changed. 

```bash
chmod o-w project_k.txt
```
[View Screenshot📷](../../Screenshots/2.png)

---

__3.__ There was a hidden file which needed to have only "read" permissions for user and group. I made the required change.

```bash
chmod u=r,g-r .project_x.txt
```
[View Screenshot📷](../../Screenshots/3.png)

---

__4.__ The `drafts` directory needed to be accessible only by its owner.

The desired permissions are:

```text
drwx------
```

This can be configured using:

```bash
chmod u=rwx,g=,o= /home/researcher2/projects/drafts
```

This gives the owner:

- Read
- Write
- Execute

while removing all permissions from the group and others.

---

# ⚓ Security Principles Applied

## Least Privilege
Users should receive only the permissions required to perform their responsibilities.
Removing unnecessary write or directory access reduces the possibility of unauthorized modification or disclosure.

---

## Access Control
Linux filesystem permissions provide discretionary access control through three primary identities:

```text
User
Group
Others
```

Permissions can then control:

```text
Read
Write
Execute
```

---

## 🛡️ Attack-Surface Reduction

Excessive filesystem permissions can enable unauthorized users to:

- Read sensitive information
- Modify files
- Delete information
- Execute files
- Access restricted directories

Restricting permissions reduces these opportunities.

---

# 🏄‍♂️ Skills Demonstrated

This project demonstrates practical knowledge of:

- Linux
- Linux filesystem permissions
- `ls`
- `chmod`
- Symbolic permissions
- Numeric/octal permissions
- Hidden files
- Directory permissions
- Access control
- Least privilege
- Security configuration
- Verification of security changes

---

## 🟰 **Summary**
I understand that managing file permissions is just about keeping things locked down safely. It ensures folks only touch what they actually need to, keeps sensitive data out of the wrong hands, and stops accidental mistakes from taking down the whole system. I know how important this responsibility is for a security analyst in an organization and have mastered it.

