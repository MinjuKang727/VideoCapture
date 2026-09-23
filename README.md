# 🎥 VideoCapture

> 파이썬으로 직접 개발한 직관적이고 가벼운 데스크톱 화면 및 오디오 녹화 프로그램입니다.

<br><br>

## 💡 개발 동기
기존 녹화 프로그램들의 불편함과 녹화 오류를 해결하고자, 직접 화면 및 시스템 오디오 동시 녹화가 가능한 프로그램을 개발하게 되었습니다.

<br><br>

## ✨ 주요 기능 (Features)
* **직관적인 UI/UX**: 
  * 녹화, 일시 정지, 취소, 음소거 기능을 탭 기반(녹화 / 저장·싱크)으로 분리하여 제공
  * 마우스 호버 시 상세 안내 툴팁(Tooltip) 지원
* **스마트한 녹화 관리**:
  * `REC_YYYYMMDD_HHMMSS.mp4` 형식으로 자동 파일명 생성 및 저장
  * 녹화 일시 정지 중 소모된 시간을 정밀하게 계산하여 비디오와 오디오 간의 싱크 어긋남 방지
* **오디오 및 싱크 제어**:
  * WASAPI 루프백을 이용한 시스템 내부 소리 녹음 지원 (음소거 토글 가능)
  * 밀리초(ms) 단위의 수동 싱크 조절 및 설정값(`config.ini`) 영구 저장
  * 음소거 녹화 시 불필요한 오디오 변환을 건너뛰고 FFmpeg를 통해 고속 저장 (`-an` 옵션 적용)

<br><br>

## 🛠️ 기술 스택 (Tech Stack)
* **Language**: Python 3.x
* **GUI**: `tkinter`, `ttk`
* **Capture & Processing**: `OpenCV (cv2)`, `mss`, `PyAudioWPatch`
* **Media Processing**: `FFmpeg`

<br><br>

## 📥 프로그램 다운로드 (사용자용)
코드를 직접 실행하지 않고 바로 프로그램을 사용하고 싶다면, 아래 깃허브 링크에서 배포 버전을 다운로드하여 실행할 수 있습니다.  
- Onefile 버전: 단일 파일(`VideoCapture.exe`)로 다운로드 및 실행이 편리합니다.  
- Onedir 버전: 압축 파일(`VideoCapture.zip`) 형태이며, 실행 속도가 더 빠를 수 있습니다.  
👉 [VideoCapture 최신 버전 다운로드 하러 가기](https://github.com/MinjuKang727/VideoCapture/releases)  

<br><br>

## ⚙️ 시작 가이드 (Getting Started)

### 1. 사전 준비 (Prerequisites)
시스템에 **FFmpeg**가 설치되어 있어야 정상적인 영상 및 오디오 병합이 가능합니다. 
(`ffmpeg.exe` 파일이 실행 파일 경로 또는 프로젝트 루트에 위치해야 합니다.)

### 2. 레포지토리 클론하기
```bash
git clone [https://github.com/MinjuKang727/VideoCapture.git](https://github.com/MinjuKang727/VideoCapture.git)
cd VideoCapture
```

### 3. 필요 라이브러리 설치
```bash
pip install -r requirements.txt
```

### 4. 프로그램 실행
```bash
python VideoRecorder.py
```

<br><br>

## 📌 트러블 슈팅 요약
- **버튼 상태 초기화 버그**: 녹화 취소/중단 시 `reset_ui_to_idle()` 함수를 구축하여 모든 버튼 상태와 아이콘을 안전하게 대기 상태로 원복.  
- **레이아웃 정렬 불일치**: 중간 프레임에 `anchor=tk.CENTER`를 적용하고 균일한 패딩을 부여하여 UI 흔들림 방지.  
- **오디오 녹음 잡음 해결**: 샘플링 속도를 44,100Hz(표준)로 고정하고, FFmpeg 병합 시 `aresample=async=1` 필터 적용.  
- **음소거 녹화 효율성**: 음소거 시 빈 오디오 파일을 생성하지 않고 FFmpeg의 `-an` 옵션으로 고속 저장 처리.

<br><br>

## 📄 라이선스 (License)
This project is licensed under the **MIT License** - 자세한 내용은 [LICENSE](https://github.com/MinjuKang727/VideoCapture/blob/67ce597cce988a9ee2d361415d44f216c120ee5a/LICENSE) 파일을 참고하세요.
