# s09_challenge_Latest  

![just debug steps of execution](https://github.com/L-Christ-ASD/s09_challenge_Latest/actions/workflows/test.yml/badge.svg)
![release after debug](https://github.com/L-Christ-ASD/s09_challenge_Latest/actions/workflows/release.yml/badge.svg)


### CI/CD


1. créez une action Github personnalisée en vous basant sur une des deux actions :  
   
   * [Exemple-actions-1](https://github.com/o-devops/debug) 
   * [Exemple-actions-1](https://github.com/profy12/lowercase-action) 

2. publiez une première version fonctionnelle pointée par un tag :  
   
   * [Tag](https://o-devops.github.io/doc/git/git-tag/)

3. publiez l'action sur le marketplace via une release Github (un raccourci va apparaître pour la publication directement dans votre dépôt)  

### Bonus :  
Essayez de publier automatique vos release, la méthode est libre,  voici quelques liens vers des automatisation :  
   * [Release-exemple-1](https://github.com/marketplace/actions/release-please-action )   
   * [Release-exemple-2](https://github.com/marketplace/actions/automatic-releases ) 


## Documentations autour de la CI/CD et de Github  

[Documentation](https://o-devops.github.io/doc/git/git-tag/)



***Good to know***:  

Versions ultérieures : Pour les versions ultérieures, le numéro de version sera incrémenté en fonction des commits. Par exemple:

feat : Une nouvelle fonctionnalité, entraînant un incrément de version mineur (1.1.0).

fix : correction d’un "bug", entraînant un incrément de version de correctif (1.0.1).

CHANGEMENT CASSANT : Un incrément de version majeur (2.0.0).

Tant que vos commits suivent les normes de commit conventionnelles, release-please-action déterminera automatiquement la version appropriée. S’il n’y a pas encore de balises de version, il créera la première pour vous lorsque vous pousserez les modifications vers la branche principale.

Souhaitez-vous plus de détails sur la façon de configurer les commits conventionnels ou autre chose ? Tenez moi informé!


## Summary  

This workflow automates the process of releasing new versions of your project whenever you push changes to the main branch. It uses Google’s release-please-action to handle the creation of release pull requests and GitHub releases.

This step uses the release-please action from Google to automate the release process.

The token input uses a personal access token stored as a secret in GitHub secrets (MY_RELEASE_TEST).

The release-type is set to simple, which is one of the strategies available in release-please.

skip-github-release: false indicates that the GitHub release should not be skipped.

skip-github-pull-request: false indicates that the GitHub pull request should not be skipped.



