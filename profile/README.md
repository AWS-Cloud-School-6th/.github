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
	<img src="https://img.shields.io/badge/Kubernetes-326CE5?style=flat&logo=Kubernetes&26logoColor=white">

</div>
<br>
<div align="left">
<br>

# 인프라 구성도

## 1. 구성도

<div align="center">
    <img src="https://github.com/user-attachments/assets/a54c7401-4cdc-4ede-81dc-20c2b0873ba9">
</div>

## 2. 구성도 상세 설명
<div align="left">

<h3>3계층 구조와 Ingress를 통한 로드 밸런싱</h3>
<p>본 구성도는 쿠버네티스 환경에서 Front - Back - DB로 연결되는 3계층(3-tier) 구조를 나타냅니다.</p>
<p>가장 앞단에는 Ingress를 배치하여 애플리케이션 레벨에서 로드 밸런싱을 구성하고, 외부에서 들어오는 트래픽의 엔드포인트를 제한함으로써 외부 노출을 최소화했습니다. 또한, GKE 내에서는 각 애플리케이션 인스턴스를 서비스로 등록하고, 서비스 네임을 DNS에 등록하여 DNS를 통해 연결될 수 있도록 설정하였습니다. 이를 통해 클라이언트의 요청이 적절히 내부 서비스로 라우팅되고 로드밸런싱되도록 하였습니다.</p>

<h3>FrontendConfig를 통한 HTTPS 리다이렉트</h3>
<p>프론트엔드 연결 단계에서 참조하는 FrontendConfig는 클라이언트의 HTTP 요청을 HTTPS로 리다이렉트하는 설정을 담고 있습니다. 이 구성 요소는 Ingress와 함께 사용되며, 보안이 강화된 HTTPS 프로토콜로만 클라이언트와의 통신이 이루어지도록 보장합니다.</p>

<h3>Front Tier와 Nginx-React 연동</h3>
<p>루트 도메인으로 접속 시, 가장 먼저 연결되는 계층은 Front Tier입니다. 이 단계에서 Nginx와 React를 하나의 Docker 이미지로 빌드하여 배포를 간소화하고 리소스 최적화를 효과적으로 구현했습니다. 80포트로 요청이 들어오면 Nginx가 이를 받아 React 서비스로 전달하며, 이후 React Pod들과 연결됩니다. 사용자가 Front 단계에서 입력한 요청들은 API 요청 형태로 Ingress를 통해 spring-svc로 라우팅됩니다. 이때 Ingress는 Front에서 들어온 80포트의 요청을 8080포트로 매핑하여 전달합니다.</p>

<h3>BackendConfig를 통한 백엔드 서비스 관리</h3>
<p>백엔드 연결 단계에서 참조하는 BackendConfig는 백엔드 서비스의 상태 확인(헬스 체크)과 세션 연결 방식(Session Affinity)을 관리하는 설정을 담고 있습니다. 헬스 체크를 통해 백엔드 서비스가 안정적으로 작동하는지 주기적으로 확인하고, 세션 어피니티 설정을 통해 쿠키를 사용하여 클라이언트의 요청이 동일한 백엔드 인스턴스로 라우팅되도록 하여 특정 세션에 대해 일관된 연결을 유지할 수 있도록 보장합니다.</p>

<h3>ConfigMap을 통한 DB 연결 관리</h3>
<p>DB와의 연결은 ConfigMap을 사용해 환경 변수를 통해 설정되며, 연결 정보는 DNS 이름으로 지정되었습니다. 이를 통해 Cloud SQL 인스턴스의 IP가 변경되더라도 지속적으로 연결이 가능하도록 구성하였습니다.</p>

</div>




<br>
<br>
<details>
<summary><strong>깃 컨벤션</strong></summary>

## 1. 커밋 유형 지정

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


- 제목은 영어로 작성한다.
- 내용은 다른 사람이 알아볼 수 있게 본인이 작업할 내용을 적는다.
- 라벨을 설정한다.
## 📌 pr convention

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
- 
</details>
## 🚨 Troubleshooting

<details>
<summary><strong>⚙️ Problem 1: Login 인증 정보가 요청에 포함되지 않음</strong></summary>

### 💡 Issue:

Login 인증 방식이 JSession이었는데, Backend에서 보내준 인증 정보를 브라우저에 저장했다가 유저가 보내는 요청에 포함되어야 했지만, 제대로 포함되지 않았다:

```bash
❓ Why:
- withCredentials: True 옵션을 사용했음에도 불구하고 계속해서 302 에러가 발생함.

✅ Solution:
🛠️ package.json에 proxy 설정을 추가하여 문제를 해결함.

```

</details>

<details>
<summary><strong>⚙️ Problem 2: 배포 시 환경변수가 무효화됨</strong></summary>

### 💡 Issue:

로컬 환경에서 정상 작동하던 환경변수가 배포 시 무효화되었다:

```bash
❓ Why:
- 배포 환경에서 환경변수가 제대로 로드되지 않음.

✅ Solution:
🛠️ package.json에서 .env 파일로 환경변수 위치를 변경하여 문제를 해결함.

```

</details>

<details>
<summary><strong>⚙️ Problem 3: 페이지 이동 시 Zustand 상태 관리가 되지 않음</strong></summary>

### 💡 Issue:

Frontend 상태 관리 라이브러리로 Zustand를 사용했는데, 페이지 이동 시 상태가 유지되지 않았다:

```bash
❓ Why:
- Zustand가 기존의 상태 관리 라이브러리와 다르게 상태 저장을 특별하게 처리하기 때문

✅ Solution:
🛠️ Zustand의 상태 저장 방식을 로컬 스토리지를 사용하도록 변경하여 문제를 해결함.

```

</details>

<details>
<summary><strong>⚙️ Problem 4: HTTPS로 변경 후 CORS 이슈 발생</strong></summary>

### 💡 Issue:

HTTP에서 HTTPS로 변경 후 CORS 이슈가 발생했다:

```bash
❓ Why:

- GET 요청은 가능했으나, POST 요청은 실패
	GET 요청이 가능했던 이유는 크롬 브라우저에서 HTTPS로 바꿔서 보내는 옵션이 활성화되어있었음
- 환경변수에 HTTP가 설정되어 있었음.

✅ Solution:
- CORS 문제로 인식하여 Backend 코드를 수정했으나 문제 해결 X
🛠️ 환경변수 설정을 HTTP에서 HTTPS로 변경하여 문제를 해결함.

```

</details>

<details>
<summary><strong>⚙️ Problem 5: Ingress에서 Backend가 정상 작동 하지 않는 현상</strong></summary>

### 💡 Issue:

Ingress의 Frontend는 정상 작동하는데 Backend는 비정상 작동:

```bash
❓ Why:
- /healthz의 80포트로 잘 못된 상태 확인

✅ Solution:
🛠️ BackendConfig를 작성하여 /actuator/health의 8080으로 상태 확인 작성
🛠️ 필요한 dependency들 추가하여 Backend 파일 Rebuild
```

</details>

<details>
<summary><strong>⚙️ Problem 6: Backend 서버의 JAR파일에서 DB 정보 하드코딩</strong></summary>

### 💡 Issue:

git에 commit하기 위해 코드를 점검하고 있는데 application.properties에 DB 정보가 하드코딩:

```bash
❓ Why:
- git에 배포 시 DB의 정보가 그대로 들어가면 피해를 볼 수도 있기 때문

✅ Solution:
🛠️ 배포 환경이 GCP의 GKE이므로 ConfigMap을 작성
🛠️ Backend 서버 deployment에 ConfigMap의 값들을 환경변수로 등록
🛠️ Backend 서버가 실행되면서 환경변수로 DB 정보를 가지고 동작

🔧 Improvement:
- Secret을 통해 구현
```

</details>

<details>
<summary><strong>⚙️ Problem 7: api 호출 시 네트워크 지연 실패</strong></summary>

### 💡 Issue:

https의 지정된 도메인으로 api 호출 시 네트워크 지연으로 실패:

```
❓ Why:
- 개인적으로 구입한 SSL을 사용하여 Ingress 파일에 적용
- frontend 호출 도메인과 api 호출 도메인은 Ingress안에서 분리
- SSL이 frontend에 연결된 도메인만 유효

✅ Solution:
🛠️ 이미 구입한 SSL에 새로운 도메인을 추가 불가능
🛠️ GCP의 Managed-Certificate를 발급
🛠️ 두 도메인 모두에 유효하게 만들어 Ingress에 적용
🛠️ api 호출 성공 확인
```

</details>

<details>
<summary><strong>⚙️ Problem 8: api 호출이 되다가 안되는 현상</strong></summary>

### 💡 Issue:

초반에만 api 호출이 되다가 api 호출이 안되며 404 에러:

```bash
❓ Why:
- Backend를 Deployment를 통해 배포
- Ingress를 통해 LoadBalancing
- 세션이 유지가 되지 않아 문제 발생

✅ Solution:
🛠️ 세션을 유지하기 위해 Ingress에 Session Affinity 추가
🛠️ GKE의 BackendConfig를 통해 Cookie로 Session Affinity 적용
🛠️ 서버가 상태 정보를 가지고 있게 되므로 좋은 솔루션 X

🔧 Improvement:
- redis 등을 활용하여 상태 정보를 외부로 빼서 서버가 상태 정보를 가지지 않게 구현
```

</details>
