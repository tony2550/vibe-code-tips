# Pro Tips & Tricks

현업 생산성을 즉시 높일 수 있는 실전 팁입니다.

## 1. Essential Shortcuts (단축키 마스터)
마우스 대신 키보드로 에이전트를 제어하십시오.

| Action | macOS | Windows/Linux | 설명 |
| :--- | :--- | :--- | :--- |
| **새 대화 시작** | `Cmd + N` | `Ctrl + N` | 컨텍스트 초기화. 새 주제 시작 시 필수. |
| **매니저/에디터 전환** | `Cmd + E` | `Ctrl + E` | 전체 뷰와 코드 뷰 전환. |
| **사이드 패널 열기** | `Cmd + L` | `Ctrl + L` | 에디터 채팅창 열기. |
| **인라인 명령어** | `Cmd + I` | `Ctrl + I` | 코드 블록 잡고 즉시 수정 지시. |
| **터미널 토글** | `` Ctrl + ` `` | `` Ctrl + ` `` | 터미널 창 제어. |

## 2. Security Settings (`settings.json`)
터미널 보안을 위해 반드시 설정하십시오.

```json
{
  // 터미널 실행 정책: 'auto'는 위험함.
  "antigravity.terminal.executionPolicy": "reviewRequired", 
  
  // 허용 목록 (안전한 조회 명령어)
  "antigravity.terminal.allowList": [
    "ls", "pwd", "git status", "git diff", "echo", "npm run test"
  ],
  
  // 차단 목록 (파괴적 명령어)
  "antigravity.terminal.denyList": [
    "rm -rf", "drop database", "aws configure", "gcloud auth"
  ]
}
```

## 3. Context Management
- **Health Check**: 30분마다 "Are you experiencing context drift?"라고 물어보세요.
- **Chaptering**: 기능 하나가 끝나면 내용을 요약하게 시키고, 새 방(`Cmd + N`)을 파서 요약본을 붙여넣고 이어가세요. "죽음의 루프"를 예방하는 가장 좋은 방법입니다.

## 4. Custom Workflows (Slash Commands)
자주 쓰는 패턴을 자동화하세요 (`.agent/workflows` 폴더에 `.md` 파일 생성).

- `/review`: "Clean Code 관점에서 리팩토링 제안해줘."
- `/docs`: "JSDoc 스타일 주석 달고 README 업데이트해줘."
- `/commit`: "변경사항 요약해서 커밋 메시지 작성해줘."

## 5. Visual Debugging (Visual Feedback)
프론트엔드 수정 시 말로 하지 마십시오.
- **Tip**: 브라우저 화면을 캡처해서 붙여넣고 **"이거 8px 만큼 왼쪽으로 옮겨"**라고 시각적으로 지시하면 훨씬 정확합니다.
