# Barcode Scanner (Python)

노트북 내장 카메라를 이용해 바코드/QR 코드를 실시간으로 읽는 간단한 파이썬 스크립트입니다.

파일
- `scanner.py`: 카메라에서 프레임을 읽어 `pyzbar`로 바코드를 디코드하고 화면에 표시합니다.
- `requirements.txt`: 필요한 패키지 목록

설치 (권장: 가상환경)

```powershell
python -m venv .venv
.\.venv\Scripts\activate
pip install -r requirements.txt
```

Windows에서 `pyzbar`가 설치되지 않는 경우:
- `conda` 사용 시: `conda install -c conda-forge pyzbar`
- 또는 윈도우용 zbar 바이너리를 설치하거나 미리 빌드된 wheel을 사용하세요.

사용법

```powershell
python scanner.py [카메라인덱스] [beep]
```

예:
- 기본 카메라, beep 활성: `python scanner.py`
- 두 번째 카메라, beep 비활성: `python scanner.py 1 false`

동작
- 바코드/QR이 인식되면 콘솔에 `타입: 데이터` 형식으로 출력됩니다.
- 새로 인식한 값에 대해(중복 제외) 윈도우에서는 짧은 비프음을 냅니다.
- `Esc` 또는 `q`키로 종료합니다.

문제 해결
- 카메라가 열리지 않으면 카메라 인덱스를 바꿔보세요 (0,1,2...).
- `pyzbar` 설치 문제가 있으면 위의 conda 방법을 시도하세요.
