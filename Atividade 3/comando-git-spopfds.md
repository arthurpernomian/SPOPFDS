## Main

### 1.1 Introduction Sequence

#### 1.1.1 Introduction to Git Commits
```bash
git commit
git commit
```

#### 1.1.2 Branching in Git
```bash
git branch bugFix
git checkout bugFix
```

#### 1.1.3 Merging in Git
```bash
git checkout -b bugFix
git commit
git checkout main
git commit
git merge bugFix
```

#### 1.1.4 Rebase Introduction
```bash
git checkout -b bugFix
git commit
git checkout main
git commit
git checkout bugFix
git rebase main
```

### 1.2 Ramping Up

#### 1.2.1 Detach yo' HEAD
```bash
git checkout C4
```

#### 1.2.2 Relative Refs (^)
```bash
git checkout bugFix^
```

#### 1.2.3 Relative Refs #2 (~)
```bash
git branch -f main C6
git checkout HEAD~1
git branch -f bugFix HEAD~1
```

#### 1.2.4 Reversing Changes in Git
```bash
git reset HEAD~1
git checkout pushed
git revert HEAD
```

### 1.3 Moving Work Around

#### 1.3.1 Cherry-pick Intro
```bash
git cherry-pick C3 C4 C7
```

#### 1.3.2 Interactive Rebase Intro
```bash
git rebase -i overHere
```

### 1.4 A Mixed Bag

#### 1.4.1 Grabbing Just 1 Commit
```bash
git checkout main
git cherry-pick bugFix
```

#### 1.4.2 Juggling Commits
```bash
git rebase -i HEAD~2
git commit --amend
git rebase -i HEAD~2
git rebase caption main
```

#### 1.4.3 Juggling Commits #2
```bash
git checkout main
git cherry-pick C2
git commit --amend
git cherry-pick C3
```

#### 1.4.4 Git Tags
```bash
git tag v1 side~1
git tag v0 main~2
git checkout v1
```

#### 1.4.5 Git Describe
```bash
git describe bugFix
git describe main
git describe v1
git describe C3
git describe C6
git describe HEAD~3
git commit
```

### 1.5 Advanced Topics

#### 1.5.1 Rebasing Multiple Branches
```bash
git rebase main bugFix
git rebase bugFix side
git rebase side another
git rebase another main
```

#### 1.5.2 Multiple Parents
```bash
git branch bugWork main^^2^
```

#### 1.5.3 Branch Spaghetti
```bash
git checkout one
git cherry-pick C4 C3 C2
git checkout two
git cherry-pick C5 C4 C3 C2
git branch -f three C2
```

## Remote

### 2.1 Push & Pull -- Git Remotes!

#### 2.1.1 Clone Intro
```bash
git clone
```

#### 2.1.2 Remote Branches
```bash
git commit
git checkout o/main
git commit
```

#### 2.1.3 Git Fetch
```bash
git fetch
```

#### 2.1.4 Git Pull
```bash
git pull
```

#### 2.1.5 Faking Teamwork
```bash
git clone
git fakeTeamwork 2
git commit
git pull
```

#### 2.1.6 Git Push
```bash
git commit
git commit
git push
```

#### 2.1.7 Diverged History
```bash
git clone
git fakeTeamwork
git commit
git pull --rebase
git push
```

#### 2.1.8 Locked Main
```bash
git reset --hard o/main
git checkout -b feature C2
git push origin feature
```

### 2.2 To Origin And Beyond -- Advanced Git Remotes!

#### 2.2.1 Push Main!
```bash
git fetch
git rebase o/main side1
git rebase side1 side2
git rebase side2 side3
git rebase side3 main
git push
```

#### 2.2.2 Merging with Remotes
```bash
git checkout main
git pull
git merge side1
git merge side2
git merge side3
git push
```

#### 2.2.3 Remote Tracking
```bash
git checkout -b side o/main
git commit
git pull --rebase
git push
```

#### 2.2.4 Git push Arguments
```bash
git push origin main
git push origin foo
```

#### 2.2.5 Git push Arguments -- Expanded!
```bash
git push origin main^:foo
git push origin foo:main
```

#### 2.2.6 Fetch Arguments
```bash
git fetch origin C3:foo
git fetch origin C6:main
git checkout foo
git merge main
```

#### 2.2.7 Source of Nothing
```bash
git push origin :foo
git fetch origin :bar
```

#### 2.2.8 Pull Arguments
```bash
git pull origin C3:foo
git pull origin C2:side
```
