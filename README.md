# Using-Linux-commands-to-manage-file-permissions

### Project description
The research team at my organization needs to update the file permissions for certain files and directories within the **projects** directory. The permissions do not currently reflect the level of authorization that should be given. Checking and updating these permissions will help keep their system secure. To complete this task, I performed the following tasks.

### Check file and directory details
The following commands demonstrate how I used LINUX to determine existing permissions set to a specific file directory
<img width="613" height="202" alt="Screen Shot 2025-07-29 at 11 46 27 AM" src="https://github.com/user-attachments/assets/5c57879a-4018-4b6c-a6d3-b3ccb1e4de40" />

I used the ***ls*** command with the ***-la*** option to display a detailed listing of the file contents and the hidden files. These files are found under the **projects** directory. The output of my command indicates that there is one directory named drafts, one hidden file named **.project_x.txt**, and five other project files.

### Describe the permissions string
The characters and what they represent are as follows:
1) *1st character*: This character is either a d or hyphen (-) and indicates the file type. If it’s a "d", it’s a directory. If it’s a hyphen (-), it’s a regular file.
2) *2nd-4th characters*: These characters indicate the read (r), write (w), and execute (x) permissions for the *user*. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted to the user.
3) *5th-7th characters*: These characters indicate the read (r), write (w), and execute (x) permissions for the *group*. When one of these characters is a hyphen (-) instead, it indicates that this permission is not granted for the group.
4) 8th-10th characters: These characters indicate the read (r), write (w), and execute (x) permissions for *other*. This owner type consists of all other users on the system apart from the user and the group. When one of these characters is a hyphen (-) instead, that indicates that this permission is not granted for other.

### Change file permissions
The organization determined that *other* shouldn't have write access to any of their files. I determined **project_k.txt** must have the write access removed for **other**.

<img width="621" height="24" alt="Screen Shot 2025-07-29 at 12 04 34 PM" src="https://github.com/user-attachments/assets/ccf733c2-c3a3-4a89-be59-da988dda3aac" />

The ***chmod*** command changes the permissions on files and directories. The first argument indicates what permissions should be changed, and the second argument specifies the file or directory. In this example, I removed write permissions from **other** for the **project_k.txt file**.

<img width="616" height="23" alt="Screen Shot 2025-07-29 at 12 06 55 PM" src="https://github.com/user-attachments/assets/71bfc5df-57a0-4c03-8ada-4d9ed890a269" />

### Change file permissions of a hidden file
The research team recently archived **project_x.txt**. They do not want anyone to have write (w) access to this project, but the user and group should have read (r) access.

The following code demonstrates how I used Linux commands to change the permissions:

<img width="612" height="23" alt="Screen Shot 2025-07-29 at 12 13 14 PM" src="https://github.com/user-attachments/assets/87b58f23-658a-4cf5-b034-67f546d551a8" />

Below is a detailed screenshot of the step:
The first two lines of the screenshot display the commands I entered, and the other lines display the output of the second command. I know **.project_x.txt** is a hidden file because it starts with a period (.). In this example, I removed write (w) permissions from the **user** and **group**, and added read (r) permissions to the **group**. I removed write (w) permissions from the **user** with ***u-w***. Then, I removed write permissions from the **group** with ***g-w***, and added read permissions to the **group** with ***g+r***.

<img width="613" height="217" alt="Screen Shot 2025-07-29 at 12 18 29 PM" src="https://github.com/user-attachments/assets/35231240-fb17-4d70-8aef-73bd82f6f276" />

### Change directory permissions
My organization wants the researcher2 user to have access to the **drafts** directory and its contents. This means that no one other than researcher2 should have execute (x)
permissions.

The following code demonstrates how I used Linux commands to change the permissions:

<img width="613" height="22" alt="Screen Shot 2025-07-29 at 12 22 49 PM" src="https://github.com/user-attachments/assets/3a10e69a-81a4-4324-9f81-edfeab38f982" />

Below is a detailed screenshot of the step:
The output here displays the permission listing for several files and directories. Line 1 indicates the current directory (projects), and line 2 indicates the parent directory (home). Line 3 indicates a regular file titled **.project_x.txt**. Line 4 is the directory (drafts) with restricted permissions.

<img width="613" height="214" alt="Screen Shot 2025-07-29 at 12 28 03 PM" src="https://github.com/user-attachments/assets/ea50ac29-2b0d-49de-8f84-deeba04fdb49" />

Here you can see that only researcher2 has execute (x) permissions. It was previously determined that the group had execute permissions, so I used the ***chmod*** command
to remove them. The researcher2 user already had execute permissions, so they did not need to be added. See below:

<img width="615" height="24" alt="Screen Shot 2025-07-29 at 12 29 33 PM" src="https://github.com/user-attachments/assets/068a9eaa-26d1-467f-9814-0660ab5c3b44" />

### Summary

I changed multiple permissions to match the level of authorization my organization wanted for files and directories in the **projects** directory. The first step was using ***ls -la*** to check the permissions for the directory. This informed my decisions in the following steps. I then used the ***chmod*** command multiple times to change the permissions on files and directories.

Ref 1 to file link: [Current file permissions](https://docs.google.com/document/d/11BOhE1g6YvFemT5ANsQoO2USuQvR8a9Wc0bKp3-6kuA/edit?tab=t.0#heading=h.dooa9fyvnog2)

Ref 2 to link file: [Instructions for including Linux commands](https://docs.google.com/document/d/19JbIGtFBdPhJSFDybElhftjf-_Xb44lhWrcDFRNeAxo/edit?tab=t.0#heading=h.dooa9fyvnog2)





