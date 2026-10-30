# TemplateHouse for Claude

템플릿하우스 프로젝트, 페이지 및 재사용 블록을 조회하고 검증하거나 수정하는
Claude용 플러그인입니다. 기존 원격 MCP 서버에 연결하며, PC에 Node.js나 별도
서버를 설치할 필요는 없습니다. 템플릿하우스 계정과 해당 작업에 필요한 이용
권한이 있어야 합니다. 각 사용자는 자신의 계정으로 로그인합니다.

## Claude 웹 / 데스크톱 / Cowork

1. Customize > Plugins > Add > Upload plugin에서 이 ZIP을 업로드합니다.
2. 설치된 TemplateHouse의 Connectors 탭을 엽니다.
3. TemplateHouse를 추가하거나 연결하고 OAuth 로그인을 완료합니다.
4. 새 대화에서 "내 템플릿하우스 프로젝트 목록을 보여줘"라고 요청합니다.

ZIP 업로드만으로 로그인까지 자동 완료되는 것은 아닙니다. Team/Enterprise는
관리자의 커넥터 추가 또는 허용이 먼저 필요할 수 있습니다. 설치 메뉴와 사용
가능 범위는 Claude 요금제 및 조직 정책을 따릅니다.

## Claude Code

ZIP을 압축 해제한 뒤 다음과 같이 로드할 수 있습니다.

```shell
claude --plugin-dir ./templatehouse-claude-plugin
```

`/mcp`에서 TemplateHouse 연결과 인증 상태를 확인합니다. 이 패키지의 스킬은
`/templatehouse:templatehouse`로 호출하거나 관련 요청에 사용할 수 있습니다.

## 연결 정보 및 검증 범위

- MCP 주소: https://mcp.temha.io/mcp
- 전송 방식: HTTP (Streamable HTTP)
- 인증: 서버 메타데이터를 통한 OAuth 연결
- 이 ZIP에는 비밀번호, 토큰 또는 OAuth 클라이언트 비밀값이 없습니다.
- 패키지 형식과 압축 파일은 로컬에서 검사했습니다. 실제 Claude 설치 및
  OAuth 로그인, 프로젝트 조회, 저장 성공 여부는 Claude에서 확인해야 합니다.
- 공개 디렉터리 심사 제출용 패키지는 아닙니다. 공개 제출에는 라이선스 등
  추가 심사 요건을 별도로 준비해야 합니다.

공식 형식과 설치 안내:
https://claude.com/docs/plugins/build

지원: https://temha.io/help/
