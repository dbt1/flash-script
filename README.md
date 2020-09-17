## Flash script for supported set top boxes

Script was forked as template from https://github.com/neutrino-hd/meta-hd51

## Extraction was done as follows:
```bash
$ git clone https://github.com/neutrino-hd/meta-hd51.git flash-script
$ cd flash-script
$ FILE='recipes-images/base-files/files/flash'
$ git filter-branch -f --prune-empty --index-filter "
                        git read-tree --empty
                        git reset \$GIT_COMMIT -- $FILE
                "         -- --all -- $FILE
$ git mv recipes-images/base-files/files/flash flash
```
Delete old directory:
```bash
$ rm -r recipes-images/base-files/files
$ git commit -m "moved flashscript into root directory"
```
