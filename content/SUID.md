SUID (set user ID) is a [[Linux]] feature to allow execution of specific binaries as other users.

When an SUID binary is executed, the RUID (real UID) keeps the user's value and the EUID (effective UID) changes to the owner of the file (usually root). For example, when `sudo` is executed, it conducts checks and sets the EUID to root, then runs the command as root.

This can be abused if SUID binaries can allow for command execution or file read without proper control.
