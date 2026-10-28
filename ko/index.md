---
title: Marionette MCP (한국어)
lang: ko
---

# Marionette MCP

**AI 클라이언트가 Windows 데스크톱 앱을 보고 조작하게 합니다.** · 오세웅(Codetelier)

[English](../) · [이용약관](terms) · [환불 정책](refund) · [개인정보 처리방침](privacy) · 지원: codetelier.support@gmail.com

Marionette MCP는 Windows용 로컬 MCP 서버입니다. Claude Code 같은 AI 클라이언트가 도구를 불러 화면을 캡처하고, 글자를 읽고, 버튼과 아이콘을 찾고, 데스크톱 앱을 클릭하거나 입력합니다. API가 없는 앱도 다룰 수 있습니다.

## 기능

- **화면 보기**: 글자 인식(OCR, 한국어·영어)과 아이콘 탐지를 PC 안에서 하고, 요소를 번호 목록으로 돌려줍니다.
- **앱 조작**: 클릭, 입력(한글 포함), 키, 스크롤, 드래그, 창 포커스·배치, 앱이 제공하면 UI Automation.
- **동작이 보임**: 화면에 포인터와 대상 강조를 표시하고, 긴급 정지(Ctrl+Alt+Backspace 또는 마우스 흔들기)로 모든 입력을 한 번에 멈춥니다.
- **앱을 배움**: 앱마다 짧은 노트(요령·함정)를 남겨 다음에 AI 클라이언트에 알려 줍니다.
- **관리자 권한 없이 동작**: 일반 사용자 권한으로 돌고, 관리자 권한 앱을 다뤄야 할 때 트레이 메뉴에서 관리자 권한으로 다시 시작합니다.
- **원격 사용(선택)**: 지정한 다른 PC의 Claude Code가 이 PC를 사용하게 합니다(예: 테스트 VM). 접속 토큰과 그 주소만 여는 방화벽 규칙을 씁니다.

## 받기

PowerShell이나 명령 프롬프트에서 [winget](https://learn.microsoft.com/ko-kr/windows/package-manager/winget/)(Windows 10·11에 들어 있음)으로 설치합니다. 관리자 권한도, 설치 화면도 필요 없습니다.

```
winget install Codetelier.Marionette
```

새 버전은 하루 한 번 확인하고, 사용자가 고른 때(자동 설치를 켜면 Claude가 쉬는 동안) 설치합니다.

## 시스템 요구 사항

| | 최소 | 권장 |
|---|---|---|
| Windows | Windows 10 버전 1809(빌드 17763) 이상, 64비트(x64, ARM64는 지원하지 않음) | Windows 10 22H2 또는 Windows 11 |
| 프로세서 | 4코어 | 코어가 많을수록 화면 분석이 빠름 |
| 메모리 | 8GB | 16GB |
| 저장 공간 | 1GB 여유(설치 후 모델 포함 약 530MB) | |
| 그래픽 | 필요 없음 | 메모리 4GB 이상인 DirectX 12 외장 GPU가 있으면 아이콘 탐지가 빨라짐(선택) |

4코어 Intel Core i3-10100, 메모리 16GB에서 잰 값: Marionette는 대기 중 약 0.2GB, 화면 분석 사이 0.5~0.8GB, CPU로 분석하는 동안 최대 약 4GB를 씁니다. 560×640 창 분석은 CPU로 약 9~13초, 1920×1080 화면 전체는 약 21초이고, GeForce GTX 1650이 아이콘 탐지를 맡으면 약 3~8초와 16초입니다. 창이나 영역만, 글자만 읽으면 더 빠릅니다.

## Claude Code 연결

Marionette가 시작되면(트레이 아이콘) Claude Code에 한 번 등록합니다.

```
claude mcp add --transport http marionette http://127.0.0.1:5300 -s user
```

그다음 Claude Code를 다시 시작합니다.

## Free와 Pro

- **Free**: 어느 1시간 동안이든 도구 호출 100회.
- **Pro**: 한도 없음. $29 한 번 결제, PC 1대. Marionette 창 **정보** 탭의 **Pro 구매**를 누르세요. 라이선스 키는 영수증 메일로 옵니다: **정보** 탭에 붙여 넣고 **등록**을 누르세요([방법](activate)). 다른 PC로 옮기려면 쓰던 PC에서 먼저 **키 삭제**를 누르세요. 14일 안에는 전액 환불합니다([환불 정책](refund)).

## 지원

codetelier.support@gmail.com
