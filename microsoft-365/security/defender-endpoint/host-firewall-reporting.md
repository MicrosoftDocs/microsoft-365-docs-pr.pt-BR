---
title: Relatórios de firewall de host no Microsoft Defender para Ponto de Extremidade
description: Hospedar e exibir relatórios de firewall no Microsoft 365 de segurança.
keywords: windows defender, firewall
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809208"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Relatórios de firewall de host no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Se você for um administrador, agora poderá hospedar relatórios de firewall [no Microsoft 365 de segurança.](https://security.microsoft.com) Esse recurso permite exibir relatórios de firewall Windows 10 e Windows Server 2019 de um local centralizado. 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar? 

- Você deve estar executando Windows 10 ou Windows Server 2019.
- Para integrar dispositivos para o serviço Microsoft Defender para Ponto de Extremidade, consulte [aqui](onboard-configure.md). 
- Para Microsoft 365 central de segurança começar a receber  os dados, você deve habilitar eventos de auditoria para Windows Defender Firewall com Segurança Avançada: 
    - [Audit Filtering Platform Packet Drop](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [Conexão da Plataforma de Filtragem de Auditoria](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- Habilita esses eventos usando o Editor de Objeto de Política de Grupo, a Política de Segurança Local ou auditpol.exe comandos. Para obter mais informações, consulte [aqui](/windows/win32/fwp/auditing-and-logging). 
    - Os dois comandos do PowerShell são:
        - **auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable** 
        - **auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable** 

## <a name="the-process"></a>O processo
> [!NOTE]
> Siga as instruções da seção acima e configure corretamente seus dispositivos para a participação inicial da visualização.

- Depois de ativar os eventos, Microsoft 365 central de segurança começará a monitorar os dados.
    - IP remoto, porta remota, porta local, IP local, nome do computador, Processo entre conexões de entrada e saída.
- Os administradores agora podem ver Windows de firewall de host [aqui](https://security.microsoft.com/firewall).
    - Relatórios adicionais podem ser facilitados baixando o [script Relatório Personalizado](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) para monitorar as atividades Windows Defender Firewall usando Power BI. 
    - Pode levar até 12 horas antes que os dados se refletem.

## <a name="supported-scenarios"></a>Cenários com suporte
Os cenários a seguir são suportados durante o Ring0 Preview. 

### <a name="firewall-reporting-in-security-center"></a>Relatórios de firewall no centro de segurança

Aqui estão alguns exemplos das páginas de relatório de firewall. Aqui você encontrará um resumo da atividade de entrada, saída e aplicativo. Você pode acessar essa página diretamente acessando https://security.microsoft.com/firewall . 

> [!div class="mx-imgBorder"]
> ![Página de relatório de firewall do host](\images\host-firewall-reporting-page.png)

Esses relatórios também podem ser acessados acessando a seção **Reports** Security Report Devices (seção) localizada na parte inferior do  >    >   **cartão Conexões de Entrada Bloqueadas do Firewall.**

### <a name="from-computers-with-a-blocked-connection-to-device"></a>De "Computadores com uma conexão bloqueada" para o dispositivo

Os cartões suportam objetos interativos. Você pode detalhar a atividade de um dispositivo clicando no nome do dispositivo, que será lançado em uma nova guia e o levará diretamente para a guia Linha https://securitycenter.microsoft.com **do Tempo do** Dispositivo. 

> [!div class="mx-imgBorder"]
> ![Computadores com uma conexão bloqueada](\images\firewall-reporting-blocked-connection.png)

Agora você pode selecionar a guia **Linha** do Tempo, que lhe dará uma lista de eventos associados a esse dispositivo. 

Depois de clicar no botão **Filtros** no canto superior direito do painel de exibição, selecione o tipo de evento que deseja. Nesse caso, selecione **Eventos de Firewall** e o painel será filtrado para eventos de Firewall. 

> [!div class="mx-imgBorder"]
> ![Botão Filtros](\images\firewall-reporting-filters-button.png)

### <a name="drill-into-advanced-hunting-preview-refresh"></a>Drill into advanced hunting (preview refresh)

Os relatórios de firewall suportam a furação do cartão diretamente na Busca **Avançada** clicando no **botão Abrir Busca** Avançada. A consulta será pré-preenchida. 

> [!div class="mx-imgBorder"]
> ![Abrir botão de busca avançada](\images\firewall-reporting-advanced-hunting.png)

A consulta agora pode ser executada e todos os eventos de Firewall relacionados dos últimos 30 dias podem ser explorados. 

Para relatórios adicionais ou alterações personalizadas, a consulta pode ser exportada para Power BI análise adicional. Relatórios personalizados podem ser facilitados baixando o [script Relatório Personalizado](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) para monitorar as atividades Windows Defender Firewall usando Power BI. 

 