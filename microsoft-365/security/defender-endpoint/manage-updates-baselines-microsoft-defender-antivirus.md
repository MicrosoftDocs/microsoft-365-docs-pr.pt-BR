---
title: Gerenciar Microsoft Defender Antivírus e aplicar linhas de base
description: Gerenciar como Microsoft Defender Antivírus recebe atualizações de produtos e proteção.
keywords: atualizações, linhas de base de segurança, proteção, agendar atualizações, forçar atualizações, atualizações móveis, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 06/04/2021
ms.openlocfilehash: 264a3b7a4a24c446048d6cfc6863f1ae9765566f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789178"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-apply-baselines"></a>Gerenciar Microsoft Defender Antivírus e aplicar linhas de base

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender Antivírus

Há dois tipos de atualizações relacionadas à Microsoft Defender Antivírus atualizadas:

- Atualizações de inteligência de segurança
- Atualizações de produtos

> [!IMPORTANT]
> Manter Microsoft Defender Antivírus atualizado é fundamental para garantir que seus dispositivos tenham a tecnologia e os recursos mais recentes necessários para proteger contra novas técnicas de malware e ataque.
> 
> Certifique-se de atualizar sua proteção antivírus mesmo que Microsoft Defender Antivírus está sendo executado no [modo passivo](./microsoft-defender-antivirus-compatibility.md).
> 
> Para ver o mecanismo, a plataforma e a data de assinatura mais atuais, visite as atualizações de inteligência de segurança para Microsoft Defender Antivírus e outros [antimalware](https://www.microsoft.com/en-us/wdsi/defenderupdates)da Microsoft.

## <a name="security-intelligence-updates"></a>Atualizações de inteligência de segurança

Microsoft Defender Antivírus usa [proteção](cloud-protection-microsoft-defender-antivirus.md) entregue na nuvem (também chamada de Serviço de Proteção Avançada da Microsoft ou MAPS) e baixa periodicamente atualizações de inteligência de segurança para fornecer proteção.

> [!NOTE]
> As atualizações são lançadas nos números KB abaixo:  
> - Microsoft Defender Antivírus: KB2267602  
> - System Center Endpoint Protection: KB2461484

A proteção entregue na nuvem está sempre ativa e requer uma conexão ativa com a Internet para funcionar. As atualizações de inteligência de segurança ocorrem em uma cadência agendada (configurável por meio da política). Para obter mais informações, [consulte Use Microsoft cloud-provided protection in Microsoft Defender Antivírus](cloud-protection-microsoft-defender-antivirus.md). 

Para ver uma lista de atualizações recentes de inteligência de segurança, consulte Atualizações de inteligência de segurança para Microsoft Defender Antivírus [e outros antimalware da Microsoft.](https://www.microsoft.com/en-us/wdsi/defenderupdates)

As atualizações do mecanismo são incluídas com atualizações de inteligência de segurança e são lançadas em uma cadência mensal.

## <a name="product-updates"></a>Atualizações de produtos

Microsoft Defender Antivírus exige atualizações mensais [(KB4052623)](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform) *(conhecidas* como atualizações de plataforma) e receberá atualizações de recursos principais juntamente com Windows 10 versões.

Você pode gerenciar a distribuição de atualizações por meio de um dos seguintes métodos: 

- [Windows Serviço de Atualização do Servidor (WSUS)](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/sum/understand/software-updates-introduction)
- O método comum que você usa para implantar a Microsoft e Windows atualizações para pontos de extremidade em sua rede.

Para obter mais informações, consulte [Manage the sources for Microsoft Defender Antivírus protection updates](/mem/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus).

> [!NOTE]
> As atualizações mensais são lançadas em fases, resultando em vários pacotes visíveis em seus [Serviços de Atualização do Servidor de Janelas.](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)

## <a name="monthly-platform-and-engine-versions"></a>Versões mensais de plataforma e mecanismo

Para obter informações sobre como atualizar ou instalar a atualização da plataforma, consulte [Update for Windows Defender antimalware platform](https://support.microsoft.com/help/4052623/update-for-windows-defender-antimalware-platform).

Todas as nossas atualizações contêm 
- melhorias de desempenho;
- melhorias de capacidade de serviço; e 
- melhorias de integração (Cloud, Microsoft 365 Defender).
<br/>
<details>
<summary> Maio-2021 (plataforma: 4.18.2105.4 | Mecanismo: 1.1.18200.4)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.341.8.0**  
&ensp;Lançado: **4 de junho de 2021**  
&ensp;Plataforma: **4.18.2105.4**  
&ensp;Mecanismo: **1.1.18200.4**  
&ensp;Fase de suporte: **Segurança e Atualizações Críticas**
    
### <a name="whats-new"></a>Novidades
- Melhorias no monitoramento de comportamento 

### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details><details>
<summary> Abril-2021 (Plataforma: 4.18.2104.14 | Mecanismo: 1.1.18100.5)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.337.2.0**  
&ensp;Lançado: **1º de abril de 2021**  
&ensp;Plataforma: **4.18.2104.14**  
&ensp;Mecanismo: **1.1.18100.5**  
&ensp;Fase de suporte: **Segurança e Atualizações Críticas**
    
### <a name="whats-new"></a>Novidades
- Lógica adicional de monitoramento de comportamento
- Detecção aprimorada do keylogger do modo kernel

### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details><details>
<summary> Março-2021 (Plataforma: 4.18.2103.7 | Mecanismo: 1.1.18000.5)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.335.36.0**  
&ensp;Lançado: **1º de abril de 2021**  
&ensp;Plataforma: **4.18.2103.7**  
&ensp;Mecanismo: **1.1.18000.5**  
&ensp;Fase de suporte: **Segurança e Atualizações Críticas**
    
### <a name="whats-new"></a>Novidades

- Melhoria no mecanismo de Monitoramento de Comportamento 
- Mitigações de ataques de força bruta de rede expandida 
- Geração adicional de eventos de tentativa de adulteração com falha quando [a Proteção contra Adulteração](prevent-changes-to-security-settings-with-tamper-protection.md) está habilitada

### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details>

### <a name="previous-version-updates-technical-upgrade-support-only"></a>Atualizações de versão anterior: Suporte técnico somente a atualização

Depois que uma nova versão de pacote é lançada, o suporte para as duas versões anteriores é reduzido apenas ao suporte técnico. Versões anteriores às listadas nesta seção são fornecidas apenas para suporte técnico de atualização. 
<br/><br/>
<details>
<summary> Fevereiro-2021 (plataforma: 4.18.2102.3 | Mecanismo: 1.1.17900.7)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.333.7.0**  
&ensp;Lançado: **9 de março de 2021**  
&ensp;Plataforma: **4.18.2102.3**  
&ensp;Mecanismo: **1.1.17900.7**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
    
### <a name="whats-new"></a>Novidades

- Recuperação aprimorada do serviço por meio [da proteção contra violações](prevent-changes-to-security-settings-with-tamper-protection.md)
- Estender escopo de proteção contra violações

### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details><details>
<summary> Janeiro-2021 (Plataforma: 4.18.2101.9 | Mecanismo: 1.1.17800.5)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**  
&ensp;Lançado: **2 de fevereiro de 2021**  
&ensp;Plataforma: **4.18.2101.9**  
&ensp;Mecanismo: **1.1.17800.5**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
    
### <a name="whats-new"></a>Novidades

- Melhorias na detecção de exploração de shellcode
- Maior visibilidade para tentativas de roubo de credenciais
- Melhorias nos recursos anti-amperes em serviços Microsoft Defender Antivírus serviços
- Suporte aprimorado para ARM emulação x64
- Correção: EDR a notificação de bloqueio permanece no histórico de ameaças depois que a proteção em tempo real realizou a detecção inicial

### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details><details>
<summary> Novembro-2020 (Plataforma: 4.18.2011.6 | Mecanismo: 1.1.17700.4)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.327.1854.0**  
&ensp;Lançado: **03 de dezembro de 2020**  
&ensp;Plataforma: **4.18.2011.6**  
&ensp;Mecanismo: **1.1.17700.4**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
    
### <a name="whats-new"></a>Novidades

- Registro em log de suporte ao status [do SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) aprimorado

### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details><details>
<summary> Outubro-2020 (Plataforma: 4.18.2010.7 | Mecanismo: 1.1.17600.5)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.327.7.0**  
&ensp;Lançado: **29 de outubro de 2020**  
&ensp;Plataforma: **4.18.2010.7**  
&ensp;Mecanismo: **1.1.17600.5**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
    
### <a name="whats-new"></a>Novidades

- Novas descrições para categorias de ameaças especiais
- Recursos de emulação aprimorados
- Recursos de permitir/bloquear endereço de host aprimorados
- Nova opção no CSP do Defender para Ignorar a mesclação de exclusões de usuários locais

### <a name="known-issues"></a>Problemas Conhecidos

Nenhum problema conhecido  
<br/>
</details><details>
<summary> Setembro-2020 (Plataforma: 4.18.2009.7 | Mecanismo: 1.1.17500.4)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.325.10.0**  
&ensp;Lançado: **01 de outubro de 2020**  
&ensp;Plataforma: **4.18.2009.7**  
&ensp;Mecanismo: **1.1.17500.4**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
    
### <a name="whats-new"></a>Novidades

- Permissões de administrador são necessárias para restaurar arquivos em quarentena
- Eventos formatados xml agora são suportados
- Suporte a CSP para ignorar mesclações de exclusão
- Novas interfaces de gerenciamento para:
   - Inspeção UDP
   - Proteção de Rede no Server 2019
   - Exclusões de endereço IP para Proteção de Rede
- Visibilidade aprimorada nas medições do TPM
- Verificação aprimorada Office módulo VBA

### <a name="known-issues"></a>Problemas Conhecidos

Nenhum problema conhecido  
<br/>
</details>
<details>
<summary> Agosto-2020 (plataforma: 4.18.2008.9 | Mecanismo: 1.1.17400.5)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.323.9.0**  
&ensp;Lançado: **27 de agosto de 2020**  
&ensp;Plataforma: **4.18.2008.9**  
&ensp;Mecanismo: **1.1.17400.5**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**

### <a name="whats-new"></a>Novidades

- Adicionar mais eventos de telemetria
- Telemetria de eventos de verificação aprimorada
- Monitoramento de comportamento aprimorado para verificações de memória
- Verificação de fluxos de macros aprimorados
- Adicionado `AMRunningMode` ao cmdlet Get-MpComputerStatus PowerShell
- [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) é ignorado. Microsoft Defender Antivírus se desliga automaticamente quando detecta outro programa antivírus.


### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details>

<details>
<summary> Julho-2020 (Plataforma: 4.18.2007.8 | Mecanismo: 1.1.17300.4)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.321.30.0**  
&ensp;Lançado: **28 de julho de 2020**  
&ensp;Plataforma: **4.18.2007.8**  
&ensp;Mecanismo: **1.1.17300.4**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
    
### <a name="whats-new"></a>Novidades

- Telemetria aprimorada para BITS
- Validação aprimorada de certificado de assinatura de código Authenticode

### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details>

<details>
<summary> Junho-2020 (Plataforma: 4.18.2006.10 | Mecanismo: 1.1.17200.2)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.319.20.0**  
&ensp;Lançado: **22 de junho de 2020**  
&ensp;Plataforma: **4.18.2006.10**  
&ensp;Mecanismo: **1.1.17200.2**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
    
### <a name="whats-new"></a>Novidades

- Possibilidade de especificar o [local dos logs de suporte](./collect-diagnostic-data.md)
- Ignorar a verificação de captura agressiva no modo Passivo.
- Permitir que o Defender atualize em conexões com metros
- Ajuste de desempenho fixo quando o cache está desabilitado 
- Consulta de registro fixa 
- Randomização de tempo de verificação fixa no ADMX

### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details>

<details>
<summary> Maio-2020 (plataforma: 4.18.2005.4 | Mecanismo: 1.1.17100.2)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.317.20.0**  
&ensp;Lançado: **26 de maio de 2020**  
&ensp;Plataforma: **4.18.2005.4**  
&ensp;Mecanismo: **1.1.17100.2**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
    
### <a name="whats-new"></a>Novidades

- Registro em log aprimorado para eventos de verificação
- Melhor tratamento de falhas no modo de usuário.
- Rastreamento de eventos adicionado para proteção contra adulteração
- Envio de amostra AMSI corrigido
- Bloqueio fixo da nuvem AMSI
- Log de instalação de atualização de segurança fixa

### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details>

<details>
<summary> Abril-2020 (Plataforma: 4.18.2004.6 | Mecanismo: 1.1.17000.2)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.315.12.0**  
&ensp;Lançado: **30 de abril de 2020**  
&ensp;Plataforma: **4.18.2004.6**  
&ensp;Mecanismo: **1.1.17000.2**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
    
### <a name="whats-new"></a>Novidades
- Melhorias do WDfilter
- Adicionar mais dados de evento acionáveis para atacar eventos de detecção de redução de superfície
- Informações de versão fixas em dados de diagnóstico e WMI
- Versão da plataforma incorreta corrigida na interface do usuário após a atualização da plataforma
- Intel de URL dinâmica para proteção contra ameaças sem arquivo
- Recurso de verificação UEFI
- Estender o log para atualizações

### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido  
<br/>
</details>

<details>
<summary> Março-2020 (Plataforma: 4.18.2003.8 | Mecanismo: 1.1.16900.2)</summary>

&ensp;Versão de atualização de inteligência de segurança: **1.313.8.0**  
&ensp;Lançado: **24 de março de 2020**  
&ensp;Plataforma: **4.18.2003.8**  
&ensp;Mecanismo: **1.1.16900.4**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
    
### <a name="whats-new"></a>Novidades

- Opção de throttling de CPU adicionada ao [MpCmdRun](./command-line-arguments-microsoft-defender-antivirus.md)
- Melhorar a funcionalidade de diagnóstico
- reduzir o tempo de tempo de inteligência de segurança (5 minutos)
- Estender a funcionalidade de log interno do mecanismo AMSI
- Melhorar a notificação para bloqueio de processos
   
### <a name="known-issues"></a>Problemas Conhecidos
[**Fixo**] Microsoft Defender Antivírus está ignorando arquivos ao executar uma verificação.

<br/>
</details>

<details>

<summary> Fevereiro-2020 (Plataforma: - | Mecanismo: 1.1.16800.2)</summary>
  

&ensp;Versão de atualização de inteligência de segurança: **1.311.4.0**   
&ensp;Lançado: **25 de fevereiro de 2020**  
&ensp;Plataforma/Cliente: **-**  
&ensp;Mecanismo: **1.1.16800.2**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
     
### <a name="whats-new"></a>Novidades

  
### <a name="known-issues"></a>Problemas Conhecidos
Nenhum problema conhecido
<br/>
</details>

<details>
<summary> Janeiro-2020 (Plataforma: 4.18.2001.10 | Mecanismo: 1.1.16700.2)</summary>
  

Versão de atualização de inteligência de segurança: **1.309.32.0**  
Lançado: **30 de janeiro de 2020**  
Plataforma/Cliente: **4.18.2001.10**  
Mecanismo: **1.1.16700.2**  
&ensp;Fase de suporte: **Suporte técnico de atualização (somente)**
     
### <a name="whats-new"></a>Novidades

- BSOD fixo no WS2016 com Exchange
- Atualizações da plataforma de suporte quando o TMP é redirecionado para o caminho da rede
- As versões de plataforma e mecanismo são [adicionadas ao WDSI](https://www.microsoft.com/en-us/wdsi/defenderupdates) <!-- The preceding URL must include "/en-us" -->
- estender a atualização de assinatura de emergência para [o modo passivo](./microsoft-defender-antivirus-compatibility.md)
- Corrigir trava 4.18.1911.3
   
### <a name="known-issues"></a>Problemas Conhecidos

[**Fixo**] dispositivos [que](/windows-hardware/design/device-experiences/modern-standby) usam o modo de espera moderno podem ter uma trava com o driver de filtro Windows Defender que resulta em uma lacuna de proteção.  Os máquinas afetados aparecem para o cliente como não atualizados para a plataforma antimalware mais recente.  
<br/>
> [!IMPORTANT]
> Esta atualização é:
> - necessário por dispositivos RS1 que executam a versão inferior da plataforma para dar suporte ao SHA2;
> - tem um sinalizador de reinicialização para sistemas que têm problemas de suspensão;
> - é re-lançado em abril de 2020 e não será superada por atualizações mais novas para manter a disponibilidade futura;  
> - é categorizado como uma atualização devido ao requisito de reinicialização; e
> - só será oferecido com o [Windows Update](https://support.microsoft.com/help/4027667/windows-10-update).
<br/>
</details>

<details>
<summary> Novembro-2019 (plataforma: 4.18.1911.3 | Mecanismo: 1.1.16600.7)</summary>

Versão de atualização de inteligência de segurança: **1.307.13.0**  
Lançado: **7 de dezembro de 2019**  
Plataforma: **4.18.1911.3**  
Mecanismo: **1.1.17000.7**  
Fase de suporte: **sem suporte**  
     
### <a name="whats-new"></a>Novidades

- Nível de rastreamento De MpCmdRun fixo
- Informações de versão fixas do WDFilter
- Melhorar notificações (PUA)
- adicionar logs MRT para dar suporte a arquivos
   
### <a name="known-issues"></a>Problemas Conhecidos
Quando essa atualização é instalada, o dispositivo precisa do pacote de salto 4.10.2001.10 para poder atualizar para a versão mais recente da plataforma.
<br/>
</details>


## <a name="microsoft-defender-antivirus-platform-support"></a>Microsoft Defender Antivírus plataforma
As atualizações de plataforma e mecanismo são fornecidas em uma cadência mensal. Para ter suporte total, mantenha-se atualizado com as atualizações mais recentes da plataforma. Nossa estrutura de suporte é dinâmica, evoluindo em duas fases, dependendo da disponibilidade da versão mais recente da plataforma:

- Fase de manutenção de Atualizações **Críticas** e Segurança - Ao executar a versão mais recente da plataforma, você estará qualificado para receber atualizações de segurança e críticas para a plataforma anti-malware.
 
- Fase de Suporte Técnico **(Somente)** - Depois que uma nova versão da plataforma for lançada, o suporte para versões mais antigas (N-2) será redução apenas para suporte técnico. As versões da plataforma anteriores ao N-2 não serão mais suportadas.*

\*O suporte técnico continuará a ser fornecido para atualizações da versão Windows 10 versão do Windows 10 (consulte Versão da plataforma incluída com Windows 10 [versões](#platform-version-included-with-windows-10-releases)) para a versão mais recente da plataforma.

Durante a fase de suporte técnico (somente), incidentes de suporte comercialmente razoáveis serão fornecidos por meio do Serviço de Atendimento ao Cliente da Microsoft & Suporte e ofertas de suporte gerenciado da Microsoft (como o Suporte Premier). Se um incidente de suporte exigir escalonamento para desenvolvimento para obter mais orientações, exigir uma atualização que não seja de segurança ou exigir uma atualização de segurança, os clientes serão solicitados a atualizar para a versão mais recente da plataforma ou uma atualização intermediária (*).

### <a name="platform-version-included-with-windows-10-releases"></a>Versão da plataforma incluída com Windows 10 versões
A tabela a seguir fornece as versões Microsoft Defender Antivírus plataforma e mecanismo que são enviadas com as versões Windows 10 versão mais recentes:    

|Windows 10 versão  |Versão da plataforma  |Versão do mecanismo |Fase de suporte |
|:---|:---|:---|:---|
|2004 (20H1/20H2) |4.18.1909.6 |1.1.17000.2 | Suporte técnico de atualização (somente) |
|1909 (19H2) |4.18.1902.5 |1.1.16700.3 | Suporte técnico de atualização (somente) |
|1903 (19H1) |4.18.1902.5 |1.1.15600.4 | Suporte técnico de atualização (somente) |
|1809 (RS5) |4.18.1807.18075 |1.1.15000.2 | Suporte técnico de atualização (somente) |
|1803 (RS4) |4.13.17134.1 |1.1.14600.4 | Suporte técnico de atualização (somente) |
|1709 (RS3) |4.12.16299.15 |1.1.14104.0 | Suporte técnico de atualização (somente) |
|1703 (RS2) |4.11.15603.2 |1.1.13504.0 | Suporte técnico de atualização (somente) |
|1607 (RS1) |4.10.14393.3683 |1.1.12805.0 | Suporte técnico de atualização (somente) |  

Para Windows 10 informações de versão, consulte a planilha Windows de fatos do ciclo [de vida.](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet)

## <a name="updates-for-deployment-image-servicing-and-management-dism"></a>Atualizações para Manutenção e Gerenciamento de Imagens de Implantação (DISM)

Recomendamos atualizar suas Windows 10 (Enterprise, Pro e edições Home), o Windows Server 2019 e Windows Server 2016 imagens de instalação do sistema operacional com as atualizações mais recentes de antivírus e antimalware. Manter as imagens de instalação do sistema operacional atualizadas ajuda a evitar uma lacuna na proteção. 

Para obter mais informações, consulte [Microsoft Defender update for Windows operating system installation images](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images).

<details>
<summary>1.1.2106.01</summary>

&ensp;Versão do pacote: **1.1.2106.01**    
&ensp;Versão da plataforma: **4.18.2104.14**   
&ensp;Versão do mecanismo: **1.1.18100.6**  
&ensp;Versão de assinatura: **1.339.1923.0**    
    
### <a name="fixes"></a>Correções
- Nenhuma

### <a name="additional-information"></a>Informações adicionais
- Nenhuma  
<br/>
</details><details>
<summary>1.1.2105.01</summary>

&ensp;Versão do pacote: **1.1.2105.01**    
&ensp;Versão da plataforma: **4.18.2103.7**   
&ensp;Versão do mecanismo: **1.1.18100.6**  
&ensp;Versão de assinatura: **1.339.42.0**    
    
### <a name="fixes"></a>Correções
- Nenhuma

### <a name="additional-information"></a>Informações adicionais
- Nenhuma  
<br/>
</details><details>
<summary>1.1.2104.01</summary>

&ensp;Versão do pacote: **1.1.2104.01**    
&ensp;Versão da plataforma: **4.18.2102.4**   
&ensp;Versão do mecanismo: **1.1.18000.5**  
&ensp;Versão de assinatura: **1.335.232.0**    
    
### <a name="fixes"></a>Correções
- Nenhuma

### <a name="additional-information"></a>Informações adicionais
- Nenhuma  
<br/>
</details><details>
<summary>1.1.2103.01</summary>

&ensp;Versão do pacote: **1.1.2103.01**    
&ensp;Versão da plataforma: **4.18.2101.9**   
&ensp;Versão do mecanismo: **1.1.17800.5**  
&ensp;Versão de assinatura: **1.331.2302.0**    
    
### <a name="fixes"></a>Correções
- Nenhuma

### <a name="additional-information"></a>Informações adicionais
- Nenhuma  
<br/>
</details><details>
<summary>1.1.2102.03</summary>

&ensp;Versão do pacote: **1.1.2102.03**    
&ensp;Versão da plataforma: **4.18.2011.6**   
&ensp;Versão do mecanismo: **1.1.17800.5**  
&ensp;Versão de assinatura: **1.331.174.0**    
    
### <a name="fixes"></a>Correções
- Nenhuma

### <a name="additional-information"></a>Informações adicionais
- Nenhuma  
<br/>
</details><details>
<summary>1.1.2101.02</summary>

&ensp;Versão do pacote: **1.1.2101.02**    
&ensp;Versão da plataforma: **4.18.2011.6**   
&ensp;Versão do mecanismo: **1.1.17700.4**  
&ensp;Versão de assinatura: **1.329.1796.0**    
    
### <a name="fixes"></a>Correções
- Nenhuma

### <a name="additional-information"></a>Informações adicionais
- Nenhuma  
<br/>
</details><details>
<summary>1.1.2012.01</summary>

&ensp;Versão do pacote: **1.1.2012.01**    
&ensp;Versão da plataforma: **4.18.2010.7**   
&ensp;Versão do mecanismo: **1.1.17600.5**  
&ensp;Versão de assinatura: **1.327.1991.0**    
    
### <a name="fixes"></a>Correções
- Nenhuma

### <a name="additional-information"></a>Informações adicionais
- Nenhuma  
<br/>
</details><details>
<summary>1.1.2011.02</summary>

&ensp;Versão do pacote: **1.1.2011.02**    
&ensp;Versão da plataforma: **4.18.2010.7**   
&ensp;Versão do mecanismo: **1.1.17600.5**  
&ensp;Versão de assinatura: **1.327.658.0**    
    
### <a name="fixes"></a>Correções
- Nenhuma

### <a name="additional-information"></a>Informações adicionais
- Assinaturas Microsoft Defender Antivírus atualizadas  
<br/>
</details><details>
<summary>1.1.2011.01</summary>

&ensp;Versão do pacote: **1.1.2011.01**    
&ensp;Versão da plataforma: **4.18.2009.7**  
&ensp;Versão do mecanismo: **1.1.17600.5**  
&ensp;Versão de assinatura: **1.327.344.0**    
    
### <a name="fixes"></a>Correções
- Nenhuma

### <a name="additional-information"></a>Informações adicionais
- Nenhuma  
<br/>
</details><details>
<summary>1.1.2009.10</summary>

&ensp;Versão do pacote: **1.1.2011.01**    
&ensp;Versão da plataforma: **4.18.2008.9**   
&ensp;Versão do mecanismo: **1.1.17400.5**  
&ensp;Versão de assinatura: **1.327.2216.0**    
    
### <a name="fixes"></a>Correções
- Nenhuma

### <a name="additional-information"></a>Informações adicionais
- Adicionado suporte para Windows 10 RS1 ou imagens de instalação posteriores do sistema operacional.  
<br/>
</details>

## <a name="additional-resources"></a>Recursos adicionais

| Artigo | Descrição  |
|:---|:---|
|[Atualização do Microsoft Defender para Windows de instalação do sistema operacional](https://support.microsoft.com/help/4568292/defender-update-for-windows-operating-system-installation-images)  | Revise os pacotes de atualização antimalware para as imagens de instalação do sistema operacional (arquivos WIM e VHD). Obter Microsoft Defender Antivírus atualizações para Windows 10 (Enterprise, Pro e edições Home), Windows Server 2019 e Windows Server 2016 de instalação.  |
|[Gerenciar como as atualizações de proteção são baixadas e aplicadas](manage-protection-updates-microsoft-defender-antivirus.md) | As atualizações de proteção podem ser entregues por meio de várias fontes. |
|[Gerenciar quando as atualizações de proteção devem ser baixadas e aplicadas](manage-protection-update-schedule-microsoft-defender-antivirus.md) | Você pode agendar quando as atualizações de proteção devem ser baixadas. |
|[Gerenciar atualizações para pontos de extremidade que estão des date](manage-outdated-endpoints-microsoft-defender-antivirus.md) | Se um ponto de extremidade perder uma atualização ou uma verificação agendada, você poderá forçar uma atualização ou verificar na próxima vez que um usuário entrar. |
|[Gerenciar atualizações aplicadas com base em evento](manage-event-based-updates-microsoft-defender-antivirus.md) | Você pode definir atualizações de proteção a serem baixadas na inicialização ou após determinados eventos de proteção entregues na nuvem. |
|[Gerenciar atualizações para dispositivos móveis e máquinas virtuais (VMs)](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)| Você pode especificar configurações, como se as atualizações devem ocorrer na energia da bateria, que são especialmente úteis para dispositivos móveis e máquinas virtuais. |
