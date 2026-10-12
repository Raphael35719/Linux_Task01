# Verification Checklist

Mark an item only after running the command and checking the result.

- [ ] `agent007` exists and has a home directory.
- [ ] `agent007` uses `/bin/bash` and belongs to the `sudo` group.
- [ ] Normal task operations were performed as `agent007`.
- [ ] `~/mission/intel` and `~/mission/ops/backup` exist.
- [ ] `targets.txt`, `routes.txt`, and `keys.txt` were created in `intel/`.
- [ ] `listing1.txt`, `listing2.txt`, and `listing3.txt` contain the requested listing outputs.
- [ ] `routes.txt` was copied into `ops/backup/`.
- [ ] `keys.txt` was removed from `intel/`.
- [ ] `targets.txt` has mode `640` / permissions `-rw-r-----`.
- [ ] Backup `routes.txt` was removed and successfully restored.
- [ ] Ownership of `targets.txt` was changed as required, and the result was observed as `agent007`.
- [ ] Evidence screenshots are saved with descriptive filenames.
- [ ] Original assignment Word document is present in `submission/`.
- [ ] All README files are accurate and no passwords/secrets are included.
- [ ] Repository has been committed and pushed to GitHub.
