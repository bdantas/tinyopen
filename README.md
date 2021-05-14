# tinyopen
Minimalistic xdg-utils replacement

# Purpose
Centralized management of all filetype associations ("preferred applications") via a simple text file

# Dependencies
- GNU/Linux with coreutils (e.g., Debian): **grep, file**
- GNU/Linux with busybox (e.g., Tiny Core Linux): **file**

# Installation
1. Put the `tinyopen` directory anywhere on your system
2. Run `/path/to/tinyopen/tinyopen-setup` once* as regular (non-root) user 

\* If you're on Tiny Core Linux, you need to run it at each boot (e.g., via a startup job in `~/.X.d/`)

# Usage
- Manage all your filetype associations by editing `tinyopen.conf`
- Troubleshoot by running `tail -f /tmp/tinyopen.log` in a terminal and watching the output as you open files

# How it works: 3 types of applications
1. Many big applications (e.g., Firefox, Thunderbird) keep their own list of filetype associations. For these applications, go to Edit -> Preferences (or similar) and manually associate all filetypes with `tinyopen`. This is the only one of the three types of applications that requires manual intervention.
2. Some applications are hardwired use `xdg-open` or `xdg-email`. After running `tinyopen-setup`, `xdg-open` and `xdg-email` are simply symlinks to `tinyopen`.
3. Other applications are hardwired to look in user's `mimeapps.list` to figure out filetype associations. The included `mimeapps.list` associates every existing filetype with `tinyopen-alias`. The `tinyopen-setup` script puts links to the included `mimeapps.list` in the appropriate places, and also creates `tinyopen-alias` as a link to `tinyopen`.

# Motivation
I created `tinyopen` because I don't want to juggle 3 separate systems of filetype associations. After running `tinyopen-setup` and rigging my big applications to open everything with `tinyopen` (see #1 in the "How it works" section above), now I can manage *all* filetype associations for *all* applications by editing *one* simple text file: `tinyopen.conf`
