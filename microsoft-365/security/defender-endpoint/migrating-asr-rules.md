---
title: Migrando de um HIPS de terceiros para regras ASR
description: Descreve como abordar uma migração de uma solução HIPS (Sistema de Prevenção contra Intrusão de Host) de terceiros para regras ASR.
keywords: Regras de redução de superfície de ataque, asr, regras de asr, quadris, sistema de prevenção contra invasões de host, regras de proteção, antiexploit, antiexploit, exploit, prevenção de infecção, Microsoft Defender para Ponto de Extremidade
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: fd7c6a217c1bc1ce3b278afb911988b94a6951e0
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062152"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>Migrando de um HIPS de terceiros para regras ASR

Este artigo ajuda você a mapear regras comuns para o Microsoft Defender para Ponto de Extremidade.

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>Cenários ao migrar de um produto HIPS de terceiros para regras ASR

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Bloquear a criação de arquivos específicos e chaves do Registro

- **Aplica-se a**- Todos os processos
- **Operação**- Criação de Arquivo
- Exemplos de **Arquivos/Pastas, Chaves/Valores do Registro, Processos, Serviços**- *.zepto, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab
- **Regras de Redução de Superfície de** Ataque - as regras asR bloqueiam as técnicas de ataque e não os Indicadores de Comprometimento (IOC). O bloqueio de uma extensão de arquivo específica nem sempre é útil, pois não impede que um dispositivo seja comprometido. Ele apenas impede parcialmente um ataque até que os invasores criem um novo tipo de extensão para a carga.
- **Outros recursos recomendados**- Ter o Microsoft Defender AV habilitado, juntamente com a Análise de Comportamento e Proteção na Nuvem é altamente recomendado. Recomendamos que você use outra prevenção, como a regra ASR "Usar proteção avançada contra ransomware". Isso fornece um nível maior de proteção contra ataques de ransomware. Além disso, muitas dessas chaves do Registro são monitoradas pelo Microsoft Defender para Ponto de Extremidade, como técnicas ASEP, que dispararão alertas específicos. As chaves do Registro usadas exigem um mínimo de privilégios de Administrador Local ou Instalador Confiável podem ser modificados. É recomendável usar um ambiente bloqueado, com contas ou direitos administrativos mínimos. Outras configurações do sistema podem ser habilitadas, incluindo "Desabilitar SeDebug para funções não necessárias" que fazem parte de nossas recomendações de segurança mais amplas.

### <a name="block-creation-of-specific-files-and-registry-keys"></a>Bloquear a criação de arquivos específicos e chaves do Registro

- **Aplica-se a**- Todos os Processos
- **Processos**- N/A
- **Operação**- Modificações do Registro
- **Exemplos de Arquivos/Pastas, Chaves/Valores do Registro, Processos, Serviços** -  *\Software*,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options*\Depurador, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcess
- **Regras de Redução de Superfície de** Ataque - as regras asR bloqueiam as técnicas de ataque e não os Indicadores de Comprometimento (IOC). O bloqueio de uma extensão de arquivo específica nem sempre é útil, pois não impede que um dispositivo seja comprometido. Ele apenas impede parcialmente um ataque até que os invasores criem um novo tipo de extensão para a carga.
- **Outros recursos recomendados**- Ter o Microsoft Defender AV habilitado, juntamente com a Análise de Comportamento e Proteção na Nuvem é altamente recomendado. Recomendamos que você use prevenção adicional, como a regra ASR "Usar proteção avançada contra ransomware". Isso fornece um nível maior de proteção contra ataques de ransomware. Além disso, várias dessas chaves do Registro são monitoradas pelo Microsoft Defender para Ponto de Extremidade, como técnicas ASEP, que dispararão alertas específicos. Além disso, as chaves do Registro usadas exigem um mínimo de privilégios de Administrador Local ou Instalador Confiável podem ser modificados. É recomendável usar um ambiente bloqueado, com contas ou direitos administrativos mínimos. Outras configurações do sistema podem ser habilitadas, incluindo "Desabilitar SeDebug para funções não necessárias" que fazem parte de nossas recomendações de segurança mais amplas.

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>Impedir a execução de programas não sólidos de unidades removíveis

- **Aplica-se a**- Programas NãoTrudos do USB
- **Processos**- *
- **Operação**- Execução do Processo
- **Exemplos de Arquivos/Pastas, Chaves/Valores do Registro, Processos, Serviços:-*
- Regras de Redução de Superfície de Ataque **-** as regras asR têm uma regra interno para impedir o lançamento de programas não assinados e não assinados de unidades removíveis: "Bloquear processos não assinados e não assinados executados a partir do USB", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4".
- **Outros recursos recomendados**- Explore controles adicionais para dispositivos USB e outras mídias removíveis usando o Microsoft Defender para Ponto de Extremidade: como controlar dispositivos USB e outras [mídias removíveis](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)usando o Microsoft Defender para Ponto de Extremidade .

### <a name="block-mshta-from-launching-certain-child-processes"></a>Impedir Mshta de iniciar determinados processos filho

- **Aplica-se a**- Mshta
- **Processos**- mshta.exe
- **Operação**- Execução do Processo
- **Exemplos de Arquivos/Pastas, Chaves/Valores do Registro, Processos, Serviços**- powershell.exe, cmd.exe, regsvr32.exe
- **Regras de Redução de** Superfície de Ataque - as regras ASR não contêm nenhuma regra específica para impedir processos filho de "mshta.exe". Esse controle está dentro do limite de Exploit Protection ou Windows Defender Application Control.
- **Outros recursos recomendados**- Habilitar Windows Defender Controle de Aplicativos para impedir mshta.exe de ser executado completamente. Se sua organização exigir "mshta.exe" para aplicativos de linha de negócios, configure uma regra específica Windows Defender Proteção de Exploração, para impedir mshta.exe iniciar processos filho.

### <a name="block-outlook-from-launching-child-processes"></a>Impedir Outlook iniciar processos filho

- **Aplica-se a**- Outlook
- **Processos**- outlook.exe
- **Operação**- Execução do Processo
- **Exemplos de Arquivos/Pastas, Chaves/Valores do Registro, Processos, Serviços**- powershell.exe
- Regras de Redução de Superfície de Ataque **-** as regras asR têm uma regra interna para impedir que aplicativos de comunicação do Office (Outlook, Skype e Teams) de iniciar processos filho: "Impedir que o aplicativo de comunicação Office cria processos filho", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".
- **Outros recursos recomendados**- Recomendamos habilizar o modo de idioma restrito do PowerShell para minimizar a superfície de ataque do PowerShell.


### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Impedir Office Aplicativos de iniciar processos filho e de criar conteúdo executável

- **Aplica-se a**- Office  
- **Processos**- winword.exe, powerpnt.exe, excel.exe
- **Operação**- Execução do Processo
- **Exemplos de Arquivos/Pastas, Chaves/Valores do Registro, Processos, Serviços**- powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe
- **Regras** de Redução de Superfície de Ataque - as regras asR têm uma regra interno para impedir que aplicativos Office iniciam processos filho: "Bloquear todos os aplicativos Office de criar processos filho", GUID "D4F940AB-401B-4EFC-AADC-AD5F3C50688A".
- **Outros recursos recomendados**- N/A
    
### <a name="block-office-apps-from-launching-child-processes-and-from-creating-executable-content"></a>Impedir Office Aplicativos de iniciar processos filho e de criar conteúdo executável

- **Aplica-se a**- Office
- **Processos**- winword.exe, powerpnt.exe, excel.exe
- **Operação**- Criação de Arquivo
- **Exemplos de Arquivos/Pastas, Chaves/Valores do Registro, Processos,** Serviços -*C:\Users \AppData **.exe, C:\ProgramData**.exe, C:\ProgramData**.com, C:\Users* AppData\Local\Temp **.com, C:\Users*\Downloads**.exe, C:\Users *\AppData **.scf, C:\ProgramData**.scf, C:\Users\Public*.exe, C:\Users*\Desktop***.exe
- **Regras de Redução de Superfície de** Ataque - N/A.

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Impedir o Wscript de ler determinados tipos de arquivos

- **Aplica-se a**- Wscript
- **Processos**- wscript.exe
- **Operação**- Leitura de arquivo
- **Exemplos de Arquivos/Pastas, Chaves/Valores do Registro, Processos,** Serviços - C:\Users *\AppData**.js, C:\Users*\Downloads**.js
- **Regras de Redução** de Superfície de Ataque - Devido a problemas de confiabilidade e desempenho, as regras asR não têm a capacidade de impedir que um processo específico leia um determinado tipo de arquivo de script. Temos uma regra para evitar vetores de ataque que podem se originar desses cenários. O nome da regra é "Bloquear JavaScript ou VBScript de iniciar conteúdo executável baixado" (GUID "D3E037E1-3EB8-44C8-A917-57927947596D") e "Bloquear a execução de scripts potencialmente ofuscados" (GUID " 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC").
- Outros recursos recomendados **-** Embora haja regras ASR específicas que reduzam determinados vetores de ataque nesses cenários, é importante mencionar que a AV é capaz, por padrão, de inspecionar scripts (PowerShell, host de script do Windows, JavaScript, VBScript e muito mais) em tempo real, por meio da Interface de Verificação antimalware (AMSI). Mais informações estão disponíveis aqui: [Interface de Verificação antimalware (AMSI)](/windows/win32/amsi/antimalware-scan-interface-portal).

### <a name="block-launch-of-child-processes"></a>Bloquear o início de processos filho

- **Aplica-se a**- Adobe Acrobat
- **Processos**- AcroRd32.exe, Acrobat.exe
- **Operação**- Execução do Processo
- **Exemplos de Arquivos/Pastas, Chaves/Valores do Registro, Processos, Serviços**- cmd.exe, powershell.exe, wscript.exe
- **Regras de Redução de Superfície de** Ataque - as regras asr permitem bloquear o Adobe Reader de iniciar processos filho. O nome da regra é "Bloquear o Adobe Reader de criar processos filho", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c".
- **Outros recursos recomendados**- N/A


### <a name="block-download-or-creation-of-executable-content"></a>Bloquear o download ou a criação de conteúdo executável

- **Aplica-se a**- CertUtil: Bloquear o download ou a criação de executáveis 
- **Processos**- certutil.exe
- **Operação**- Criação de Arquivo
- **Exemplos de Arquivos/Pastas, Chaves/Valores do Registro, Processos, Serviços**- *.exe
- **Regras de Redução de** Superfície de Ataque - as regras asR não suportam esses cenários porque fazem parte da proteção Microsoft Defender Antivírus de ataque.
- **Outros recursos recomendados**- o Microsoft Defender AV impede que CertUtil cria ou baixa conteúdo executável.


### <a name="block-processes-from-stopping-critical-system-components"></a>Impedir que os processos parem componentes críticos do sistema

- **Aplica-se a**- Todos os Processos
- **Processos**- *
- **Operação**- Término do Processo
- Exemplos de **Arquivos/Pastas, Chaves/Valores** do Registro, Processos, Serviços - MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe*, services.exe, csrss.exe, smss.exe, wininit.exe e muito mais.
- **Regras de Redução** de Superfície de Ataque - as regras asR não suportam esses cenários porque são protegidas com Windows 10 proteções de segurança internas.
- **Outros recursos recomendados**- ELAM (AntiMalware de Início Antecipado), PPL (Protection Process Light), PPL AntiMalware Light e System Guard.

### <a name="block-specific-launch-process-attempt"></a>Bloquear tentativa de processo de início específico

- **Aplica-se a**- Processos Específicos
- **Processos**- "Nomear seu Processo"
- **Operação**- Execução do Processo
- **Exemplos de Arquivos/Pastas, Chaves/Valores do Registro, Processos, Serviços**- tor.exe, bittorrent.exe, cmd.exe, powershell.exe e muito mais
- **Regras de Redução de** Superfície de Ataque - Em geral, as regras asR não são projetadas para funcionar como gerenciador de aplicativos.
- **Outros recursos recomendados**- Para impedir que os usuários iniciam processos ou programas específicos, é recomendável usar Windows Defender Controle de Aplicativos. Os indicadores de Arquivo e Certificado do Microsoft Defender para Endpoint podem ser usados em um cenário de Resposta a Incidentes (não deve ser visto como um mecanismo de controle de aplicativo).
    
### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>Bloquear alterações não autorizadas para Microsoft Defender Antivírus configurações

- **Aplica-se a**- Todos os Processos
- **Processos**- *
- **Operação**- Modificações do Registro
- Exemplos de **Arquivos/Pastas, Chaves/Valores do Registro, Processos,** Serviços - HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring e assim por diante.
- **Regras de Redução de** Superfície de Ataque - as regras asR não abrangem esses cenários porque fazem parte da proteção do Microsoft Defender para Ponto de Extremidade.
- Outros recursos recomendados **-** a Proteção contra Adulteração (aceitação, gerenciada do Intune) impede alterações não autorizadas em DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring e DisableIOAVProtection registry keys (e muito mais).

Confira também

- [Perguntas frequentes sobre a redução da superfície de ataque](attack-surface-reduction-faq.yml)
- [Habilitar regras da redução da superfície de ataque](enable-attack-surface-reduction.md)
- [Avaliar as regras da redução da superfície de ataque](evaluate-attack-surface-reduction.md)
