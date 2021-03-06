

https://user-images.githubusercontent.com/28341544/150537897-482bb440-f9e6-49bb-ae1e-7a92f9f21e6b.mp4


<br />

## 1. Overview
### 1) 프로젝트 개요    
* 2020년 하반기, 갤럭시워치3 출시에 맞춰 UK 포함 12개 국가에 오픈할 프로모셔널 컴포넌트의 프론트엔드 개발
* 고퀄리티 이미지, 애니메이션 등 비주얼적인 요소에 중점을 둔 프로젝트
* 삼성 프로젝트 특성 상 반응형 UI, 글로벌 확장성 대응 고려 및 웹접근성 준수 필수

> **[Live URL]**
> - France : https://www.samsung.com/fr/watches/mix-and-match/
> - Germany : https://www.samsung.com/de/watches/mix-and-match/    
> 
> &nbsp;
> (* 페이지 하단에 있는 공백영역은 컴포넌트가 주입된 템플릿 페이지의 코드에서 발생. 해당 컴포넌트의 원래의 개발 의도는 뷰포트 전체 크기를 단독으로 차지하는 것)

&nbsp;
### 2) 프로젝트 진행 환경 및 요건
* 기획서가 부재한 상황으로 해외 디자인 업체에서 제공하는 디자인가이드, 애니메이션/인터렉션 영상을 기반으로 기획요건을 유추해 개발해야 하는 환경
* 삼성에서 사용하는 AEM이라는 CMS에서 HTML, CSS, JS 코드를 입력할 수 있는 Raw Code 컴포넌트에 등록 가능하도록 고려하여 개발
* `글로벌 대응`을 위한 확장성 고려 (RTL, 길어지는 텍스트에 따른 UI 변화, 로컬 텍스트 적용 등)
* `반응형` UI 및 `웹접근성` 준수
* 크로스브라우징 범위:    
  * 최신 브라우저
  * IE11이상 (IE11은 콘텐츠 유실이 없는 수준으로 확인하며, 일부 부자연스러운 애니메이션 등은 논이슈 처리로 협의)

<br />
<br />

## 2. 기술스택 및 참여도
> 총 참여자: 2명

> `HTML` & `SCSS`: 100%    
> `JavaScript` (+ libraries): 70%
  * **기술스택 관련** :    
    * 주요 외부 JS library로 `jQuery`, `TweenMax(GSAP)`, `jQuery ba-outside-events`, `Swiper` 사용
    * 내부 공용 library 사용 (접근성 강화된 carousel 라이브러리, 팝업 등 키보드 포커스 제어용 라이브러리, 접근성 등 고려된 모달 라이브러리 및 기타 util 코드 등)
  * **참여도 관련** :    
    * 컴포넌트 관련 모든 HTML / SCSS 작업
    * API 통신, 최초 수신된 데이터 가공 및 팝업 데이터 바인딩 관련 외의 나머지 프론트엔드 개발 전담       
    * 이 외에 고객사와의 개발 관련 메인 커뮤니케이션 담당


<br />
<br />

## 3. 주요 개발 스펙
* **메인 화면**:    
  * 사이트 로딩 시 intro 비디오 자연스럽게 노출
  * 각 메뉴 전환 및 상품 선택에 따라 다양한 애니메이션 적용
  * 각 선택된 밴드의 컬러 코드를 배경색으로 노출
  * 하단 우측 버튼 클릭 시 배경 Theme 변경
  * 상품이미지 너비를 브라우저 높이에 따라 유동적으로 계산 (width를 vh기준으로 선언)
  * Strap 메뉴에서 '기본밴드'로 이동 가능한 CTA 추가
  * 모바일 구간에서 서브메뉴가 길어저 화면을 벗어나는 경우 대비하여 터치 스크롤 가능하도록 구현하며 각 메뉴 활성화 시 화면에 나타나도록 구현
  * 우측 'X' 버튼 클릭 시 되돌아가기 기능 구현
  * 각 상품 가격 밑의 CTA 클릭 시 팝업 노출
* **Watchface 화면**:    
  * Watchface들이 마우스 휠 이벤트에 따라 회전할 수 있도록 구현    
  (접근성을 위해 키보드 이벤트 또한 고려하여 구현)
  * 메인 watch frame 이미지 사이즈 유동적으로 계산하여 노출    
  (각 상품별 알 사이즈가 다른 watch frame 대응을 위한 스펙)
  * Watchface의 개수에 따라 각 watchface 간의 간격을 유지할 수 있도록 watchface가 회전하는 원형의 사이즈를 유동적으로 계산하여 구현

