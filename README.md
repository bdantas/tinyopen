# tinyopen
Minimalistic xdg-utils replacement

# Purpose
Centralized management of all filetype associations ("preferred applications") via a simple text file

# Dependencies
- GNU/Linux with coreutils (e.g., Debian): **grep, file**
- GNU/Linux with busybox (e.g., Tiny Core Linux): **file**

# Installation
1. Put the `tinyopen` directory anywhere on your system
2. Run `/path/to/tinyopen/tinyopen-setup` once* as regular user 

\* If you run Tiny Core Linux, run `/path/to/tinyopen/tinyopen-setup` at each boot (e.g., via a startup job in `~/.X.d/`)

# Usage
- Manage all your filetype associations by editing `tinyopenrc`
- Troubleshoot by running `tail -f /tmp/tinyopen.log` in a terminal and watching the output as you open files

# How it works: 3 types of applications
1. Many big applications (e.g., Firefox, Thunderbird) keep their own list of filetype associations. For these applications, go to Edit -> Preferences (or the like) and manually associate all filetypes with the `tinyopen` script. This is the only one of the three types of applications that requires manual intervention.
2. Some applications are hardwired use `xdg-open`. The `tinyopen-setup` script makes `xdg-open` be a link to `tinyopen`. Easy!
3. Some applications are hardwired to look in user's `mimeapps.list` to figure out filetype associations. The included `mimeapps.list` file associates every existing filetype with `mimeapps-open`, which in turn is a link to the `tinyopen` script. The `tinyopen-setup` script takes care of all of this for you.
