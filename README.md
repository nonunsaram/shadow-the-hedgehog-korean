# 섀도우 더 헤지혹 한국어 패치 — 원본 GameCube · PlayStation 2

《Shadow the Hedgehog》 **원본 GameCube판**과 **PlayStation 2판**을 한국어로 즐기기 위한 비공식 팬 번역 패치입니다. 원본의 게임플레이와 각 지역판의 음성을 유지합니다.

## 다운로드

[최신 릴리스에서 .xdelta 다운로드](https://github.com/nonunsaram/shadow-the-hedgehog-korean/releases/latest)

| 기종 | 사용할 원본 | 음성 | 버전 | 패치 |
|---|---|---|---|---|
| GameCube | 일본판 · GUPJ8P | 일본어 | v0.2 | [GC JP 한국어 패치](patches/Shadow-the-Hedgehog-GC-JP-Korean-v0.2.xdelta) |
| GameCube | 미국판 · GUPE8P | 영어 | v0.2 | [GC USA 한국어 패치](patches/Shadow-the-Hedgehog-GC-USA-Korean-v0.2.xdelta) |
| PS2 | 일본판 · SLPM-66166 | 일본어 / 영어 선택 | v0.1 | [PS2 JP 한국어 패치](patches/Shadow-the-Hedgehog-PS2-JP-Korean-v0.1.xdelta) |
| PS2 | 한국 정식 발매판 · SLKA-25335 | 일본어 / 영어 선택 | v0.1 | [PS2 KR 한국어 패치](patches/Shadow-the-Hedgehog-PS2-KR-Korean-v0.1.xdelta) |

게임 ISO나 설치 프로그램은 포함하지 않습니다. 본인이 소유한 게임에서 추출한, 해당 지역의 수정되지 않은 원본 ISO가 필요합니다. 각 패치는 대응하는 원본에 한 번만 적용하며, 서로 겹쳐 적용하지 않습니다.

## 적용 방법

1. 아래 확인값과 일치하는 원본 ISO를 준비합니다.
   - GameCube: 일본판·미국판 모두 `1,459,978,240`바이트
   - PS2 일본판: `4,493,836,288`바이트 / PS2 한국 정식 발매판: `4,494,131,200`바이트
2. GameCube판을 RVZ로만 가지고 있다면 Dolphin의 변환 기능으로 **ISO**로 변환합니다. 스크럽(불필요 데이터 제거) 옵션은 끄고, 변환 결과의 SHA-256을 아래 표와 비교합니다. `.xdelta`는 RVZ에 직접 적용하지 않습니다.
3. 원본에 맞는 `.xdelta`를 내려받아 xdelta3 호환 도구로 적용하고, 새 ISO로 저장합니다.
4. 결과 ISO의 SHA-256을 아래 표와 비교한 후 실행합니다(GameCube: Dolphin 등, PS2: PCSX2 등).

xdelta3 명령 예시:

```text
xdelta3 -d -s "원본.iso" "Shadow-the-Hedgehog-PS2-JP-Korean-v0.1.xdelta" "Shadow-Korean-PS2-JP.iso"
```

패치 파일 확인값은 [SHA256SUMS.txt](SHA256SUMS.txt)에 있습니다. Windows에서는 `Get-FileHash -Algorithm SHA256 '파일.iso'`로 확인할 수 있습니다.

### 언어 설정

- **GameCube**: 게임의 **Options → 자막 언어에서 日本語(Japanese)**를 선택하면 한국어가 표시됩니다. 미국판 패치에서도 음성은 원래의 영어로 유지됩니다.
- **PS2**: 새로 시작하면 자막·메뉴는 한국어, 음성은 일본어로 시작합니다. 옵션의 음성 언어에서 일본어/English를 고를 수 있습니다. 이미 이 게임의 저장 데이터가 있으면 저장된 언어 설정을 불러오므로, 옵션에서 자막 언어를 **한국어**로 바꿔 주세요.

## 원본 및 결과 ISO 확인값

| 구분 | SHA-256 |
|---|---|
| GC 일본판 원본 | `9ca5223e47c551e13659742c1db0de78a637ed3a709512239f9c353c22e7cfb3` |
| GC 일본판 한국어 결과 v0.2 | `8c003c4da2bc312dd22e41bc88a9714e6cfc048a0ed5cdc8703bc38aff06da2a` |
| GC 미국판 원본 | `54c79de9517a7a88e73e7354c7710a024e27d9db7b064336444c399bced3668c` |
| GC 미국판 한국어 결과 v0.2 | `2df8dc7e623bd879446e89ed3dd9b1a83f3faebe4d1fb1438021d288a00e2efc` |
| PS2 일본판 원본 | `a9d8c9131ac0aa31f813bcc8ce48bf50ab57e95cb776d5d2ba3d25d2658ca054` |
| PS2 일본판 한국어 결과 v0.1 | `e8ca833f17451466573716ac05bbef76ea44700ea404122e408e69bf00b5c152` |
| PS2 한국 정식 발매판 원본 | `3280a7d91f2b9ef766785c9b3bd55ae271f4cbb4eed130d57063a08c0843fc87` |
| PS2 한국 정식 발매판 한국어 결과 v0.1 | `de2df64ce73ed8824fc35a3710070690dcc688da477bbee7e8959048b876ff77` |

## 변경 내역

### GameCube v0.2

- 자막 언어를 日本語로 두면 타이틀 로고에 나오던 가타카나 부제(シャドウ・ザ・ヘッジホッグ)를 지우고 영문판 로고로 바꿨습니다.
- v0.1과 다른 파일은 `csdFiles/honban_JP.txd` 하나뿐입니다. v0.1 패치는 [v0.1 릴리스](https://github.com/nonunsaram/shadow-the-hedgehog-korean/releases/tag/v0.1)에 남아 있습니다.

### PS2 v0.1 (첫 공개)

- 게임큐브 원본 한국어 패치의 번역(11,036개 대사·문구)과 메뉴 이미지를 PS2판에 옮겼습니다. 각 대사의 번호·표시 시간·음성 번호는 PS2판 원본을 유지합니다.
- 조작 안내를 PS2 표기로 바꿨습니다: Y→△, X→○, B→□, A→× 버튼, C 스틱→오른쪽 스틱, 컨트롤 스틱→왼쪽 스틱, R 트리거→R2, 십자 버튼→방향 키.
- 한글 글꼴, 메뉴 이미지, 타이틀 로고(영문판 로고)를 교체했습니다.
- 실행 파일은 판마다 9바이트만 바꿨습니다. 본체 언어와 관계없이 처음부터 한국어 자막·일본어 음성으로 시작하게 하고, 음성 언어 목록에 '한국어' 대신 '일본어'가 표시되게 했습니다.

## 패치 범위와 확인 사항

- 글꼴과 UI를 한국어화하며 각 지역판의 원래 음성·영상은 유지합니다. GameCube판은 실행 코드도 원본 그대로입니다.
- 번역은 일본어 대사를 기준으로 하므로 영어 음성과 표현이 다를 수 있습니다.
- 모든 패치는 원본에 실제 적용한 결과 ISO 해시가 위 표와 일치함을 확인했습니다.
- GameCube v0.1에서 Dolphin으로 한국어 저장 안내, 스토리 메뉴, 오프닝 자막, 웨스토폴리스 진입과 일시정지 화면을 확인했습니다. v0.2의 로고 교체는 원본 영문 로고 이미지와 대조했습니다.
- PS2판은 PCSX2에서 부팅, 타이틀, 메뉴, 옵션(언어 선택), 스토리 컷신과 인게임 자막을 확인했습니다. PS2판은 화면을 늘려 출력하는 방식 때문에 자막이 GameCube판보다 가로로 약간 넓게 보입니다.
- 전체 분기·엔딩의 완주 검수와 실기 검증은 완료하지 않았습니다. 문제 제보 시 기종, 지역판, 장면, 표시 내용을 함께 알려 주세요.

## 팬 제작 개선판 Reloaded도 한국어로 즐길 수 있습니다

게임플레이와 편의성 개선을 적용한 팬 제작 개선 패치 **Shadow the Hedgehog: Reloaded**용 한국어 패치도 별도로 제공합니다.

- [Reloaded 한국어 패치 저장소 및 설치 안내](https://github.com/nonunsaram/shadow-the-hedgehog-reloaded-korean)
- [Reloaded 원 제작팀 저장소](https://github.com/ShadowTheHedgehogHacking/ShdTH-Reloaded)

이 저장소는 원본 GameCube판·PS2판용이고, 위 저장소는 Reloaded용입니다. 원본용 한국어 패치를 Reloaded ISO에 적용하거나 그 반대로 적용할 수는 없습니다.

## 제작 및 권리 안내

한국어 번역·시각 자산: 노는사람. Reloaded 한국어 프로젝트의 번역과 자산을 원본 일본판·미국판·PS2판 구조에 맞게 적용했습니다. 원본 GameCube판 적용 및 검증 도구 작업에는 Codex를, PS2판 이식 및 검증 도구 작업에는 Claude를 사용했습니다.

Shadow the Hedgehog 및 관련 게임·상표의 권리는 SEGA와 각 권리자에게 있습니다. 본 프로젝트는 공식 제품이 아닌 팬 번역입니다.

글꼴: LINE Seed KR 및 KOTRA 도약체. 관련 이용 조건은 [licenses](licenses)에 포함했습니다. xdelta3는 별도 도구이며 이 배포에 실행 파일을 포함하지 않습니다.
