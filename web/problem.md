# **인사 정보 SPA 리뉴얼**

당신은 기존의 인사 정보 페이지를 SPA로 리뉴얼하는 업무를 맡게 되었습니다.
**Vanilla JS만을 이용**하여 아래의 요구사항에 맞게 작업해서 **세 시간 내에** 리뉴얼된 페이지를 게시해주세요.

### **주의사항**

- `index.html`, `home.html`, `signup.html` 에 있는 마크업 구조와 클래스 및 id 이름은 변경하면 안 됩니다. `style.css` 내의 선택자(class 및 id) 또한 변경하면 안 됩니다. **변경 시, 평가에 불이익이 있을 수 있습니다.**
- 모든 경로 앞에 **`/web/`을 절대경로**로 붙여주어야 합니다 (`index.html`을 참고해주세요).

## **1\. 공통**

### **1.1. GNB**

HOME 메뉴와 SINGUP 메뉴를 화면에 렌더링해주는 GNB 컴포넌트를 만들어야 합니다. 기본으로 제공되는 `home.html`, `signup.html` 의 마크업을 참고하여 아래 그림과 같이 리뉴얼되도록 GNB의 UI를 작성합니다. 구현에 대한 자세한 명세는 구성 요소, 기능, 스타일을 참고해주세요.
![header.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/f775a606-5401-43cd-9047-9b5dca84c8c0/header.png)

#### **1.1.1. 구성 요소**

GNB는 다음 2가지 요소로 구성됩니다.

- HOME 메뉴: 등록된 인사 정보를 카드 형태로 볼 수 있는 페이지로 이동하는 메뉴입니다.
- SIGNUP 메뉴: 인사 정보를 등록할 수 있는 페이지로 이동하는 메뉴입니다.

#### **1.1.2. 기능**

> 주어진 <b>`Header.js`</b> 파일에 코드를 작성합니다.

~~- HOME 메뉴를 클릭하면 URL 주소는 `/web/` 가 되며, 인사 정보를 카드 형태로 볼 수 있는 페이지가 렌더링 됩니다.~~
![img_gnb_func_02.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/c8a08e39-93aa-4ebd-a248-85d63a094463/img_gnb_func_02.png)

~~- SIGNUP 메뉴를 클릭하면 URL 주소는 `/web/signup` 가 되며, 인사 정보를 등록할 수 있는 페이지가 렌더링 됩니다.~~
![img_gnb_func_04.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/ef50b305-1cca-42cb-8543-1390d60b5940/img_gnb_func_04.png)

_참고: 컴포넌트를 작성하는데 필요한 함수 등을 작성하기 위해 새로운 파일을 생성하는 것은 가능합니다._

#### **1.1.3. 스타일**

> 주어진 <b>`style.css`</b> 파일 내에서만 코드를 작성 및 수정합니다.

~~- HOME 메뉴는 항상 좌측에, SIGNUP 메뉴는 우측에 정렬되어야 합니다.~~

~~- HOME 메뉴는 좌측에서 `15px` 만큼 떨어진 곳에 있습니다.~~

~~- SIGNUP 메뉴는 우측에서 `15px` 만큼 떨어진 곳에 있습니다.~~

~~- 메뉴 이름 글자 위에 마우스 오버를 하면 커서가 손 모양으로 바뀝니다.~~

_참고: CSS 선택자(class 및 id)는 수정이 불가합니다._

### **1.2. 페이지 제목**

![img_contenttitle_demo.gif](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/20badb41-f650-4b10-bb1e-b5055668b601/img_contenttitle_demo.gif)

#### **1.2.1. 기능**

> 주어진 <b>`ContentTitle.js`</b> 파일에 코드를 작성합니다.

페이지 제목을 관리할 수 있는 컴포넌트를 만들어 홈페이지와 등록페이지별로 제목이 렌더링 되도록 합니다.

~~- HOME 메뉴를 클릭했을 때, 요구사항에 맞는 페이지 제목이 렌더링 됩니다.~~

~~- SIGNUP 메뉴를 클릭했을 때, 요구사항에 맞는 페이지 제목이 렌더링 됩니다.~~

_참고: 컴포넌트를 작성하는데 필요한 함수 등을 작성하기 위해 새로운 파일을 생성하는 것은 가능합니다._

### **1.3. 인사 정보 데이터**

기존 인사 정보 데이터에는 이름, 이메일, 직군 정보만 있었습니다. 하지만 인사 정보 페이지를 리뉴얼하기 위해 사내 직원들로부터 추가로 닉네임, MBTI 정보를 받았습니다.

1. 리뉴얼 전/후 데이터는 다음과 같습니다.
   ![img_old_new_data.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/b759f2ac-2eef-4021-96e2-261506dfd282/img_old_new_data.png)
   JSON 데이터는 fetch API를 통해 불러옵니다.
2. ~~과제에서 주어진 리뉴얼 후의 데이터는 로컬스토리지가 처음 생성될 때 로컬스토리지에 저장됩니다.~~

   ~~- 로컬 저장소는 다음과 같은 형태로 구성합니다.~~

   ~~- key(키): personalInfo~~

   ~~- value(값): 객체 데이터 형식으로 이루어져 있고, 필드와 각 필드의 정보는 다음과 같습니다.~~
   ~~- `idx`: 몇 번째로 등록된 데이터인지를 나타내는 인덱스 - `name`: 사용자의 이름 - `email`: 사용자의 이메일 - `nickname`: 사용자의 닉네임 - `role`: 사용자의 직군 - `mbti`: 사용자의 MBTI~~

   - 이후 인사 정보 등록 페이지에서 새로 추가되는 데이터도 동일한 형태로 저장됩니다.

기존의 데이터가 적용된 페이지를 새로운 데이터를 활용하여 다음 요구사항에 맞게 인사 정보 페이지를 리뉴얼해주세요.

_참고: 키값과 필드 값이 다를 경우, 0점 처리됩니다._

## **2\. 인사 정보 페이지**

카드를 뒤집으면 인사 정보에 새로 추가된 MBTI 정보를 확인할 수 있는 형태로 인사 정보 페이지를 리뉴얼합니다.
기본으로 제공되는 `home.html` 의 마크업을 참고하여 아래 GIF와 같이 리뉴얼되도록 인사 정보 페이지의 UI를 작성합니다. 구현에 대한 자세한 명세는 구성 요소, 기능, 스타일을 참고해주세요.
![img_homepage_demo.gif](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/11440ed0-23d8-406a-bd69-cbe219e35832/img_homepage_demo.gif)

### **2.1. 구성 요소**

인사 정보 페이지는 다음 2가지 요소로 구성됩니다.

- 페이지 제목 섹션: 페이지 제목이 렌더링 되는 섹션입니다.
- 카드 인터페이스 섹션: 등록된 인사 정보가 카드 형태로 보이는 섹션입니다.

### **2.2. 기능**

> 주어진 <b>`HomePage.js`</b> 파일에 코드를 작성합니다.

1. 앞에서 구현한 `ContentTitle.js` 를 이용하여 페이지의 제목이 ‘Great PeoPle’가 되도록 합니다.
2. 카드 앞면에는 인사 정보의 닉네임이, 카드 뒷면에는 카드 앞면의 닉네임에 해당하는 인사 정보의 MBTI가 표시됩니다.
3. 카드를 클릭하면 카드가 뒤집히면서 카드 뒷면이 나타납니다.
   - ‘is-flipped’ 클래스 명을 사용하여 카드가 뒤집히도록 합니다.
   - 카드가 뒤집히는 애니메이션은 주어진 `style.css` 에 구현이 되어있습니다.
4. 브라우저 창 종료 후 재접속 했을 때, 카드의 뒤집힌 상태가 유지되도록 카드의 상태를 로컬스토리지에 기록합니다. 카드 상태의 로컬스토리지는 다음과 같은 형태로 구성합니다 (키값과 필드 값이 다를 경우, 0점 처리됩니다).
   - key(키): cardStatus
   - value(값): 객체 데이터 형식으로 이루어져 있고, 필드와 각 필드의 정보는 다음과 같습니다.
     - `idx`: 몇 번째로 입력된 데이터인지를 나타내는 인덱스
     - `status`: 카드가 뒤집힌 여부를 알 수 있는 상태 - 카드의 클래스 이름으로 값을 저장 (뒤집힌 카드는 'card is-flipped', 뒤집히지 않은 카드는 'card'로 저장되어 있어야 합니다)
5. 페이지 하단에 도달했을 때, 그다음 카드가 순차적으로 계속 로드되는 사용자 경험을 제공하기 위해 무한스크롤 기능을 구현합니다.

_참고: 컴포넌트를 작성하는데 필요한 함수 등을 작성하기 위해 새로운 파일을 생성하는 것은 가능합니다._

### **2.3. 스타일**

> 주어진 <b>`style.css`</b> 파일 내에서만 코드를 수정합니다.

![img_homepage_style_01.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/b67a3166-b139-494c-ad81-15cfb572969b/img_homepage_style_01.png)

- 카드가 보이는 영역은 위 그림과 같이 정렬되도록 합니다.
  카드가 보이는 영역에서는 `display`, `flex-flow`, `justify-content`, `align-content` 등의 속성을 사용할 수 있으며, 카드 하나에 대한 너비 설정은 필요하지 않습니다.
- 카드의 영역의 수정 내용은 다음과 같습니다.
  - 카드 사이즈의 가로는 `200px`, 세로는 `260px` 으로 수정합니다.
  - 카드 위에 마우스 오버를 하면 커서가 손 모양으로 바뀝니다.
- 카드의 스타일은 다음과 같은 내용으로 수정합니다.

  - 카드 앞면과 뒷면의 공통된 스타일
    - 글자는 카드의 수직 가운데 정렬이 되어야 합니다.
    - 글자는 굵기는 `700` 이어야 합니다.
    - 글자는 크기는 `40px` 이어야 합니다.
    - 카드의 기본 글자 색상은 흰색입니다.
  - 카드 앞면의 스타일
    - 카드 앞면의 배경색은 `#0D0D0D` 이어야 합니다.
  - 카드 뒷면의 스타일

    - 카드 뒷면의 배경색은 `#F2F2F2` 이어야 합니다.
    - 카드 뒷면의 글자 색상은 `#3098F2` 이어야 합니다.

    // 여기까지 했음. 로컬스토리지에 flip 상태 저장 못함

_참고: CSS 선택자(class 및 id)는 수정이 불가합니다._

## **3\. 인사 정보 등록 페이지**

5가지 정보(이름, 이메일, 닉네임, 직군, MBTI)를 입력하고 등록할 수 있는 인사 정보 입력 폼을 요구사항에 맞게 리뉴얼합니다.
기본으로 제공되는 `signup.html` 의 마크업을 참고하여 아래 그림과 같이 리뉴얼되도록 인사 정보 등록 페이지의 UI를 작성합니다. 구현에 대한 자세한 명세는 구성 요소, 기능, 스타일을 참고해주세요.
![img_signup.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/1ca6e938-1684-4ac2-bb9d-f28918908212/img_signup.png)

### **3.1. 구성 요소**

이 페이지는 다음 4가지 요소로 구성됩니다.

- 페이지 제목: 페이지 제목이 표시됩니다.
- 3개의 텍스트 필드와 2개의 셀렉트 필드: 로컬저장소에 새 요소를 삽입하기 위한 입력을 제공하는 필드입니다.
- “등록" 버튼: 로컬스토리지에 새 요소를 삽입하기 위한 버튼으로 입력 필드 값의 유무와 상관없이 항상 활성화되어 있어야 합니다.

### **3.2. 기능**

> 주어진 <b>`SignupPage.js`</b> 파일에 코드를 작성합니다.

1. 앞에서 구현한 `ContentTitle.js` 를 이용하여 페이지의 제목이 ‘Sign Up, GreatPeoPle!’가 되도록 합니다.
2. 텍스트 필드와 셀렉트 필드에 다음과 같은 레이블이 지정되어야 합니다.
   - 3개의 텍스트 필드: 이름, 이메일, 닉네임
   - 2개의 셀렉트 필드: 직군, MBTI
3. 이름, 이메일, 닉네임, 직군은 필수 입력 요소이고, 레이블 우측에 필수 입력 요소임을 나타내는 ‘(필수\*)’ 글자가 표시되어야 합니다.
   - 태그: `<span></span>`
   - 속성: `class="mark"`
4. 이름, 이메일, 닉네임에 대해서는 유효성 확인이 필요합니다.
   - 이름: 한글만 입력이 가능하며, 문자열의 길이는 2\~4입니다. 또한 숫자 및 특수문자 입력은 불가능합니다.
   - 이메일:
     - 이메일 ID: 대소문자 구분 없이 영문만 입력이 가능합니다. 숫자 입력은 가능하지만, 특수문자 입력은 불가능합니다.
     - 메일 서버 도메인 주소: `grepp.co` 만 입력이 가능합니다.
   - 닉네임: 대소문자 구분 없이 영문만 입력이 가능하며, 문자열의 길이는 3\~10 입니다.
   - 텍스트 필드에 잘못된 값을 입력했을 경우, 해당 필드에 대한 간단한 설명을 추가함으로써 사용자가 정확한 값을 입력할 수 있도록 합니다.
     - 이름의 경우, 아래 그림과 같이 _"2\~4 글자의 한글만 입력이 가능합니다."_ 라는 설명이 추가되어야 합니다.
       ![img_signuppage_func_08.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/ae7c6e49-38bb-4164-9220-08de28c28dfe/img_signuppage_func_08.png)
     - 이메일의 경우, 아래 그림과 같이 _"이메일 ID는 영문(대소문자 구분 없음)과 숫자만 입력이 가능하며, @grepp.co 형식의 이메일만 입력이 가능합니다."_ 라는 설명이 추가되어야 합니다.
       ![img_signuppage_func_14.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/819f08e3-7e1e-4d97-a3fb-0128d305df0c/img_signuppage_func_14.png)
     - 닉네임의 경우, 아래 그림과 같이 _"대소문자 구분 없이 3\~10 글자의 영문만 입력이 가능합니다."_ 이라는 설명이 추가되어야 합니다.
       ![img_signuppage_func_20.png](https://grepp-programmers.s3.ap-northeast-2.amazonaws.com/files/production/b54d4138-86f4-4482-86e5-c7bd0a0aff24/img_signuppage_func_20.png)
5. 직군은 4개의 옵션 - 직군을 선택해주세요, 프론트엔드, 백엔드, 풀스택 - 을 가지고 있습니다.
6. MBTI는 17개의 옵션 - MBTI를 선택해주세요, ENFJ, ENTJ, ENFP, ENTP, ESFJ, ESTJ, ESFP, ESTP, INFJ, INTJ, INFP, INTP, ISFJ, ISTJ, ISFP, ISTP - 을 가지고 있습니다.
7. 필수 입력 요소들의 값이 채워진 후 "등록" 버튼을 클릭하면
   - 입력받은 이메일과 닉네임이 로컬스토리지에 없는 새로운 데이터일 경우, 로컬스토리지에 새 인사 정보가 추가됩니다.
   - 새 항목이 로컬스토리지 목록에 추가되면 _"성공적으로 등록되었습니다."_ alert 창이 나타납니다.
   - 새 항목이 로컬스토리지 목록에 성공적으로 추가되면 텍스트 및 셀렉트 필드 값이 초기화되고, URL은 `/web/signup` 으로 변함이 없어야 합니다.
   - 입력받은 이메일 혹은 닉네임과 중복되는 데이터가 로컬저장소에 있는 경우, _“이메일 혹은 닉네임이 이미 등록되어 있습니다.”_ 라는 메시지와 함께 오류 경고창이 표시됩니다.

_참고: 컴포넌트를 작성하는데 필요한 함수 등을 작성하기 위해 새로운 파일을 생성하는 것은 가능합니다._

### **3.3. 스타일**

> 파일: 주어진 <b>`style.css`</b> 파일 내에서만 코드를 작성 및 수정합니다.

- 레이블 영역의 스타일
  - padding 속성을 이용하여 레이블 영역 안쪽에 상하 `3px`, 좌우 `5px` 크기만큼의 여백을 줍니다.
  - 레이블의 글자 크기는 `0.7em` 이고, 글자 색상은 `#5A5C66` 입니다.
  - 필수 요소임을 나타내는 글자는 레이블의 우측에 위치하며 글자의 색상은 빨간색입니다.
- 텍스트 필드와 셀렉트 필드 스타일
  - 3개의 텍스트 필드의 글자 크기는 `1.0em`, 글자 색상은 `#5A5C66` 입니다.
  - 2개의 셀렉트 필드의 글자 크기는 `1.0em`, 글자 색상은 `#5A5C66` 입니다.
- “등록" 버튼 스타일
  - 버튼의 글자 크기는 `1.0em` 입니다.
  - 버튼의 배경색은 `#29323C` 이고, 글자 색상은 흰색입니다.
  - 버튼 위에 마우스 오버를 하면 커서가 손 모양으로 바뀝니다.
  - 버튼 위에 마우스 오버를 하면 버튼의 색상이 `#637488`로 바뀝니다.

_참고: CSS 선택자(class 및 id)는 수정이 불가합니다._
