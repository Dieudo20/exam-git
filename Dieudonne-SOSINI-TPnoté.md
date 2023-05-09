SOSINI DIEUDONNE 


SOSINI DIEUDONNE 


## Création du dépôt de code (2 pts)

->  git clone https://github.com/Dieudo20/exam-git.git
-> la difference entre le depot local et le depot distant, est que le depot dépôt local contient une copie complète de l'historique du dépôt distant, tandis que le dépôt distant contient la version actuelle du code et de l'historique
- > pour verifier la branche courante on utilise la commande "git branch" et cette branche courante est indiquée par un astérisque.      

## Ajout d'un fichier dans l'historique (2 pts)

*sosin@Dieudonne-S MINGW64 ~/Documents/Partiel-GIT/exam-git (main)
$ git add Dieudonne-SOSINI-TPnoté.md

sosin@Dieudonne-S MINGW64 ~/Documents/Partiel-GIT/exam-git (main)
$ git commit -m
error: switch `m' requires a value

sosin@Dieudonne-S MINGW64 ~/Documents/Partiel-GIT/exam-git (main)
$ git commit -m Dieudonne-SOSINI-TPnoté.md
[main d919d0c] Dieudonne-SOSINI-TPnoté.md
 1 file changed, 12 insertions(+)
 create mode 100644 "Dieudonne-SOSINI-TPnot\303\251.md"

sosin@Dieudonne-S MINGW64 ~/Documents/Partiel-GIT/exam-git (main)
$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working tree clean


#### Branche `ansible` (2 pts)

- > sosin@Dieudonne-S MINGW64 ~/Documents/Partiel-GIT/exam-git (main)
$ git checkout -b ansible
Switched to a new branch 'ansible'
- > mkdir ansible

-> cp TP\ noté\ -\ TP\ noté\ -\ Ansible/mes_hosts ansible/
cp TP\ noté\ -\ TP\ noté\ -\ Ansible/mon_playbook.yml ansible/
git add ansible/mes_hosts ansible/mon_playbook.yml
git commit -m "Add mes_hosts and mon_playbook files to ansible branch"
nano ansible/mes_hosts
git add ansible/mes_hosts ansible/mon_playbook.yml
git commit -m "Update mes_hosts and mon_playbook files with environment description"
git push origin ansible



####  Préparation d'un hook de pre-push (3 pts)

- > git checkout -b hook
mkdir scripts
touch scripts/pre-push
#!/bin/sh

echo "Liste des derniers commits :"
echo "$(git log --oneline -n 5)"

chmod +x scripts/pre-push