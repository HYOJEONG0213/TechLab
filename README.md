# TechLab — 크래프톤 정글 Tech Lab (DirectX 11 게임 엔진 제작)

> 8주간 매주 팀을 바꿔가며 **DirectX 11 기반 게임 엔진을 바닥부터** 만든 기록입니다.
> 2D 렌더러에서 시작해 에디터, 리소스 파이프라인, 공간 분할 최적화, 라이팅/섀도우까지 확장했습니다.

**기간** 2026.08.31 ~ 2026.10.22 (8주) · **언어/기술** C++17, DirectX 11, HLSL, ImGui, XAudio2

---

## 한눈에 보기

| 주차 | 주제 | 맡은 작업 | 저장소 |
|---|---|---|---|
| [1주차](1주차/README.md) | 게임잼 — 핀볼킹 | 마우스 Picking, 발사 UI, 용암/게임오버 로직 | [PinballKing](https://github.com/HyoJeongYang0213/PinballKing) |
| [2주차](2주차/README.md) | 2D → 3D World | 카메라 시스템(원근/직교), **뮐러-트럼보어 레이캐스트 피킹**, 프레임 상수 버퍼 최적화 | [week2team2](https://github.com/Kimyoungkyun-jg/week2team2) |
| [3주차](3주차/README.md) | Texture & Wireframe | 라이트 액터 설계 + ImGui 편집 UI, **JSON 씬 직렬화 확장**, Batch Line 렌더링 | [week3](https://github.com/HyoJeongYang0213/week3) |
| [4주차](4주차/README.md) | OBJ Import / StaticMesh / 멀티 뷰포트 | **Splitter Tree 기반 4분할 에디터 뷰포트**, 뷰포트별 독립 카메라, 작업 환경 저장·복원 | [GameLabWeek4](https://github.com/chsportfor/GameLabWeek4) |
| [5주차](5주차/README.md) | Brute Force Competition (최적화) | **Octree 공간 분할 + Frustum Culling**, BVH 피킹 → **피킹 지연 -93%** | [podoEngine-w5](https://github.com/ksang9609/podoEngine-w5) |
| [6주차](6주차/README.md) | Editor / PIE Mode, Fog | **후처리(ScreenPass) 파이프라인**, SceneDepth 뷰모드, Height/Distance Fog | [Week6](https://github.com/grukall/Week6) |
| [7주차](7주차/README.md) | Let There Be Light | PointLight 컴포넌트/액터, **Uber Shader 라이팅**, screen-space TBN 노멀맵 | [Week7](https://github.com/songkuk1/GameTechLabWekk7) |
| [8주차](8주차/README.md) | Shadow Map | **다단계 Shadow Map 컬링**, ShadowPass, `stat shadow` 통계 및 스트레스 테스트 | [Week8](https://github.com/808Jade/Techlab4_Week8) |

---

## 대표 성과 3가지

### 1. 공간 분할로 피킹 지연 93% 감소 (5주차)
Octree를 설계해 Frustum Culling과 피킹 후보 필터링에 함께 적용하고, `Contains()`를 Inside/Intersect/Outside 3단계로 판정해 서브트리 단위로 컬링했습니다.
카메라 기준 front-to-back 순회 + 거리순 정렬 + 조기 종료로 **피킹 지연 시간 -93.03%**, 이후 BVH로 전환해 **추가 -75.87%** 를 얻었습니다.

### 2. Splitter Tree 기반 4분할 에디터 뷰포트 (4주차)
`SWindow` / `SSplitter(H·V)` 를 트리로 구성해 비율 조절이 가능한 4분할 뷰포트를 만들고, 뷰포트마다 독립 카메라(Perspective / Ortho 6방향)·뷰 모드·기즈모를 동기화했습니다. 스플리터 비율과 카메라 상태를 `editor.ini`와 씬 파일에 저장해 작업 환경을 복원합니다.

### 3. 후처리 파이프라인과 Shadow Map 컬링 (6·8주차)
렌더타깃 → 풀스크린 ScreenPass 구조의 멀티패스 후처리를 구현하고 깊이 버퍼 선형화로 SceneDepth 뷰모드, 셰이더 적분 기반 Fog를 추가했습니다.
8주차에는 밝기·반경·Caster/Receiver 유무·광원 Frustum·화면 점유율 기준의 다단계 Shadow Map 컬링과 `stat shadow` 통계를 만들어 스트레스 테스트로 효과를 검증했습니다.

---

## 다룬 기술 영역

- **렌더링** Forward Shading, Per-Vertex/Per-Pixel Lighting, Uber Shader 퍼뮤테이션, Shadow Map(Acne·Bias·Peter Panning), 멀티패스 후처리, Batch Line
- **엔진 구조** UObject·UWorld·ULevel·AActor·UActorComponent, Component Pattern, Editor/PIE 모드, 씬 직렬화(JSON)
- **최적화** Octree·BVH, Frustum Culling, Light Culling, 상수 버퍼 갱신 최소화, 인덱스 버퍼, 스트레스 테스트 기반 프로파일링
- **에디터 툴링** ImGui 패널, 기즈모, 멀티 뷰포트, 설정 영속화
