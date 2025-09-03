# TP Git & GitHub

[Adresse du repository
](https://github.com/Nefferou/Capsule-Git)

## Étape 1 – Créer un projet GitHub et le cloner
1. Installer [Git](https://git-scm.com/downloads) sur votre poste
2. Connectez-vous à [GitHub](https://github.com) et créez un **nouveau dépôt** (vide, sans README).  
3. Copiez l’URL de votre projet (bouton vert **Code** → HTTPS).  
4. Sur votre PC, ouvrez un terminal et tapez :

   ```bash
   git clone https://github.com/<utilisateur>/<projet>.git
   ```
Vous avez maintenant une copie du projet en local.

---

## Étape 2 – Créer, ajouter et enregistrer un fichier
1. Créez un fichier `hello.txt` avec le texte : `Bonjour Git !` dans votre Local Repository.
2. Vérifiez l’état du projet :

   ```bash
   git status
   ```

3. Ajoutez et enregistrez ce fichier :

   ```bash
   git add hello.txt
   git commit -m "Ajout du fichier hello.txt"
   ```
---

## Étape 3 – Envoyer sur GitHub
1. Envoyez votre modification :

   ```bash
   git push
   ```

2. Vérifiez sur GitHub que `hello.txt` est bien présent dans votre Remote Repository.

---

## Étape 4 – Travailler avec une branche
1. Créez et basculez sur une nouvelle branche `update-hello-file` :

   ```bash
   git checkout -b update-hello-file
   ```

2. Modifiez `hello.txt` → ajoutez votre prénom.  
3. Sauvegardez vos changements :

   ```bash
   git add hello.txt
   git commit -m "Mise à jour du message avec prénom"
   git push origin update-hello-file
   ```

---

## Étape 5 – Fusionner la branche
1. Retournez sur la branche principale :

   ```bash
   git checkout main
   ```
2. Fusionnez la branche :

   ```bash
   git merge update-hello-file
   git push
   ```

---


## Étape 6 – Collaborer sur un projet

### 6.1 Travailler à plusieurs (cas simple)
1. Un étudiant crée un projet sur GitHub et le partage avec son binôme (ajout comme **collaborateur** dans GitHub).  
2. Les deux étudiants **clonent** le même projet sur leur ordinateur :  

   ```bash
   git clone https://github.com/<utilisateur>/<projet>.git
   ```  
3. Étudiant A ajoute un fichier `fileA.txt`, commit et push :  
   ```bash
   git add fileA.txt
   git commit -m "Ajout du fichier A"
   git push
   ```  
4. Étudiant B récupère les modifications avec :  
   ```bash
   git pull
   ```  
Le fichier `fileA.txt` apparaît aussi chez l’étudiant B.  

---

### 6.2 Bonus – Simuler un conflit
1. Étudiant A modifie la première ligne de `hello.txt` puis :  
   ```bash
   git add hello.txt
   git commit -m "Modification par A"
   git push
   ```  
2. Étudiant B modifie **la même ligne** de `hello.txt` puis :  
   ```bash
   git add hello.txt
   git commit -m "Modification par B"
   git push
   ```  
Git refuse le `push` car le fichier a changé en ligne.  

3. Étudiant B fait un `pull` :  
   ```bash
   git pull
   ```  
Git signale un **conflit** dans `hello.txt`.  

4. Résolvez le conflit en ouvrant le fichier et en choisissant quelle version garder (supprimer `<<<<<<<`, `=======`, `>>>>>>>`).  

5. Sauvegardez et validez la résolution :  
   ```bash
   git add hello.txt
   git commit -m "Résolution du conflit"
   git push
   ```

---

## Bonus 1 – Ajouter un projet local sur GitHub
1. Créez un dossier vide et initialisez Git :

   ```bash
   mkdir projet-local
   cd projet-local
   git init
   ```
2. Ajoutez un fichier `readme.md`, puis :
   ```bash
   git add readme.md
   git commit -m "Initialisation du projet local"
   ```
3. Créez un dépôt vide sur GitHub.  
4. Reliez votre projet local :
   ```bash
   git remote add origin https://github.com/<utilisateur>/<projet>.git
   git branch -M main
   git push -u origin main
   ```

---

## Bonus 2 – Revenir en arrière
- **Annuler une modification locale** :
  ```bash
  git restore <fichier>
  ```
- **Annuler un commit sans casser l’historique** :
  ```bash
  git revert <id_commit>
  ```
- **Revenir radicalement à un commit précis (⚠️ dangereux)** :
  ```bash
  git reset --hard <id_commit>
  ```

---

## Objectifs atteints
- Cloner un projet GitHub  
- Ajouter, commit et push des fichiers  
- Créer et fusionner des branches  
- Résoudre un conflit simple  
- Publier un projet local sur GitHub  
- Utiliser restore, revert et reset  

Félicitations, vous avez réalisé vos premiers pas avec Git et GitHub !
