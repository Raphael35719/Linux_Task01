# Task Notes

## Source task
**Practical Task: Secure File Management & User Configuration on Kali Linux**  
Objective: demonstrate fundamental Linux filesystem and user-management commands by creating a secure workspace for a new user and organizing files with appropriate structure and permissions.

## Requirements from the supplied document
1. Create user `agent007` with a home directory, `/bin/bash` shell, and membership in the `sudo` group.
2. Set the user's password and switch to the new account.
3. Create `/home/agent007/mission/` with `intel/` and `ops/backup/`.
4. In `intel/`, create `targets.txt`, `routes.txt`, and `keys.txt`; save `ls`, `ls -l`, and `ls -la` output to `listing1.txt`, `listing2.txt`, and `listing3.txt`.
5. Copy `routes.txt` to `ops/backup/`; remove `keys.txt` from `intel/`.
6. Set `targets.txt` to owner read/write, group read-only, and no permissions for others.
7. Remove the backup copy of `routes.txt`, then recover it from `intel/`.
8. As root/admin, change ownership of `intel/targets.txt` to another user (for example `root`), then return to `agent007` and inspect with `ls -l`.
9. Explain `chmod`, `ls -l`, and `useradd`.

## Privilege constraint
The supplied document says not to use root for file operations; a new user must be created and all steps except `useradd` and `usermod` must be performed using that user. It separately specifies an advanced ownership step “as root.” Follow your instructor's interpretation for this explicit exception and document the account used for each step.

## Permission target
`chmod 640 targets.txt` corresponds to owner `rw-`, group `r--`, others `---`.

## Definitions
- `useradd`: creates a user account; `-m` creates a home directory, `-s /bin/bash` selects the shell, and `-G sudo` adds the user to the supplementary `sudo` group.
- `ls -l`: lists files in long format, including permission bits, owner, group, size, and modification time.
- `chmod`: changes file permission bits.
