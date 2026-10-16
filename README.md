# Loki et le Passage des Étoiles

Site statique de la BD familiale avec Hélia, Noé et Loki. Cette première version contient une page minimale pour valider la publication automatique.

## Structure

- `site/` : seuls fichiers publiés, avec `site/index.html` comme page d’entrée.
- `.github/workflows/deploy-ovh.yml` : publication GitHub Actions par SFTP.
- `README.md` : documentation du dépôt, non publiée.

Ce projet ne nécessite ni installation ni étape de build.

## Publication

Adresse : https://nogues.app/bd-loki-etoile/

Les modifications sont proposées par pull request vers `main`. Leur fusion déclenche l’envoi de `site/` uniquement vers `www/bd-loki-etoile` sur OVHcloud.

Configurer les secrets GitHub `OVH_SFTP_HOST`, `OVH_SFTP_USER` et `OVH_SFTP_PASSWORD`. S’ils sont absents, le workflow ignore la publication et affiche un avertissement.

Le workflow ajoute ou remplace les fichiers, sans supprimer ceux du serveur. Tout fichier devenu obsolète doit être supprimé manuellement dans `www/bd-loki-etoile`.

Après la fusion, vérifier l’exécution dans l’onglet **Actions**, puis la page publiée sur ordinateur et sur mobile.
