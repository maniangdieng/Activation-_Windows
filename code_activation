@echo off
>NUL 2>&1 reg.exe query "HKU\S-1-5-19" || (
    ECHO SET UAC = CreateObject^("Shell.Application"^) > "%TEMP%\Getadmin.vbs"
    ECHO UAC.ShellExecute "%~f0", "%1", "", "runas", 1 >> "%TEMP%\Getadmin.vbs"
    "%TEMP%\Getadmin.vbs"
    DEL /f /q "%TEMP%\Getadmin.vbs" 2>NUL
    Exit /b
)

title Windows ON

echo.
echo ============================================================
echo Author: StarKev
echo ============================================================
echo Version: 1.0
echo.
echo.
echo Appuyez sur n'importe quelle touche pour commencer.
echo.
pause > nul
goto menu

REM sélection de la version de Windows à activer
:menu
cls
echo.
title Windows ON
echo Choisissez votre version de Windows 10/11 a activer:
echo.
echo 1) Famille / Core
echo 2) Professionel
echo 3) Professionel pour les Stations de travail
echo 4) Professionel Education
echo 5) Education
echo 6) Enterprise
echo 7) Enterprise 2019 LTSC ( Win10 )
echo.
echo Autres options :
echo.
echo s) Supprimer la licence Windows
echo a) Activer avec une cle personnalisee
echo v) Verifier l'etat d'activation Windows
echo x) Sortir
echo.

set choix=
set /p choix="Entrez votre choix: "
if not '%choix%'=='' set choix=%choix:~0,1%
if '%choix%'=='1' goto Famille
if '%choix%'=='2' goto Professionel
if '%choix%'=='3' goto proSDT
if '%choix%'=='4' goto proEDU
if '%choix%'=='5' goto Education
if '%choix%'=='6' goto Enterprise
if '%choix%'=='7' goto LTSC2019
if '%choix%'=='s' goto suppWin
if '%choix%'=='a' goto winLicen
if '%choix%'=='v' goto stat
if '%choix%'=='x' goto exit
echo "%choix%" n'est pas valide, essayez a nouveau.
pause
goto menu

REM Options principale
:Famille
cls
echo.
echo En cours d'activation de Windows....
echo.
cscript %SYSTEMROOT%\System32\slmgr.vbs /ipk YTMG3-N6DKC-DKB77-7M9GH-8HVX7 > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /skms kms.03k.org > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /ato > nul
goto fin

:Professionel
cls
echo.
echo En cours d'activation de Windows....
echo.
cscript %SYSTEMROOT%\System32\slmgr.vbs /ipk W269N-WFGWX-YVC9B-4J6C9-T83GX > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /skms kms.03k.org > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /ato > nul
goto fin

:proSDT
cls
echo.
echo En cours d'activation de Windows....
echo.
cscript %SYSTEMROOT%\System32\slmgr.vbs /ipk NRG8B-VKK3Q-CXVCJ-9G2XF-6Q84J > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /skms kms.03k.org > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /ato > nul
goto fin

:proEDU
cls
echo.
echo En cours d'activation de Windows....
echo.
cscript %SYSTEMROOT%\System32\slmgr.vbs /ipk 6TP4R-GNPTD-KYYHQ-7B7DP-J447Y > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /skms kms.03k.org > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /ato > nul
goto fin

:Education
cls
echo.
echo En cours d'activation de Windows....
echo.
cscript %SYSTEMROOT%\System32\slmgr.vbs /ipk NPPR9-FWDCX-D2C8J-H872K-YT43 > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /skms kms.03k.org > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /ato > nul
goto fin

:Enterprise
cls
echo.
echo En cours d'activation de Windows....
echo.
cscript %SYSTEMROOT%\System32\slmgr.vbs /ipk NW6C2-QMPVW-D7KKK-3GKT6-VCFB2 > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /skms kms.03k.org > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /ato > nul
goto fin

:LTSC2019
cls
echo.
echo En cours d'activation de Windows....
echo.
cscript %SYSTEMROOT%\System32\slmgr.vbs /ipk M7XTQ-FN8P6-TTKYV-9D4CC-J462D > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /skms kms.03k.org > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs /ato > nul
goto fin

:fin
cscript %SYSTEMROOT%\System32\slmgr.vbs -dli
pause
goto menu

REM Autres options
:suppWin
cls
echo.
cscript %SYSTEMROOT%\System32\slmgr.vbs -upk > nul
echo.
echo La licence Windows a ete desinstaller
echo.
pause
goto menu

:winLicen
cls
echo.
echo Entrez votre cle d'activation sous le format XXXXX-XXXXX-XXXXX-XXXXX-XXXXX
echo.
set /p cle="Entrez votre choix: ")
echo.
echo Activation en cours....
cscript %SYSTEMROOT%\System32\slmgr.vbs /ipk %cle% > nul
cscript %SYSTEMROOT%\System32\slmgr.vbs -dli
echo.
echo La cle de licence a ete installe
echo.
pause
goto menu

:stat
cls
echo.
cscript %SYSTEMROOT%\System32\slmgr.vbs -dli
echo.
pause
goto menu

:exit
exit
