---
title: CSS 작동 방식
slug: Learn/CSS/First_steps/How_CSS_works
translation_of: Learn/CSS/First_steps/How_CSS_works
---
{{LearnSidebar}}
{{PreviousMenuNext("Learn/CSS/First_steps/How_CSS_is_structured", "Learn/CSS/First_steps/Using_your_new_knowledge", "Learn/CSS/First_steps")}}

CSS 기본 사항, CSS 의 목적 및 간단한 스타일 시트 작성 방법을 배웠습니다. 이 강의에서는 브라우저가 CSS 와 HTML 을 가져와서 웹 페이지로 만드는 방법을 살펴 봅니다.

<table class="learn-box standard-table">
  <tbody>
    <tr>
      <th scope="row">전제조건:</th>
      <td>
        기본적인 컴퓨터 활용능력,
        <a
          href="https://developer.mozilla.org/en-US/Learn/Getting_started_with_the_web/Installing_basic_software"
          >기본 소프트웨어 설치</a
        >,
        <a
          href="https://developer.mozilla.org/en-US/Learn/Getting_started_with_the_web/Dealing_with_files"
          >파일 작업</a
        >의 기본 지식 및 HTML 기본 사항 (<a
          href="/en-US/docs/Learn/HTML/Introduction_to_HTML"
          >HTML 소개</a
        >
        학습.)
      </td>
    </tr>
    <tr>
      <th scope="row">목적:</th>
      <td>
        브라우저에서 CSS 와 HTML 을 구문 분석하는 방법의 기본 사항과
        브라우저에서 CSS 를 이해하지 못할 경우 어떻게 되는지 이해하기.
      </td>
    </tr>
  </tbody>
</table>

## CSS 는 실제로 어떻게 작동합니까?

브라우저가 문서를 표시할 때, 문서의 콘텐츠와 해당 스타일 정보를 결합해야 합니다. 아래 나열된 여러 단계로 문서를 처리합니다. 이것은 브라우저가 웹 페이지를 로드할 때 발생하는 작업의 매우 단순화된 버전이며, 다른 브라우저가 다른 방식으로 작업을 처리한다는 점을 명심하십시오. 그러나 이것은 대략 일어나는 일입니다.

1. 브라우저는 HTML (예: 네트워크에서 HTML 을 수신) 을 로드합니다.
2. {{Glossary("HTML")}} 을 {{Glossary("DOM")}} (_Document Object Model_) 로 변환합니다. DOM 은 컴퓨터 메모리의 문서를 나타냅니다. DOM 은 다음 섹션에서 좀 더 자세히 설명됩니다.
3. 그런 다음 브라우저는 포함된 이미지 및 비디오와 같은 HTML 문서에 연결된 대부분의 리소스와 연결된 CSS 를 가져옵니다! JavaScript 는 작업에서 나중에 처리되므로 더 간단하게 하기위해 여기에서는 다루지 않습니다.
4. 브라우저는 가져온 CSS 를 구문 분석하고 선택자 유형별로 다른 규칙을 다른 "buckets" 으로 정렬합니다. 예: 요소, class, ID 등 찾은 선택자를 기반으로 DOM 의 어느 노드에 어떤 규칙을 적용해야 하는지 결정하고, 필요에 따라 스타일을 첨부합니다 (이 중간 단계를 render tree 라고 합니다).
5. render tree 는 규칙이 적용된 후에 표시되어야 하는 구조로 배치됩니다.
6. 페이지의 시각적 표시가 화면에 표시됩니다 (이 단계를 painting 이라고 함).

다음 그림은 작업의 간단한 보기를 제공합니다.

![](https://mdn.mozillademos.org/files/11781/rendering.svg)

## DOM 정보

DOM 은 트리와 같은 구조를 가지고 있습니다. 마크 업 언어의 각 요소, 속성 및 텍스트는 트리 구조에서 {{Glossary("Node/DOM","DOM node")}} 가 됩니다. 노드는 다른 DOM 노드와의 관계에 의해 정의됩니다. 일부 요소는 자식 노드의 부모이고 자식 노드에는 형제가 있습니다.

DOM 은 CSS 와 문서의 내용이 만나는 곳이기 때문에 DOM 을 이해하면 CSS 를 설계, 디버그 및 유지 관리하는 데 도움이 됩니다. 브라우저 DevTools 로 작업을 시작하면, 적용할 규칙을 보기 위해 항목을 선택할 때 DOM 을 탐색하게 됩니다.

## 실제 DOM 표현

길고 지루한 설명이 아니라 실제 HTML 이 DOM 으로 변환되는 방법을 보여주는 예제를 살펴 보겠습니다.

다음 HTML 코드를 사용하십시오:

```html
<p>
  Let's use:
  <span>Cascading</span>
  <span>Style</span>
  <span>Sheets</span>
</p>
```

DOM 에서, `<p>` 요소에 해당하는 노드는 부모입니다. 자식은 텍스트 노드이고 `<span>` 요소에 해당하는 세 개의 노드입니다. `SPAN` 노드는 부모이며, 텍스트 노드는 자식입니다:

```
P
├─ "Let's use:"
├─ SPAN
|  └─ "Cascading"
├─ SPAN
|  └─ "Style"
└─ SPAN
   └─ "Sheets"
```

브라우저가 이전 HTML 을 해석하는 방법입니다 — 위의 DOM 트리를 렌더링 한 다음 브라우저에서 다음과 같이 출력합니다:

{{EmbedLiveSample('A_real_DOM_representation', '100%', 55)}}

```css hidden
p {margin:0;}
```

## DOM 에 CSS 적용하기

CSS 를 문서에 추가하여 스타일을 지정했다고 가정해 봅시다. 다시 한 번, HTML 은 다음과 같습니다:

```html
<p>
  Let's use:
  <span>Cascading</span>
  <span>Style</span>
  <span>Sheets</span>
</p>
```

다음 CSS 를 적용한다고 가정해 봅시다:

```css
span {
  border: 1px solid black;
  background-color: lime;
}
```

브라우저는 HTML 을 구문 분석하고 그로부터 DOM 을 작성한 다음, CSS 를 구문 분석합니다. CSS 에서 사용할 수 있는 유일한 규칙에는 `span` 선택자가 있으므로, 브라우저는 CSS 를 매우 빠르게 정렬할 수 있습니다! 이 규칙을 세 개의 `<span>` 각각에 적용한 다음 최종 시각적 표현을 화면에 표시합니다.

업데이트 된 출력은 다음과 같습니다:

{{EmbedLiveSample('Applying_CSS_to_the_DOM', '100%', 55)}}

다음 과목의 [CSS 디버깅](/ko/docs/Learn/CSS/Building_blocks/Debugging_CSS) 기사에서 브라우저 DevTools 를 사용하여, CSS 문제를 디버깅하고 브라우저가 CSS 를 해석하는 방법에 대해 자세히 알아 봅니다.

## 브라우저에서 인식하지 못하는 CSS 를 발견하면 어떻게 됩니까?

[이전 수업](/ko/docs/Learn/CSS/First_steps/What_is_CSS#Browser_support) 에서 브라우저가 모두 동시에 새로운 CSS 를 구현하는 것은 아니라고 언급했습니다. 또한 많은 사람들이 최신 버전의 브라우저를 사용하지 않습니다. CSS 가 항상 개발되고 있으므로 브라우저가 인식할 수 있는 것보다 앞서 있기 때문에 브라우저가 CSS 선택자 또는 인식하지 못하는 선언을 발견하면 어떻게 될지 궁금할 수 있습니다.

대답은 아무것도 하지 않으며, CSS 의 다음 단계로 넘어갑니다!

브라우저가 규칙을 구문 분석하고 이해하지 못하는 속성 이나 값을 발견하면, 이를 무시하고 다음 선언으로 넘어갑니다. 오류가 발생하여 속성 또는 값의 철자가 틀렸거나 속성 또는 값이 너무 새롭고 브라우저가 아직 이를 지원하지 않는 경우, 이 작업을 수행합니다.

마찬가지로, 브라우저가 이해하지 못하는 선택자를 만나면, 전체 규칙을 무시하고 다음 규칙으로 넘어갑니다.

아래 예에서 나는 영국 영어 철자를 색상에 사용했는데, 그 속성은 인식되지 않기 때문에 유효하지 않습니다. 그래서 내 단락은 파란색으로 표시되지 않았습니다. 그러나 다른 모든 CSS 가 적용 되었습니다. 유효하지 않은 라인만 무시됩니다.

```html
<p> 나는 이 텍스트를 크고 굵은 파란색으로 표시하고 싶습니다.</p>
```

```css
p {
  font-weight: bold;
  colour: blue; /* color 속성의 잘못된 철자 */
  font-size: 200%;
}
```

{{EmbedLiveSample('Skipping_example', '100%', 200)}}

이 동작은 매우 유용합니다. 이는 새로운 CSS 를 향상된 기능으로 사용할 수 있음을 의미하며, 새 기능을 이해하지 못할 경우 오류가 발생하지 않습니다 — 브라우저는 새로운 기능을 얻거나 얻지 못합니다. cascade 작동 방식 및 브라우저가 스타일이 동일한 마지막 CSS 를 사용한다는 사실과 동일한 특성을 가진 두 규칙이 있을 경우, 새 CSS 를 지원하지 않는 브라우저에 대한 대안을 제공할 수도 있습니다.

이것은 새롭고 모든 곳에서 지원되지 않는 값을 사용하려는 경우 특히 효과적입니다. 예를 들어, 구형 브라우저는 `calc()` 를 값으로 지원하지 않습니다. 박스에 대해 대체 너비를 픽셀 단위로 지정한 다음, `calc()` 값을 `100% - 50px` 로 너비를 지정하십시오. 오래된 브라우저는 픽셀 버전을 사용하지만, 이해하지 못하는 `calc()` 에 대한 라인은 무시합니다. 새로운 브라우저는 픽셀을 사용하여 라인을 해석하지만, 나중에 cascade 에서 나타날 때 `calc()` 를 사용하여 라인을 재정의 합니다.

```css
.box {
  width: 500px;
  width: calc(100% - 50px);
}
```

우리는 이후 수업에서 다양한 브라우저를 지원하는 더 많은 방법을 다룰 것입니다.

## 마지막으로

이 강의를 거의 끝냈습니다; 할 일이 하나 더 있습니다. 다음 기사에서는 [새로운 지식을 사용](/ko/docs/Learn/CSS/First_steps/Using_your_new_knowledge) 하여 예제의 스타일을 변경하여 작업의 일부 CSS 를 테스트 합니다.

{{PreviousMenuNext("Learn/CSS/First_steps/How_CSS_is_structured", "Learn/CSS/First_steps/Using_your_new_knowledge", "Learn/CSS/First_steps")}}

## 이번 강의에서는

1. [CSS 란 무엇인가?](/ko/docs/Learn/CSS/First_steps/What_is_CSS)
2. [CSS 로 시작하기](/ko/docs/Learn/CSS/First_steps/Getting_started)
3. [CSS 의 구조](/ko/docs/Learn/CSS/First_steps/How_CSS_is_structured)
4. [CSS 작동 방식](/ko/docs/Learn/CSS/First_steps/How_CSS_works)
5. [새로운 지식을 사용](/ko/docs/Learn/CSS/First_steps/Using_your_new_knowledge)
