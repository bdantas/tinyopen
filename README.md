# tinyopen
Minimalistic xdg-utils replacement

# Purpose
Centralized management of all filetype associations ("preferred applications") via a simple text file

# Dependencies
- GNU/Linux with coreutils (e.g., Debian): **grep, file**
- GNU/Linux with busybox (e.g., Tiny Core Linux): **file**

# Installation
1. Put the `tinyopen` directory anywhere on your system
2. Run `tinyopen-setup` once* as regular user 

\* If you run Tiny Core Linux (or other GNU/Linux OS without filesystem persistence), run `tinyopen-setup` at each boot

# Usage
- Manage all your filetype associations by editing `tinyopenrc`
- Troubleshoot by running `tail -f /tmp/tinyopen.log` in a terminal and watching the output as you open files
