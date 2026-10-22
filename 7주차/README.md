# Tech Lab 7주차 (Let There Be Light)

## 🎮 Let There Be Light

**제작 기간**: 2026.10.08 ~ 2026.10.15 (7일)

**작업깃허브** : https://github.com/songkuk1/GameTechLabWekk7


## ✨ 주요 기능

- Forward Shading 을 이용한 Per-Vertex Light, Per-Pixel Light 구현
- Ambient, Directional, Point, Spot Light 구현
- Light Culling 구현
- Uber Shader 구현 

## 👥 담당
- 라이트 클래스 구조 개선(LightComponent, LightActor 확장하기 좋게 리팩토링)
- PointLight 컴포넌트, 액터 구현, 와이어 프레임 시각화 추가 
- PointLight UberLit.hlsl 셰이더와 상수 버퍼 기반 및 연산
- ddx/ddy 기반 screen-space TBN 계산으로 탄젠트 없는 노멀 맵 프로토타입 작성