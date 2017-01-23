FROM microsoft/windowsservercore

SHELL ["powershell", "-Command", "$ErrorActionPreference = 'Stop'; $ProgressPreference = 'SilentlyContinue';"]

ENV NPM_CONFIG_PYTHON=python2.7 \
    NPM_CONFIG_MSVS_VERSION=2015

RUN Invoke-WebRequest -Uri https://nodejs.org/dist/v6.9.4/node-v6.9.4-x64.msi -OutFile node.msi -UseBasicParsing ; \
    Start-Process -FilePath msiexec -ArgumentList '/i node.msi /qn' -NoNewWindow -Wait ; \
    Invoke-WebRequest -Uri https://www.python.org/ftp/python/2.7.13/python-2.7.13.amd64.msi -OutFile python.msi -UseBasicParsing ; \
    Start-Process -FilePath msiexec -ArgumentList '/i python.msi /qn' -NoNewWindow -Wait ; \
    Invoke-WebRequest -Uri https://download.microsoft.com/download/5/f/7/5f7acaeb-8363-451f-9425-68a90f98b238/visualcppbuildtools_full.exe -OutFile buildtools.exe -UseBasicParsing ; \
    Start-Process buildtools.exe -ArgumentList '/NoRestart /S' -NoNewWindow -Wait

CMD [ "node" ]
