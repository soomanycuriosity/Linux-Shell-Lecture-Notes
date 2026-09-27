# Linux-Shell-Lecture-Notes
# Week 4 Lecture Note: Shell Commands

Overview
리눅스/유닉스 환경에서 핵심이 되는 기본 쉘 명령어(Shell Commands) 정리 노트입니다. 파일 시스템 탐색, 파일 관리, 내용 조회, 권한 설정 등 자주 사용하는 명령어를 위주로 구성했습니다.

==================================================

1. Directory Navigation & Search (디렉토리 이동 및 확인)

* pwd (Print Working Directory)
  - 설명: 현재 작업 중인 디렉토리의 절대 경로를 출력합니다.
  - 사용 예시:
    pwd
    # 출력 예: /home/user/workspace

* ls (List)
  - 설명: 현재 디렉토리 내의 파일과 폴더 목록을 조회합니다.
  - 주요 옵션:
    -l : 파일 권한, 소유자, 크기, 수정일 등 상세 정보(Long format) 출력
    -a : 숨김 파일(.으로 시작하는 파일)을 포함하여 전체 출력
    -h : 파일 크기를 사람이 읽기 쉬운 단위(KB, MB, GB)로 표시
  - 사용 예시:
    ls -lah

* cd (Change Directory)
  - 설명: 다른 디렉토리로 이동합니다.
  - 주요 경로 표기:
    .  : 현재 디렉토리
    .. : 상위 디렉토리
    ~  : 홈(Home) 디렉토리
    -  : 이전 작업 디렉토리
  - 사용 예시:
    cd ..          # 상위 디렉토리로 이동
    cd ~/Documents # 홈 디렉토리 내 Documents 폴더로 이동

==================================================

2. File & Directory Management (파일 및 디렉토리 관리)

* mkdir (Make Directory)
  - 설명: 새로운 디렉토리를 생성합니다.
  - 주요 옵션:
    -p : 하위 디렉토리 경로까지 한 번에 생성
  - 사용 예시:
    mkdir -p project/src/components

* touch
  - 설명: 빈 파일을 생성하거나, 기존 파일의 최종 수정 시각을 현재로 업데이트합니다.
  - 사용 예시:
    touch main.py

* cp (Copy)
  - 설명: 파일이나 디렉토리를 복사합니다.
  - 주요 옵션:
    -r : 디렉토리와 그 내부 하위 항목까지 재귀적으로 복사
  - 사용 예시:
    cp script.py script_backup.py
    cp -r src/ src_backup/

* mv (Move)
  - 설명: 파일이나 디렉토리를 이동시키거나 이름을 변경합니다.
  - 사용 예시:
    mv old_name.txt new_name.txt  # 이름 변경
    mv file.txt ./folder/         # 폴더 이동

* rm (Remove)
  - 설명: 파일이나 디렉토리를 삭제합니다. (주의: 휴지통을 거치지 않고 완전히 삭제됨)
  - 주요 옵션:
    -r : 디렉토리 및 내부 내용 전체 삭제
    -f : 경고창 없이 강제 삭제
  - 사용 예시:
    rm file.txt
    rm -rf target_folder/

==================================================

3. File Viewing & Manipulation (파일 내용 확인 및 처리)

* cat
  - 주요 기능: 파일 전체 내용 출력
  - 사용 예시: cat config.txt

* head
  - 주요 기능: 파일 상단 N줄 출력 (기본 10줄)
  - 사용 예시: head -n 20 log.txt

* tail
  - 주요 기능: 파일 하단 N줄 출력 (기본 10줄, -f로 실시간 모니터링)
  - 사용 예시: tail -f app.log

* grep
  - 주요 기능: 파일 내 특정 문자열/패턴 검색
  - 사용 예시: grep "ERROR" system.log

==================================================

4. Permissions & Redirection (권한 및 파이프)

* Redirection (>, >>) & Pipe (|)
  - >  : 명령의 결과를 파일로 저장 (덮어쓰기)
  - >> : 명령의 결과를 파일 끝에 추가 (이어쓰기)
  - |  : 앞 명령의 출력을 뒤 명령의 입력으로 전달
  - 사용 예시:
    ls -l > file_list.txt
    ps aux | grep python

* chmod (Change Mode)
  - 설명: 파일이나 디렉토리의 접근 권한(읽기 r, 쓰기 w, 실행 x)을 변경합니다.
  - 사용 예시:
    chmod +x run.sh   # 실행 권한 부여
    chmod 755 run.sh  # rwxr-xr-x 권한 설정
