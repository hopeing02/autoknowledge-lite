# autoknowledge-lite

## AI provider selection

Set `AUTOKNOWLEDGE_AI_PROVIDER` to `openai`, `claude`, or `local`. When it is
not set, the server selects OpenAI when `OPENAI_API_KEY` exists, then Claude
when `ANTHROPIC_API_KEY` exists, and otherwise uses the offline deterministic
analyzer. Generated Markdown always contains both the AI summary and the full
original content.

```powershell
$env:AUTOKNOWLEDGE_AI_PROVIDER = "openai"
```

## GitHub automatic synchronization

The local Vault can be connected to a private GitHub repository. After the
repository is cloned or initialized, enable synchronization before starting the
server:

```powershell
$env:AUTOKNOWLEDGE_VAULT_DIR = "C:\\My-Development-Ecosystem-Phase10\\apps\\autoknowledge-lite\\vault"
$env:AUTOKNOWLEDGE_GIT_SYNC = "true"
$env:AUTOKNOWLEDGE_GIT_BRANCH = "main"
```

Only the generated Markdown note is staged. API keys, environment files, and
raw job JSON are not added to the Vault repository.

- 유형: `python`
- 프로젝트 문서: [`docs/15_projects/autoknowledge-lite/`](../../docs/15_projects/autoknowledge-lite/)

## 시작점

이 애플리케이션의 코드와 테스트는 이 폴더에서 관리합니다. 상세 설계·SDS·API·DB·UI 문서는 중앙 문서 폴더를 단일 원본으로 사용합니다.

## Obsidian Vault

기본 Vault는 `vault/`입니다. Obsidian에서 이 폴더를 Vault로 열면 자동 생성된 노트가 `AutoKnowledge/`에 표시됩니다. 기존 Vault를 사용하려면 서버 실행 전에 다음을 설정합니다.

```powershell
$env:AUTOKNOWLEDGE_VAULT_DIR = "C:\경로\내-Vault"
```
