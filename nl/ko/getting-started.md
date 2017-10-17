---

copyright:
  years: 2017
lastupdated: "2017-09-06"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:app_name: data-hd-keyref="app_name"}

# 시작하기 튜토리얼
{: #getting_started}

* {: download} 축하합니다. {{site.data.keyword.Bluemix}}에 Hello World 샘플 애플리케이션을 배치했습니다. 시작하려면 이 단계별 안내서를 따르십시오. 또는 <a class="xref" href="http://bluemix.net" target="_blank" title="(샘플 코드 다운로드)"><img class="hidden" src="../../images/btn_starter-code.svg" alt="애플리케이션 코드 다운로드" />샘플 코드를 다운로드</a>하고 직접 탐색하십시오.

Python 시작하기 튜토리얼에 따라 개발 환경을 설정하고, 앱을 로컬 및 {{site.data.keyword.Bluemix}}에 배치하고, 앱에 {{site.data.keyword.Bluemix}} 데이터베이스 서비스를 통합합니다.

## 시작하기 전에
{: #prereqs}

다음이 필요합니다.
* [{{site.data.keyword.Bluemix_notm}} 계정](https://console.ng.bluemix.net/registration/)
* [Cloud Foundry CLI ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://github.com/cloudfoundry/cli#downloads){: new_window}
* [Git ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://git-scm.com/downloads){: new_window}
* [Python ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://www.python.org/downloads/){: new_window}

## 1단계: 샘플 앱 복제
{: #clone}

이제 앱에 대한 작업을 시작할 준비가 되었습니다. 저장소를 복제하고 샘플 앱이 있는 디렉토리로 변경하십시오.
  ```
git clone https://github.com/IBM-Bluemix/get-started-python
  ```
  {: pre}
  ```
cd get-started-python
  ```
  {: pre}

  *get-started-python* 디렉토리에서 파일을 확인하여 컨텐츠를 익히십시오.

## 2단계: 로컬로 앱 실행
{: #run_locally}

시스템에 Python을 설정하는 것과 관련된 사항은 [The Hitchhiker’s Guide to Python! ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](http://docs.python-guide.org/en/latest/)을 참조하십시오.
{: tip}

앱을 로컬로 실행할 수 있도록 [requirements.txt ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://pip.readthedocs.io/en/stable/user_guide/#requirements-files) 파일에 나열된 종속 항목을 설치하십시오.

[가상 환경 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://packaging.python.org/installing/#creating-and-using-virtual-environments)을 선택적으로 사용하여 이러한 종속 항목과 다른 Python 프로젝트 또는 사용자 운영 체제의 종속 항목 간의 충돌을 방지할 수 있습니다.


  ```
pip install -r requirements.txt
  ```
  {: pre}

또는 Python3을 사용하여 다음을 실행할 수 있습니다.

  ```
python3 -m pip install -r requirements.txt
  ```
  {: pre}

앱을 실행하십시오.
  ```
python hello.py
  ```
  {: pre}

 http://localhost:8000에서 앱 보기


## 3단계: 배치를 위한 앱 준비
{: #prepare}

{{site.data.keyword.Bluemix_notm}}에 배치하는 경우 manifest.yml 파일을 설정하는 것이 도움이 될 수 있습니다. manifest.yml에는 앱에 대한 기본 정보(예: 이름, 각 인스턴스에 할당할 메모리 크기, 라우트)가 포함됩니다. `get-started-python` 디렉토리에 샘플 manifest.yml 파일을 제공했습니다.

manifest.yml 파일을 열고 `name`을 `GetStartedPython`에서 앱 이름 <var class="keyword varname" data-hd-keyref="app_name">app_name</var>으로 변경하십시오.
{: download}

  ```
  applications:
  - name: GetStartedPython
    random-route: true
    memory: 128M
  ```
  {: codeblock}

이 manifest.yml 파일에서 **random-route: true**는 사용자 라우트가 다른 라우트와 충돌하지 않도록 앱을 위한 임의 라우트를 생성합니다. 원하는 경우, **random-route: true**를 **host: myChosenHostName**으로 바꾸고 사용하려는 호스트 이름을 제공할 수 있습니다. [자세히 보기...](/docs/manageapps/depapps.html#appmanifest)
{: tip}

## 4단계: 앱 배치
{: #deploy}

Cloud Foundry CLI를 사용하여 앱을 배치할 수 있습니다. 

API 엔드포인트를 선택하십시오.
   ```
cf api <API-endpoint>
   ```
   {: pre}

명령의 *API-endpoint*를 다음 목록의 API 엔드포인트로 바꾸십시오.

|URL|지역|
|:-------------------------------|:---------------|
|  https://api.ng.bluemix.net| 미국 남부|
| https://api.eu-gb.bluemix.net| 영국|
| https://api.au-syd.bluemix.net| 시드니|
| https://api.eu-de.bluemix.net | 프랑크푸르트|

{{site.data.keyword.Bluemix_notm}} 계정에 로그인

  ```
cf login
  ```
  {: pre}

연합 사용자 ID가 있기 때문에 `cf login` 또는 `bx login` 명령을 사용하여 로그인할 수 없는 경우 `cf login --sso` 또는 `bx login --sso` 명령을 사용하여 싱글 사인온 ID로 로그인할 수 있습니다. 자세한 정보는 [연합 ID로 로그인](https://console.bluemix.net/docs/cli/login_federated_id.html#federated_id)을 참조하십시오.

*get-started-python* 디렉토리에서 {{site.data.keyword.Bluemix_notm}}에 앱 푸시
  ```
cf push
  ```
  {: pre}

이를 수행하는 데 시간이 좀 걸릴 수 있습니다. 배치 프로세스에 오류가 있는 경우 `cf logs <Your-App-Name> --recent` 명령을 사용하여 문제점을 해결할 수 있습니다. 

배치가 완료되면 앱이 실행 중이라는 메시지가 표시됩니다. push 명령의 출력에 나열된 URL에서 앱을 확인하십시오. 또한
  ```
cf apps
  ```
  {: pre}
  명령을 실행하여 앱 상태를 보고 URL을 확인할 수 있습니다.

## 5단계: 데이터베이스 추가
{: #add_database}

다음으로, 이 애플리케이션에 NoSQL 데이터베이스를 추가하고 애플리케이션을 설정하여 로컬 및 {{site.data.keyword.Bluemix_notm}}에서 이를 실행할 수 있도록 합니다.

1. 브라우저에서 {{site.data.keyword.Bluemix_notm}}에 로그인하십시오. `대시보드`로 이동하십시오. `이름` 열에서 해당 이름을 클릭하여 애플리케이션을 선택하십시오.
2. `연결`을 클릭한 다음 `새로 연결`을 클릭하십시오.
2. `데이터 및 분석` 섹션에서 `Cloudant NoSQL DB`를 선택한 다음 서비스를 `작성`하십시오.
3. 프롬프트가 표시되면 `다시 스테이징`을 선택하십시오. {{site.data.keyword.Bluemix_notm}}가 애플리케이션을 다시 시작하고, `VCAP_SERVICES` 환경 변수를 사용하여 애플리케이션에 데이터베이스 신임 정보를 제공합니다. 이 환경 변수는 {{site.data.keyword.Bluemix_notm}}에서 실행 중인 경우에만 애플리케이션에서 사용 가능합니다.

환경 변수를 사용하면 배치 설정을 소스 코드와 구분할 수 있습니다. 예를 들어, 데이터베이스 비밀번호를 하드 코딩하는 대신 소스 코드에서 참조하는 환경 변수에 이 비밀번호를 저장할 수 있습니다. [자세히 보기...](/docs/manageapps/depapps.html#app_env)
{: tip}

## 6단계: 데이터베이스 사용
{: #use_database}
이제 이 데이터베이스를 가리키도록 로컬 코드를 업데이트합니다. 애플리케이션이 사용할 서비스의 신임 정보를 저장할 JSON 파일을 작성합니다. 이 파일은 애플리케이션이 로컬로 실행 중인 경우에만 사용됩니다. {{site.data.keyword.Bluemix_notm}}에서 실행 중인 경우 신임 정보는 VCAP_SERVICES 환경 변수에서 읽습니다.

1. 다음 컨텐츠를 포함한 `get-started-python` 디렉토리의 `vcap-local.json` 파일을 작성하십시오.
  ```
  {
    "services": {
      "cloudantNoSQLDB": [
        {
          "credentials": {
            "username":"CLOUDANT_DATABASE_USERNAME",
            "password":"CLOUDANT_DATABASE_PASSWORD",
            "host":"CLOUDANT_DATABASE_HOST"
          },
          "label": "cloudantNoSQLDB"
        }
      ]
    }
  }
  ```
  {: pre}

2. {{site.data.keyword.Bluemix_notm}} UI에서 앱 -> 연결 -> Cloudant -> 신임 정보 보기를 선택하십시오.

3. 신임 정보의 `username`, `password` 및 `host`를 복사하여 `vcap-local.json` 파일의 동일한 필드에 붙여넣어 **CLOUDANT_DATABASE_USERNAME**, **CLOUDANT_DATABASE_PASSWORD** 및 **CLOUDANT_DATABASE_URL**을 바꾸십시오.

4. 애플리케이션을 로컬로 실행하십시오.
  ```
python hello.py
  ```
  {: pre}

  http://localhost:8000에서 앱을 보십시오. 이제 앱에 입력한 이름이 데이터베이스에 추가됩니다.

  로컬 앱과 {{site.data.keyword.Bluemix_notm}} 앱은 데이터베이스를 공유합니다. 위에서 push 명령의 출력에 나열된 URL을 통해 {{site.data.keyword.Bluemix_notm}} 앱을 확인하십시오. 이 중 하나의 앱에서 추가하는 이름은 브라우저를 새로 고치면 두 앱에 모두 표시됩니다.

앱을 지속할 필요가 없는 경우 예상치 않은 비용이 발생하지 않도록 앱을 중지하십시오.
{: tip}
