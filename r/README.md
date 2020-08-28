# Docker R on Windows

Some images used to test Docker on Windows.

All images are based on Server Core 2004 and contain R, RTools, VC++ x64 Redistributable, SQL Server ODBC Drivers (v11)

Specific versions:

- rservercore-340
  - R 3.4.0

## Build scripts

```shell
# R 3.4.0
docker build ./rservercore-340 --tag rservercore:3.4.0
```

## Run R in the container
```
docker run -it --rm rservercore:3.4.0 R
```

## Useful links

> All Windows/x64

VC++
- https://aka.ms/vs/16/release/vc_redist.x64.exe

SQL Server ODBC Drivers
- Versions - https://docs.microsoft.com/en-us/sql/connect/odbc/windows/release-notes-odbc-sql-server-windows
- v11 - https://go.microsoft.com/fwlink/?linkid=2121206
- v17 - https://go.microsoft.com/fwlink/?linkid=2137027

R and RTools
- R 3.4.0 - https://cran.r-project.org/bin/windows/base/old/3.4.0/R-3.4.0-win.exe
- RTools 3.5 (For R 3.3-3.6) - https://cran.r-project.org/bin/windows/Rtools/Rtools35.exe