# object-detection 커스터마이징 교육을 위한 실습코드입니다.

교육은 Yolov5의 pre-trained된 모델을 이용합니다.

우측 상단의 'Code' 버튼을 눌러 Zip 파일로 코드를 다운받아 주세요.

## 아래 순서대로 환경을 구축한 후 실습을 진행해 주세요.

#### 실습은 Python 3.9.10 버전 인터프리터 + 가상환경 방식으로 진행합니다.

- Object Detection AI모델링은 파이썬 기초 문법만 알아서는 한계가 있습니다. 파이썬이 작동하는 방식, 컴퓨터비전, 데이터 수집/전처리 등에 대한 배경 지식이 있어야 하고, 그 무엇보다 OS, 파일&디렉토리 구조, GPU(nVidia) 등 PC환경에 대한 이해가 꼭 있어야 합니다. 그렇지 않을 경우 에러 발생시 대처가 어렵습니다.

- PC에 GPU 드라이버, CUDA, cuDNN 설치 및 세팅은 완료되어 있다고 가정하고 건너뜁니다.


#### 1. Python 설치(PC에 파이썬이 설치되어 있을 경우 Pass)

- https://www.python.org/ftp/python/3.9.10/python-3.9.10-amd64.exe

#### 2. VS CODE 설치(PC에 설치되어 있을 경우 Pass)

- https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user

#### 3. (사내망의 경우) pip를 SSL Error없이 원활히 실행하기 위해 아래와 같이 진행합니다.

- 파일 탐색기를 열고 C: → 사용자 → poscoedu_ph(혹은 본인의 윈도우 계정 이름) 폴더로 진입

- 새로운 폴더를 만들고 폴더명을 'pip'로 변경

- 만들어진 pip 폴더로 들어간 후, 오른쪽 마우스 클릭 → 새로 만들기 → 텍스트 문서 클릭

- 만들어진 파일의 이름을 'pip.ini'로 변경

- pip.ini 파일을 더블클릭해 메모장으로 실행한 후, 아래 내용을 복사/붙여넣기하고 저장, 메모장 종료

>[global]<br>trusted-host = pypi.org files.pythonhosted.org download.pytorch.org

#### 4. Yolov5 모델 다운로드를 위한 Git 설치

- <a href="https://git-scm.com/download/win">https://git-scm.com/download/win</a> 으로 접속

- '64-bit Git for Windows Setup' 을 클릭해 git 프로그램을 다운로드 받은 후 더블클릭하여 설치

#### 5. OD 프로젝트를 위한 파이썬 가상환경 생성

- 커맨드 프롬프트 실행 후 아래 명령어 입력

>cd Desktop
>
>mkdir venv
>
>cd venv
>
>python -m venv venv_od

#### 6. vs code의 인터프리터를 가상환경 인터프리터로 설정

- vs code에서 'Ctrl + Shift + p' 를 눌러 파레트를 실행한 다음 'interpreter' 입력해 검색

- 'Python: Select Interpreter'를 선택한 후 'Enter Interpreter Path'를 선택, 'Find' 클릭

- 바탕화면 → venv → venv_od → Scripts 폴더로 들어간 다음 'python.exe' 선택 후 확인

## pytorch와 각종 패키지 설치

파이토치는 CUDA 버전에 맞춰 적합한 버전을 설치해야 합니다.

#### 1. vs code에서 'Ctrl + Shift + ~'를 눌러 터미널을 실행합니다.

- Powershell로 실행될 경우 오류가 날 수 있습니다. command prompt로 띄워 주세요.

#### 2. pytorch를 PC 환경에 맞춰 선택해 설치합니다.

- 브라우저를 열고 주소창에 'https://pytorch.org/get-started/locally/' 입력 후 이동

- START LOCALLY 부분의 옵션을 Stable, Windows, Pip, Python 으로 선택

- 'Compute Platform' 부분의 옵션은 본인의 환경에 맞게 선택(GPU가 없다면 CPU로, GPU가 있다면 CUDA 버전에 맞춰 선택)

- 'Run this Command' 부분에 출력된 명령문을 복사한 후 커맨드 창에 붙여넣고 실행

#### 3. 터미널에서 pip upgrade 후 필요한 기본 패키지를 설치합니다.

>pip install --upgrade pip
>
>pip install jupyter opencv-python tqdm pandas tensorflow-gpu tensorboard gitpython matplotlib Pillow psutil PyYAML requests scipy thop seaborn

### 이제 준비는 끝났습니다. 교재에 맞춰 따라하다보면 나만의 Object Detection 모델을 만들 수 있을 것입니다.
