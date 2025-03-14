---
layout: single
title: "Algorithm For File Updates in Python"
excerpt: "Importing and parsing a text file in a security-related scenario"
classes: wide
---

# Algorithm for File Updates in Python

## Project description

In this scenario, I am a security professional working at a health care company. As part of my job, I'm required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.

My task is to create an algorithm that uses Python code to check whether the allow list contains any IP addresses identified on the remove list. If so, I should remove those IP addresses from the file containing the allow list.

## Open the file that contains the allow list

To accomplish this:

- Assign 'import_file' variable to the filename 'allow_list.txt' using '='.

- Assign 'remove_list' variable to the list ["192.168.97.225","192.168.150.170","192.168.201.40","192.168.58.57"] using '='.

- Begin using a 'with' statement to 'open' the file in a safe way that will close it when finished.

```
# Assign 'import_file' to the file 'allow_list.txt'.

import_file = "allow_list.txt"

# Assign 'remove_list' to a list of IP addresses that are no longer allowed to access restricted information.

remove_list = ["192.168.97.225","192.168.150.170","192.168.201.40","192.168.58.57"]

# First line of the 'with' statement.

with open(import_file, "r") as file:
```

## Read the file contents

To accomplish this:

- Use the .read() method to import the file into the variable 'ip_addresses' using '=' in the 'with' statement body.

- Display 'ip_addresses' using print() function.

```
# Assign 'import_file' to the file 'allow_list.txt'.

import_file = "allow_list.txt"

# Assign 'remove_list' to a list of IP addresses that are no longer allowed to access restricted information.

remove_list = ["192.168.97.225","192.168.150.170","192.168.201.40","192.168.58.57"]

# Build 'with' statement to read in the initial value of the file.

with open(import_file, "r") as file:

    # Use .read() to read the imported file and store it in a variable name 'ip_addresses'.
    ip_addresses = file.read()

# Display 'ip_addresses'.

print(ip_addresses)
```

## Convert the string into a list

To accomplish this:

- Use the .split() method to split the string 'ip_addresses' into a list 'ip_addresses' since the ip addresses are separated by a new line.

- Display the list ip_addresses using print() function.

```
# Assign 'import_file' to the file 'allow_list.txt'.

import_file = "allow_list.txt"

# Assign 'remove_list' to a list of IP addresses that are no longer allowed to access restricted information.

remove_list = ["192.168.97.225","192.168.150.170","192.168.201.40","192.168.58.57"]

# Build 'with' statement to read in the initial value of the file.

with open(import_file, "r") as file:

    # Use .read() to read the imported file and store it in a variable name 'ip_addresses'.
    ip_addresses = file.read()

# Use .split() to convert 'Ip_addresses' from a string to a list.

ip_addresses = ip_addresses.split()

# Display 'ip_addresses'.

print(ip_addresses)
```

## Iterate through the IP addresses

To accomplish this:

- Use a 'for' loop to iterate through the 'ip_addresses' list using 'element' as the loop variable.

- For now, display each element with the print() function.

```
# Assign 'import_file' to the file 'allow_list.txt'.

import_file = "allow_list.txt"

# Assign 'remove_list' to a list of IP addresses that are no longer allowed to access restricted information.

remove_list = ["192.168.97.225","192.168.150.170","192.168.201.40","192.168.58.57"]

# Build 'with' statement to read in the initial value of the file.

with open(import_file, "r") as file:

    # Use .read() to read the imported file and store it in a variable name 'ip_addresses'.
    ip_addresses = file.read()

# Use .split() to convert 'Ip_addresses' from a string to a list.

ip_addresses = ip_addresses.split()

# Build an iterative statement.
# Name loop variable 'element'.
# Loop through ip_addresses.

for element in ip_addresses:

    # Display 'element' in every iteration.
    print(element)
```

## Remove IP addresses that are on the remove list

To accomplish this:

- Replace the displaying of each element with a conditional statement.

- Use an 'if' statement to check if the 'element' is in the 'remove_list'

- If it is, use the .remove() method to remove the 'element' from 'ip_addresses'

- Use the print() function to display the new 'ip_addresses' list

```
# Assign 'import_file' to the file 'allow_list.txt'.

import_file = "allow_list.txt"

# Assign 'remove_list' to a list of IP addresses that are no longer allowed to access restricted information.

remove_list = ["192.168.97.225","192.168.150.170","192.168.201.40","192.168.58.57"]

# Build 'with' statement to read in the initial value of the file.

with open(import_file, "r") as file:

    # Use .read() to read the imported file and store it in a variable name 'ip_addresses'.
    ip_addresses = file.read()

# Use .split() to convert 'Ip_addresses' from a string to a list.

ip_addresses = ip_addresses.split()

# Build an iterative statement.
# Name loop variable 'element'.
# Loop through ip_addresses.

for element in ip_addresses:

    # Build conditional statement.
    # if 'element' is in the remove_list,

    if element in remove_list:

        # then remove the current element from ip_addresses.
        ip_addresses.remove(element)

# Display 'ip_addresses'.

print(ip_addresses)
```

## Update the file with the revised list of IP addresses

To accomplish this:

- Convert 'ip_addresses' from a list to a string with the .join() method using "\n" to have each ip address on new line.

- Using a 'with' to open 'import_file' in write mode, rewrite the file with 'ip_addresses' using the .write() method on the file.

```
# Assign 'import_file' to the file 'allow_list.txt'.

import_file = "allow_list.txt"

# Assign 'remove_list' to a list of IP addresses that are no longer allowed to access restricted information.

remove_list = ["192.168.97.225","192.168.150.170","192.168.201.40","192.168.58.57"]

# Build 'with' statement to read in the initial value of the file.

with open(import_file, "r") as file:

    # Use .read() to read the imported file and store it in a variable name 'ip_addresses'.
    ip_addresses = file.read()

# Use .split() to convert 'Ip_addresses' from a string to a list.

ip_addresses = ip_addresses.split()

# Build an iterative statement.
# Name loop variable 'element'.
# Loop through ip_addresses.

for element in ip_addresses:

    # Build conditional statement.
    # if 'element' is in the remove_list,

    if element in remove_list:

        # then remove the current element from ip_addresses.
        ip_addresses.remove(element)

# convert 'ip_addresses' back to a string with addresses separated on new lines.

ip_addresses = "\n".join(ip_addresses)

# Build 'with' statement to rewrite the original file.

with open(import_file, "w") as file:

    # Rewrite the file, replacing the content with 'ip_addresses'.
    file.write(ip_addresses)
```

## Summary

The final algorithm includes:

- The reading of the file of approved IP addresses into a variable.

- Converting this variable into a list of addresses.

- Removing the addresses in the remove list from this list of addresses.

- Converting the revised list of approved addresses back into a string separating the addresses on new lines.

- Rewriting the file with the updated list.
