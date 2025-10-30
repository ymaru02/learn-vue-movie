# Vue3 영화 검색 앱

Vue 3와 OMDb API로 만든 현대적인 영화 검색 애플리케이션입니다. 영화, TV 시리즈, 에피소드를 아름답고 반응형 인터페이스로 검색할 수 있습니다.

[![Netlify Status](https://api.netlify.com/api/v1/badges/your-badge-id/deploy-status)](https://app.netlify.com/sites/stupefied-hodgkin-d9d350/deploys)

## 데모

[라이브 데모](https://stupefied-hodgkin-d9d350.netlify.app/)

## 주요 기능

- **영화 검색** - 제목, 타입(영화/시리즈/에피소드), 연도별로 검색
- **상세 정보** - 평점, 줄거리, 출연진 등 영화의 종합적인 정보 확인
- **반응형 디자인** - 데스크톱과 모바일 환경 모두 최적화
- **점진적 이미지 로딩** - 스켈레톤 로더를 활용한 부드러운 이미지 로딩
- **보안 API 연동** - 서버리스 함수를 통한 API 키 보호
- **현대적인 아키텍처** - Vue 3, Vuex 4, Vue Router 4 기반

## 기술 스택

### 프론트엔드
- **Vue 3** - 프로그레시브 JavaScript 프레임워크
- **Vue Router 4** - Vue.js 공식 라우터
- **Vuex 4** - 모듈형 아키텍처 기반 상태 관리
- **Bootstrap 5** - 반응형 디자인을 위한 UI 프레임워크
- **SCSS** - 유지보수 가능한 스타일을 위한 CSS 전처리기

### 빌드 및 개발 도구
- **Webpack 5** - 모듈 번들러
- **Babel** - JavaScript 트랜스파일러
- **ESLint** - 코드 린팅
- **PostCSS** - autoprefixer를 포함한 CSS 처리

### 백엔드
- **Netlify Functions** - API 프록시를 위한 서버리스 함수
- **Axios** - API 요청을 위한 HTTP 클라이언트

### 테스팅
- **Jest** - 단위 테스트 프레임워크
- **Vue Test Utils** - Vue 공식 테스팅 라이브러리
- **Cypress** - E2E 테스트 프레임워크

## 시작하기

### 사전 요구사항

- Node.js (v14 이상)
- npm 또는 yarn
- OMDb API 키 ([OMDb API](http://www.omdbapi.com/apikey.aspx)에서 발급)

### 설치 방법

1. 저장소 클론:
```bash
git clone https://github.com/yourusername/movie-app.git
cd movie-app
```

2. 의존성 설치:
```bash
npm install
```

3. 루트 디렉토리에 `.env` 파일 생성:
```bash
OMDB_API_KEY=your_api_key_here
```

### 개발 서버 실행

Netlify Functions와 함께 개발 서버 실행:
```bash
npm run dev
```

앱은 `http://localhost:8080`에서 실행됩니다.

Webpack 개발 서버만 실행 (서버리스 함수 없이):
```bash
npm run dev:webpack
```

### 빌드

프로덕션용 빌드:
```bash
npm run build
```

빌드된 파일은 `dist/` 디렉토리에 생성됩니다.

## 테스트

### 단위 테스트

Jest로 단위 테스트 실행:
```bash
npm run test:unit
```

사일런트 모드로 테스트 실행:
```bash
npm run test:unit:silent
```

### E2E 테스트

Cypress 테스트 러너 열기:
```bash
npm run test:e2e
```

헤드리스 모드로 Cypress 테스트 실행:
```bash
npm run test:e2e:headless
```

## 코드 품질

ESLint로 코드 검사 및 수정:
```bash
npm run lint
```

## 프로젝트 구조

```
movie-app/
├── src/
│   ├── components/          # 재사용 가능한 Vue 컴포넌트
│   │   ├── Header.vue       # 헤더 컴포넌트
│   │   ├── Footer.vue       # 푸터 컴포넌트
│   │   ├── Search.vue       # 검색 폼 컴포넌트
│   │   ├── MovieList.vue    # 영화 목록 컴포넌트
│   │   ├── MovieItem.vue    # 개별 영화 카드 컴포넌트
│   │   ├── Headline.vue     # 히어로 섹션 컴포넌트
│   │   ├── Loader.vue       # 로딩 스피너 컴포넌트
│   │   └── Logo.vue         # 로고 컴포넌트
│   ├── routes/              # 페이지 컴포넌트
│   │   ├── Home.vue         # 검색 페이지
│   │   ├── Movie.vue        # 영화 상세 페이지
│   │   ├── About.vue        # 소개 페이지
│   │   ├── NotFound.vue     # 404 페이지
│   │   └── index.js         # 라우터 설정
│   ├── store/               # Vuex 상태 관리
│   │   ├── index.js         # Store 설정
│   │   ├── movie.js         # 영화 모듈
│   │   └── about.js         # 소개 모듈
│   ├── plugins/             # 커스텀 Vue 플러그인
│   │   └── loadImage.js     # 이미지 프리로딩 플러그인
│   ├── scss/                # 글로벌 스타일
│   │   └── main.scss
│   ├── assets/              # 정적 자산 (이미지)
│   ├── App.vue              # 루트 컴포넌트
│   └── main.js              # 애플리케이션 진입점
├── functions/               # Netlify 서버리스 함수
│   └── movie.js             # OMDb API 프록시
├── tests/                   # 단위 테스트
│   ├── components/          # 컴포넌트 테스트
│   ├── routes/              # 라우트 테스트
│   └── store/               # Store 테스트
├── cypress/                 # E2E 테스트
│   ├── integration/         # 통합 테스트 시나리오
│   ├── support/             # 테스트 유틸리티
│   └── plugins/             # Cypress 플러그인
└── static/                  # 공개 정적 파일
```

## 환경 변수

다음 변수를 포함한 `.env` 파일을 생성하세요:

```env
OMDB_API_KEY=your_omdb_api_key
```

Netlify 배포 시에는 Netlify 대시보드에서 환경 변수를 설정하세요.

## 배포

### Netlify

이 프로젝트는 GitHub과 연동된 Netlify 지속적 배포로 구성되어 있습니다.

1. GitHub에 코드 푸시
2. Netlify에서 저장소 가져오기
3. Netlify 대시보드에서 환경 변수 설정
4. 배포!

빌드 설정:
- **빌드 명령어:** `npm run build`
- **배포 디렉토리:** `dist`
- **Functions 디렉토리:** `functions`

## API 연동

이 애플리케이션은 [OMDb API](http://www.omdbapi.com/)를 사용하여 영화 데이터를 가져옵니다. API 키는 환경 변수에 안전하게 저장되며, 노출을 방지하기 위해 Netlify Functions를 통해 접근됩니다.

### API 엔드포인트

`/.netlify/functions/movie`의 서버리스 함수는 두 가지 유형의 요청을 처리합니다:

1. **영화 검색:**
```javascript
axios.post('/.netlify/functions/movie', {
  title: 'Inception',
  type: 'movie',
  year: '2010',
  page: 1
})
```

2. **영화 상세 정보:**
```javascript
axios.post('/.netlify/functions/movie', {
  id: 'tt1375666'
})
```

## 브라우저 지원

- Chrome (최신)
- Firefox (최신)
- Safari (최신)
- Edge (최신)

## 기여하기

기여는 언제나 환영합니다! Pull Request를 자유롭게 제출해주세요.

## 라이선스

이 프로젝트는 MIT 라이선스로 제공됩니다.

## 감사의 말

- [OMDb API](http://www.omdbapi.com/) - 영화 데이터 제공
- [Vue.js](https://vuejs.org/) - 훌륭한 프레임워크를 만들어준 팀
- [Bootstrap](https://getbootstrap.com/) - UI 컴포넌트 제공

## 문의

질문이나 피드백이 있으시면 GitHub에서 이슈를 열어주세요.
