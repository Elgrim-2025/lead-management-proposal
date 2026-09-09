# 리드 관리 시스템 제안 페이지

비개발자 클라이언트에게 링크로 전달하는 단일 페이지입니다. `index.html` 하나로 끝나고
빌드 과정이 없습니다. 폰트만 CDN에서 받아옵니다.

## 배포

```bash
git init
git add index.html README.md
git commit -m "제안 페이지"
git branch -M main
git remote add origin git@github.com:<계정>/<저장소>.git
git push -u origin main
```

저장소 Settings → Pages → Source를 `Deploy from a branch`,
Branch를 `main` / `/ (root)`로 두면 1~2분 뒤
`https://<계정>.github.io/<저장소>/` 로 열립니다.

비공개로 전달해야 하면 저장소를 Private으로 두고 Pages 대신
Netlify Drop이나 Vercel에 `index.html`만 올려도 동일하게 동작합니다.

## 수정할 만한 곳

`<script>` 블록 안 세 군데만 고치면 내용이 바뀝니다.

- `heroData` — 첫 화면에서 한 줄씩 쌓이는 기록
- `STEPS` — 시뮬레이션 12단계. 각 항목의 `h`는 제목, `n`은 설명,
  `rows`는 그 단계에서 추가되는 기록, `s`는 왼쪽에 띄울 화면 이름
- `BASE` / `FINAL` — 하단 통계 카드의 계약 전후 수치

화면 목업을 늘리려면 `#screens` 안에 `<div class="screen" data-s="이름">`을 추가하고
해당 단계의 `s`에 그 이름을 넣으면 됩니다.

인물명, 금액, 통계 수치는 전부 예시값입니다. 실제 제출 전에
클라이언트 업종에 맞는 차종·매체·단가로 바꿔 주십시오.
