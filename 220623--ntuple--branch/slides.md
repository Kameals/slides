---
# try also 'default' to start simple
# theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
---

# 브랜치 전략 소개

## Main-Git-Flow

발표자 : Hamill Kim (Dev 팀)

---

# 소개

<br>

Dev 팀 백엔드 개발자

---

# 개요

<br>

원활한 협업을 위해 Dev 팀에서 운용 중인 전략을 소개합니다.

<br>

- 📝 **브랜치 용어 소개**
- 🎨 **브랜치 전략의 중요성**
- 🧑‍💻 **우리의 Main-Git-Flow 소개**
- 🤹 **데모 : Hamill의 작업 흐름을 보자**
- 🛠 **마무리**

<br>

<style>
h1 {
  background-color: #2B90B6;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

---

# 개요

회사는 협업을 통해 서비스를 고객에게 제공합니다. 
멤버간, 팀간, 부서간에는 다양한 방식과 정해진 규칙에 따라 협업이 이루어 집니다. 

이번 발표에서는 개발팀은 어떻게 협업하는가.
싱크트리 소스코드를 여러 명의 개발자가 어떤 규칙을 바탕으로 큰 충돌 없이 원활하게 개발하는가에 대한 이야기를 해보려고 합니다.

---

# 1. 비개발자를 위한 사전 지식

- 브랜치란?
- 브랜치 전략이란?

---

## 1-1. 브랜치란?

<br>
<br>

- 동일한 소스코드 위에서 어떤 개발자는 버그를 수정하기도 하고 또 다른 개발자는 새로운 기능을 만들어 내기도 함
- 이처럼 여러 사람이 동일한 소스코드를 기반으로 서로 다른 작업을 할 때에는 각각 서로 다른 버전의 코드가 만들어 질 수 밖에 없음

<br>
<br>

### 이럴 때, 여러 개발자들이 동시에 다양한 작업을 할 수 있게 만들어 주는 기능이 바로 '브랜치(Branch)'

<br>
<br>

- 각자 독립적인 작업 영역 안에서 마음대로 소스코드를 변경할 수 있고
- 이렇게 분리된 작업 영역에서 변경된 내용은 나중에 원래의 버전과 비교해서 하나의 새로운 버전으로 만들어 낼 수 있음

---

## 1-2. 브랜치 전략이란?

- 회사마다, 팀마다 각기 다른 프로세스와 서비스 배포 전략이 있습니다.
- 브랜치 전략은 원활한 개발과 배포를 위해, 개발 조직이 서로 어떻게 협업할 것인지에 대한 구체적인 전략입니다.

---

# 2. Dev 팀에서 사용하는 브랜치 전략 소개

## Main-Git-Flow 

- 배경
- 얻을 수 있는 장점
- 어떤 방식인가

---

# 3. Hamill 의 작업 흐름 예시

---

# 마무리

<br>

- 브랜치 전략은 소스코드를 안정적으로 관리하기 위한 협업에 필요한 최소 규칙입니다. 
- 동일한 소스코드에 대해 서로 다른 방식으로 일한다면 매 배포때마다 의사소통 비용이 발생할 것이고
- 작업자간, 부서간 업무 스트레스는 증가할 것이고 업무 생산성도 떨어질 것입니다. 

서비스를 원활하고 안정적으로 배포하기 위해서는 서로 동일한 용어와 방식으로 의사소통하는 것이 중요하다고 생각합니다.

감사합니다.

---

<br>

Read more 
- [Git 브랜치 전략](https://www.notion.so/ntuple/Git-6c45e9ffb5094f50940f25dfc42eb713)
- [PR 리뷰 전략](https://www.notion.so/ntuple/PR-87b3d712fcbd47fb8178169933a17cc4)
- [부서간 개발 업무 규칙](https://www.notion.so/ntuple/d98d2f273f29426790bee053e59aa408)