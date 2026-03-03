# python-ip-allowlist-automation
## Project Overview
This project automates the process of maintaining an IP allow list used to control access to restricted content. The script removes unauthorized IP addresses from an existing allow list file based on a predefined removal list.

This project demonstrates secure access control management, Python file handling, and automation of security operations.

---

## Problem Statement
The organization manages access to restricted resources using an `allow_list.txt` file containing approved IP addresses. A separate removal list identifies IP addresses that should no longer have access.

Manually updating the file increases the risk of human error and inconsistent enforcement of access controls.

---

## Solution
I developed a Python script that:

- Opens and reads the existing allow list file
- Converts file contents into a list structure
- Iterates through a removal list
- Removes unauthorized IP addresses
- Rewrites the updated allow list securely back to the file

This automation improves efficiency, reduces manual errors, and strengthens enforcement of least privilege access control.

---

## Technologies Used
- Python 3
- File handling (`open`, `read`, `write`)
- String manipulation (`split`, `join`)
- List operations (`remove`)
- Iteration and conditionals

---

## Key Security Concepts Demonstrated
- Access control management
- Least privilege principle
- Automation in security operations
- Data handling and file integrity

---

## Example Code Snippet

```python
with open("allow_list.txt", "r") as file:
    ip_addresses = file.read().split()

for element in remove_list:
    if element in ip_addresses:
        ip_addresses.remove(element)

updated_ips = "\n".join(ip_addresses)

with open("allow_list.txt", "w") as file:
    file.write(updated_ips)
