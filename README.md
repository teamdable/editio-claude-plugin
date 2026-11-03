# editio

editio CMS를 쓰는 기자와 데스크가 Claude에서 기사를 검색하고, 원고를 쓰고 고치고, 송고와 데스크 검토까지 처리하는 플러그인입니다.
CMS 화면과 같은 계정, 매체 권한, 원고와 저장 이력을 씁니다.

## 사용 조건

- editio CMS 계정과 사용할 매체의 활성 소속
- 승인된 매체. 정지되었거나 체험 기간이 끝난 매체는 연결할 수 없습니다

## 연결

Claude에서는 플러그인의 커넥터 탭이나 설정의 커넥터에서 editio를 연결합니다. Claude Code에서는 `/mcp`에서 editio를 선택해 인증합니다.
CMS 로그인 화면에서 이메일과 비밀번호 또는 Google 계정으로 로그인한 뒤 매체와 허용할 작업을 고릅니다.

연결 하나는 매체 하나에 속합니다.
매체를 바꾸거나 권한을 추가하려면 연결을 해제하고 다시 연결합니다.
반려와 승인은 허용한 작업과 CMS의 데스크 역할이 모두 있어야 실행됩니다.

## 할 수 있는 작업

- 기사 검색, 원고와 저장 이력 조회
- 새 원고 저장, 초안의 제목과 일반 텍스트 문단 수정
- 어깨제목, 부제목, 카테고리, 태그, 요약, 출처, 바이라인, 기사 유형, 제공 구분, 지면일 설정
- 송고, 회수, 수정 재개, 데스크 반려와 승인

발행과 예약은 지원하지 않으며 승인은 발행이 아닙니다.
사진, 표, 서식이 있는 문단은 수정하지 않고 그대로 둡니다.

## 데이터 처리

- 플러그인에는 스킬 2개와 원격 MCP 서버 주소 `https://cms.editio.kr/api/v2/mcp` 하나만 들어 있습니다. 사용자 컴퓨터에서 실행하는 코드나 hook은 없습니다
- 도구를 호출하면 결과로 원고, 기사 설정, 저장 이력, 송고와 검토 기록이 Claude에 전달됩니다. 플러그인은 editio 서버 밖으로 데이터를 보내지 않습니다
- 로그인 정보는 CMS 화면에서만 입력하며 플러그인은 비밀번호나 인증 코드를 받지 않습니다
- 연결은 30일 동안 유지됩니다. CMS의 연결된 앱에서 언제든 해제할 수 있으며, 해제해도 원고와 저장 이력은 삭제되지 않습니다

## 지원

- 고객지원: https://cms.editio.kr/support
- 개인정보처리방침: https://cms.editio.kr/privacy
- 이용약관: https://cms.editio.kr/terms

플러그인 파일은 Apache-2.0 라이선스를 따릅니다. editio 서비스 이용은 이용약관을 따르며, editio 이름과 로고 사용권은 라이선스에 포함되지 않습니다.

## English

editio connects Claude to the editio newsroom CMS. Reporters and desk editors can search articles, read manuscripts and save history, save and edit drafts, set article metadata, submit manuscripts, and reject or approve them as the desk. Each connection uses the user's own CMS account, is bound to one media they belong to, and is limited to the permissions approved on the CMS consent page and to their CMS role. Publishing and scheduling are not available, and approval is not publication. The plugin contains two skills and one remote MCP server at `https://cms.editio.kr/api/v2/mcp`; it runs no local code. Tool results such as manuscripts, settings and history are returned to Claude only when a tool is called.
