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

- 어떤 방식인가
- 얻을 수 있는 장점

---

## 2-1. 요약하자면?


---

## 2-2. 얻을 수 있는 장점


---

# 3. Hamill 의 작업 흐름 예시

- develop 에서 일감 feature main(이하 main) 생성
- main 에서 실제 작업 브랜치 생성
    - (main 하나로 완결할 수 있는 간단한 작업이면 main 에서 바로 작업해도 되지만, 저는 작업 단위를 줄이기 위해 가급적 작업 브랜치를 잘게 나누려고 하는 편)
- sub1 작업이 완료되면 sub1->main PR 을 생성 후 리뷰 요청
- 리뷰 받는 동안, 다음 작업을 위해 sub2 브랜치를 sub1 에서 생성
- sub2 작업이 완료되면 sub2->sub1 PR 을 생성 후 리뷰 요청
- 의식하는 부분
    - PR 머지 순서는 항상 상위 브랜치 부터
        - sub2 -> sub1 리뷰가 끝났다고 하여, sub2->sub1 머지부터 하면...
            - 진행 중인 sub1->main PR 에 sub2 내용이 diff 로 표시되어 버리므로, 리뷰가 어려워짐
        - 따라서 sub2->sub1 리뷰가 끝났다고 하더라도, sub1->main 리뷰가 끝날때까지는 그대로 둔다
        - 이 방식은 선작업이 후작업에 영향을 줄때 하는 방식으로, 작업간에 영향이 없다면 각 작업을 main 에서 브랜치 생성하여 개별적으로 PR 후 main 에 머지해도 됨
        - 그러나 일반적으로 PR 을 작게 유지하면서 작업하려면 다음 작업은 앞작업에 후속 작업이므로, 기본적으로 위 방식을 취함
    - 내 작업엔 항상 최신 develop 브랜치 내용을 반영
        - develop 에는 구현이 완료된 일감들이 수시로 머지됨
        - 내 작업이 다른 일감에 의해 영향을 받는지 수시로 확인하면서 작업하는 것이 조기에 문제를 발견하여 사이드 이펙트를 최소화 할 수 있다는 마인드
        - 따라서, develop->main 으로 수시로 (체감상 diff 가 쌓인다고 느껴질때) 역머지
        - main->sub... 에 역머지
        - conflict 발생하면 해결하며, 어떻게 해결해야할지 애매할때는 해당 부분 개발자와 논의 후 해결
        - develop 에 머지된 내용으로 인해 내가 개발중인 기능에 사이드 이펙트가 발생했다면 기본적으로 그 부분은 내가 해결 (먼저 develop 에 머지한 사람에게는 내 기능은 블랙박스 상태이므로, 해결 책임은 나에게 있다)
    - 내가 개발중인 내용이 develop 보다 hotfix 로 먼저 배포하게 일정이 변경되었다면, master 에서 hotfix 를 생성하여 

---

# 4. 데모


---

# 5. 마무리

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