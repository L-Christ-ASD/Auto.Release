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

**Les versions ultérieures** : Pour les versions ultérieures, le numéro de version sera incrémenté en fonction des commits. Par exemple:

**feat** : Une nouvelle fonctionnalité, entraînant un incrément de version mineur (1.1.0).

**fix** : correction d’un "bug", entraînant un incrément de version de correctif (1.0.1).

**BREAKING CHANGE** (Changement cassant) : Un incrément de version majeur (2.0.0).

Tant que vos commits suivent les normes de commit conventionnelles, release-please-action déterminera automatiquement la version appropriée. S’il n’y a pas encore de balises de version, il créera la première pour vous lorsque vous pousserez les modifications vers la branche principale.


## Que fait-il ? 

Ce workflow automatise le processus de publication de nouvelles versions de votre projet chaque fois que vous poussez des modifications dans la branche principale. Il utilise l'action release-please de Google pour gérer la création des pull requests de publication et des versions sur GitHub.

Cette étape utilise l'action release-please de Google pour automatiser le processus de publication.

Le jeton (token) utilise un jeton d'accès personnel stocké comme un secret dans les secrets GitHub (MY_RELEASE_TEST).

Le type de publication (release-type) est défini sur simple, qui est l'une des stratégies disponibles dans release-please.

skip-github-release: false indique que la publication GitHub ne doit pas être ignorée.

skip-github-pull-request: false indique que la pull request GitHub ne doit pas être ignorée.



## exemple de workflow:

```
name: release after debug
    

on:
    push:
      branches:
        - main
  
permissions:
    contents: write
    pull-requests: write
  
  
jobs:
    release-test:
      runs-on: ubuntu-latest

      steps:
        - name: "Build & test"
          run: |
            echo "done!"

        - uses: L-Christ-ASD/automatic-Release-action@v4
          with:
            # this assumes that you have created a personal access token
            # (PAT) and configured it as a GitHub action secret named
            # `MY_RELEASE_PLEASE_TOKEN` (this secret name is not important).
            token: ${{ secrets.MY_RELEASE_TEST}}
            # this is a built-in strategy in release-please, see "Action Inputs"
            # for more options
            release-type: simple
            skip-github-release: false
            skip-github-pull-request: false

```

