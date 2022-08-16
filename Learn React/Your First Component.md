## Your First Component

Components는 React의 핵심 개념 중 하나입니다. 그것들(Components)은 사용자 인터페이스를 구축하는 기반이 되어 React 여정을 시작하기에 완벽한 장소가 됩니다!

### Components: UI building blocks

웹에서 HTML을 사용하면 `<h1>` 및 `<li>`와 같은 내장 태그들을 사용하여 풍부한(rich) 구조화된 문서를 만들 수 있습니다.

이 마크업은 기사의 `<article>`, 제목의 `<h1>` 및 목차를 정렬된 목록 `<ol>`로 나타냅니다.
Markup은 위와 같이, 스타일을 위한 CSS와 상호 작용을 위한 JavaScript와 결합되어 웹에서 볼 수 있는 모든 UI의 모든 sidebar, avatar, modal, dropdown에 걸쳐져 있습니다.

React는 당신의 앱을 위한 재사용 가능한 UI 요소들인 커스텀화(사용자 지정)된 components들을 markup, CSS 및 JavaScript를 결합 할 수 있게 한다. 위에서 본 목차 코드는 모든 페이지에서 렌더링할 수 있는 `<TableOfContents />` 구성 요소로 바뀔 수 있습니다. 내부적으로는 여전히 `<article>`, `<h1>` 등과 같은 동일한 HTML 태그를 사용합니다.

HTML 태그와 마찬가지로 순서지정 및 중첩된 component들로 전체 페이지를 디자인하는 구성을 할 수 있습니다. 예를 들어, 읽고 있는 문서 페이지는 React 구성 요소로 구성되어 있습니다.

\*compose를 '구성하다' 더 자연스러운 표현으로 해석하라고 하셨는데, 혹시 무엇이었는지 말씀해주실 수 있나요?

프로젝트가 성장함에 따라 이미 작성된 components를 재사용하여 많은 디자인을 구성할 수 있으므로 개발 속도가 빨라질 수 있습니다. 위의 목차는 `<TableOfContents />`를 사용하여 모든 화면에 추가할 수 있습니다! Chakra UI 및 Material UI와 같은 React 오픈 소스 커뮤니티에서 공유하는 수천 개의 components로 프로젝트를 바로 시작할 수도 있습니다.

## Defining a component

본래(전통적으로) 웹 페이지를 만들 때, 웹 개발자는 콘텐츠를 마크업한 다음 일부 JavaScript를 뿌려서 상호 작용을 추가했습니다. 이 작업은 웹에서 좋은 상호 작용이 일어날 때 효과적이었습니다. 이제 많은 사이트와 모든 앱에서 예상이 됩니다. React는 여전히 동일한 기술을 사용하면서 상호작용성을 최우선으로 합니다. React 구성 요소는 마크업을 뿌릴 수 있는 JavaScript 기능입니다.

components를 만들어내는 법

### Step 1: Export the component

`export default`의 prefix(접두사)는 표준 JavaScript 구문입니다(React에만 해당되지 않음). 이는 나중에 다른 파일에서 가져올 수 있도록 파일의 주요 기능을 표시할 수 있습니다.

### Define the fucntion

`function Profile() {}`은 Profile 이라는 이름을 가진 JavaScript 함수를 정의합니다.

### Add markup

Components는 `src` 및 `alt` 속성이 있는 <img /> 태그를 반환합니다. <img />는 HTML처럼 작성되었지만 실제로 내부는 JavaScript입니다! 이 구문을 JSX라고 하며 JavaScript 내부에 마크업을 포함할 수 있습니다.

Return 문은 Components로서 한 줄에 모두 작성할 수 있습니다.

하지만 마크업이 모두 return 키워드와 같은 줄에 있지 않으면 다음과 같이 한 쌍의 괄호로 묶어야 합니다.

### Using component

Profile의 component를 정의했으므로 이제 다른 Component 안에 중첩할 수 있습니다. 예를 들어, 여러 프로필 Components를 사용하는 갤러리 Component로 내보낼 수 있습니다.

## What the browser sees

- `<section>`은 소문자이므로(소문자로 시작한다는 뜻인 것 같음) React는 우리가 HTML 태그를 참조한다는 것을 알고 있습니다.

`<Profile />`은 대문자 P로 시작하므로 React는 Profile이라는 component를 사용하고 싶다는 것을 알고 있습니다.

그리고 Profile에는 더 많은 HTML이 포함되어 있습니다: <img />. 결국, 이것은 브라우저가 보는 것입니다.

### Nesting and organizing components

Component는 일반적인 JavaScript 함수이므로 동일한 파일에 여러 component를 넣을 수 있습니다. 이는 component가 상대적으로 작거나 서로 밀접하게 관련되어 있는 경우에 편리합니다. 이 파일이 꽉 차면 언제든지 Profile을 별도의 파일로 이동할 수 있습니다. Import에 대한 페이지에서 이 작업을 수행하는 방법을 곧 배우게 될 것입니다.

Profile Component는 Gallery 내에서 여러 번 렌더링되기 때문에 Gallery는 각 Profile을 "자식"으로 렌더링하는 상위 구성 요소라고 말할 수 있습니다. 이것은 React의 마법의 일부입니다. Component를 한 번 정의한 다음 원하는 만큼 여러 위치에서 사용할 수 있습니다.
