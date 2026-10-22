# Tech Lab 8주차 (Where there is light, there is also shadow)


## 🎮 Where there is light, there is also shadow


**제작 기간**: 2026.10.15 ~ 2026.10.22 (7일)

**작업깃허브** : https://github.com/808Jade/Techlab4_Week8


## ✨ 주요 기능

- Shadow Map 구현
- Acne 현상, Bias 문제, Peter Panning 이해
- 그림자 중첩, 해상도 부족 해결

## 👥 담당
- Light Depth View 셰이더 생성
- ShadowPass 추가해 Details 패널에 연결
- 광원다단계 Shadow Map 컬링 구현(밝기, 반경, Caster/Receiver 유무, 광원 Frustum, 화면 점유율 기준)
- stat shadow 통계(캐시 적중, 메모리), 스트레스 테스트씬으로 최적화 검증
- ReceiveShadow 플래그를 Uber Shader 퍼뮤테이션으로 연결 