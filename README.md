# 라오스 골프 라운지 — 올리는 방법

모르는 손님끼리 같은 공간에 머무는 웹페이지예요. 파일은 이렇게 들어 있어요.

- `index.html` : 라운지 화면 전체
- `config.js` : 실시간 서버 키, 상품 링크, 문의처 (여기만 고치면 돼요)
- `assets/` : 사진

키를 넣지 않아도 혼자 둘러보는 건 됩니다. 아래 1~3단계를 하면 "🟢 함께 모드"가 켜져요.

---

## 1단계. Supabase에서 실시간 서버 만들기 (무료, 5분)

1. https://supabase.com 접속 → **Start your project** → GitHub 계정으로 로그인
2. **New project**
   - Name: `laos-lounge` (아무거나)
   - Database Password: 아무거나 (메모만 해 두세요)
   - Region: **Northeast Asia (Seoul)**
3. 프로젝트가 만들어지면 왼쪽 아래 ⚙️ **Project Settings → API** 로 이동
4. 두 값을 복사해요.
   - **Project URL** (예: `https://abcdefgh.supabase.co`)
   - **anon public** 키 (`eyJ...`로 시작하는 긴 글자)

> 테이블은 만들 필요 없어요. 이 라운지는 저장 없이 "지금 접속한 사람끼리"만 주고받아요.

## 2단계. config.js에 붙여넣기

`config.js`를 메모장으로 열어서 아래 두 줄에 붙여넣고 저장해요.

```js
supabaseUrl: "https://abcdefgh.supabase.co",
supabaseAnonKey: "eyJhbGciOi...",
```

문의처를 보여주고 싶으면 `contact: "카카오톡 채널 @블루스카이투어"`처럼 넣어요.

## 3단계. GitHub Pages로 올리기 (무료)

1. https://github.com 로그인 → 오른쪽 위 **＋ → New repository**
   - Repository name: `laos-lounge`
   - **Public** 선택 → **Create repository**
2. 만들어진 화면에서 **uploading an existing file** 클릭
3. 압축을 푼 폴더 안의 `index.html`, `config.js`, `README.md`, `assets` 폴더를 통째로 끌어다 놓기 → **Commit changes**
4. 저장소 **Settings → Pages**
   - Source: **Deploy from a branch**
   - Branch: **main** / **/(root)** → **Save**
5. 1~2분 뒤 같은 화면 위쪽에 주소가 떠요: `https://아이디.github.io/laos-lounge/`

이 주소를 손님 단톡방이나 인스타 프로필 링크에 넣으면 끝이에요.

---

## 확인하는 법

- 휴대폰과 PC에서 같은 주소로 들어가서, 오른쪽 위가 **🟢 함께 모드**인지 확인
- 한쪽에서 걸어 다니거나 말을 남기면 다른 쪽에 보이면 성공

## 알아두면 좋은 것

- **무료 플랜 제한:** 동시 접속 200명, 월 메시지 200만 건까지 무료라 충분해요.
- **자동 일시정지:** Supabase 무료 프로젝트는 **7일 동안 아무도 안 들어오면 일시정지**돼요. 그러면 "혼자 모드"로만 보여요. Supabase 대시보드에서 **Restore**를 누르면 다시 켜져요.
- **대화는 저장되지 않아요.** 새로고침하거나 나가면 사라지는 게 정상이에요.
- **욕설·광고 필터:** 기본 단어만 거르고 있어요. 문제가 생기면 `config.js`의 `room` 이름을 바꾸면 방이 새로 열려요.
- **AI 사진 표기:** 메콩강·야시장·저녁 사진은 AI 연출 이미지라 "(연출 이미지)"로 표기돼 있어요.
