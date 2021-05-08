---
title: Logs de diagnóstico
description: Logs que podem ser coletados de dispositivos durante a solução de problemas e como eles são armazenados
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52272883"
---
# <a name="diagnostic-logs"></a>Logs de diagnóstico

Quando solucionarmos um problema em um dispositivo gerenciado pela Área de Trabalho Gerenciada da Microsoft, se um relatado ou identificado pelo nosso serviço, talvez seja preciso coletar certos logs de diagnóstico do dispositivo sem intervenção do usuário. Não coletamos conteúdo ou informações gerados pelo usuário de diretórios de usuários. Coletamos apenas dados de diagnóstico e log que dizem respeito à saúde e ao status do dispositivo.

Armazenamos todos os logs coletados por 28 dias e os excluímos. Processemos todos os logs coletados de um dispositivo seguindo nossos padrões [de tratamento de dados.](privacy-personal-data.md)

## <a name="data-collected"></a>Dados coletados

Essa lista inclui todas as pastas, logs de eventos, executáveis ou locais do registro dos Área de Trabalho Gerenciada da Microsoft que podem coletar logs de diagnóstico. Os dados reais coletados serão um subconjunto dessa lista e dependerão do problema identificado.

### <a name="registry-keys"></a>Chaves de registro

- Serviços HKLM \\ SYSTEM \\ CurrentControlSet \\
- HKLM \\ SOFTWARE \\ Microsoft \\ Surface
- Políticas de SOFTWARE HKLM \\ \\ Microsoft Windows \\ \\ \\ WindowsUpdate
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ MUI \\ UILanguages
- Políticas de software HKLM \\ \\ Microsoft \\ \\ WindowsStore
- Software HKLM \\ \\ Microsoft Windows \\ \\ \\ WindowsStore WindowsUpdate do CurrentVersion \\
- Software HKLM \\ \\ Microsoft Windows NT \\ \\ CurrentVersion
- Software HKLM \\ \\ Microsoft Windows NT \\ \\ CurrentVersion
- SOFTWARE HKLM \\ \\ Microsoft Windows \\ \\ CurrentVersion \\ AppModel
- Firmware do controle HKLM \\ SYSTEM \\ CurrentControlSetResources \\ \\
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate
- Software HKLM \\ \\ Microsoft Windows \\ \\ CurrentVersion \\ Appx
- Software HKLM \\ \\ Microsoft Windows NT \\ \\ CurrentVersion \\ Superfetch
- Instalação do SISTEMA HKLM \\ \\
- HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension
- HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot
- Software HKLM \\ Microsoft Windows Proteção Avançada contra \\ \\ Ameaças
- Software HKLM \\ Microsoft \\ Windows \\ \\ LogonUI de \\ \\ autenticação CurrentVersion
- SOFTWARE HKLM \\ \\ Microsoft Windows Internet \\ \\ CurrentVersion \\ Configurações
- Software HKLM \\ \\ Microsoft Windows \\ \\ \\ Desinstalação do CurrentVersion
- Políticas de software HKLM \\ \\
- Políticas de SOFTWARE HKLM \\ \\ Microsoft \\ \\ Cryptography Configuration \\ \\ SSL
- Políticas de SOFTWARE HKLM \\ Microsoft Windows Proteção Avançada contra \\ \\ \\ Ameaças
- SOFTWARE HKLM \\ \\ WOW6432Node \\ Microsoft \\ Windows \\ \\ Desinstalação do CurrentVersion
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL

### <a name="commands"></a>Comandos

- %programfiles% \\ windows defendermpcmdrun.exe \\ -GetFiles
- %windir% \\ system32 \\certutil.exe -store
- %windir% \\ system32 \\certutil.exe -store -user my
- %windir% \\ system32 \\Dsregcmd.exe /status
- %windir% \\ system32 \\ipconfig.exe /all
- %windir% \\ system32 \\ipconfig.exe /displaydns
- %windir% \\ system32 \\mdmdiagnosticstool.exe
- %windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log
- %windir% \\ system32 \\netsh.exe advfirewall mostram allprofiles
- %windir% \\ system32 \\netsh.exe advfirewall mostrar global
- %windir% \\ system32 \\netsh.exe lan mostrar perfis
- %windir% \\ system32 \\netsh.exe winhttp show proxy
- %windir% \\ system32 \\netsh.exe wlan mostrar perfis
- %windir% \\ system32 \\netsh.exe wlan show wlanreport
- %windir% \\ system32 \\ping.exe -n 50 localhost
- %windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html
- %windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html
- bitsadmin /list /allusers /verbose
- fltMC.exe
- bcdedit /enum all /v
- manage-bde -protectors -get
- Windows PowerShell comandos:
    - Get-appxpackage -allusers
    - Get-appxpackage -packagetype bundle
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject -Class win32 \_ product
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32 \_ PnPSignedDriver

### <a name="event-logs"></a>Logs de eventos

- Aplicativo
- Microsoft-Windows-AppLocker/EXE e DLL
- Microsoft-Windows-AppLocker/MSI e Script
- Microsoft-Windows-AppLocker/Packaged app-Deployment
- Microsoft-Windows-AppLocker/Packaged app-Execution
- Gerenciamento do Microsoft-Windows-Bitlocker/Bitlocker
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operacional
- Configurar
- Sistema

### <a name="files"></a>Arquivos

- %ProgramData% \\ \\ Coletores de DiagnosticLogCSP da Microsoft \\ \\ \* .etl
- %ProgramData% \\ Logs do Microsoft \\ IntuneManagementExtension \\ \\ \* .\*
- %ProgramData% \\ Microsoft Windows Defender Suporte \\ \\ \\MpSupportFiles.cab
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport \\wlan-report-latest.html
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html
- %windir% \\ ccm \\ logs \* .log
- %windir% \\ ccmsetup \\ logs \* .log
- %windir% \\ registra \\ CBS \\ cbs.log
- %windir% \\ logs \\ measuredboot \* .\*
- %windir% \\ Logs \\ WindowsUpdate \* .etl
- %windir% \\ inf \\ \* .log
- Sessões de manutenção %windir% \\ \\ActionList.xml \\
- Sessões de manutenção %windir% \\ \\Sessions.xml \\
- %windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log
- %windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb
- %windir% \\ logs \\ dism \\ dism.log
- %SystemRoot% \\ Logs \\ winevt do System32 \\\\
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ \\ \* skylib .blog
- %appdata% \\ Microsoft \\ Teams \\ media-stack \\ \* .etl
- %appdata% \\ Microsoft \\ Teams \\logs.txt
- %windir% \\ Windows \\ System32 \\ winevt \\ \* .\*