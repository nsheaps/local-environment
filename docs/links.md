All files are symlinks to the needed files.
Generally these should be git ignored and direnv should make the symlinks when you check out the code and run direnv, however this repo hasn't been set up with direnv yet, so the symlinks are committed.

In git, hardlinks look like the target files, but soft links are treated as a simple file with
the path passed to `ls -s <path> <where to make the new link>` so git doesn't actually contain the secrets from those files or folders. You can confirm this by running `readlink <where the link is>` which will show you the path to the target file.

You may be scared, but deleting the symlinks in this folder will not delete the target files.

```bash
ln -s '../../.zshrc' .
ln -s '../../.zprofile' .
ln -s '../../.claude.json' .
ln -s '../../.commitronrc' .
ln -s '../../.gitconfig' .
ln -s '../../.profile' .
ln -s '../../.kube/' .
ln -s '../../.aws/' .
```