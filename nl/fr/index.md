---

copyright:
  years: 2015, 2017
lastupdated: "2017-06-20"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}

# Python
{: #python_runtime}

L'environnement d'exécution Python dans {{site.data.keyword.Bluemix}} repose sur le pack python_buildpack.
Le pack python_buildpack fournit un environnement d'exécution complet pour les applications Python 2 et Python 3.
{: shortdesc}

Le pack python_buildpack sera utilisé si le répertoire racine de votre appli contient un fichier requirements.txt ou setup.py.

## Application de démarrage
{: #starter_application}

{{site.data.keyword.Bluemix}} propose une application de démarrage Python.  L'application de démarrage Python est une appli Python simple qui peut servir de modèle pour votre appli. Vous pouvez expérimenter cette application et effectuer des modifications puis les envoyer par commande push vers l'environnement {{site.data.keyword.Bluemix}}.  Voir [Utilisation des applications de démarrage](/docs/cfapps/starter_app_usage.html) pour obtenir de l'aide.

## Versions d'environnement d'exécution
{: #runtime_versions}

Vous pouvez spécifier la version de Python à utiliser par votre appli en définissant python-versionnumber dans le fichier runtime.txt se trouvant à la racine de votre application. Par exemple :

```
python-3.6.0
```
{: codeblock}

Si aucune version n'est spécifiée, la version 2.7.13 est sélectionnée par défaut.

### Versions disponibles :
{: #available_versions}

Les versions de Python suivantes sont disponibles dans le [pack de construction Python](https://github.com/cloudfoundry/python-buildpack/releases/tag/v1.5.15) qui est installé dans {{site.data.keyword.Bluemix}} :

* 2.7.12
* 2.7.13
* 3.3.5
* 3.3.6
* 3.4.5
* 3.4.6
* 3.5.2
* 3.5.3
* 3.6.0

Si votre application requiert une version de Python qui n'est pas répertoriée, vous pouvez
utiliser le [pack de construction Python](https://github.com/cloudfoundry/python-buildpack) externe pour
la déployer.

# rellinks
{: #rellinks notoc}
## general
{: #general notoc}
* [Cloud Foundry buildpack for Python](https://github.com/cloudfoundry/python-buildpack)
