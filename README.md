# PermBook

**PermBook**은 `LuckPerms`의 펄미션 그룹 및 노드를 제공하는 플러그인입니다.

## 주요 특징
- **LuckPerms** 플러그인을 꼭 필요로 합니다.
- `/권한북 생성 <펄미션 노드>` 명령어로 펄미션 노드가 담긴 책을 지급합니다.
- 펄미션 노드가 담긴 책을 우클릭하면 Confirm GUI가 나오며 취소 또는 적용을 할 수 있습니다.
- 만약 권한이 이미 적용 중이라면 권한 적용이 취소 됩니다.

## 설정 파일
- **`permbook.yml`**: 권한책 아이템 디자인
```yaml
permbook:
  name: "&e권한북"
  lore:
    - ""
    - "&7해당 책을 우클릭하여 권한을 획득하세요"
    - ""
    - "&7권한 정보 : {perm}"
    - ""
```
- 플러그인의 컨픽을 다루는 초보자도 손 쉽게 권한북 디자인을 수정 할 수 있습니다.

- **`messages.yml`**: 명령어 안내, GUI 버튼 이름, 메시지 등  
```yaml
messages:
  no-console: "&c이 명령어는 플레이어만 사용할 수 있습니다."
  usage-create: "&e사용법:\n&f\n&f- /권한북 생성 <펄미션노드> - 펄미션 권한이 담긴 책을 생성합니다.\n&f- /권한북 리로드 - permbook.yml/messages.yml를 리로드합니다.\n&f"
  book-created: "&aLuckPerms 권한 '{perm}'이(가) 담긴 책을 지급했습니다."
  already-has-perm: "&c이미 해당 권한을 가지고 있습니다!"
  perm-registered: "&aLuckPerms 권한 '{perm}'이(가) 등록되었습니다!"
  perm-cancelled: "&c권한 등록이 취소되었습니다."
  perm-fail: "&c권한 등록 중 오류가 발생했습니다. 콘솔 로그를 확인하세요."
  reload-complete: "&aPermBook 설정 파일이 리로드되었습니다!"
  no-permission: "&c이 명령어를 사용할 권한이 없습니다."

gui:
  title: "정말 이 권한을 적용 하겠습니까?"

  cancel-name: "&c취소"
  cancel-lore:
    - ""
    - "&7클릭하여 권한 적용을 취소합니다."
    - ""

  confirm-name: "&a등록"
  confirm-lore:
    - ""
    - "&7클릭하여 권한을 적용합니다."
    - ""
    - "&7권한 적용 전 다시 한번 확인하세요."
    - "&7권한 정보: &e{perm}"
    - ""

  info-name: "&e정말 이 권한을 적용 하시겠습니까?"
  info-lore:
    - ""
    - "&7왼쪽: 권한 취소"
    - "&7오른쪽: 권한 적용"
    - ""

  cancel-slots: "0-3"
  confirm-slots: "5-8"
```
- 플러그인의 컨픽을 다루는 초보자도 손 쉽게 메세지 디자인을 수정 할 수 있습니다.
