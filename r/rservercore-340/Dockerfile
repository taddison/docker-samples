FROM mcr.microsoft.com/windows/servercore:2004

RUN mkdir c:\temp
WORKDIR c:/temp

# VC++ redist
RUN curl -Lo vc_redist.x64.exe  https://aka.ms/vs/16/release/vc_redist.x64.exe
RUN vc_redist.x64.exe /install /quiet /norestart

# ODBC
RUN curl -Lo msodbcsql.msi https://go.microsoft.com/fwlink/?linkid=2137027
RUN msiexec.exe /i msodbcsql.msi ADDLOCAL=ALL /norestart /qn /quiet /passive IACCEPTMSODBCSQLLICENSETERMS=YES

# R
RUN curl.exe -o r-install.exe https://cran.r-project.org/bin/windows/base/old/3.4.0/R-3.4.0-win.exe
RUN r-install.exe /VERYSILENT /DIR="C:\R\"

# RTools
RUN curl.exe -o rtools35.exe https://cran.r-project.org/bin/windows/Rtools/Rtools35.exe
RUN rtools35.exe /VERYSILENT /DIR="C:\RTools\"

# Environment
RUN setx path "%path%;C:\RTools\bin;C:\R\bin"

# Cleanup
WORKDIR c:/
RUN powershell remove-item c:\temp -recurse