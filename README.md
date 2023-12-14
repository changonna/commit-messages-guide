# Commit Messages Guide

## ⁉ 커밋 메시지란 ?

Git과 같은 분산 버전 관리 시스템에서 개발자가 코드를 변경하고 저장소에 적용할 때마다 커밋 메시지를 작성하여 해당 변경 사항에 대한 설명과 의도를 기록합니다.

### 규칙에 맞춰 커밋 메시지를 작성해야 하는 이유

1. 가독성 향상: 다른 개발자나 팀원들이 변경 이력을 빠르게 이해하고 파악할 수 있도록 도와줍니다.

2. 협업 간의 일관성: 협업 시 오해나 혼란을 최소화하고 코드 변경에 대한 일관성을 유지할 수 있습니다.

3. 버그 추적 및 유지보수 용이성: 커밋 메시지를 검색하여 특정 기능이나 버그 수정 내용을 쉽게 찾을 수 있습니다.

4. 프로젝트 이해도 증가: 새로 합류한 개발자나 향후 개발자들에게 프로젝트 이해도를 높여줍니다.

5. 코드 리뷰 향상: 리뷰어가 변경 사항에 대한 이해를 높이고 적절한 피드백을 제공하기가 더 쉬워집니다.











## 🪐 Commit Message 구성
```
{emoji} {type}({scope}): {subject} //header(제목)
​
{body} //body(본문)
​
{issue tracker} //footer(꼬리말)

{breaking change}
```





## 🤝 기본 규칙

다른 개발자들이 커밋의 목적과 변경 내용을 빠르게 이해할 수 있도록 명확하고 간결하게 작성한다.

* Header(제목)

  - 제목 행은 (영문 기준) **50글자 이하**

  - 첫 글자는 **대문자로 작성**
      > feat: **A**dd new feature 🟢
      > 
      > feat: add new feature ❌

  - 제목 끝에 **특수문자 사용 X** 
      (마침표, 느낌표, 물음표 등)
      > open the door  🟢
      > 
      > open the door.!? ❌

  - 제목은 **명령문**으로 사용, 과거형X
      > **Add** user authentication feature  🟢
      > 
      > Added user authentication feature ❌

* Body(본문) - 부연설명이 필요한 경우에 작성(생략가능)

  - 제목과 본문을 **빈 행으로 구분**

  - 본문의 각 행은 (영문 기준) **72글자 이하**

  - 어떻게(How) 보다는 <u>무엇(What)</u>과 <u>왜(Why)</u>를 설명한다.

* Footer(꼬리말) - 생략가능

  - "유형: #issue tracker ID" 형식으로 사용합니다.
    > Resolves: #123
  - 여러개의 이슈 번호를 적을 때는 쉼표로 구분합니다.
    > Resolves: #7, #8

---

## 📌 Header(제목)

### 1. {emoji} (선택사항)

이모지는 간단하게 커밋의 특성을 표현하는 데 사용될 수 있습니다.
동료 개발자들의 커밋 목적이나 의도를 쉽게 식별할 수 있게 됩니다.

> 더 많은 Gitmoji가 있는 [Gitmoji Site](https://gitmoji.dev/)

### Gitmoji 예시
|이모지|예약어|설명|원문|
|--|----|----|----|
|🎨|`:art:`|새 기능|Improve structure / format of the code.|
|⚡️|`:zap:`|성능 개선|Improve performance.|
|🔥|`:fire:`|코드/파일 삭제|Remove code or files.|
|🐛|`:bug:`|**버그 수정**|Fix a bug.|
|🚑️|`:ambulance:`|긴급 수정|Critical hotfix.|
|✨|`:sparkles:`|**새 기능 추가**|Introduce new features.|
|📝|`:memo:`|문서 추가/수정|Add or update documentation.|
|🚀|`:rocket:`|배포|Deploy stuff.|
|💄|`:lipstick:`|UI/스타일 파일 추가/수정|Add or update the UI and style files.|
|🎉|`:tada:`|프로젝트 시작|Begin a project.|
|✅|`:white_check_mark:`|**테스트 추가/수정**|Add, update, or pass tests.|
|🔖|`:bookmark:`|릴리즈/버전 태그|Release / Version tags.|
|⏪|`:rewind:`|변경 내용 되돌리기|Revert changes.|
|🔀|`:twisted_rightwards_arrows:`|브랜치 합병|Merge branches.|
|♻️|`:recycle:`|코드 리팩토링|Refactor code.|
|🔧|`:wrench:`|구성 파일 추가/삭제|Add or update configuration files.|
|🔨|`:hammer:`|개발 스크립트 추가/수정|Add or update development scripts.|
|🚚|`:truck:`|리소스 이동, 이름 변경|Move or rename resources (e.g.: files paths routes).|
|💡|`:bulb:`|주석 추가/수정|Add or update comments in source code.|
|🗃|`:card_file_box:`|데이터베이스 관련 수정|Perform database related changes.|

### 2. {type}
Type은 Commit의 종류를 나타냅니다.

|태그|설명|관련 이모지|헤더 사용예시|
|------|-------|--------|---------|
|docs|단순한 **문서 추가 및 수정**|📝|📝 docs(readme): update installation instructions|
|**<u>feat</u>**|새로운 **기능 추가**|✨|✨ feat(user-auth): implement social media login|
|**<u>fix</u>**|**버그 수정**|🐛|🐛 fix(data-processing): resolve null pointer issue|
|perf|**성능 개선**|⚡️|⚡ perf(api): optimize database query for faster response|
|refactor|기능 추가(feat), 버그수정(fix), 성능 개선(perf)을 제외한 코드 수정|♻️|♻️ refactor(api): simplify error handling|
|style|code style 변경(Code Formatting, 세미콜론(;) 누락 등)|🎨|🎨 style: format code according to style guidelines|
|design|사용자 UI 디자인 변경 (CSS 등)|💄|💄 style(ui): update button styles|
|test|test code, refactoring test code 추가|🧪|🧪 test(api): add unit tests for authentication service|
|revert|이전 커밋으로 회귀할 때|⏪️|⏪ revert: undo last commit|
|build|빌드 파일 또는 외부 종속성에 영향을 미치는 수정|~~💚~~|
|ci|CI 설정 파일 수정|
|chore|빌드 업무 수정, 패키지 매니저 수정(.gitignore 수정 같은 경우)|
|rename|파일 혹은 폴더명을 수정한 경우|🚚|🚚 rename: change component file names
|remove|파일을 삭제한 경우|🔥|🔥 remove: delete obsolete utility functions

태그중에서 가장 많이 사용하는 것은 <u>`feat`</u>과 <u>`fix`</u>입니다.
`style`, `design`처럼 로직 변화가 없을 경우에 커밋 메시지에 명시해주는 것만으로도 추후 오류를 찾을 때 많은 도움이 됩니다.

### 3. ({scope}) (선택사항)
커밋이 어떤 부분에 영향을 미쳤는지를 나타냅니다. 이 부분은 선택적이며, 변경 사항의 범위를 더 명시적으로 표현할 때 사용됩니다.
**함수**나 **메소드**를 직접적으로 명시하기도 합니다.
> fix(filter): ...
> 
> fix(필터): ...

### 4. {subject}
커밋의 간단한 한 줄 요약으로, 50자 이내로 작성하는 것이 좋습니다. 변경 사항의 핵심을 나타내야 합니다.

> Add user authentication feature
> 
> 사용자 인증 기능 추가

---

## 📋 Body(본문)

### {body}
커밋에 대한 자세한 설명이나 배경을 기술하는 부분입니다. 필수는 아니지만, 변경 사항을 더 자세히 설명할 수 있도록 도움이 됩니다.

---

## 🔗 Footer(꼬리말) - 선택사항

주로 커밋과 관련된 이슈 트래킹, 변경 사항의 영향 등에 대한 추가적인 정보를 기록하는 데 사용됩니다. 

#### issue tracker

- 해결: Closes(종료), Fixes(수정), Resolves(해결)
- 참고: Ref(참고), Related to(관련), See also(참고)

1. resolves(관련 이슈 **해결**): 이 커밋이 특정 이슈를 해결한다는 것을 명시합니다.
    ```
    resolves: #123
    ```

2. refs(**참조**) : 이 커밋이 특정 이슈를 참조한다는 것을 명시합니다.
    ```
    refs: #456
    ```
3. closes(이슈 **닫힘**) : 이 커밋이 특정 이슈를 해결했으며, 해당 이슈를 닫을 때 사용합니다.
    ```
    closes: #789
    ```

#### breaking changes (중요한 변경 사항)
: 소프트웨어의 새로운 버전이나 업데이트에서 기존 버전과 호환되지 않는, 즉 기존 코드나 동작에 중요한 변화를 가져오는 변경을 의미합니다. 이는 주로 API 변경, 데이터베이스 스키마 변경, 라이브러리 버전 업그레이드 등이 해당될 수 있습니다.

```
Breaking Changes: API endpoint signature changed
```

#### Footer 예시
```
resolves: #123               // 꼬리말 => issue 123을 해결했으며,
ref: #456                                 issue 456 를 참고해야하며,
related to: #7, #8         현재 커밋에서 아직 issue 7과 8이 해결되지 않았다.
```

---


## 🤹‍♀️ Commit Message 작성 예시

* English
  ```
  ✨ feat(Authentication): Add user authentication feature

  * Implement user authentication functionality.
  * Enhance security by validating user credentials.
  * Connect authentication module with user database.

  Resolves: #567
  ```

* 한글
  ```
  ✨ feat(인증): 사용자 인증 기능 추가

  * 사용자 인증 기능 구현.
  * 사용자 자격 증명을 유효성 검사하여 보안 강화.
  * 인증 모듈을 사용자 데이터베이스와 연결.

  Resolves: #567
  ```

++ 추가로 좋은 커밋 메시지를 작성하기 위해 [좋은 git commit 메시지를 위한 영어 사전](https://blog.ull.im/engineering/2019/03/10/logs-on-git.html)를 참고해보자

---

## 📚 References

* [sj960126/Commit-message](https://github.com/sj960126/Commit-message)


* [[Git] 커밋 메시지 규약 정리(the AngularJS commit conventions)](https://velog.io/@outstandingboy/Git-%EC%BB%A4%EB%B0%8B-%EB%A9%94%EC%8B%9C%EC%A7%80-%EA%B7%9C%EC%95%BD-%EC%A0%95%EB%A6%AC-the-AngularJS-commit-conventions)

* [ Gitmoji 사용법 정리 (+ 깃모지 툴 소개)](https://inpa.tistory.com/entry/GIT-%E2%9A%A1%EF%B8%8F-Gitmoji-%EC%82%AC%EC%9A%A9%EB%B2%95-Gitmoji-cli)
