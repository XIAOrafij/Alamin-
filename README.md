name: Windows Cloud PC - Anydesk

on:
  workflow_dispatch:

jobs:
  build:
    name: Start Building...
    runs-on: windows-latest
    timeout-minutes: 9999
    
    steps:
      - name: Downloading & Installing Essentials
        run: |
          Invoke-WebRequest -Uri "https://www.dropbox.com/scl/fi/7eiczvgil84czu55dxep3/Downloads.bat?rlkey=wzdc1wxjsph2b7r0atplmdz3p&dl=1" -OutFile "Downloads.bat"
          cmd /c Downloads.bat

      - name: Log In To AnyDesk
        run: cmd /c start.bat

      - name: Time Counter
        run: Start-Sleep -Seconds 14400
