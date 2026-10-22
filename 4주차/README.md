# Tech Lab 4주차 (OBJ Import, StaticMesh and multiple viewport rendering)

## 🎮 OBJ Import, StaticMesh and multiple viewport rendering

**제작 기간**: 2026.09.17 ~ 2026.09.23 (7일)

**작업깃허브** : https://github.com/chsportfor/GameLabWeek4


## ✨ 주요 기능

- OBJ 임포트 시스템 구현
- 엔진 리소스 파이프라인 관계 구축 이해
- 정적 메시(StaticMesh) 렌더링 이해
- 다중 뷰포트(Viewport) 구현

## 👥 담당
- SWindow, SSpliteer(H/V) 기반 Splitter Tree로 4분할 에디터 뷰포트 설계, 구현
- 뷰포트별 독립 카메라(Perspective/Ortho 6방향)와 뷰 모드, 기즈모 동기화 
- 스플릿터 비율, 카메라 정보를 editor.ini, 씬 파일에 저장해 작업 환경 복원