---
제목: 시작하기
설명: >-
  이 포괄적인 개요를 통해 Chirpy 기본 사항을 시작해보세요.
  첫 번째 Chirpy 기반 웹사이트를 설치, 구성 및 사용하는 방법과 이를 웹 서버에 배포하는 방법을 배우게 됩니다.
작가: 코트
날짜: 2019-08-09 20:55:00 +0800
카테고리: [블로깅, 튜토리얼]
태그: [시작하기]
핀: 사실
media_subpath: '/posts/20180809'
---

## 전제조건

[Jekyll Docs](https://jekyllrb.com/docs/installation/)의 안내에 따라 기본 환경 설치를 완료하세요. [Git](https://git-scm.com/)도 설치해야 합니다.

## 설치

### 새 사이트 만들기

이 테마에 대한 새 저장소를 만드는 방법에는 두 가지가 있습니다.

- [**Chirpy Starter 사용**](#option-1-using-the-chirpy-starter) — 쉽게 업그레이드하고 관련 없는 프로젝트 파일을 격리하여 글쓰기에 집중할 수 있습니다.
- [**GitHub Fork**](#option-2-github-fork) — 맞춤형 개발에는 편리하지만 업그레이드가 어렵습니다. Jekyll에 익숙하지 않고 이 프로젝트를 수정하거나 기여할 생각이 없다면 이 접근 방식은 권장되지 않습니다.

#### 옵션 1. Chirpy Starter 사용

GitHub에 로그인하고 [**Chirpy Starter**][starter]로 이동한 후 <kbd>이 템플릿 사용</kbd> > <kbd>새 저장소 만들기</kbd> 버튼을 클릭하고 새 저장소 이름을 지정하세요. `USERNAME.github.io`, 여기서 `USERNAME`은 GitHub 사용자 이름을 나타냅니다.

#### 옵션 2. GitHub 포크

GitHub에 로그인하여 [fork **Chirpy**](https://github.com/cotes2020/jekyll-theme-chirpy/fork)로 이름을 'USERNAME.github.io'로 바꿉니다('USERNAME'은 귀하의 사용자 이름).

다음으로 저장소를 로컬 머신에 복제하고 [Node.js][nodejs]가 설치되어 있는지 확인한 후 저장소의 루트 디렉터리로 이동하여 다음 명령을 실행합니다.

``콘솔
$ bash 도구/init.sh
````

> GitHub 페이지에 사이트를 배포하지 않으려면 위 명령 끝에 '--no-gh' 옵션을 추가하세요.
{: .prompt-정보 }

위 명령은 다음을 수행합니다.

1. [최신 태그][최신 태그]에 대한 코드를 확인하세요(사이트의 안정성을 보장하기 위해: 기본 브랜치에 대한 코드가 개발 중이므로).
2. 필수적이지 않은 샘플 파일을 제거하고 GitHub 관련 파일을 관리하세요.
3. CSS/JS 자산 파일을 빌드한 다음 Git에서 추적하도록 만듭니다.
4. 위의 변경 사항을 저장하려면 자동으로 새 커밋을 생성하세요.

### 종속성 설치

로컬 서버를 처음 실행하기 전에 사이트의 루트 디렉터리로 이동하여 다음을 실행하세요.

``콘솔
$ 번들
````

## 용법

### 구성

필요에 따라 `_config.yml`{: .filepath}의 변수를 업데이트합니다. 그 중 일부는 일반적인 옵션입니다.

- `url`
- `아바타`
- `시간대`
- `랭`

### 소셜 연락처 옵션

사이드바 하단에 소셜 연락처 옵션이 표시됩니다. `_data/contact.yml`{: .filepath } 파일에서 지정된 연락처를 켜거나 끌 수 있습니다.

### 스타일시트 사용자 정의

스타일시트를 사용자 정의해야 하는 경우 테마의 `assets/css/jekyll-theme-chirpy.scss`{: .filepath}를 Jekyll 사이트의 동일한 경로에 복사한 다음 끝에 사용자 정의 스타일을 추가하세요.

`6.2.0` 버전부터 `_sass/addon/variables.scss`{: .filepath}에 정의된 SASS 변수를 덮어쓰려면 기본 sass 파일 `_sass/main.scss`{: .filepath를 복사하세요. }를 사이트 소스의 `_sass`{: .filepath} 디렉터리에 넣은 다음 새 파일 `_sass/variables-hook.scss`{: .filepath}를 만들고 새 값을 할당합니다.

### 정적 자산 사용자 정의

정적 자산 구성은 '5.1.0' 버전에서 도입되었습니다. 정적 자산의 CDN은 `_data/origin/cors.yml`{: .filepath } 파일로 정의되며, 웹 사이트가 게시되는 지역의 네트워크 상황에 따라 일부를 교체할 수 있습니다.

또한 정적 자산을 자체 호스팅하려면 [_chirpy-static-assets_](https://github.com/cotes2020/chirpy-static-assets#readme)을 참조하세요.

### 로컬 서버 실행

게시하기 전에 사이트 콘텐츠를 미리 보고 싶을 수도 있으므로 다음과 같이 실행하세요.

``콘솔
$ exec jekyll s 번들
````

몇 초 후에 로컬 서비스가 _<http://127.0.0.1:4000>_에 게시됩니다.

## 배포

배포가 시작되기 전에 `_config.yml`{: .filepath} 파일을 확인하고 `url`이 올바르게 구성되었는지 확인하세요. 또한, [**프로젝트 사이트**](https://help.github.com/en/github/working-with-github-pages/about-github-pages#types-of-github-pages)를 선호하신다면 -sites) 사용자 정의 도메인을 사용하지 않거나 **GitHub 페이지** 이외의 웹 서버에서 기본 URL을 사용하여 웹사이트를 방문하려면 `baseurl`을 다음으로 시작하는 프로젝트 이름으로 변경해야 합니다. 슬래시(예: `/project-name`)

이제 다음 방법 중 _ONE_을 선택하여 Jekyll 사이트를 배포할 수 있습니다.

### GitHub Actions를 사용하여 배포

준비해야 할 몇 가지 사항이 있습니다.

- GitHub Free 플랜을 사용 중인 경우 사이트 저장소를 공개로 유지하세요.
- `Gemfile.lock`{: .filepath}을 저장소에 커밋했고 로컬 컴퓨터에서 Linux를 실행하지 않는 경우 사이트 루트로 이동하여 잠금 파일의 플랫폼 목록을 업데이트하세요.

  ``콘솔
  $ 번들 잠금 --add-platform x86_64-linux
  ````

다음으로 _Pages_ 서비스를 구성합니다.

1. GitHub에서 저장소로 이동합니다. _설정_ 탭을 선택한 다음 왼쪽 탐색 모음에서 _페이지_를 클릭하세요. 그런 다음 **소스** 섹션(_빌드 및 배포_ 아래)의 드롭다운 메뉴에서 [**GitHub Actions**][pages-workflow-src]를 선택합니다.  
![빌드 소스](pages-source-light.png){: .light .border .normal w='375' h='140' }
![빌드 소스](pages-source-dark.png){: .dark .normal w='375' h='140' }

2. 모든 커밋을 GitHub에 푸시하여 _Actions_ 워크플로를 트리거합니다. 저장소의 _작업_ 탭에서 실행 중인 _빌드 및 배포_ 워크플로를 볼 수 있습니다. 빌드가 완료되고 성공하면 사이트가 자동으로 배포됩니다.

이 시점에서 GitHub가 표시하는 URL로 이동하여 사이트에 액세스할 수 있습니다.

### 수동으로 빌드 및 배포

자체 호스팅 서버에서는 **GitHub Actions**의 편리함을 누릴 수 없습니다. 따라서 로컬 컴퓨터에 사이트를 구축한 다음 사이트 파일을 서버에 업로드해야 합니다.

소스 프로젝트의 루트로 이동하여 다음과 같이 사이트를 빌드합니다.

``콘솔
$ JEKYLL_ENV=프로덕션 번들 exec jekyll b
````

출력 경로를 지정하지 않으면 생성된 사이트 파일은 프로젝트 루트 디렉터리의 `_site`{: .filepath} 폴더에 배치됩니다. 이제 해당 파일을 대상 서버에 업로드해야 합니다.

[노드JS]: https://nodejs.org/
[스타터]: https://github.com/cotes2020/chirpy-starter
[pages-workflow-src]: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site# 사용자 정의-github-actions-workflow로 게시
[최신 태그]: https://github.com/cotes2020/jekyll-theme-chirpy/tags
