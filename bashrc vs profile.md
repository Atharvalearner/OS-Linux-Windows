.bashrc is a user-specific Bash shell configuration file that is executed whenever a new interactive, non-login Bash shell starts. It is commonly used to define aliases, shell functions, environment variables, and customize the command prompt. .profile is a user-specific login initialization file that runs once when the user logs in. It is typically used to set environment variables and update the PATH so they are available for the user's login session.





***# .bashrc:***

* a user-specific shell configuration file that is executed whenever a new interactive, non-login Bash shell starts.
* It is used to customize the shell environment.
* Location: Each user has their own .bashrc file: /home/username/.bashrc





***# .profile:***

* a user-specific login shell initialization file that runs when the user logs in.
* Unlike .bashrc, it executes once during login.
* Location: /home/username/.profile



***# Check kernel version: uname -r***

***# Check complete kernel info: uname -a***



**| --------------------------------------------------------------------------------- | --------------------------------------------- |**

**| .bashrc                                                                           | .profile                                      |**

**| --------------------------------------------------------------------------------- | --------------------------------------------- |**

| Runs for interactive non-login Bash shells                                        | Runs once when the user logs in               |

| Used for aliases, prompt, shell functions                                         | Used for login environment variables and PATH |

| Executed every time a new terminal window/tab opens (for Bash interactive shells) | Executed only at user login                   |

| --------------------------------------------------------------------------------- | --------------------------------------------- |



***# Easy Memory Trick***

.bashrc → Every new Bash terminal

.profile → At login

