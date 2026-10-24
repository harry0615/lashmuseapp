# LashMuse website

Official marketing, support, and privacy site for the LashMuse iOS app.

## Production

- Site: https://lashmuseapp.com/
- English: `/`
- Korean: `/ko/`
- App Store ID: `6760812078`
- Live repository: `harry0615/lashmuseapp`
- Hosting: **GitHub Pages**, production branch `main`, repository root `/`
- Custom domain: `lashmuseapp.com` (keep the `CNAME` file)

Cloudflare manages DNS. Website content is published from this repository by
GitHub Pages. The older `harry0615/lashmuse-site` repository is not the publishing
source for the current domain. Its Cloudflare Pages instructions do not apply.

## 사이트 내용 수정 및 배포

1. 이 저장소의 `main` 브랜치에서 수정할 파일을 엽니다.
2. GitHub의 연필 아이콘(Edit this file)을 눌러 수정하고 Commit changes로 저장합니다.
3. Actions에서 `pages build and deployment`가 성공했는지 확인합니다.
4. https://lashmuseapp.com/ 및 https://lashmuseapp.com/ko/ 에서 결과를 확인합니다.

| 수정 대상 | 파일 |
| --- | --- |
| 영문 소개 페이지 | `index.html` |
| 한국어 소개 페이지 | `ko/index.html` |
| 공통 디자인 | `assets/site.css` |
| 앱 화면 이미지 | `screens/` |
| 개인정보처리방침 | `privacy.html`, `privacy-ko.html` 및 언어별 파일 |
| 고객지원 | `support.html`, `support-ko.html` 및 언어별 파일 |
| 검색 로봇 안내 및 사이트맵 | `robots.txt`, `sitemap.xml` |

내용을 수정할 때 DNS를 변경할 필요는 없습니다. 새 페이지를 추가했다면
실제 공개 URL을 `sitemap.xml`에 넣으세요. 이미지 파일 이름을 바꿀 때는
두 언어의 HTML에 있는 이미지 경로도 함께 수정하세요.

## Static assets

Commit the actual screenshot files under `screens/`. The HTML, image preload,
Open Graph, Twitter, and JSON-LD references must point to files that exist in the
published repository. The restored images originate from the same owner's
`harry0615/lashmuse-site/screens/` directory.

GitHub Pages does **not** execute `functions/` (Cloudflare Pages Functions),
`_headers`, or `_redirects`. Those legacy files are not the mechanism for serving
images or configuring redirects on this host. Domain redirects and HTTPS are
configured in repository Settings > Pages.

## Google Search Console

Property: `sc-domain:lashmuseapp.com`

1. Keep the existing Google verification TXT record in DNS.
2. Open https://search.google.com/search-console and select `lashmuseapp.com`.
3. In Sitemaps, use https://lashmuseapp.com/sitemap.xml.
4. Inspect the exact public URL after a meaningful content update, run a live test,
   and request indexing when needed. Repeated requests do not speed up indexing.
5. Check performance separately from index coverage. An indexed URL is eligible
   for search but is not guaranteed to rank for a particular query.

The English and Korean landing pages include canonical and reciprocal hreflang
metadata, crawlable HTML, Open Graph/Twitter metadata, JSON-LD, and an iPhone
Smart App Banner. Sitemap availability and a verification TXT record alone do
not guarantee indexing or search ranking.
