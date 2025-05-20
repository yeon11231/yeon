# 25_05_20_vscode,gcc,git환경구축

```powershell
# 1. 관리자 권한 PowerShell 실행 후 실행 정책 우회
Set-ExecutionPolicy Bypass -Scope Process -Force

# 2. Chocolatey 한 줄 설치
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.SecurityProtocolType]::Tls12
iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))

# 관리자 권한 PowerShell에서 실행
Import-Module "$env:ChocolateyInstall\helpers\RefreshEnv.psm1"

# 이제 refreshenv 사용 가능
refreshenv

# 3. 환경변수 갱신
refreshenv


# 4. VS Code 설치 (모두 기본, 전부 yes)
choco install vscode -y --accept-license --no-progress

# 5. 설치 확인
code --version

# 관리자 권한 PowerShell에서

# MinGW 설치
choco install mingw -y --accept-license --no-progress

# 설치 후 환경 변수 갱신
refreshenv

# gcc 확인
gcc --version

# g++ 확인
g++ --version

# (2) Git 설치 (모두 기본, 전부 yes)
choco install git -y --accept-license --no-progress

# (3) 환경변수 갱신
refreshenv  # 또는 PowerShell 창을 닫았다가 다시 열어도 됩니다

# (4) 설치 확인
git --version
```

