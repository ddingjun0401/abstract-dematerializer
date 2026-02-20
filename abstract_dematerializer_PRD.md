# 초록 해체 분석기 PRD

------------------------------------------------------------------------

## 0. PRD 한 줄 요약 (One-liner)

이 서비스는 논문을 읽는 대학생·대학원생이 논문 초록의 핵심 영어 단어를
기반으로 자신의 이해 부족을 진단하고, 맞춤형 단어장을 통해 논문 이해력을
높이도록 돕는 웹 기반 학습 서비스이다.

------------------------------------------------------------------------

## 1. Problem (문제 정의)

### 1-1. 어떤 문제가 있는가?

#### 🔹 지금 어떤 상황에서 문제가 발생하는가?

-   논문을 읽을 때 초록(Abstract)에서부터 이해가 막힌다.
-   모르는 단어가 있어도 "대충 맥락으로 넘긴다."
-   초록은 이해했는데 본문에서 또 막힌다.
-   단어를 따로 정리하려면 너무 번거롭다.

#### 🔹 이 문제가 왜 중요한가?

-   초록은 논문의 압축판이다.
-   초록 단어를 이해 못하면:
    -   연구 질문을 잘못 이해한다.
    -   방법론을 오해한다.
    -   결과 해석이 틀린다.
-   결국 논문 읽는 시간이 2\~3배 늘어난다.

#### 🔹 가이드 질문 기반 정리

  -----------------------------------------------------------------------
  질문                      현재 상황
  ------------------------- ---------------------------------------------
  이 문제는 언제            새로운 논문을 처음 읽을 때
  발생하는가?               

  지금은 어떻게 해결하는가? 사전 검색 / GPT에 복붙 / 따로 단어장 정리

  왜 불편한가?              흐름이 끊기고, 반복되고, 체계적이지 않음
  -----------------------------------------------------------------------

------------------------------------------------------------------------

### 1-2. 왜 아직 잘 해결되지 않았는가?

#### 🔹 기존 해결책의 한계

📖 일반 단어장 앱\
- 논문 맥락과 연결되지 않음\
- 빈도 기반 우선순위 없음

🔍 사전 검색\
- 즉각적 이해는 되지만 누적 학습 안 됨

🤖 GPT 요약\
- 단어 이해 대신 요약에 의존하게 됨\
- 장기적 독해력 향상에 도움 제한적

#### 🔹 구조적 문제

-   논문 단어를 체계적으로 추출해주는 서비스가 거의 없음
-   초록 기반 학습 설계가 없음
-   논문 구조 기반 확장 학습이 없음

------------------------------------------------------------------------

## 2. Target User (타겟 사용자)

### 2-1. 핵심 사용자 정의

-   연령: 22\~32세
-   직업: 대학생 / 대학원생 / 연구 초심자
-   상황:
    -   매주 논문을 읽어야 함
    -   영어 논문이 부담스러움
    -   초록에서 이해가 막힘

예시 인물:

> 26세 대학원 1학기 학생.\
> 수업과 연구를 위해 매주 5편 이상 논문을 읽지만, 초록 단어 때문에 읽는
> 속도가 느림.

------------------------------------------------------------------------

### 2-2. 사용 시나리오

1.  논문 PDF 업로드\
2.  초록 단어 자동 추출\
3.  "이 단어 아나요?" 체크\
4.  모르는 단어 기반 자동 단어장 생성\
5.  초록 학습 완료\
6.  추가 학습 단어장 생성 (본문 확장 예측 기반)

------------------------------------------------------------------------

## 3. Solution (해결책)

### 3-1. 우리가 제공하는 핵심 해결 방식

논문 초록 단어를 기반으로 내 이해 수준을 진단하고, 논문 독해에 최적화된
맞춤 단어장을 자동 생성해준다.

**👉 논문 읽기 전에, 내가 모르는 단어부터 정리해준다.**

------------------------------------------------------------------------

### 3-2. 핵심 기능 (3개 이내)

#### 1️⃣ 초록 단어 자동 추출 기능

-   PDF 업로드
-   초록 영역 자동 인식
-   영단어 전체 추출
-   중복 제거 + 빈도 정렬

#### 2️⃣ 이해도 체크 기반 맞춤 단어장 생성

-   단어 O/X 체크
-   모르는 단어만 정리
-   정의 + 예문 + 논문 문맥 예시 제공

#### 3️⃣ 확장 예측 단어장 생성

-   초록의 핵심 개념 기반
-   본문에서 자주 등장할 확장 단어 추천

예: - abstract에 "heuristic" → "systematic processing" 예측 - abstract에
"anthropomorphism" → "mind perception", "agency" 추천

⚠️ 기능 확장 금지\
- 게임화 ❌\
- 커뮤니티 ❌\
- 요약 기능 ❌

초기에는 단어 학습 특화에 집중

------------------------------------------------------------------------

## 4. User Flow

1.  웹 접속\
2.  논문 PDF 업로드\
3.  초록 자동 추출\
4.  단어 이해 체크\
5.  맞춤 단어장 생성\
6.  확장 단어장 생성\
7.  저장 또는 복습

------------------------------------------------------------------------

## 5. Success Metric

### 📊 정량 지표

-   논문 1편당 평균 단어 학습 완료율 ≥ 70%
-   2회 이상 업로드 사용자 비율 ≥ 40%

보조 지표: - 단어장 다운로드 비율 - 초록 학습 완료까지 평균 시간

------------------------------------------------------------------------

## 6. Scope & Constraints

### 6-1. 이번 프로젝트에서 하지 않는 것

-   로그인 기능 없음
-   사용자 데이터 저장 없음
-   논문 전체 자동 번역 기능 없음
-   AI 요약 기능 없음
-   모바일 앱 개발 없음 (웹 only)

### 6-2. 현실적 제약

-   1\~2인 개발
-   NLP 완벽 정확도 불가
-   초록 추출 정확도 목표 80\~90%
-   개발 기간 4\~6주 MVP

------------------------------------------------------------------------

## 7. Why Now?

### 🔹 기술적 이유

-   LLM 기반 텍스트 파싱 정확도 상승
-   PDF 구조 인식 기술 발전
-   맞춤형 학습 AI 구현 비용 하락

### 🔹 사용자 환경 변화

-   대학원생 논문 읽기 부담 증가
-   영어 논문 의존도 증가
-   AI 학습 보조 도구 사용 증가

요약 서비스는 많지만, 독해력을 직접 올려주는 서비스는 거의 없음.

------------------------------------------------------------------------

## 8. Reference / Inspiration

-   Quizlet
-   Anki
-   Semantic Scholar
-   Grammarly

**차별점: 논문 초록 중심 학습 설계**

------------------------------------------------------------------------

# 개발 상세 명세 (Development Specification)

> 아래 섹션은 위 기획 PRD(섹션 0\~8)를 기반으로, 실제 개발에 착수할 수
> 있도록 기술 스택·아키텍처·API·UI·에러 처리·개발 일정 등을 상세히
> 기술한다.

------------------------------------------------------------------------

## 9. 기술 스택 명세 (Tech Stack)

### 9-1. Frontend

| 구분 | 기술 | 버전/비고 |
|------|------|-----------|
| 프레임워크 | **Next.js 15** (App Router) | SSR + API Routes 통합 |
| 언어 | **TypeScript** | 타입 안전성 확보 |
| 스타일링 | **Tailwind CSS v4** | 유틸리티 기반, 빠른 반복 |
| UI 컴포넌트 | **shadcn/ui** | Radix UI 기반, 접근성 보장, Tailwind 통합 |
| 상태 관리 | **Zustand** + sessionStorage persist | 로그인 없음 → 탭 단위 상태 관리 |
| PDF 미리보기 | **react-pdf** (pdfjs-dist 래핑) | 업로드 시 PDF 프리뷰 (선택) |

### 9-2. Backend (Next.js API Routes)

| 구분 | 기술 | 용도 |
|------|------|------|
| API 레이어 | **Next.js Route Handlers** (`app/api/`) | 별도 서버 불필요, 서버리스 |
| PDF 파싱 | **pdf-parse** | 순수 JS, 서버리스 호환, 텍스트 추출 |
| NLP/토큰화 | **compromise.js** | 토큰화, POS 태깅, 레마화 (영어 특화) |
| 학술 단어 필터 | **AWL/AVL 정적 JSON** | AWL 570 단어군 + AVL 3,000 레마 |
| 사전 API | **Free Dictionary API** | 무료, API 키 불필요, 정의+예문+발음 제공 |
| LLM | **Google Gemini API** (`@google/genai`) | Flash-Lite 무료 티어: 1,000 req/day, 15 RPM |

> **Free Dictionary API 엔드포인트:**
> `GET https://api.dictionaryapi.dev/api/v2/entries/en/{word}`

> **Gemini 용도:** (1) 초록 추출 폴백 (2) 확장 단어 예측 (3) 문맥 예문
> 생성 (4) 사전 미등록 단어 정의 폴백

### 9-3. 인프라

| 구분 | 기술 | 비고 |
|------|------|------|
| 호스팅 | **Vercel** (Hobby plan) | 150K 함수 호출/월, 10초 타임아웃, 100GB 대역폭 |
| 파일 업로드 | Vercel Serverless Functions | 최대 4.5MB (학술 PDF 보통 0.5\~3MB) |
| 환경 변수 | `.env.local` | `GEMINI_API_KEY` 저장 (.gitignore에 포함됨) |
| 패키지 매니저 | **npm** | |

### 9-4. 개발 도구

- **ESLint**: 코드 품질
- **Prettier**: 코드 포맷팅
- **Vitest + React Testing Library**: 단위/통합 테스트
- **Playwright**: E2E 테스트 (MVP 이후 선택)

------------------------------------------------------------------------

## 10. 시스템 아키텍처 (System Architecture)

### 10-1. 고수준 아키텍처

```
[브라우저 클라이언트]
    │
    ├── Next.js App Router (SSR + CSR)
    │     ├── Page: /                    (업로드)
    │     ├── Page: /analyze             (초록 확인)
    │     ├── Page: /analyze/words       (단어 체크)
    │     ├── Page: /vocabulary          (맞춤 단어장)
    │     └── Page: /vocabulary/extension (확장 단어장)
    │
    ├── Zustand Store (sessionStorage persist)
    │     ├── pdfFileName, abstractText
    │     ├── extractedWords[]
    │     ├── wordChecks{}
    │     ├── vocabularyList[]
    │     └── extensionWords[]
    │
    └── Next.js API Routes (Serverless)
          ├── POST /api/extract-abstract
          │     ├── pdf-parse (텍스트 추출)
          │     ├── Regex + Heuristic (초록 감지)
          │     └── Gemini API (폴백)
          │
          ├── POST /api/extract-words
          │     ├── compromise.js (토큰화, POS)
          │     ├── AWL/AVL 필터
          │     └── 빈도 정렬 + 중복 제거
          │
          ├── POST /api/define-words
          │     ├── Free Dictionary API (일괄 조회)
          │     └── Gemini API (폴백)
          │
          └── POST /api/extension-words
                ├── Gemini API (확장 단어 예측)
                └── Free Dictionary API (정의 조회)
```

### 10-2. 데이터 플로우

```
1. 업로드 → Browser File API → FormData POST → /api/extract-abstract
   → pdf-parse → 초록 감지 알고리즘 → { abstract, method, confidence }

2. 단어 추출 → abstract text POST → /api/extract-words
   → compromise.js → AWL 필터 → { words[], totalCount, academicCount }

3. 이해도 체크 → 클라이언트 전용 (Zustand 상태)
   → 사용자 O/X 입력 → wordChecks 업데이트

4. 단어장 생성 → unknown words POST → /api/define-words
   → Free Dictionary API + Gemini 폴백 → { vocabulary[] }

5. 확장 단어 → abstract + words POST → /api/extension-words
   → Gemini 예측 → Free Dictionary API → { extensionWords[] }
```

### 10-3. 초록 추출 3단계 알고리즘

학술 PDF는 초록 구조가 표준화되어 있지 않으므로, 다층 감지 방식을 사용한다.

**Layer 1 - 키워드 경계 감지 (Regex)**

```
패턴: /abstract[\s\n]*(.+?)(?=\n\s*(?:introduction|keywords|1\.|I\.|key\s*words))/is
```

- "Abstract" 키워드를 섹션 헤더로 인식
- 다음 섹션 헤더(Introduction, Keywords, 1., I.)까지 텍스트 캡처

**Layer 2 - 휴리스틱 폴백**

- "Abstract" 키워드가 없는 경우 발동
- 제목(ALL CAPS 또는 짧은 중앙 정렬), 저자명(콤마 구분 고유명사), 소속(University, Department, 이메일) 라인 건너뜀
- 본문 시작부터 150\~300 단어 캡처

**Layer 3 - Gemini API 폴백**

- Layer 1, 2의 결과가 50단어 미만 또는 500단어 초과 시 발동
- PDF 첫 2페이지 텍스트를 Gemini에 전송

```
프롬프트: "다음은 학술 논문의 첫 부분입니다. Abstract(초록) 부분만 정확히
추출해주세요. 초록이 명시적으로 표시되지 않은 경우, 논문의 요약에 해당하는
첫 번째 단락을 반환하세요. JSON 형식으로 반환: { \"abstract\": \"...\" }"
```

**정확도 목표:** 80\~90% (섹션 6-2 제약 조건 준수)

------------------------------------------------------------------------

## 11. 데이터/저장소 설계 (Storage Design)

### 11-1. 원칙

- 서버 측 데이터베이스 없음 (섹션 6-1: 사용자 데이터 저장 없음)
- 모든 상태는 브라우저 내 Zustand + sessionStorage에 저장
- 탭 종료 시 데이터 자동 삭제

### 11-2. Zustand 스토어 스키마

```typescript
// lib/types.ts

interface AppState {
  // Step 1: 업로드
  pdfFile: File | null;
  pdfFileName: string;
  rawText: string;

  // Step 2: 초록
  abstractText: string;
  abstractExtractionMethod: 'regex' | 'heuristic' | 'llm';
  abstractConfidence: number; // 0~1

  // Step 3: 단어 목록
  extractedWords: ExtractedWord[];

  // Step 4: 이해도 체크
  wordChecks: Record<string, 'known' | 'unknown' | 'unchecked'>;

  // Step 5: 단어장
  vocabularyList: VocabularyEntry[];

  // Step 6: 확장 단어
  extensionWords: VocabularyEntry[];

  // UI 상태
  currentStep: 1 | 2 | 3 | 4 | 5 | 6;
  isLoading: boolean;
  error: string | null;
}

interface ExtractedWord {
  word: string;           // 원형
  lemma: string;          // 기본형 (레마)
  frequency: number;      // 초록 내 출현 횟수
  pos: string;            // 품사 (noun, verb, adjective, adverb)
  isAcademic: boolean;    // AWL/AVL 매칭 여부
  sentenceContext: string; // 초록에서의 원문 문장
}

interface VocabularyEntry {
  word: string;
  lemma: string;
  phonetic: string;        // 발음 기호
  audioUrl: string;        // 발음 오디오 URL
  definitions: Definition[];
  paperContext: string;     // 초록에서의 문맥 예문
  customExample: string;   // Gemini 생성 도메인 예문
  source: 'dictionary' | 'llm';
}

interface Definition {
  partOfSpeech: string;
  definition: string;
  example: string;
  synonyms: string[];
}

// 확장 단어 전용 추가 필드
interface ExtensionVocabularyEntry extends VocabularyEntry {
  reason: string;              // 예측 근거
  relatedAbstractWord: string; // 연결된 초록 단어
}
```

### 11-3. sessionStorage Persist 설정

```typescript
// lib/store.ts
import { create } from 'zustand';
import { persist, createJSONStorage } from 'zustand/middleware';

export const useAppStore = create<AppState>()(
  persist(
    (set, get) => ({
      // 초기값 및 액션 정의
    }),
    {
      name: 'abstract-dematerializer-storage',
      storage: createJSONStorage(() => sessionStorage),
      partialize: (state) => ({
        // File 객체는 직렬화 불가 → 파일명만 저장
        pdfFileName: state.pdfFileName,
        abstractText: state.abstractText,
        abstractExtractionMethod: state.abstractExtractionMethod,
        extractedWords: state.extractedWords,
        wordChecks: state.wordChecks,
        vocabularyList: state.vocabularyList,
        extensionWords: state.extensionWords,
        currentStep: state.currentStep,
      }),
    }
  )
);
```

### 11-4. 정적 데이터 파일

```
data/
  awl-words.json      ← AWL 570 단어군 (~3,000 변형 포함)
  common-2000.json    ← 영어 상위 2,000 빈출 단어 (제외 목록)
```

- 빌드 타임 또는 첫 API 요청 시 로드, 인메모리 캐시

------------------------------------------------------------------------

## 12. 상세 기능 명세 (Feature Specifications)

### 기능 1: PDF 업로드 및 초록 추출

#### 12-1-1. PDF 업로드

- **허용 형식:** `.pdf` 파일만
- **최대 크기:** 4MB (Vercel 4.5MB 제한에 여유)
- **업로드 방식:** `FormData` via `fetch` POST
- **클라이언트 검증:** 파일 타입, 파일 크기
- **서버 검증:** 파일 타입 재확인, pdf-parse 시도

#### 12-1-2. 텍스트 추출 파이프라인

```
1. PDF를 Buffer로 수신
2. pdf-parse → data.text (전체 텍스트) + data.numpages
3. numpages > 50이면 거부 (일반 논문 아님)
4. 초록 감지 알고리즘 실행 (10-3 참조)
5. 반환: { abstract, method, confidence, pageCount }
```

#### 12-1-3. 초록 수동 편집

- 추출된 초록을 사용자에게 보여줌
- 부정확할 경우 textarea에서 직접 수정 가능
- "이 초록이 맞나요?" 확인 단계: `수정하기` / `이 초록으로 진행` 버튼

---

### 기능 2: 단어 추출 및 이해도 체크

#### 12-2-1. 단어 추출 파이프라인

```
1. 초록 텍스트 수신
2. compromise.js로 문장 분리 → 토큰 분리
3. POS 태깅: 명사, 동사, 형용사, 부사 식별
4. 레마화: "hypothesized" → "hypothesize"
5. 필터링:
   - 구두점, 숫자, 1글자 제거
   - common-2000.json 제외 목록 필터
   - 고유명사 제거 (compromise NER)
   - awl-words.json 매칭 시 isAcademic: true
6. 중복 제거: 레마 기준 그룹화, 빈도 카운트
7. 정렬: 1차 빈도(내림차순), 2차 학술 단어 우선
```

**예상 결과:** 일반적인 초록(150\~300단어)에서 15\~40개의 학술/전문 단어 추출

#### 12-2-2. 이해도 체크 UI

- 단어를 카드 형태로 스크롤 가능한 목록에 표시
- 각 카드: 단어(대), 품사 뱃지(소), 빈도 수(소)
- O (초록, "알아요") / X (빨강, "몰라요") 토글 버튼
- 일괄 선택: `모두 모름` / `모두 앎` 버튼
- 진행률: "15/32 단어 체크 완료"
- 모든 단어 체크 완료 전까지 다음 단계 비활성

---

### 기능 3: 맞춤형 단어장 생성

#### 12-3-1. 사전 조회 파이프라인

```
1. "unknown"으로 표시된 단어 수집
2. 각 단어에 대해 Free Dictionary API 호출:
   GET https://api.dictionaryapi.dev/api/v2/entries/en/{word}
3. 레이트 리밋: 요청 간 50ms 딜레이 (60 req/min 이내)
4. API 404 또는 불완전 데이터 시 Gemini 폴백:
   프롬프트: "학술 영단어 '{word}'의 사전 항목을 제공해주세요.
   JSON: { definition, partOfSpeech, example, synonyms[] }"
5. 초록 내 해당 단어 등장 문장 추출 (sentenceContext 활용)
```

#### 12-3-2. 문맥 예문 생성 (Gemini)

```
프롬프트: "'{word}'라는 단어가 다음 학술 초록에 등장합니다: '{abstractText}'.
같은 학술 분야에서 '{word}'의 사용법을 보여주는 명확한 예문 1개를 생성하세요.
비원어민 영어 학습자가 이해할 수 있어야 합니다.
JSON: { example: string }"
```

**배치 최적화:** 모든 미지 단어를 하나의 Gemini 요청으로 묶어 API 호출 최소화

#### 12-3-3. 단어 카드 표시 항목

| 항목 | 설명 |
|------|------|
| 단어 | 원형 + 발음 기호 |
| 오디오 | 발음 재생 버튼 |
| 품사 | 뱃지 (noun, verb 등) |
| 정의 | 주요 정의 1\~2개 |
| 사전 예문 | 일반 영어 예문 |
| 논문 문맥 | 초록에서의 원문 (해당 단어 **굵게** 표시) |
| AI 예문 | Gemini 생성 도메인 맞춤 예문 |
| 동의어 | 접기/펼치기 |

---

### 기능 4: 확장 예측 단어장

#### 12-4-1. 확장 단어 예측 (Gemini)

```
프롬프트:
"당신은 학술 어휘 전문가입니다. 다음은 학술 논문의 초록입니다:
'{abstractText}'

초록의 핵심 단어: [{wordList}]

이 논문의 **본문(body)**에서 높은 확률로 등장하지만 초록에는 없는
학술 영어 단어 10~15개를 예측해주세요. 다음에 집중하세요:
1. 연구 방법론 관련 용어
2. 통계/분석 용어
3. 해당 분야 전문 용어
4. 학술 담화 표지어

JSON 배열: [{ word: string, reason: string, relatedAbstractWord: string }]"
```

#### 12-4-2. 확장 단어 보강

- 기능 3과 동일한 사전 조회 파이프라인 적용
- 추가 필드: `reason` (예측 근거), `relatedAbstractWord` (연결 초록 단어)

#### 12-4-3. 확장 단어장 표시

- 기능 3과 동일한 카드 포맷
- 추가: "연결 단어" 뱃지 (어떤 초록 단어와 관련되는지)
- "예측 단어" 라벨로 명확히 구분

------------------------------------------------------------------------

## 13. API 설계 (API Endpoints)

### 13-1. `POST /api/extract-abstract`

**Request:**
```
Content-Type: multipart/form-data
Body: { file: File (PDF, max 4MB) }
```

**Response (200):**
```json
{
  "success": true,
  "data": {
    "abstract": "The purpose of this study...",
    "method": "regex",
    "confidence": 0.92,
    "pageCount": 12,
    "title": "Paper Title or null"
  }
}
```

**Errors:**
```
400: { "success": false, "error": "INVALID_FILE_TYPE" }
      "PDF 파일만 업로드 가능합니다"

400: { "success": false, "error": "FILE_TOO_LARGE" }
      "파일 크기가 4MB를 초과합니다"

400: { "success": false, "error": "EMPTY_PDF" }
      "PDF에서 텍스트를 추출할 수 없습니다"

422: { "success": false, "error": "ABSTRACT_NOT_FOUND", "fallbackText": "..." }
      "초록을 자동으로 찾지 못했습니다"

500: { "success": false, "error": "PARSE_FAILED" }
      "PDF 파일을 읽을 수 없습니다"
```

---

### 13-2. `POST /api/extract-words`

**Request:**
```json
{
  "abstract": "The purpose of this study..."
}
```

**Response (200):**
```json
{
  "success": true,
  "data": {
    "words": [
      {
        "word": "heuristic",
        "lemma": "heuristic",
        "frequency": 3,
        "pos": "noun",
        "isAcademic": true,
        "sentenceContext": "Participants relied on heuristic processing..."
      }
    ],
    "totalUniqueWords": 28,
    "academicWordCount": 15,
    "abstractWordCount": 230
  }
}
```

**Errors:**
```
400: { "success": false, "error": "ABSTRACT_TOO_SHORT" }
      "초록이 너무 짧습니다 (최소 30단어)"

400: { "success": false, "error": "ABSTRACT_TOO_LONG" }
      "초록이 너무 깁니다 (최대 500단어)"
```

---

### 13-3. `POST /api/define-words`

**Request:**
```json
{
  "words": ["heuristic", "anthropomorphism", "mediation"],
  "abstractText": "The purpose of this study..."
}
```

**Response (200):**
```json
{
  "success": true,
  "data": {
    "vocabulary": [
      {
        "word": "heuristic",
        "lemma": "heuristic",
        "phonetic": "/hjʊˈɹɪstɪk/",
        "audioUrl": "https://...",
        "definitions": [
          {
            "partOfSpeech": "noun",
            "definition": "A practical method for solving problems...",
            "example": "The heuristic approach proved effective.",
            "synonyms": ["rule of thumb", "shortcut"]
          }
        ],
        "paperContext": "Participants relied on **heuristic** processing...",
        "customExample": "In cognitive psychology, a heuristic is a mental shortcut...",
        "source": "dictionary"
      }
    ],
    "dictionaryHits": 2,
    "llmFallbacks": 1
  }
}
```

**Errors:**
```
400: { "success": false, "error": "NO_WORDS_PROVIDED" }
429: { "success": false, "error": "RATE_LIMIT_EXCEEDED" }
      "요청이 너무 많습니다. 잠시 후 다시 시도해주세요"
```

---

### 13-4. `POST /api/extension-words`

**Request:**
```json
{
  "abstractText": "The purpose of this study...",
  "knownWords": ["method", "result"],
  "unknownWords": ["heuristic", "anthropomorphism"]
}
```

**Response (200):**
```json
{
  "success": true,
  "data": {
    "extensionWords": [
      {
        "word": "systematic processing",
        "reason": "heuristic의 대비 개념으로 본문에서 비교 논의 예상",
        "relatedAbstractWord": "heuristic",
        "lemma": "systematic processing",
        "phonetic": "...",
        "definitions": [...],
        "paperContext": "",
        "customExample": "...",
        "source": "llm"
      }
    ],
    "predictionCount": 12
  }
}
```

**Errors:**
```
500: { "success": false, "error": "LLM_GENERATION_FAILED" }
      "확장 단어 생성에 실패했습니다. 다시 시도해주세요"
```

---

### 13-5. 레이트 리밋

| 엔드포인트 | 제한 | 방식 |
|-----------|------|------|
| `/api/extract-abstract` | 10 req/min per IP | 인메모리 |
| `/api/extract-words` | 20 req/min per IP | 인메모리 |
| `/api/define-words` | 5 req/min per IP | 인메모리 |
| `/api/extension-words` | 5 req/min per IP | 인메모리 |

------------------------------------------------------------------------

## 14. UI/UX 페이지별 상세 기술서

### 14-1. 메인/업로드 페이지 (`/`)

**레이아웃:**
```
┌─────────────────────────────────────────┐
│  Step ① ─ ② ─ ③ ─ ④ ─ ⑤  (진행 표시줄) │
├─────────────────────────────────────────┤
│                                         │
│         초록 해체 분석기                  │
│  논문 초록의 영단어를 분석하고            │
│  나만의 맞춤 단어장을 만들어보세요        │
│                                         │
│  ┌─────────────────────────────┐        │
│  │                             │        │
│  │   📄 PDF 파일을 드래그하거나  │        │
│  │      클릭하여 업로드하세요    │        │
│  │                             │        │
│  │      [파일 선택하기]         │        │
│  │                             │        │
│  │  .pdf 파일만 가능 · 최대 4MB │        │
│  └─────────────────────────────┘        │
│                                         │
└─────────────────────────────────────────┘
```

**한국어 UI 텍스트:**
| 요소 | 텍스트 |
|------|--------|
| 제목 | "초록 해체 분석기" |
| 부제 | "논문 초록의 영단어를 분석하고 나만의 맞춤 단어장을 만들어보세요" |
| 드래그존 안내 | "PDF 파일을 드래그하거나 클릭하여 업로드하세요" |
| 버튼 | "파일 선택하기" |
| 제한 안내 | ".pdf 파일만 가능 · 최대 4MB" |
| 로딩 | "PDF를 분석하고 있습니다..." |
| 에러: 파일 형식 | "PDF 파일만 업로드 가능합니다" |
| 에러: 크기 초과 | "파일 크기가 4MB를 초과합니다" |
| 에러: 스캔 PDF | "텍스트를 추출할 수 없는 PDF입니다. 스캔된 PDF는 지원하지 않습니다" |
| 에러: 비영어 | "영어 논문만 지원합니다" |

**컴포넌트:** `pdf-upload-zone.tsx` (드래그앤드롭 + 파일 선택 + 검증)

---

### 14-2. 초록 확인 페이지 (`/analyze`)

**레이아웃:**
```
┌─────────────────────────────────────────┐
│  Step ① ─ ●② ─ ③ ─ ④ ─ ⑤              │
├─────────────────────────────────────────┤
│                                         │
│  추출된 초록을 확인해주세요               │
│                                         │
│  ┌─ 추출 방법: 자동 추출 ───────────┐   │
│  │                                  │   │
│  │  The purpose of this study was   │   │
│  │  to examine the relationship...  │   │
│  │                                  │   │
│  └──────────────────────────────────┘   │
│                                         │
│  ⚠️ 추출 정확도가 낮을 수 있습니다.      │
│     초록을 확인해주세요. (confidence<0.7) │
│                                         │
│  [수정하기]        [이 초록으로 진행하기]  │
│                                         │
└─────────────────────────────────────────┘
```

**한국어 UI 텍스트:**
| 요소 | 텍스트 |
|------|--------|
| 제목 | "추출된 초록을 확인해주세요" |
| 추출 방법 뱃지 | "자동 추출" / "AI 추출" / "휴리스틱 추출" |
| 경고 (confidence < 0.7) | "추출 정확도가 낮을 수 있습니다. 초록을 확인해주세요." |
| 수정 모드 안내 | "초록 텍스트를 직접 수정할 수 있습니다" |
| 버튼: 수정 | "수정하기" |
| 버튼: 진행 | "이 초록으로 진행하기" |
| 버튼: 수정 완료 | "수정 완료" |
| 초록 미발견 시 | "초록을 자동으로 찾지 못했습니다. 아래에 직접 붙여넣어주세요." |
| 직접 입력 placeholder | "논문의 초록(Abstract)을 여기에 붙여넣어주세요..." |

---

### 14-3. 단어 이해도 체크 페이지 (`/analyze/words`)

**레이아웃:**
```
┌─────────────────────────────────────────┐
│  Step ① ─ ② ─ ●③ ─ ④ ─ ⑤              │
├─────────────────────────────────────────┤
│                                         │
│  초록에서 28개의 주요 단어를 찾았습니다    │
│  학술 단어 15개 · 전문 용어 13개          │
│                                         │
│  [모두 앎]  [모두 모름]                   │
│                                         │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐│
│  │heuristic │ │mediation │ │cognition ││
│  │noun · 3회 │ │noun · 2회 │ │noun · 1회 ││
│  │ [O] [X]  │ │ [O] [X]  │ │ [O] [X]  ││
│  └──────────┘ └──────────┘ └──────────┘│
│                                         │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐│
│  │ ...      │ │ ...      │ │ ...      ││
│  └──────────┘ └──────────┘ └──────────┘│
│                                         │
├─────────────────────────────────────────┤
│  15/28 체크 완료 │ 앎: 8개 │ 모름: 7개   │
│                    [단어장 생성하기] ▶    │
└─────────────────────────────────────────┘
```

**한국어 UI 텍스트:**
| 요소 | 텍스트 |
|------|--------|
| 제목 | "초록에서 {N}개의 주요 단어를 찾았습니다" |
| 부제 | "학술 단어 {N}개 · 전문 용어 {N}개" |
| O 버튼 | "알아요" (툴팁) |
| X 버튼 | "몰라요" (툴팁) |
| 일괄: 모두 앎 | "모두 앎" |
| 일괄: 모두 모름 | "모두 모름" |
| 진행 표시 | "{checked}/{total} 체크 완료" |
| 요약 | "아는 단어: {known}개 · 모르는 단어: {unknown}개" |
| 진행 버튼 | "단어장 생성하기" |
| 비활성 안내 | "모든 단어를 체크해야 진행할 수 있습니다" |

**카드 상태 시각 표시:**
- 미체크: 회색 테두리
- O (앎): 초록 테두리 + 초록 배경 옅게
- X (모름): 빨강 테두리 + 빨강 배경 옅게

---

### 14-4. 맞춤 단어장 페이지 (`/vocabulary`)

**레이아웃:**
```
┌─────────────────────────────────────────┐
│  Step ① ─ ② ─ ③ ─ ●④ ─ ⑤              │
├─────────────────────────────────────────┤
│                                         │
│  나만의 단어장 - 12개 단어                │
│                                         │
│  [전체] [학술 단어만] │ 정렬: [빈도순 ▼]  │
│                                         │
│  ┌──────────────────────────────────┐   │
│  │ heuristic  /hjʊˈɹɪstɪk/  🔊    │   │
│  │ noun                             │   │
│  │ ──────────────────────────────── │   │
│  │ 정의: A practical method for...  │   │
│  │ 예문: The heuristic approach...  │   │
│  │ ──────────────────────────────── │   │
│  │ 📄 논문 문맥:                    │   │
│  │ "Participants relied on          │   │
│  │  **heuristic** processing when..." │  │
│  │ ──────────────────────────────── │   │
│  │ 💡 도메인 예문:                   │   │
│  │ "In cognitive psychology, a      │   │
│  │  heuristic is a mental shortcut.."│  │
│  │ ──────────────────────────────── │   │
│  │ 동의어: rule of thumb, shortcut  │   │
│  └──────────────────────────────────┘   │
│                                         │
│  ┌──────────────────────────────────┐   │
│  │ mediation  (접힌 상태)     [펼치기]│   │
│  │ noun · "중재, 매개"              │   │
│  └──────────────────────────────────┘   │
│                                         │
├─────────────────────────────────────────┤
│  [확장 단어장 보기 ▶]  [단어장 다운로드 ⬇]│
└─────────────────────────────────────────┘
```

**한국어 UI 텍스트:**
| 요소 | 텍스트 |
|------|--------|
| 제목 | "나만의 단어장 - {N}개 단어" |
| 필터 탭 | "전체" / "학술 단어만" |
| 정렬 | "빈도순" / "알파벳순" |
| 카드: 정의 라벨 | "정의" |
| 카드: 예문 라벨 | "예문" |
| 카드: 논문 문맥 | "논문 문맥" |
| 카드: 도메인 예문 | "도메인 예문" |
| 카드: 동의어 | "동의어" |
| 카드: 접힌 상태 | "[펼치기]" / "[접기]" |
| 카드: 오디오 | 🔊 (발음 재생) |
| 카드: 출처 | "사전" / "AI 생성" 뱃지 |
| 버튼: 확장 | "확장 단어장 보기" |
| 버튼: 다운로드 | "단어장 다운로드" |
| 로딩 | "단어 정보를 불러오고 있습니다..." |
| 에러 | "일부 단어의 정의를 불러올 수 없습니다" |

**다운로드 형식:**
- CSV: `단어, 품사, 정의, 예문, 논문 문맥`
- 텍스트: 보기 좋게 정리된 텍스트 파일

---

### 14-5. 확장 단어장 페이지 (`/vocabulary/extension`)

**레이아웃:**
```
┌─────────────────────────────────────────┐
│  Step ① ─ ② ─ ③ ─ ④ ─ ●⑤              │
├─────────────────────────────────────────┤
│                                         │
│  본문 확장 예측 단어 - 12개               │
│                                         │
│  ℹ️ 이 단어들은 논문 본문에서 자주 등장할  │
│  것으로 예측되는 단어입니다               │
│                                         │
│  ┌──────────────────────────────────┐   │
│  │ systematic processing            │   │
│  │ 연결: heuristic                  │   │
│  │ 근거: heuristic의 대비 개념으로   │   │
│  │       본문에서 비교 논의 예상      │   │
│  │ ────────────────────────────────  │   │
│  │ (단어장 카드와 동일한 형식)        │   │
│  └──────────────────────────────────┘   │
│                                         │
├─────────────────────────────────────────┤
│ [처음부터 다시하기 ↺]  [통합 다운로드 ⬇] │
└─────────────────────────────────────────┘
```

**한국어 UI 텍스트:**
| 요소 | 텍스트 |
|------|--------|
| 제목 | "본문 확장 예측 단어 - {N}개" |
| 안내 배너 | "이 단어들은 논문 본문에서 자주 등장할 것으로 예측되는 단어입니다" |
| 연결 뱃지 | "연결: {relatedAbstractWord}" |
| 근거 라벨 | "예측 근거" |
| 예측 태그 | "예측 단어" 뱃지 |
| 버튼: 리셋 | "처음부터 다시하기" |
| 버튼: 다운로드 | "단어장 통합 다운로드" |
| 로딩 | "확장 단어를 예측하고 있습니다..." |

---

### 14-6. 공통 디자인 시스템

**shadcn/ui 사용 컴포넌트:** `Card`, `Button`, `Badge`, `Progress`, `Toast`, `Textarea`, `Dialog`, `Tabs`, `Separator`

**색상:**
- Primary: 파랑/인디고 (학술 느낌)
- 성공/앎: 초록 (`green-500`)
- 경고/모름: 빨강 (`red-500`)
- 배경: 흰색 / 회색 (`gray-50`)

**반응형:** 모바일 지원하되 데스크톱 최적화 (PDF 업로드가 주로 데스크톱에서 발생)

**진행 표시줄 (Step Progress):**
```
① 업로드 → ② 초록 확인 → ③ 단어 체크 → ④ 단어장 → ⑤ 확장 단어장
```
- 완료 단계: 파란 원 + 체크
- 현재 단계: 파란 원 + 굵은 텍스트
- 미래 단계: 회색 원

------------------------------------------------------------------------

## 15. 에러 처리 및 엣지 케이스

### 15-1. PDF 업로드 에러

| 상황 | 감지 방법 | 사용자 메시지 | 복구 |
|------|----------|-------------|------|
| PDF가 아닌 파일 | 파일 타입 검사 | "PDF 파일만 업로드 가능합니다" | 재업로드 |
| 손상된 PDF | pdf-parse 예외 | "PDF 파일을 읽을 수 없습니다. 다른 파일을 시도해주세요" | 재업로드 |
| 스캔/이미지 PDF | 추출 텍스트 < 50자 | "텍스트를 추출할 수 없는 PDF입니다. 스캔된 PDF는 지원하지 않습니다" | 텍스트 기반 PDF 재업로드 |
| 크기 초과 | 크기 > 4MB | "파일 크기가 4MB를 초과합니다. 더 작은 파일을 업로드해주세요" | 압축 후 재업로드 |
| 비영어 PDF | 언어 감지 휴리스틱 | "영어 논문만 지원합니다" | 영어 논문 업로드 |
| 초록 미발견 | 3단계 감지 모두 실패 | "초록을 자동으로 찾지 못했습니다. 직접 붙여넣기 해주세요" | 수동 입력 textarea 표시 |
| 50페이지 초과 | numpages > 50 | "일반 학술 논문만 지원합니다 (최대 50페이지)" | 다른 PDF 업로드 |

### 15-2. 단어 추출 엣지 케이스

| 상황 | 처리 |
|------|------|
| 매우 짧은 초록 (< 30단어) | 경고 표시 + 제한된 단어로 진행 |
| 매우 긴 초록 (> 500단어) | 500단어로 자르고 안내 |
| 학술 단어 0개 | 가장 빈출이 낮은 10개 단어 포함 |
| 하이픈 복합어 (meta-analysis) | 단일 토큰으로 처리 |
| 약어 (NLP, fMRI) | 보존, 사전 조회 건너뜀, "약어" 표시 |
| 숫자 혼합 (p-value, COVID-19) | 보존, 기술 용어로 분류 |

### 15-3. 사전 API 실패

| 상황 | 처리 |
|------|------|
| 단어 미등록 (404) | Gemini 폴백 |
| 레이트 리밋 도달 | 지수 백오프 재시도 |
| API 완전 다운 | 전체 Gemini 폴백 |
| Gemini도 실패 | "정의를 불러올 수 없습니다" + 검색 링크 제공 |

### 15-4. Gemini API 실패

| 상황 | 처리 |
|------|------|
| 일일 한도 초과 | "오늘 사용량을 초과했습니다. 내일 다시 시도해주세요" |
| 잘못된 JSON 응답 | 1회 재시도 (엄격한 프롬프트), 실패 시 건너뜀 |
| 타임아웃 (> 10초) | 부분 결과 반환 + 안내 |
| 확장 단어 너무 일반적 | AWL 목록 대조 필터링 |

### 15-5. 브라우저/세션 엣지 케이스

| 상황 | 처리 |
|------|------|
| 프로세스 중 새로고침 | sessionStorage에서 상태 복원. PDF 파일은 소실 → "PDF를 다시 업로드해주세요" (초록 데이터는 보존) |
| sessionStorage 용량 초과 | 정상 동작하되 상태 미저장 (graceful degradation) |
| 여러 탭 사용 | 각 탭 독립 상태 (sessionStorage 탭 격리) |
| 느린 네트워크 | 로딩 스피너 + 타임아웃 메시지 |

------------------------------------------------------------------------

## 16. 개발 단계 (4\~6주 MVP)

### Sprint 0: 프로젝트 셋업 (1\~2일차)

- [ ] `npx create-next-app@latest` (TypeScript, Tailwind, ESLint, App Router, npm)
- [ ] shadcn/ui 초기화 + 기본 컴포넌트 설치
- [ ] 프로젝트 폴더 구조 생성
- [ ] Zustand 스토어 스켈레톤
- [ ] `.env.local` 설정 (`GEMINI_API_KEY`)
- [ ] Git 저장소 초기화
- [ ] Vercel 프로젝트 연결

### Sprint 1: PDF 업로드 + 초록 추출 (3\~7일차)

- [ ] 업로드 페이지 UI (드래그앤드롭, 파일 검증)
- [ ] `/api/extract-abstract` 라우트 (pdf-parse 연동)
- [ ] 초록 감지 알고리즘 (Regex + Heuristic)
- [ ] 초록 확인 페이지 (표시 + 편집 + 확인)
- [ ] Gemini 폴백 연동
- [ ] **산출물:** PDF 업로드 → 초록 확인 플로우 완성

### Sprint 2: 단어 추출 + 이해도 체크 (8\~12일차)

- [ ] `/api/extract-words` 라우트 (compromise.js + AWL 필터)
- [ ] 정적 데이터 파일 준비 (AWL JSON, common words JSON)
- [ ] 단어 체크 페이지 UI (카드 그리드, O/X 토글)
- [ ] Zustand 상태 연동
- [ ] 진행률 추적, 일괄 선택, 유효성 검증
- [ ] **산출물:** 단어 추출 + O/X 체크 플로우 완성

### Sprint 3: 단어장 생성 (13\~17일차)

- [ ] `/api/define-words` 라우트 (Free Dictionary API 연동)
- [ ] Gemini 사전 폴백
- [ ] 문맥 예문 생성 (Gemini)
- [ ] 단어장 페이지 UI (펼치기/접기 카드, 오디오, 정의)
- [ ] 필터/정렬 기능
- [ ] **산출물:** 맞춤 단어장 완성

### Sprint 4: 확장 단어장 + 마무리 (18\~22일차)

- [ ] `/api/extension-words` 라우트 (Gemini 예측)
- [ ] 확장 단어장 페이지 UI
- [ ] 다운로드/내보내기 (CSV, 텍스트)
- [ ] 전체 플로우 통합 테스트
- [ ] 레이트 리밋 미들웨어, 에러 바운더리
- [ ] **산출물:** 전체 사용자 플로우 완성

### Sprint 5: 폴리싱 + 배포 (23\~28일차)

- [ ] UI 다듬기, 반응형 확인, 로딩 상태
- [ ] 모든 엣지 케이스 에러 처리
- [ ] 성능 최적화 (API 응답 캐싱, 배치 요청)
- [ ] 테스트 (단위, 통합)
- [ ] Vercel 프로덕션 배포
- [ ] **산출물:** 배포 완료된 MVP

### 버퍼 (6주차)

- 사용자 테스트 기반 버그 수정
- 초록 추출 정확도 튜닝
- Gemini 프롬프트 개선

------------------------------------------------------------------------

## 17. 테스팅 전략

### 17-1. 단위 테스트 (Vitest)

| 대상 | 테스트 내용 |
|------|-----------|
| 초록 감지 Regex | 10+ 실제 초록 형식 (Abstract 헤더 유무, 다양한 섹션 마커) |
| 단어 추출 파이프라인 | 알려진 초록에 대한 토큰화, 레마화, 필터링 |
| AWL 필터 | 학술 단어 정확 식별 |
| Common 단어 필터 | 제외 목록 정상 작동 |
| API 응답 파서 | Dictionary API 응답 정규화, Gemini JSON 파싱 |

### 17-2. 통합 테스트 (Vitest + fetch 모킹)

| 대상 | 테스트 내용 |
|------|-----------|
| `/api/extract-abstract` | 정상 PDF → 올바른 초록, 손상 PDF → 에러, 이미지 PDF → 에러 |
| `/api/extract-words` | 알려진 초록 → 예상 단어 목록, 빈 초록 → 에러 |
| `/api/define-words` | Dictionary 성공, 404 → Gemini 폴백, 전부 실패 → graceful |
| `/api/extension-words` | Gemini 유효 JSON 반환, 잘못된 응답 → 재시도/건너뜀 |

### 17-3. 수동 테스트 체크리스트

- [ ] 10개 실제 학술 PDF 테스트 (CS, 생물학, 심리학, 경제학 등)
- [ ] "Abstract" 라벨 없는 PDF 테스트
- [ ] 매우 짧은 초록 (1\~2문장) 테스트
- [ ] 매우 긴 초록 (300단어 초과) 테스트
- [ ] 비영어 PDF 테스트
- [ ] Chrome, Firefox, Safari 전체 플로우
- [ ] 페이지 새로고침 시 sessionStorage 복원
- [ ] Gemini API 키 누락/유효하지 않은 경우

### 17-4. 성능 기준

| 단계 | 목표 시간 |
|------|----------|
| PDF 업로드 + 초록 추출 | < 3초 |
| 단어 추출 | < 1초 |
| 사전 조회 (20단어) | < 5초 |
| 확장 단어 생성 | < 8초 |
| 전체 플로우 (업로드 → 확장 단어장) | < 30초 |

------------------------------------------------------------------------

## 18. 프로젝트 폴더 구조

```
abstract-dematerializer/
├── app/
│   ├── layout.tsx                      # 루트 레이아웃 (프로바이더)
│   ├── page.tsx                        # 메인/업로드 페이지
│   ├── analyze/
│   │   ├── page.tsx                    # 초록 확인 페이지
│   │   └── words/
│   │       └── page.tsx                # 단어 체크 페이지
│   ├── vocabulary/
│   │   ├── page.tsx                    # 맞춤 단어장 페이지
│   │   └── extension/
│   │       └── page.tsx                # 확장 단어장 페이지
│   ├── api/
│   │   ├── extract-abstract/
│   │   │   └── route.ts               # PDF 업로드 + 초록 추출
│   │   ├── extract-words/
│   │   │   └── route.ts               # 단어 추출
│   │   ├── define-words/
│   │   │   └── route.ts               # 사전 조회 + Gemini 폴백
│   │   └── extension-words/
│   │       └── route.ts               # 확장 단어 예측
│   └── globals.css                     # Tailwind 기본 스타일
├── components/
│   ├── ui/                             # shadcn/ui 컴포넌트
│   │   ├── button.tsx
│   │   ├── card.tsx
│   │   ├── badge.tsx
│   │   ├── progress.tsx
│   │   ├── toast.tsx
│   │   ├── textarea.tsx
│   │   ├── tabs.tsx
│   │   └── dialog.tsx
│   ├── pdf-upload-zone.tsx             # 드래그앤드롭 업로드
│   ├── abstract-viewer.tsx             # 초록 표시 + 편집
│   ├── word-card.tsx                   # 개별 단어 카드 (O/X)
│   ├── word-grid.tsx                   # 단어 카드 그리드
│   ├── vocabulary-card.tsx             # 단어장 항목 카드
│   ├── vocabulary-list.tsx             # 단어장 목록 + 필터
│   ├── step-progress.tsx               # 단계 진행 표시줄
│   └── loading-spinner.tsx             # 로딩 상태
├── lib/
│   ├── store.ts                        # Zustand 스토어
│   ├── types.ts                        # 공유 TypeScript 인터페이스
│   ├── pdf-parser.ts                   # pdf-parse 래퍼
│   ├── abstract-detector.ts            # 초록 감지 알고리즘
│   ├── word-extractor.ts               # compromise.js 단어 추출
│   ├── word-filter.ts                  # AWL/common 단어 필터
│   ├── dictionary-client.ts            # Free Dictionary API 클라이언트
│   ├── gemini-client.ts                # Gemini API 클라이언트 래퍼
│   ├── rate-limiter.ts                 # 레이트 리밋 유틸리티
│   └── export.ts                       # CSV/텍스트 내보내기
├── data/
│   ├── awl-words.json                  # Academic Word List
│   └── common-2000.json                # 영어 상위 2,000 빈출 단어
├── __tests__/
│   ├── abstract-detector.test.ts
│   ├── word-extractor.test.ts
│   ├── word-filter.test.ts
│   └── api/
│       ├── extract-abstract.test.ts
│       ├── extract-words.test.ts
│       └── define-words.test.ts
├── public/
│   └── favicon.ico
├── .env.local                          # GEMINI_API_KEY
├── .gitignore
├── next.config.ts
├── tailwind.config.ts
├── tsconfig.json
└── package.json
```

------------------------------------------------------------------------

## 19. 기술 의사결정 근거 요약

| 결정 | 선택 | 검토한 대안 | 선택 이유 |
|------|------|-----------|----------|
| PDF 파싱 | pdf-parse | pdfjs-dist, unpdf, pdf2json | 순수 JS, 네이티브 바이너리 없음, Vercel 서버리스 즉시 호환 |
| NLP | compromise.js | natural, wink-nlp | 최소 번들, 영어 전용(필요 충분), 빠른 POS 태깅 + 레마화 |
| 학술 단어 필터 | AWL/AVL 정적 JSON | LLM 기반 필터, 빈도 코퍼스 | 결정적, 빠름, API 비용 없음. AWL은 학술 영어 어휘 연구의 표준 |
| 사전 | Free Dictionary API | Merriam-Webster, WordsAPI, Oxford | 완전 무료, API 키 불필요, 충분한 데이터 품질 |
| LLM | Gemini Flash-Lite (무료) | OpenAI GPT, Claude API | 프로젝트 설정에 ai.google.dev 참조. 무료 1,000 req/day, MVP 충분 |
| 상태 관리 | Zustand + sessionStorage | React Context, Redux, localStorage | Zustand 최소(< 1KB). sessionStorage는 탭 격리 + 종료 시 삭제 → "데이터 미저장" 제약 부합 |
| UI 라이브러리 | shadcn/ui | Material UI, Chakra, Ant Design | 복사-붙여넣기 소유권, Radix 기반 접근성, 완벽한 Tailwind 통합 |
| 배포 | Vercel (Hobby) | Netlify, AWS Amplify, Railway | .gitignore에 이미 설정됨. 최고의 Next.js 통합. 무료 티어 MVP 충분 |
