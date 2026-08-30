# Codex Sidecar

[English](README.md) | **한국어**

Codex 옆에 AI를 두세요.

MCP도 없습니다. 터널도 없습니다. Connector도 없습니다. API Key도 없습니다.

> 귀찮았던 건 복사와 붙여넣기가 아니었습니다.  
> 창을 왔다 갔다 하는 것이었습니다.

Codex Sidecar는 Skill만으로 구성된 아주 작은 Codex Plugin입니다.

Codex의 기존 in-app Browser에서 AI 웹 앱을 열고, 이미 열린 탭이 있다면 가능한 경우 해당 탭을 재사용합니다. Browser를 화면에 표시한 뒤 사용자가 계속 이용할 수 있도록 탭을 열어둡니다.

**Version 0.1.0은 ChatGPT만 지원합니다.**  
현재 `https://chatgpt.com/`을 엽니다. 다른 AI 웹 앱은 아직 지원하지 않습니다.

## 왜 만들었나요?

때로는 가장 단순한 연결 방법이 가장 편리합니다.

Codex에서는 작업을 하고, ChatGPT는 바로 옆에서 생각을 돕고, 필요할 때 둘 사이에서 복사하고 붙여넣으면 됩니다.

Codex Sidecar는 [Codex with ChatGPT (C2C)](https://github.com/XiaoDuoYa/codex-with-chatgpt)에서 아이디어를 얻었습니다.

C2C는 ChatGPT를 Codex 옆에서 사용할 수 있게 하는 것뿐 아니라, workspace를 인식하여 자동으로 계획과 리뷰를 수행하는 강력한 통합 workflow를 제공합니다.

Codex Sidecar는 그중 **ChatGPT를 Codex 옆에 두는 경험만 가져오고, 의도적으로 거기서 멈춥니다.**

## 하는 일

- OpenAI의 Browser Plugin을 Codex에서 사용할 수 있는지 확인합니다.
- 이미 `chatgpt.com` 탭이 열려 있으면 해당 탭을 재사용합니다.
- 필요한 경우 ChatGPT 탭 하나를 새로 엽니다.
- Codex의 in-app Browser panel을 화면에 표시합니다.
- Browser Plugin이 지원하는 범위에서 탭을 사용자에게 넘겨주고 열린 상태로 유지합니다.

Codex Sidecar는 ChatGPT 대화를 읽거나, 입력하거나, 전송하거나, 복사하거나, 요약하지 않습니다.

## 사용하지 않는 것

Codex Sidecar는 다음 기능이나 인프라를 사용하지 않습니다.

- MCP
- Cloudflare
- Connector
- Node.js CLI
- 외부 또는 로컬 서버
- OpenAI API 또는 API Key
- Workspace 접근
- 자동 메시지 또는 PLAN/REVIEW loop
- Codex DOM 또는 설치 파일 patch
- Browser Plugin 코드 포함

## 요구 사항

- Plugin과 Skill을 지원하는 Codex
- OpenAI Browser Plugin 및 `control-in-app-browser` Skill
- `https://chatgpt.com/`에 접속할 수 있는 환경

Browser Plugin은 OpenAI가 별도로 제공합니다. Codex Sidecar에는 포함되어 있지 않습니다.

Browser 사용 가능 여부, panel 위치, tab 유지 방식 및 로그인 동작은 설치된 Codex와 Browser Plugin 버전에 따라 달라질 수 있습니다.

## 설치

Codex 플러그인 마켓플레이스에서 Codex Sidecar를 설치합니다. 먼저 marketplace를 추가합니다.

```bash
codex plugin marketplace add SANTAMAGO/Codex-Sidecar
```

그다음 Codex Sidecar를 설치합니다.

```bash
codex plugin add codex-sidecar@codex-sidecar
```

설치가 끝나면 **새 Codex task를 시작**하여 새로 설치된 Skill을 불러옵니다.

그다음 Codex에게 다음과 같이 요청하면 됩니다.

> Open ChatGPT next to Codex.

ChatGPT 로그인이 필요하면 화면에 표시된 Browser tab에서 직접 로그인하세요.

Codex Sidecar는 사용자의 로그인 정보나 자격 증명을 읽거나 저장하지 않습니다.

## Codex Sidecar와 C2C

두 프로젝트는 서로 다른 문제를 해결합니다.

| | Codex Sidecar | C2C |
|---|---|---|
| 주요 목적 | ChatGPT를 옆에 표시 | 자동 계획 및 리뷰 |
| Codex 옆에서 ChatGPT 사용 | Yes | Yes |
| 복사/붙여넣기 workflow | Yes | Yes |
| 자동 PLAN/REVIEW | No | Yes |
| Workspace 접근 | No | Yes, read-only |
| 통합 인프라 | None | MCP 및 secure connection |

ChatGPT가 workspace를 인식하고 자동으로 계획 및 리뷰 workflow에 참여하기를 원한다면 C2C를 사용하세요.

단순히 Codex 옆에 ChatGPT 웹사이트를 띄워놓고 사용하고 싶다면 Codex Sidecar를 사용하면 됩니다.

## 개인정보 및 보안

Codex Sidecar는 instruction만으로 구성되어 있습니다.

별도의 서버, telemetry, credential 저장소 또는 workspace integration이 없습니다.

Skill은 다음 정보를 확인하지 않도록 명시적으로 제한합니다.

- ChatGPT 대화 내용
- Cookie
- Browser storage
- 로그인 정보
- Token
- Browser profile

## 감사의 말

[Codex with ChatGPT (C2C)](https://github.com/XiaoDuoYa/codex-with-chatgpt)에서 아이디어를 얻었습니다.

C2C의 source code는 Codex Sidecar에 포함하거나 복사하지 않았습니다.

## Disclaimer

**비공식 community project이며 OpenAI와 제휴하거나 OpenAI의 보증을 받은 프로젝트가 아닙니다.**

ChatGPT, Codex 및 OpenAI는 OpenAI의 상표입니다.

이 프로젝트는 OpenAI의 proprietary Browser Plugin을 포함하거나 재배포하지 않습니다.

## License

MIT License.

자세한 내용은 [LICENSE](LICENSE)를 확인하세요.

