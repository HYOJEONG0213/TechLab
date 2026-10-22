# Tech Lab 5주차 (Brute Force Competition)

## 🎮 Brute Force Competition

**제작 기간**: 2026.09.28 ~ 2026.10.01 (3일)

**작업깃허브** : https://github.com/ksang9609/podoEngine-w5


## ✨ 주요 기능

- 다양한 최적화 기법 구현
- 다양한 병목 현상 경험 및 원인 이해
- stress 테스트 진행(Picking ms, FPS ms)

## 👥 담당
- Octree 공간 분할 구조 설계 및 Frustum Culling 과 피킹 후보 필터링에 적용
- Contains() 3단계 판정(Inside/Intersect/Outside) 로 서브트리 단위 컬링 구현
- 드래그 종료시 리빌드, 부분 갱신, stray 관리로 동적 씬에서 갱신 비용 감소
- 카메라 기준 front-to-back 순회, 거리순 정렬, 조기 종료로 피킹 비용 감소 (피킹 지연 시간 -93.03% 감소)
- Octree Picking을 BVH 피킹으로 수정(피킹 지연 시간 75.87% 감소)