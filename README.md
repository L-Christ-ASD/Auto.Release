# s09_challenge_Latest  

![just debug execution](https://github.com/L-Christ-ASD/s09_challenge_Latest/actions/workflows/test.yml/badge.svg)
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

