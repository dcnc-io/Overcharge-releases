# 공개 Windows 베타

Windows x64용 설치형과 포터블을 같은 소스 및 Io 0.4.1로 제공합니다. 미서명 베타이며 Windows가 미확인 게시자 경고를 표시할 수 있습니다. 다운로드는 https://overcharge.io/download/ 에서 제공하는 버전 고정 링크를 사용합니다. 보안 기능을 끄지 마세요.

이번 공개 베타는 실행 검증 미완료를 명시하고 게시합니다. 검증 PC의 Windows 앱 제어 정책이 미서명 EXE를 차단했습니다. 소스 테스트와 패키징 검증은 실제 EXE 실행·설치·업데이트·제거 검증을 대신하지 않습니다. 실게임 수신도 이번 빌드에서 확인하지 않았습니다.

1. 설치형 EXE는 현재 사용자에게 설치하며 관리자 권한을 요청하지 않습니다. 시작 메뉴의 Overcharge로 실행합니다. 포터블은 설치 없이 EXE를 실행합니다.
2. 앱에서 Dota 상태를 확인합니다. 연결 설정의 Install / repair connection을 직접 선택합니다. Dota를 찾지 못하면 Choose Dota folder에서 설치 폴더를 선택합니다.
3. Dota가 닫혀 있다고 확인된 경우에만 Launch Dota 2가 실행 요청을 보냅니다. 이미 열린 게임은 종료하거나 다시 실행하지 않습니다. 필요한 경우 사용자가 편한 시점에 종료하고 앱의 실행 버튼을 사용합니다.
4. 수신기가 Listening이어도 실제 게임 데이터가 도착한 것은 아닙니다. 수신·오래된 데이터·알 수 없는 draft 필드를 구분합니다. Ranked 전체 픽/밴 및 양 팀 전체 라인업을 보장하지 않습니다.
5. Heroes / Builds / Matches는 기본 브라우저의 운영 웹으로 열립니다. 인터넷이 없어도 로컬 앱과 연결 상태 화면은 사용할 수 있습니다. 기존 로컬 기록은 Diagnostics and existing local records에서 확인합니다.
6. Check for updates는 다운로드 페이지를 엽니다. 자동 다운로드/자동 설치는 없습니다. 앱을 닫고 새 설치형을 실행하거나 포터블 파일을 교체합니다. 설치형 업데이트와 제거는 기존 사용자 데이터를 지우지 않습니다.

공개 자료에는 SHA-256, 버전, 배포 종류, 서명 상태와 소스 커밋을 기록합니다. 체크섬은 파일 동일성을 확인하며 게시자 서명을 대신하지 않습니다. GSI 토큰과 개인 캡처는 공개하지 않습니다.

## 향후 Windows 코드 서명 전환

이번 릴리스에서는 가입·결제·서명 서비스를 만들지 않습니다. 추후 순서는 다음과 같습니다.

1. 게시자 명의와 해당 인증기관의 현재 가입 자격을 확인합니다. Microsoft Artifact Signing 또는 기존 공인 코드 서명 수단을 선택하고 신원 검증을 완료합니다.
2. 비밀키는 지원되는 보안 저장소/HSM 또는 서비스에 보관하고, 빌드 실행기에 필요한 최소 서명 권한을 부여합니다. 인증값은 저장소에 넣지 않습니다.
3. 실제 고정된 electron-builder 버전에 맞게 signing 설정과 현재 unsigned-only 검증을 함께 변경합니다. 앱 EXE, 설치기, 제거 프로그램에 SHA-256 서명과 RFC 3161 타임스탬프를 적용하며 서명 실패 시 배포를 중단합니다.
4. SignTool verify /pa /all /v와 Get-AuthenticodeSignature로 게시자·신뢰 체인·타임스탬프를 검증합니다. 서명 후 EXE 해시를 다시 계산합니다.
5. 새 버전으로 게시하고 익명 재다운로드·설치·업데이트를 검증한 뒤 웹 manifest의 서명 상태와 파일 정보를 전환합니다. 기존 파일을 덮어쓰지 않습니다.

서명과 SmartScreen 평판은 별개이며 경고가 즉시 사라진다고 약속하지 않습니다.

공식 자료: https://learn.microsoft.com/en-us/azure/artifact-signing/faq · https://www.electron.build/v26/docs/features/code-signing/code-signing-win/ · https://learn.microsoft.com/en-us/windows/win32/seccrypto/signtool
