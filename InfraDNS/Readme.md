#Build.ps1
(dot source : invoke-testfailure)
clean
generateenvironmentfiles
installmodules
scriptanalysis
unittests (invoke-testfailure if any pester failures occur)
compileconfigs

#Original IPs
ARecords            = @{'TFSSrv1'= '10.0.0.10';'Client'='10.0.0.15';'BuildAgent'='10.0.0.30';'TestAgent1'='10.0.0.40';'TestAgent2'='10.0.0.50'};

#My IPs
ARecords            = @{'TFSSrv1'= '10.4.0.104';'Client'='10.4.0.103';'BuildAgent'='10.4.0.100';'TestAgent1'='10.4.0.101';'TestAgent2'='10.4.0.102'};
#not building a TFS server, using VSTS instead
#zone and domain name will also changed from contoso