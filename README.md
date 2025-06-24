# git-town-child-sync-issue-demo

# create root branch
git town hack a
echo a > a.txt
git add .
git commit -m "a"

# create child
git town append b
echo b > b.txt
git add .
git commit -m "b"

# create grand child #1
git town append c1
echo c1 > c1.txt
git add .
git commit -m "c1"

git checkout b

# create grand child #2
git town append c2
echo c2 > c2.txt
git add .
git commit -m "c2"

# propose root
git checkout a
git town propose

# adjust root
echo a1 > a.txt
echo a2 >> a.txt
git add .
git commit -m "a"
git town sync

# ship root (or use GH)
git town ship

# sync grand child #1 -> all fine
git checkout c1
git town sync

# sync grand child #2 -> adds commit
git checkout c2
git town sync
