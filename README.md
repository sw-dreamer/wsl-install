# WSL란?

WSL란 Windows Subsystem for Linux의 약자로 Windows 운영체제에서 리눅스 배포판을 실행할 수 있도록 해주는 호환성 계층입니다.

이 시스템은 Windows와 Linux 환경을 서로 연동하여 개발자들이 두 운영체제를 동시에 사용할 수 있도록 돕습니다.

WSL은 **Windows 10 이후 버전**에서 제공되며, 주로 개발 환경을 설정할 때 유용하게 사용됩니다.

리눅스의 강력한 개발 도구와 명령어를 사용하면서, Windows의 그래픽 인터페이스와 프로그램들을 동시에 활용할 수 있습니다.



WSL에서는 ***WSL 1, WSL 2*** 두 가지의 주요 버전이 있습니다.

   - **WSL 1**: 리눅스 커널을 Windows 내에서 가상화하는 방식으로 동작합니다.
               성능은 비교적 낮지만, 리눅스 명령어와 도구를 사용할 수 있게 해줍니다.

   - **WSL 2**: *WSL 1과는 달리* 실제 리눅스 커널을 Windows의 가상 머신에서 실행하는 방식입니다.

  <hr/>

# WSL의 장점

## 1. 리눅스 도구 및 환경을 Windows에서 사용 가능

   - 리눅스 기반의 개발 도구 및 명령어를 Windows에서 실행할 수 있습니다.
   
     예를 들어, bash, git, grep, awk 등 다양한 리눅스 명령어를 Windows 환경에서 그대로 사용할 수 있습니다.
   
     그래서 개발자가 다양한 플랫폼에서 작업할 때 유용합니다.

## 2. 빠르고 효율적인 개발 환경

   - 리눅스에서만 실행되는 다양한 개발 도구(예: Docker, Node.js, Python 등)를 Windows에서 직접 사용할 수 있어, 개발자가 크로스 플랫폼 환경에서 작업할 때 매우 유용합니다.
     
   - WSL 2에서는 실제 리눅스 커널을 실행하기 때문에 성능이 WSL 1보다 뛰어납니다.

## 3. 가상 머신 없이 리눅스 사용

   - WSL은 리눅스 환경을 Windows 내에서 가상 머신 없이 실행할 수 있기 때문에, 리소스 소모가 적고 빠르게 동작합니다.
     
   - WSL 2는 가상화 기술을 사용하지만, 여전히 가상 머신보다 훨씬 더 효율적입니다.

## 4. Windows와 리눅스 간의 파일 시스템 접근

   - WSL을 통해 Windows와 리눅스 시스템 간에 파일을 손쉽게 공유할 수 있습니다.
     
   - Windows 파일 시스템과 리눅스 파일 시스템을 동시에 사용하면서, 두 시스템의 파일을 자유롭게 이동시키고 수정할 수 있습니다.
     
## 5. Windows와 리눅스의 통합된 개발 환경

   - WSL은 Visual Studio Code 같은 IDE와 통합되어 Windows와 리눅스 환경을 동시에 사용할 수 있게 해줍니다.
     
   - 개발자가 두 환경을 전환할 필요 없이, 리눅스 기반의 개발을 Windows 환경에서 직접 할 수 있습니다.
     
## 6. Docker와 같은 컨테이너 기술 지원

   - WSL 2는 Docker와 같은 컨테이너 기술을 원활하게 실행할 수 있는 환경을 제공합니다.
     
   - Windows에서 리눅스 기반의 Docker 컨테이너를 실행할 수 있어, 다양한 개발 및 테스트 작업을 통합된 환경에서 할 수 있습니다.
     
## 7. 배포판 선택의 유연성

   - WSL을 사용하면 여러 리눅스 배포판(Ubuntu, Debian, Kali Linux 등)을 선택하여 설치할 수 있습니다.
     
     이는 개발자들이 각자의 요구에 맞는 배포판을 선택하여 최적화된 개발 환경을 구축할 수 있게 합니다.

  <hr/>

# WSL 설치 가이드

  이 가이드는 Windows Subsystem for Linux(WSL)를 설치하는 방법을 설명합니다.

## 1. PowerShell 관리자 권한 실행

  PowerShell을 관리자 권한으로 실행합니다.

## 2. 리눅스를 위한 Windows 하위 시스템 사용

  아래 명령어를 실행하여 리눅스를 위한 Windows 하위 시스템을 활성화합니다.

   ```powershell
   dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
   ```
## 3. Virtual Machine 사용

  WSL 2를 사용하려면 가상 머신 기능을 활성화해야 합니다. 아래 명령어를 실행합니다.

   ```powershell
   dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
   ```
## 4. WSL 설치

  WSL을 설치하려면 다음 명령어를 실행합니다.

   ```powershell
   wsl --install
   ```
  ## 문제 발생 시
  만약 문제가 발생한다면, 아래 명령어를 실행하여 웹에서 WSL을 다운로드하여 설치할 수 있습니다.

   ```powershell
   wsl --install --web-download
   ```
## 5. 재부팅

  설치 후 재부팅을 진행합니다.

## 6. WSL 2로 버전 변경

  WSL 2를 기본 버전으로 설정하려면 powershell 관리자 권한으로 실행 후 아래 명령어를 실행합니다.

   ```powershell
   wsl --set-default-version 2
   ```

## 7. WSL 상태 확인

  설치된 WSL 버전 및 상태를 확인하려면 아래 명령어를 사용합니다.
  
   ```powershell
   wsl --status
   ```
   ```powershell
   wsl -l -v
   ```

## 8. 재부팅

  설정을 완료한 후 시스템을 다시 재부팅합니다.
