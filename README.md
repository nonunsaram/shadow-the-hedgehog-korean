# 섀도우 더 헤지혹 원본 GameCube 한국어 패치 v0.1

《Shadow the Hedgehog》 **원본 GameCube판**을 한국어로 즐기기 위한 비공식 팬 번역 패치입니다. 원본의 게임플레이와 화면비, 각 지역판의 음성을 유지합니다.

## 다운로드

[최신 릴리스에서 .xdelta 다운로드](https://github.com/nonunsaram/shadow-the-hedgehog-korean/releases/latest)

| 사용할 원본 | 음성 | 패치 |
|---|---|---|
| 일본판 · GUPJ8P | 일본어 | [JP 한국어 패치](patches/Shadow-the-Hedgehog-GC-JP-Korean-v0.1.xdelta) |
| 미국판 · GUPE8P | 영어 | [USA 한국어 패치](patches/Shadow-the-Hedgehog-GC-USA-Korean-v0.1.xdelta) |

게임 ISO나 설치 프로그램은 포함하지 않습니다. 본인이 소유한 게임에서 추출한 해당 지역의 수정되지 않은 원본이 필요합니다. 두 패치는 각각 대응하는 원본에 한 번만 적용하며, 서로 겹쳐 적용하지 않습니다.

## 적용 방법

1. 아래 확인값과 일치하는 일본판 또는 미국판 원본 ISO를 준비합니다. 두 원본 모두 `1,459,978,240`바이트입니다.
2. RVZ만 있는 경우 Dolphin의 변환 기능으로 **ISO**로 변환합니다. 스크럽(불필요 데이터 제거) 옵션은 끄고, 변환 결과의 SHA-256을 아래 표와 비교합니다. `.xdelta`는 RVZ에 직접 적용하지 않습니다.
3. 원본 지역에 맞는 `.xdelta`를 내려받아 xdelta3 호환 도구로 적용하고, 새 ISO로 저장합니다.
4. 결과 ISO의 SHA-256을 아래 표와 비교한 후 Dolphin 등에서 실행합니다.
5. 게임의 **Options → 자막 언어에서 日本語(Japanese)**를 선택하면 한국어가 표시됩니다. 미국판 패치에서도 음성은 원래의 영어로 유지됩니다.

xdelta3 명령 예시:

```text
xdelta3 -d -s "Original-USA.iso" "Shadow-the-Hedgehog-GC-USA-Korean-v0.1.xdelta" "Shadow-Korean-USA.iso"
```

일본판은 원본과 패치 파일을 JP용으로 바꿔 적용하세요. 패치 확인값은 [SHA256SUMS.txt](SHA256SUMS.txt)에 있습니다. Windows에서는 `Get-FileHash -Algorithm SHA256 '파일.iso'`로 확인할 수 있습니다.

## 원본 및 결과 ISO 확인값

| 구분 | SHA-256 |
|---|---|
| 일본판 원본 | `9ca5223e47c551e13659742c1db0de78a637ed3a709512239f9c353c22e7cfb3` |
| 일본판 한국어 결과 | `ddf5cf2f542af0b37fc06b0c2d8aada7a9f2b72f54ba6cfe66f2b68ecad24925` |
| 미국판 원본 | `54c79de9517a7a88e73e7354c7710a024e27d9db7b064336444c399bced3668c` |
| 미국판 한국어 결과 | `4a11639ecddddd4b876401758515a4b73f1269e5a0399aa11974553a8a94d49a` |

## 패치 범위와 확인 사항

- 일본판 11,036개, 미국판 11,034개 비어 있지 않은 대사·문구 위치에 한국어를 반영했습니다.
- 글꼴과 UI를 한국어화하며 실행 코드와 각 지역판의 원래 음성·영상은 유지합니다.
- 번역은 일본어 대사를 기준으로 하므로 영어 음성과 표현이 다를 수 있습니다.
- 두 패치 모두 실제 적용 후 결과 ISO 해시 일치를 확인했습니다. Dolphin에서 한국어 저장 안내, 스토리 메뉴, 오프닝 자막, 웨스토폴리스 진입 및 일시정지 화면을 확인했습니다.
- 전체 분기·엔딩의 완주 검수와 실기 검증은 완료하지 않았습니다. 문제 제보 시 지역판, 장면, 표시 내용을 함께 알려 주세요.

## 팬 제작 개선판 Reloaded도 한국어로 즐길 수 있습니다

게임플레이와 편의성 개선을 적용한 팬 제작 개선 패치 **Shadow the Hedgehog: Reloaded**용 한국어 패치도 별도로 제공합니다.

- [Reloaded 한국어 패치 저장소 및 설치 안내](https://github.com/nonunsaram/shadow-the-hedgehog-reloaded-korean)
- [Reloaded 원 제작팀 저장소](https://github.com/ShadowTheHedgehogHacking/ShdTH-Reloaded)

이 저장소는 원본 GameCube판용이고, 위 저장소는 Reloaded용입니다. 원하는 판본의 안내를 따라 설치하세요. 원본용 한국어 패치를 Reloaded ISO에 적용하거나 그 반대로 적용할 수는 없습니다.

## 제작 및 권리 안내

한국어 번역·시각 자산: 노는사람. Reloaded 한국어 프로젝트의 번역과 자산을 원본 일본판·미국판 구조에 맞게 적용했습니다. 원본판 적용 및 검증 도구 작업에는 Codex를 사용했습니다.

Shadow the Hedgehog 및 관련 게임·상표의 권리는 SEGA와 각 권리자에게 있습니다. 본 프로젝트는 공식 제품이 아닌 팬 번역입니다.

글꼴: LINE Seed KR 및 KOTRA 도약체. 관련 이용 조건은 [licenses](licenses)에 포함했습니다. xdelta3는 별도 도구이며 이 배포에 실행 파일을 포함하지 않습니다.
