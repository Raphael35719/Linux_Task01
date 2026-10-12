# Command Workflow — Kali Linux

Follow the assignment's privilege rule: create/configure the user with admin privileges, then do the normal file operations as `agent007`. Replace no names unless your instructor approves.

## 1. Create the user (admin account)
```bash
sudo useradd -m -s /bin/bash -G sudo agent007
sudo passwd agent007
```
If the account already exists, do not rerun `useradd`; inspect it first with `id agent007` and `getent passwd agent007`.

## 2. Switch to `agent007`
```bash
su - agent007
whoami
id
```
Confirm `whoami` prints `agent007`. Enter the password when prompted; do not include passwords in screenshots or Git history.

## 3. Create the workspace
```bash
mkdir -p ~/mission/intel ~/mission/ops/backup
cd ~/mission
pwd
find . -maxdepth 3 -type d -print
```
Expected folders include `intel`, `ops`, and `ops/backup`.

## 4. Create files and save listings
```bash
cd ~/mission/intel
touch targets.txt routes.txt keys.txt
ls > listing1.txt
ls -l > listing2.txt
ls -la > listing3.txt
cat listing1.txt
cat listing2.txt
cat listing3.txt
```
The three listing files are created in `intel/`. Since each listing command writes into a file in the same directory, the later listings may include the listing files themselves.

## 5. Copy and remove files
```bash
cp routes.txt ../ops/backup/
rm keys.txt
ls -l
ls -l ../ops/backup/
```
Only remove the specifically requested `keys.txt`; double-check the path before using `rm`.

## 6. Set and verify `targets.txt` permissions
```bash
chmod 640 targets.txt
ls -l targets.txt
stat -c '%A %a %U:%G %n' targets.txt
```
Expected mode is `640` (`-rw-r-----`): owner read/write, group read, others no access.

## 7. Simulate removal and recover the backup
```bash
rm ../ops/backup/routes.txt
ls -l ../ops/backup/
cp routes.txt ../ops/backup/
ls -l ../ops/backup/routes.txt
```
This deliberately removes the backup copy, then restores it from `intel/routes.txt`.

## 8. Ownership change (admin step)
The assignment asks for the owner of `intel/targets.txt` to be changed to another user (for example, `root`), then to switch back to `agent007` and inspect with `ls -l`. From an account with sudo privileges, run:
```bash
sudo chown root:root /home/agent007/mission/intel/targets.txt
sudo -u agent007 ls -l /home/agent007/mission/intel/targets.txt
```
If your instructor specifically requires switching sessions, use `exit` to leave `agent007`, run the `chown` command from the admin account, then `su - agent007` and run:
```bash
ls -l ~/mission/intel/targets.txt
```
Note: after ownership is changed to `root`, `agent007` may no longer be able to modify the file. That is the expected observation; do not try to bypass permissions unless instructed.

## 9. Final verification
```bash
whoami
find ~/mission -maxdepth 3 -printf '%M %u:%g %p\n'
ls -l ~/mission/intel
ls -l ~/mission/ops/backup
```
Capture screenshots for the evidence folder and complete `docs/VERIFICATION_CHECKLIST.md`.
