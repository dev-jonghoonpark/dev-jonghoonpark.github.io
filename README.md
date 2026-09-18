# dev-jonghoonpark.github.io

호스트 루트(`https://dev-jonghoonpark.github.io/`)를 서빙하는 사용자 사이트.

## 왜 있나

크롤러는 **호스트 루트의 `/robots.txt` 하나만** 읽는다.
`dev-jonghoonpark.github.io/crossfit-guide/` 같은 프로젝트 사이트가 자기 안에
`robots.txt` 를 만들어 둬도 구글은 그 파일을 보지 않는다.

이 저장소가 없던 동안에는 `https://dev-jonghoonpark.github.io/robots.txt` 가 404 였고,
그래서 모든 프로젝트 사이트의 크롤링 규칙과 `Sitemap:` 선언이 구글에 전달되지 않았다.
이제 `public/robots.txt` 하나가 15개 Pages 프로젝트 전부를 커버한다.

## 구조

| 경로 | 서빙 주소 | 비고 |
|---|---|---|
| `public/robots.txt` | `/robots.txt` | 크롤링 규칙 · 사이트맵 선언 |
| `public/index.html` | `/` | 루트 랜딩 페이지 |
| `public/.nojekyll` | — | Jekyll 처리 끄기 |

`public/` 만 Actions 로 배포된다. 저장소 루트의 README·워크플로는 올라가지 않는다.

## 사이트맵 추가하기

사이트맵을 가진 프로젝트가 생기면 `public/robots.txt` 맨 아래에 한 줄 추가한다:

```
Sitemap: https://dev-jonghoonpark.github.io/<저장소이름>/sitemap.xml
```

선언한 주소는 실제로 200 이어야 한다. 404 인 사이트맵을 적어두면 서치 콘솔에 오류로 쌓인다.

## 랜딩 페이지 목록

`public/index.html` 의 링크는 저장소 `homepage` 필드에 `github.io` 주소가
설정돼 있던 것만 넣어 뒀다. 나머지 Pages 프로젝트도 노출하고 싶으면 직접 추가할 것.
