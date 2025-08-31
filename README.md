# DailyAlleyAI-Promo-ImageOutpainting-Python

## 프로젝트 소개
- 참여 대회 : 2025년 13기 멋쟁이사자처럼 해커톤 
- 팀명 : 순대볶음
- 서비스명 : DailyAlley
- AI 서비스명 : Promo & Ad Image Generator (FastAPI)

## 프로젝트 개요
소상공인들은 온라인 홍보의 필요성을 잘 알고 있지만, 전문적인 사진 편집이나 카피라이팅 역량 부족으로 실제 실행에 어려움을 겪습니다.  
**Promo & Ad Image Generator**는 이러한 문제를 해결하기 위해 기획된 프로젝트로, AI를 활용해 **사진 보정 → 홍보 문구 생성** 을 제공하는 백엔드 서비스입니다.  

이 프로젝트는 **[멋쟁이사자처럼 13기 해커톤]**에서 진행된 팀 프로젝트 중, 제가 담당한 **AI 파트**를 정리한 것입니다.

---

## 핵심 기여
- **FastAPI 기반 백엔드 개발**  
  - REST API 설계 및 라우팅 구조화
  - `/v1/generate-promo`, `/v1/outpaint`, `/v1/upload-store-images` 등 주요 엔드포인트 구현
- **AI 모델 연동**  
  - Google Gemini를 활용한 자연어 프롬프트 강화 및 맞춤형 홍보 문구 생성
  - OpenAI DALL·E·Stable Diffusion Inpainting·rembg를 조합한 이미지 보정/배경 제거 파이프라인 구축
- **AWS + Docker 배포**  
  - Amazon Linux 2023 환경에서 Docker 컨테이너 기반 서비스 배포
  - 환경 변수 관리(.env) 및 CORS 설정 적용

---

## 기능 소개
1. **AI 이미지 보정**  
   - 음식 사진의 색감·구도를 자동으로 보정  
   - 배경 제거(rembg) 및 SNS 친화적인 구도로 재구성  

2. **맞춤형 홍보 문구 생성**  
   - 업로드된 이미지 + 가게 정보 기반  
   - “세련된”, “열정적인”, “고급스러운” 등 톤 앤 매너를 반영  

---

## 기술 스택
- **Language/Framework**: Python, FastAPI  
- **AI/ML**: Google Gemini, OpenAI DALL·E, Stable Diffusion Inpainting, rembg  
- **Infra**: Docker, AWS EC2 (Amazon Linux 2023)  
- **Etc**: Uvicorn, Python-dotenv, Pillow  

---

### 코드 파일
- app.py : FastAPI 앱 및 라우트 등록
- config.py : 환경 변수 및 설정
- utils.py : 공용 유틸 함수
- routes_promo.py : 홍보용 텍스트 생성 라우트
- routes_ad_image.py : 이미지 가공 라우트
- routes_upload_store.py : 원본 이미지 저장 라우트
- test.py : 테스트용 함수 
---

### 환경 파일
- Dockerfile : 도커 컨테이너 설정
- requirements.txt : 필요 라이브러리

---
### 환경 변수 설정 방법
.env 파일 생성 후 아래의 코드 복붙
```dotenv
GEMINI_API_KEY="자신의 Gemini API Key"
OPENAI_API_KEY="자신의 OpenAI API Key"
GEMINI_MODEL="gemini-1.5-flash"
```
