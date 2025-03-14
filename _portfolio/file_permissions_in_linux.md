---
layout: single
title: "File Permissions in Linux"
excerpt: "Use Linux commands to manage file permissions"
classes: wide
---

# File permissions in Linux

## Project description

Here is the scenario:

> I am a security professional at a large organization. I mainly work
> with their research team. Part of my job is to ensure users on this
> team are authorized with the appropriate permissions. This helps keep
> the system secure.
>
> My task is to examine existing permissions on the file system. I'll
> need to determine if the permissions match the authorization that
> should be given and modify them as needed.

Linux has a powerful access permission system to insure appropriate
authorization controls. The Linux command line will used to view and
then modify the permissions in the project directory.

## Check file and directory details

To check the file and directory details (including hidden files and
directories) use

```
ls -al
```

from the projects directory. The a option lists hidden files and
directories, and the l option lists the permissions.

The output includes the following permissions:

```
-rw\--w\-\-\-- .project_x.txt

drwx\--x\-\-- drafts

-rw-rw-rw- project_k.txt

-rw-r\-\-\-\-- project_m.txt

-rw-rw-r\-- project_r.txt

-rw-rw-r\-- project_t.txt
```

## Describe the permissions string

The 10 character code contains the following information:

- First character is the type (d = directory, - = file)

- 2nd-4th characters are the permissions for the user (u, i.e. the
  owner) in order as read (r), write (w) and execute (x), (- is used
  in each place to indicate permission is not given).

- 5th-7th characters are the read, write, and execute permissions for
  the group (g) -- see above for details.

- 8th-10th characters are the read, write, and execute permissions for
  other (o, i.e. the world) -- see above for details.

For example:

```
-rw-rw-rw- project_k.txt
```

- This is a file (1st character is -)

- The user has read and write access but not execute access (2nd-4th
  characters are rw-)

- The group has read and write access but not execute access (5th-7th
  characters are rw-)

- Other has read and write access but not execute access (8th-10th
  characters are rw-)

## Change file permissions

The organization does not allow others to have write access to any
files. The project_k.txt file needs to have its permissions changed:

```
chmod o-w project_k.txt
```

- chmod is the command

- o-w means remove write access for other

This results in the following permissions:

```
-rw-rw-r\-- project_k.txt
```

## Change file permissions on a hidden file

The research team has archived .project_x.txt, which is why it's a
hidden file. This file should not have write permissions for anyone, but
the user and group should be able to read the file. Use the command:

```
chmod u-w,g+r-w .project_x.txt
```

- u-w removes write access for the user

- g+r-w adds read access and removes write access for the group

- Note: permission changes for types (user, group, or other) are
  separated by a comma with no spaces

This results in the following permissions:

```
-r\--r\-\-\-\-- .project_x.txt
```

## Change directory permissions

The files and directories in the projects directory belong to the
researcher2 user. Only researcher2 should be allowed to access the
drafts directory and its contents. Use the command:

```
chmod g-x drafts
```

- g-x removes execution access for the group

This results in the following permissions:

```
drwx\-\-\-\-\-- drafts
```

## Summary

Linux has powerful access permission authorization for files and
directories. The ls command is used to view the permissions (with the
options -al). The chmod command is used to modify the permissions for
files and directories.
