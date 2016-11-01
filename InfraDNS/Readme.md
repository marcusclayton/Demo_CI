#Build.ps1
(dot source : invoke-testfailure)
clean
generateenvironmentfiles
installmodules
scriptanalysis
unittests (invoke-testfailure if any pester failures occur)
compileconfigs