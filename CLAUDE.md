# Grand Oral — Fiche récap

## Infos pratiques

| | |
|---|---|
| **Date** | Lundi 22 juin 2026 |
| **Heure** | 10h00 (arriver 30 min avant → **9h30**) |
| **Lieu** | Institution Ste Jeanne d'Arc, 15 rue du Chanoine Brun, 68100 Mulhouse |
| **Durée** | 0h20 de passage (20 min) |
| **Commission** | ST2S23 |
| **À apporter** | Convocation + pièce d'identité |

## Mes deux questions

**Question 1** : En quoi le développement de l'intelligence artificielle dans les contenus pornographiques constitue-t-il un enjeu de santé publique pour la protection des jeunes ?

**Question 2** : Dans quelle mesure l'exposition précoce à la pornographie constitue-t-elle un enjeu de santé publique chez les adolescents ?

## Déroulé de l'épreuve

### 1. Préparation (20 min)

Je ne sais pas à l'avance laquelle des deux questions sera choisie par le jury : je dois donc préparer des notes pour **les deux questions**, pas une seule. C'est pendant ce temps que je prépare mes notes/brouillon pour l'exposé.

### 2. Le jury choisit une des deux questions

### 3. Exposé (10 min)

Debout, sans notes, je présente la question tirée et ma réponse argumentée. Le jury n'interrompt pas.

### 4. Entretien (10 min)

Le jury pose des questions principalement sur le texte que j'ai récité (l'exposé), et éventuellement un peu sur mon projet d'orientation. J'ai le droit d'utiliser le **tableau** pour répondre/illustrer mes réponses pendant cette partie.

**Jury** : généralement 2 personnes (prof de spécialité + un autre membre).

## Ce qui compte le plus

- Clarté et structure du propos (plus que la quantité d'infos)
- Capacité à argumenter, à rester calme même sans réponse parfaite
- Aisance à l'oral : regarder le jury, articuler, ne pas réciter par cœur
- Voir aussi `Grand Oral/Grille d'évaluation officielle.md` pour les critères précis du jury (qualité orale, prise de parole en continu, connaissances, interaction, argumentation)

## Dossier "Grand Oral" — état actuel

Contenu du dossier `Grand Oral/` à ce jour :

- `Grand Oral — Plan de travail.md` — checklist de suivi
- `Grille d'évaluation officielle.md` — grille officielle (annexe 1, notes de service 2020-036/037), vérifiée conforme au document du ministère
- `Question 1 — IA et pornographie.md` — exposé complet, terminé : chiffres ARCOM corrigés, définition de "deepfake" en intro, distinction loi du 30/07/2020 (vérification d'âge) vs loi SREN du 21/05/2024 art. 226-8-1 (sanctionne la diffusion de deepfakes sexuels), limite VPN
- `Question 1 — Plan mémorisable.md` — version mots-clés/fil conducteur de Question 1, à jour avec le texte
- `Question 2 — Exposition précoce à la pornographie.md` — exposé complet (avec résultats de questionnaire personnel, 41 répondants), **pas encore relu/fact-checké**, **pas encore de plan mémorisable**

## À préparer avant lundi

- [x] Plan détaillé / texte de l'exposé pour la Question 1
- [x] Plan mémorisable (mots-clés) pour la Question 1
- [ ] Relire et fact-checker le texte de la Question 2 (comme fait pour Q1)
- [ ] Plan mémorisable (mots-clés) pour la Question 2
- [ ] Lien clair entre chaque question et mon projet d'orientation (pas encore fait, à faire en priorité)
- [ ] Anticiper 5-6 questions probables du jury sur chaque sujet (texte récité + un peu d'orientation)
- [ ] S'entraîner à voix haute, debout, sans notes, chronométré (10 min) pour chaque question
- [ ] Réfléchir à ce que je pourrais utiliser/écrire au tableau pendant l'entretien

---

## Notes techniques pour Claude (lire avant de modifier des fichiers de ce repo)

**Bug connu et récurrent dans ce repo** : les outils Write/Edit peuvent indiquer un succès alors que le fichier réellement visible depuis le shell (et donc ce qui part dans `git commit`/`git push`) reste tronqué — coupé en plein mot, parfois après plusieurs paragraphes. Ce bug s'est produit plusieurs fois sur `CLAUDE.md` et sur les fichiers du dossier `Grand Oral/`, y compris après des commits déjà effectués.

**Protocole obligatoire après toute modification de fichier important (avant de commit) :**
1. Après un Write/Edit, vérifier via bash : `wc -l "<fichier>"` et `tail -5 "<fichier>"` — la fin doit être une phrase complète, pas un mot coupé.
2. Si le contenu semble correct, `git add` + `git commit`, puis vérifier le **blob committé** lui-même : `git show HEAD:"<fichier>" | wc -l` et `tail -5` — ne pas se fier uniquement au working tree.
3. Si une troncature est détectée (mot coupé en fin de fichier, nombre de lignes anormalement bas), **reconstruire le fichier entier via un heredoc bash** (`cat > "fichier" << 'EOF' ... EOF`) plutôt que de ré-essayer Write/Edit — c'est la méthode qui a fonctionné à chaque fois pour corriger ce bug.

**Réseau** : le sandbox n'a pas accès à GitHub (`git fetch`/`push` renvoient une erreur 403 du proxy). Je peux committer localement mais l'utilisateur doit faire `git pull --rebase` puis `git push` depuis sa machine à chaque fois.

**Fichiers avec différences de fin de ligne (CRLF/LF)** : plusieurs fichiers hors du dossier Grand Oral (chapitres 24 à 30, Philosophie, STSS Notions importantes) apparaissent modifiés dans `git status` à cause d'un bruit de fin de ligne sans rapport avec mon travail — ne pas les committer par erreur, ce n'est pas un vrai changement de contenu.
