# Tech Lab 5주차 (Editor Mode and PIE (Play In Editor) Mode, Clearing the Fog)

## 🎮 Editor Mode and PIE (Play In Editor) Mode, Clearing the Fog

**제작 기간**: 2026.10.01 ~ 2026.10.08 (7일)

**작업깃허브** : https://github.com/grukall/Week6


## ✨ 주요 기능

- Editor 모드, PIE 모드 구현
- 다중 World 생성, 소멸, 실행
- Component Pattern 을 이용한 Actor System 구축
- UWorld, ULevel, AActor, UActorComponent 클래스 관계 이해 
- Post Process Pass 구현을 통한 Multi-Pass Rendering 이해 

## 👥 담당
- 렌더타깃->풀스크린 ScreenPass 구조의 후처리 파이프라인 구현 
- 깊이버퍼 선형화, 정규화로 SceneDepth 뷰모드 구현
- Distance/Exponential Height Fog를 후처리 셰이더에서 적분 계산으로 구현, 컴포넌트,ShowFlag로 에디터 연동 