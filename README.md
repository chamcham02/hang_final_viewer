# 행정법 기말 필기본 뷰어

https://chamcham02.github.io/hang_final_viewer/

이 저장소에는 **필기 내용이 없습니다.** 비공개 저장소 `chamcham02/hang_final`에 있는 기말 필기본 HTML(왼쪽 강의안 · 오른쪽 정리본)을 GitHub 토큰으로 불러와 여는 작은 페이지(`index.html`)만 있습니다.

## 처음 한 번(기기마다)
1. GitHub에서 [Fine-grained 토큰 만들기](https://github.com/settings/personal-access-tokens/new)
2. **Repository access** → Only select repositories → `chamcham02/hang_final`
3. **Permissions** → Repository permissions → **Contents: Read and write**
4. 만들어진 토큰(`github_pat_…`)을 뷰어 첫 화면에 붙여 넣기

중간 필기본(`notes_hangjeong`)에 쓰던 토큰을 [토큰 목록](https://github.com/settings/personal-access-tokens)에서 고쳐 `hang_final`도 고르면, 그 토큰을 넣어 둔 기기에서는 이 화면 없이 바로 열립니다(처음 한 번만 옮겨 쓰고, 필기본에서 연결을 해제하면 다시 옮겨 오지 않습니다).

## 동작
- 열 때마다 저장소 폴더 목록으로 필기본 파일의 sha만 확인하고, 바뀐 경우에만 파일(약 650KB)을 다시 받아 기기(IndexedDB `hang-final-viewer`)에 보관합니다. 인터넷이 없거나 응답이 늦으면(보관본이 있을 때 8초) 보관본으로 엽니다.
- 필기본에서 편집·하이라이트·메모한 내용은 같은 토큰으로 비공개 저장소의 `notes-data` 브랜치에 자동 커밋되어 다른 기기에서도 보입니다.
- 토큰은 그 기기 브라우저(localStorage `gh-sync:token:hang_final`)에만 저장되고 `api.github.com` 말고는 보내지 않습니다. 중간 필기본 뷰어의 토큰 자리(`gh-sync:token`)는 덮어쓰지 않습니다.
- `chamcham02.github.io` 아래의 다른 Pages 사이트도 같은 저장소를 읽을 수 있으니, 이 계정의 Pages 저장소에 믿을 수 없는 코드는 올리지 마세요. 토큰이 새었다면 토큰 목록에서 지우면 바로 막힙니다.
