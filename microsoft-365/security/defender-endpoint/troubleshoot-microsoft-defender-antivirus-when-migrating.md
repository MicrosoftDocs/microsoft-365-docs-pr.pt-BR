---
title: Solucionar problemas do Microsoft Defender Antivírus durante a migração de uma solução de terceiros
description: Solucionar erros comuns ao migrar para Microsoft Defender Antivírus
keywords: event, error code, logging, troubleshooting, microsoft defender antivírus, windows defender antivírus, migration
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: martyav
ms.author: v-maave
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 3fcc79e767edb533a20402a2f92ba4abc7d8386a
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764586"
---
# <a name="troubleshoot-microsoft-defender-antivirus-while-migrating-from-a-third-party-solution"></a>Solucionar problemas do Microsoft Defender Antivírus durante a migração de uma solução de terceiros

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)


Você pode encontrar ajuda aqui se encontrar problemas ao migrar de uma solução de segurança de terceiros para Microsoft Defender Antivírus.

## <a name="review-event-logs"></a>Revisar logs de eventos

Abra o aplicativo visualizador de eventos selecionando o **ícone pesquisar** na barra de tarefas e procurando o *visualizador de eventos*.

Informações sobre Microsoft Defender Antivírus podem ser encontradas em **Logs de** Aplicativos e Serviços  >  **da Microsoft**  >  **Windows**  >  **Windows Defender**. 

A partir daí, selecione **Abrir** em **Operacional**.

Selecionar um evento no painel de detalhes mostrará mais informações sobre um evento no painel inferior, nas guias **Geral** e **Detalhes.**

## <a name="microsoft-defender-antivirus-wont-start"></a>Microsoft Defender Antivírus não iniciará

Esse problema pode se manifesto na forma de várias IDs de evento diferentes, todas com a mesma causa subjacente.

### <a name="associated-event-ids"></a>IDs de eventos associados

 ID de evento | Nome do log | Descrição | Source
-|-|-|-
15 | Aplicativo | Atualizou Windows Defender status com êxito para SECURITY_PRODUCT_STATE_OFF. | Central de Segurança
5007 | Microsoft-Windows-Windows Defender/Operacional | Windows Defender Antivírus A configuração foi alterada.  Se esse for um evento inesperado, você deverá revisar as configurações, pois isso pode ser o resultado de malware.<br /><br />**Valor antigo:** Default\IsServiceRunning = 0x0<br />**Novo valor:** HKLM\SOFTWARE\Microsoft\Windows Defender\IsServiceRunning = 0x1 | Windows Defender
5010 | Microsoft-Windows-Windows Defender/Operacional | Windows Defender Antivírus verificação de spyware e outros softwares potencialmente indesejados está desabilitado. | Windows Defender

### <a name="how-to-tell-if-microsoft-defender-antivirus-wont-start-because-a-third-party-antivirus-is-installed"></a>Como saber se o Microsoft Defender Antivírus não iniciará porque um antivírus de terceiros está instalado

Em um Windows 10, se você não estiver usando o Microsoft Defender para Ponto de Extremidade e tiver um antivírus de terceiros instalado, Microsoft Defender Antivírus será automaticamente desligado. Se você estiver usando o Microsoft Defender para Ponto de Extremidade com um antivírus de terceiros instalado, Microsoft Defender Antivírus iniciará no modo passivo, com funcionalidade reduzida.

> [!TIP]
> O cenário descrito se aplica somente a Windows 10. Outras versões do Windows têm respostas diferentes para Microsoft Defender Antivírus sendo [executados](microsoft-defender-antivirus-compatibility.md) juntamente com software de segurança de terceiros.

#### <a name="use-services-app-to-check-if-microsoft-defender-antivirus-is-turned-off"></a>Use o aplicativo Serviços para verificar se Microsoft Defender Antivírus está desligado

Para abrir o aplicativo Serviços, selecione o **ícone Pesquisar** na barra de tarefas e procure *por serviços.* Você também pode abrir o aplicativo na linha de comando digitando *services.msc*.

As informações Microsoft Defender Antivírus serão listadas no aplicativo Serviços em **Windows Defender**  >  **Operacional**. O nome do serviço antivírus *é Windows Defender Antivírus Service*.

Ao verificar o aplicativo,  você pode ver que o serviço Windows Defender Antivírus está definido como manual , mas quando você tenta iniciar esse serviço manualmente, você tem um aviso informando que o serviço de serviço Windows Defender Antivírus no Computador Local foi iniciado e *interrompido. Alguns serviços param automaticamente se não estão em uso por outros serviços ou programas.*

Isso indica que o Microsoft Defender Antivírus foi automaticamente desligado para preservar a compatibilidade com um antivírus de terceiros.

#### <a name="generate-a-detailed-report"></a>Gerar um relatório detalhado

Você pode gerar um relatório detalhado sobre as políticas de  grupo ativas no momento abrindo um prompt de comando no modo de administração e inserindo o seguinte comando:

```powershell
GPresult.exe /h gpresult.html
```

Isso gerará um relatório localizado em *./gpresult.html*. Abra esse arquivo e você poderá ver os resultados a seguir, dependendo de como Microsoft Defender Antivírus foi desligado.

##### <a name="group-policy-results"></a>Resultados da política de grupo

##### <a name="if-security-settings-are-implemented-via-group-policy-gpo-at-the-domain-or-local-level-or-though-system-center-configuration-manager-sccm"></a>Se as configurações de segurança são implementadas por meio de política de grupo (GPO) no domínio ou no nível local, ou embora o System center configuration manager (SCCM)

No relatório GPResults, sob o título, *Windows Components/Windows Defender Antivírus*, você pode ver algo como a entrada a seguir, indicando que o Microsoft Defender Antivírus está desligado.

Política | Configuração | GpO vencedor
-|-|-
Desativar Windows Defender Antivírus | Habilitado | Win10-Workstations

###### <a name="if-security-settings-are-implemented-via-group-policy-preference-gpp"></a>Se as configurações de segurança são implementadas por meio da preferência de política de grupo (GPP)

Sob o título, item do Registro (Caminho da chave: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender, Nome do *valor: DisableAntiSpyware)*, você pode ver algo como a entrada a seguir, indicando que Microsoft Defender Antivírus está desligado.

DisableAntiSpyware | -
-|-
GpO vencedor | Win10-Workstations
Resultado: Sucesso | 
**Geral** | 
Action | Atualizar
**Properties** | 
Hive | HKEY_LOCAL_MACHINE
Caminho da chave | SOFTWARE\Policies\Microsoft\Windows Defender
Nome do valor  | DisableAntiSpyware
Tipo do valor | REG_DWORD
Dados de valor | 0x1 (1)

###### <a name="if-security-settings-are-implemented-via-registry-key"></a>Se as configurações de segurança são implementadas por meio da chave do Registro

O relatório pode conter o seguinte texto, indicando que Microsoft Defender Antivírus está desligado:
 
> Registro (regedit.exe)
>
> HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender DisableAntiSpyware (dword) 1 (hex)

###### <a name="if-security-settings-are-set-in-windows-or-your-windows-server-image"></a>Se as configurações de segurança são definidas em Windows ou sua imagem Windows Server

Seu administrador imaginário pode ter definido a política de segurança, **[DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware)**, localmente por *GPEdit.exe*, *LGPO.exe*, ou modificando o Registro em sua sequência de tarefas. Você pode [configurar um Identificador de Imagem Confiável](/windows-hardware/manufacture/desktop/configure-a-trusted-image-identifier-for-windows-defender) para Microsoft Defender Antivírus.

### <a name="turn-microsoft-defender-antivirus-back-on"></a>Ativar Microsoft Defender Antivírus de novo

Microsoft Defender Antivírus ativará automaticamente se nenhum outro antivírus estiver ativo no momento. Você precisará desativar completamente o antivírus de terceiros para garantir Microsoft Defender Antivírus pode ser executado com funcionalidade completa.

> [!WARNING]
> As soluções sugerindo que você edite os valores de início do Windows Defender para *wdboot,* *wdfilter,* *wdnisdrv,* *wdnissvc* e *windefend* no HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services não são compatíveis e podem forçar você *a* fazer uma nova imagem do sistema.

O modo passivo estará disponível se você começar a usar o Microsoft Defender para Ponto de Extremidade e um antivírus de terceiros juntamente com Microsoft Defender Antivírus. O modo passivo permite que o Microsoft Defender digitalize arquivos e se atualize, mas não correção de ameaças. Além disso, o monitoramento de comportamento por meio da Proteção em Tempo [Real](configure-real-time-protection-microsoft-defender-antivirus.md) não está disponível no modo passivo, a menos que a prevenção contra perda de dados do Ponto de Extremidade [(DLP)](/microsoft-365/security/defender-endpoint/information-protection-in-windows-overview) seja implantada.

Outro recurso, conhecido como verificação periódica [limitada,](limited-periodic-scanning-microsoft-defender-antivirus.md)está disponível para usuários finais quando Microsoft Defender Antivírus está definido para desativar automaticamente. Esse recurso permite que Microsoft Defender Antivírus os arquivos periodicamente juntamente com um antivírus de terceiros, usando um número limitado de detecções.

> [!IMPORTANT]
> A verificação periódica limitada não é recomendada em ambientes corporativos. Os recursos de detecção, gerenciamento e relatório disponíveis ao executar Microsoft Defender Antivírus neste modo são reduzidos em comparação ao modo ativo.

### <a name="see-also"></a>Confira também

* [Microsoft Defender Antivírus compatibilidade](microsoft-defender-antivirus-compatibility.md)
* [Microsoft Defender Antivírus no aplicativo Segurança do Windows aplicativo](microsoft-defender-security-center-antivirus.md)