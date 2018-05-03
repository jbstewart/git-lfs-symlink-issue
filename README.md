# Repo to recreate issue with git-lfs lock command 

The git-lfs unlock command fails if there is a symlinked folder in the parent path of the repo.

## Steps to recreate
- `mkdir parent`
- `cd parent`
- `mkdir outer1`
- `git clone https://github.com/jbstewart/git-lfs-symlink-issue.git`
- `ln -s git-lfs-symlink-issue outer2`
- `cd outer2`
- `git lfs lock folder1/folder2/TestImage.png`

## But this works...
- `cd ../outer1/git-lfs-symlink`
- `git lfs lock folder1/folder2/TestImage.png`




