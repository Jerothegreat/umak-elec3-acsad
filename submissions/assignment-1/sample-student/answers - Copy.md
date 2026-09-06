ANSWER_1: The course-portal application is failing because it's getting a "Permission denied" error when trying to read its own configuration file.
ANSWER_2: The permissions are currently set to `-rw-------` (octal 600), meaning only the owner (root) has read and write access, while the group (which the course-portal account belongs to) and others have absolutely zero access.
ANSWER_3: 640
ANSWER_3_WHY: 400 still leaves the group with zero access so it won't fix the error, 755 gives unnecessary execute permissions and lets random others read the file, and 777 is super insecure because it lets anyone write and execute it. 
ANSWER_4_ORDER: B, G, E, D, F, A, I, C, H
ANSWER_5: Any other user logged into the system would get full write access, meaning they could mess up our configuration file or add malicious code to it.
ANSWER_6: Actually opening the Course Materials Portal in a web browser and seeing the page load correctly instead of crashing.
ANSWER_7_BRIDGE: component=file configuration, detect=an automated monitoring alert, recover=a deployment script running again, proof=an automated website ping getting a 200 OK