# zama-commit
for i in {1..20}
do
  echo "Commit $i line" >> README.md
  git add README.md
  GIT_AUTHOR_DATE="$(date -d "$i days ago" +"%Y-%m-%dT12:00:00")" \
  GIT_COMMITTER_DATE="$(date -d "$i days ago" +"%Y-%m-%dT12:00:00")" \
  git commit -m "Commit $i"
done
git push
