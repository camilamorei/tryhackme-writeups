Become a Hacker

TryHackMe room: https://tryhackme.com/room/becomeahacker

Task 1: What Is Offensive Security?

Completed the introduction to offensive security.

Offensive security focuses on proactively testing systems by attempting to identify weaknesses before real attackers can exploit them.

The room uses ethical hacking in a legal and permission-based environment to demonstrate how attackers identify and chain weaknesses.

Task 2: Enumeration

Used Gobuster to enumerate directories on the web application.

Hidden Web Page

The scan discovered:

/login
Status Code

The /login page returned:

200

This demonstrated how directory enumeration can reveal functionality that may not be directly visible on a website.

Task 3: Exploiting Weaknesses

This task demonstrated how multiple small weaknesses can be chained together to produce a larger security impact.

The hidden /login page provided an entry point for testing the authentication mechanism.

Credentials

The admin username was tested against a password wordlist using both manual testing and Hydra.

Hydra found:

Username: admin
Password: qwerty
Secret Message

After logging in with the discovered credentials, the application displayed:

THM{born_to_hack!}
Failed Password Attempts

The Hydra dictionary attack made:

17

failed password attempts before finding the correct password.

Hydra

The command used was:

hydra -l admin -P passlist.txt www.onlineshop.thm http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V

This demonstrated a dictionary attack against an HTTP login form.

Task 4: Where to Go From Here

Completed the room and reviewed the next steps for continuing a cybersecurity learning journey.

Key Terminology
Scope — The exact systems and actions allowed during a security test.
Vulnerability — A hidden weakness that could be exploited by an attacker.
Exploit — A method or technique that takes advantage of a vulnerability.
Enumeration — Collecting information about systems, users, and services to identify potential weaknesses.
Credentials — Login details such as usernames and passwords.
Authentication — The process of verifying someone's identity during login.
Dictionary attack — Using a predefined wordlist to attempt to guess credentials.
Career Opportunities

The room introduced several offensive security roles:

Penetration Tester / Ethical Hacker
Vulnerability Researcher
Red Team Operator
Tools Used
Gobuster
Hydra
Web browser
Linux CLI
What I Learned
What offensive security is and why it is used.
How hackers think about systems from an adversarial perspective.
How directory enumeration can discover hidden functionality.
How vulnerabilities can be chained together.
How weak credentials can lead to unauthorized access.
How dictionary attacks work.
How to use Gobuster for web directory enumeration.
How to use Hydra for automated password testing.
The difference between vulnerabilities, exploits, enumeration, authentication, and credentials.
How offensive security techniques are applied in ethical and authorized environments.
