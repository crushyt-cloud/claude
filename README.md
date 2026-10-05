# claude

Claude Code와 함께 작업하는 개인 작업 공간입니다.

실험, 메모, 작은 프로젝트를 이 저장소에 모아 둡니다.

## 사용법

### 1. 저장소 받기

```bash
git clone https://github.com/crushyt-cloud/claude.git
cd claude
```

### 2. Claude Code로 작업하기

저장소 폴더를 Claude Code(데스크톱 앱의 Code 탭 또는 터미널의 `claude`)에서 열고, 하고 싶은 작업을 말로 요청합니다.

```bash
claude
```

### 3. 변경 사항 올리기 (브랜치 → PR → 머지)

`main`에 바로 커밋하지 않고, 작업마다 브랜치를 만들어 PR로 합칩니다.

```bash
git switch main
git pull
git switch -c docs/my-change      # 작업용 브랜치 만들기
# ... 파일 수정 ...
git add .
git commit -m "변경 내용 요약"
git push -u origin docs/my-change
gh pr create --fill                # PR 열기
gh pr merge --merge --delete-branch  # 확인 후 머지
```

브랜치 이름은 작업 종류를 앞에 붙입니다. 예: `docs/…`(문서), `feat/…`(기능), `fix/…`(버그 수정), `chore/…`(설정·정리).

## 저장소 규칙

- 줄바꿈은 `.gitattributes`에 따라 LF로 통일됩니다. 단, `.bat`, `.cmd`, `.ps1`은 CRLF를 유지합니다.
- `.env`, 로그, 에디터 설정 파일은 `.gitignore`로 커밋에서 제외됩니다. 비밀 정보는 `.env`에만 두세요.
