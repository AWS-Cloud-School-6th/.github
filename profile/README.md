<div align="center">
	    <h2> AWS Cloud School 3 Tier Project</h2>
    <h3> 🤼‍♂️ 일석2조 </h3>
    <p> Platforms & Languages </p>
<div>
<div align="center">
    <img src="https://img.shields.io/badge/Java-007396?style=flat&logo=Conda-Forge&logoColor=white"/>
	<img src="https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=HTML5&logoColor=white" />
	<img src="https://img.shields.io/badge/CSS3-1572B6?style=flat&logo=CSS3&logoColor=white" />
	<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=JavaScript&logoColor=white" />
	<br>
	<img src="https://img.shields.io/badge/Spring Boot-6DB33F?style=flat&logo=Spring Boot&logoColor=white" />
    <img src="https://img.shields.io/badge/React-61DAFB?style=flat&logo=React&logoColor=white"/>
	<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=MySQL&logoColor=white" />
</div>
<br>
<div align="left">
<br>
<br>

# 서비스 개요

1. 
    
2. 
    

---
<br>
<br>

# 깃 컨벤션 (커밋, 깃 플로우 전략)

##  커밋 메시지 컨벤션

<aside>
✅

### 1. 커밋 유형 지정

- 커밋 유형은 영어 대문자로 작성하기
    
    
    | 커밋 유형 | 의미 |
    | --- | --- |
    | Feat | 새로운 기능 추가 |
    | Fix | 버그 수정 |
    | Add | Feat 이외의 부수적인 코드 추가/라이브러리 추가/ 새로운 View나 Activity 생성 |
    | Docs | 문서 수정 |
    | Style | 코드 formatting, 세미콜론 누락, 코드 자체의 변경이 없는 경우 |
    | Refactor | 코드 리팩토링 |
    | Test | 테스트 코드, 리팩토링 테스트 코드 추가 |
    | Chore | 패키지 매니저 수정, 그 외 기타 수정 ex) .gitignore |
    | Design | CSS 등 사용자 UI 디자인 변경 |
    | Comment | 필요한 주석 추가 및 변경 |
    | Rename | 파일 또는 폴더 명을 수정하거나 옮기는 작업만인 경우 |
    | Remove | 파일을 삭제하는 작업만 수행한 경우 |
    | !BREAKING CHANGE | 커다란 API 변경의 경우 |
    | !HOTFIX | 급하게 치명적인 버그를 고쳐야 하는 경우 |

### 2. 제목과 본문을 빈행으로 분리

- 커밋 유형 이후 제목과 본문은 한글로 작성하여 내용이 잘 전달될 수 있도록 할 것
- 본문에는 변경한 내용과 이유 설명 (어떻게 보다는 무엇 & 왜를 설명)

### 3. 제목 첫 글자는 대문자로, 끝에는 `.` 금지

### 4. 제목은 영문 기준 50자 이내로 할 것

### 5. 자신의 코드가 직관적으로 바로 파악할 수 있다고 생각하지 말자

### 6. 여러가지 항목이 있다면 글머리 기호를 통해 가독성 높이기

```
- 변경 내용 1
- 변경 내용 2
- 변경 내용 3
```

</aside>

###  규칙에 맞는 좋은 커밋메시지를 작성해야 하는 이유

- 팀원과의 소통
- 편리하게 과거 추적 가능
- 나중에 실무에서 익숙해지기 위해



###  한 커밋에는 한 가지 문제만!

- 추적 가능하게 유지해주기
- 너무 많은 문제를 한 커밋에 담으면 추적하기 어렵다.

###  CLI에서 커밋 메시지 여러 줄로 작성하는 방법

<aside>
✅ 쌍따옴표를 닫지 말고 개행하며 작성 → 다 작성한 후에 쌍따옴표를 닫으면 작성 완료

```bash
git commit -m "FEAT: 회원가입 기능 추가

- 회원가입 기능 추가"
```
</aside>

## 📌 issue convention

---

- 제목은 영어로 작성한다.
- 내용은 다른 사람이 알아볼 수 있게 본인이 작업할 내용을 적는다.
- 라벨을 설정한다.
## 📌 pr convention

---

- 제목은 영어로 작성한다. (이슈 컨벤션과 같음)
- [영어 대문자] #이슈번호 - 해당 이슈 내용 (꼭 이슈랑 동일하지는 않아도 된다. 이슈 번호만 신경써서 적기)
- 내용에는 변경 사항을 적는다.
- 해당 이슈의 `closed #이슈`를 단다.
- assignees를 본인으로 설정한다.
- reviewers를 설정한다.
- 라벨을 설정한다.
- 코드 리뷰를 받는다.
- 변경 request 단 경우 확인 후 resolve를 한다.
- 스쿼시 머지를 한다.
