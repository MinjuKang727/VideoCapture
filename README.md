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

## ⚙️ 시작 가이드 (Getting Started)

### 1. 사전 준비 (Prerequisites)
시스템에 **FFmpeg**가 설치되어 있어야 정상적인 영상 및 오디오 병합이 가능합니다. 
(`ffmpeg.exe` 파일이 실행 파일 경로 또는 프로젝트 루트에 위치해야 합니다.)

### 2. 레포지토리 클론하기
```bash
git clone [https://github.com/MinjuKang727/VideoCapture.git](https://github.com/MinjuKang727/VideoCapture.git)
cd VideoCapture
```
