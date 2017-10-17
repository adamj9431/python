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

{{site.data.keyword.Bluemix}} の Python ランタイムには python_buildpack が採用されています。
python_buildpack は、Python 2 と Python 3 の両方のアプリケーションのための完全なランタイム環境を提供します。
{: shortdesc}

python_buildpack は、アプリケーションのルート・ディレクトリーに requirements.txt ファイルまたは setup.py ファイルが含まれている場合に使用されます。

## スターター・アプリケーション
{: #starter_application}

{{site.data.keyword.Bluemix}} には、Python スターター・アプリケーションが用意されています。Python スターター・アプリケーションは、アプリケーションに使用できるテンプレートを提供する、シンプルな Python アプリケーションです。スターター・アプリケーションを試し、{{site.data.keyword.Bluemix}} 環境に対して変更を行い、プッシュすることができます。スターター・アプリケーションの使用に関するヘルプについては、[『スターター・アプリケーションの使用』](/docs/cfapps/starter_app_usage.html)を参照してください。

## ランタイム・バージョン
{: #runtime_versions}

アプリケーションのルートにある runtime.txt ファイルで python-versionnumber を設定することにより、アプリケーションで使用する Python のバージョンを指定できます。例えば、次のように指定します。

```
python-3.6.0
```
{: codeblock}

バージョンを指定しない場合は、デフォルトでバージョン 2.7.13 が選択されます。

### 使用可能なバージョン:
{: #available_versions}

現在 {{site.data.keyword.Bluemix}} にインストールされている [Python ビルドパック](https://github.com/cloudfoundry/python-buildpack/releases/tag/v1.5.15)では、以下の Python バージョンが使用できます。

* 2.7.12
* 2.7.13
* 3.3.5
* 3.3.6
* 3.4.5
* 3.4.6
* 3.5.2
* 3.5.3
* 3.6.0

アプリケーションが、リストされていない Python バージョンを必要とする場合は、外部の [Python ビルドパック](https://github.com/cloudfoundry/python-buildpack)を使用してアプリケーションをデプロイできます。

# 関連リンク
{: #rellinks notoc}
## 一般
{: #general notoc}
* [Cloud Foundry buildpack for the Python Language](https://github.com/cloudfoundry/python-buildpack)
