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
- 공개 디렉터리 심사용 소스는 아래 GitHub 저장소에서 확인할 수 있습니다.
  https://github.com/openfieldth/templatehouse-claude-plugin

## 정책

- 라이선스: https://temha.io/policy/license
- 개인정보처리방침: https://temha.io/policy/privacy
- 지원: https://temha.io/help/

공식 형식과 설치 안내:
https://claude.com/docs/plugins/build


## 데이터 처리 및 외부 서비스

OAuth 인증 과정에서 계정 식별 정보와 이용 권한을 조회하고, 연결 유지에 필요한 인증 정보를 처리·저장합니다. 사용자의 비밀번호는 조회하거나 저장하지 않습니다. 프로젝트·페이지·블록 이름과 HTML, CSS, JavaScript 및 디자인 설정을 조회·저장하며, 콘텐츠에 포함된 개인정보도 처리될 수 있습니다.

이미지·영상 검색 시 템하 MCP 서버는 검색 키워드를 Unsplash 및 Pexels API로 전송합니다. 프로젝트·페이지·블록 콘텐츠 자체는 해당 서비스로 전송하지 않습니다.

저장한 프로젝트·페이지·블록 콘텐츠는 사용자가 수정·삭제할 때까지 보관될 수 있어 30일 이상 보관될 수 있습니다. OAuth 인증 및 계정 연결 정보는 연결 해제·만료·탈퇴 시점까지 관련 정책에 따라 보관될 수 있습니다.

이 플러그인은 웹 제작자·디자이너·개발자를 위한 도구이며 18세 미만 사용자를 대상으로 하지 않습니다.
