---
title: Exibir relatórios para proteção avançada contra ameaças
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Encontre e use relatórios para a proteção avançada contra ameaças do Office 365 no centro de conformidade de segurança &amp; .
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e2bb4b0248294589b3e6e7a1a095e4f63d47d8e2
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446294"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Exibir relatórios para a proteção avançada contra ameaças do Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


As organizações de proteção avançada contra ameaças (ATP) do Office 365 (por exemplo, as assinaturas do Microsoft 365 E5 ou os complementos do plano ATP 1 ou ATP 2) contêm uma variedade de relatórios relacionados à segurança. Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-the-atp-reports), poderá exibir esses relatórios no centro de conformidade & de segurança acessando **Reports** o \> **painel**relatórios. Para ir diretamente para o painel relatórios, abra <https://protection.office.com/insightdashboard> .

![O painel de relatórios no centro de conformidade & segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a>Relatório de tipos de arquivo da proteção avançada contra ameaças

O relatório de **relatórios tipos de arquivo de proteção avançada contra ameaças** mostra o tipo de arquivos detectados como mal-intencionados por [anexos seguros](atp-safe-attachments.md).

 O modo de exibição de agregação do relatório permite 90 dias de filtragem, enquanto o modo de exibição de detalhes permite apenas 10 dias de filtragem.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **tipos de arquivo do Office ATP**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ATPFileReport> .

![Widget tipos de arquivo do Office ATP no painel relatórios](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> As informações neste relatório também estão disponíveis no relatório de [disposição avançada de mensagens de proteção contra ameaças](#advanced-threat-protection-message-disposition-report).

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a>Exibição de relatório para o relatório de tipos de arquivo de proteção avançada contra ameaças

Os seguintes modos de exibição estão disponíveis:

- **Exibir dados por: arquivo**: o gráfico contém as seguintes informações:

  - **Anexos mal-intencionados do Excel**
  - **Anexos de flash mal-intencionados**
  - **Anexos PDF mal-intencionados**
  - **Anexos mal-intencionados do PowerPoint**
  - **URLs mal-intencionadas**
  - **Anexos de palavras maliciosas**
  - **Anexos executáveis maliciosos**
  - **Outros**

  Ao passar o mouse sobre um determinado dia (ponto de dados), você pode ver a divisão de tipos de arquivos mal-intencionados que foram detectados por [anexos seguros](atp-safe-attachments.md) e [proteção Antimalware no EOP](anti-malware-protection.md).

  ![Exibição de arquivo no relatório de tipos de arquivo ATP](../../media/atp-file-types-report-file-view.png)

  Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.

- **Exibir dados por: Message**: o gráfico contém as seguintes informações:

  - **Bloquear acesso**
  - **Mensagens substituídas**
  - **Mensagens monitoradas**
  - **Substituído por entrega de emails dinâmicas**: para obter mais informações, consulte [entrega dinâmica em políticas de anexos seguros](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Exibição de mensagem no relatório de tipos de arquivo ATP](../../media/atp-file-types-report-message-view.png)

  Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o valor de **mensagens adicionais passadas** .

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a>Exibição da tabela de detalhes para o relatório de tipos de arquivo de proteção avançada contra ameaças

Se você clicar em **Exibir tabela de detalhes**, o relatório fornecerá uma visão quase em tempo real de todos os cliques que acontecerem na organização pelos últimos 10 dias. As informações mostradas dependem do gráfico que você estava observando:

- **Exibir dados por: arquivo**:

  - **Date**
  - **Endereço do destinatário**
  - **Endereço do remetente**.
  - **ID da mensagem**: disponível no campo de cabeçalho **Message-ID** no cabeçalho da mensagem e deve ser exclusivo. Um valor de exemplo é `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observe os colchetes angulares).
  - **Arquivo**

  Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.

- **Exibir dados por: mensagem**:

  - **Date**
  - **Endereço do destinatário**
  - **Endereço do remetente**.
  - **ID da mensagem**
  - **Arquivo**
  - **Subject**

  Se você clicar em **filtros**, poderá modificar os resultados com os seguintes filtros:

  - **Data de início** e **data de término**
  - Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o valor de **mensagens adicionais passadas** .

Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.

## <a name="advanced-threat-protection-message-disposition-report"></a>Relatório de disposição de mensagens da Proteção Avançada contra Ameaças

O relatório de **disposição de mensagens ATP** mostra as ações que foram tomadas para mensagens de email que foram detectadas como tendo conteúdo mal-intencionado.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **disposição de mensagens do Office ATP**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ATPMessageReport> .

![Widget de disposição de mensagens ATP do Office 365 no painel relatórios](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> As informações neste relatório também estão disponíveis no [relatório tipos de arquivo de proteção avançada contra ameaças](#advanced-threat-protection-file-types-report).

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a>Exibição de relatório para o relatório de disposição avançada de mensagens de proteção contra ameaças

Os seguintes modos de exibição estão disponíveis:

- **Exibir dados por: Message**: o gráfico contém as seguintes informações:

  - **Bloquear acesso**
  - **Mensagens substituídas**
  - **Mensagens monitoradas**
  - **Substituído por entrega de emails dinâmicas**: para obter mais informações, consulte [entrega dinâmica em políticas de anexos seguros](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies).

  ![Exibição de mensagem no relatório de tipos de arquivo ATP](../../media/atp-file-types-report-message-view.png)

  Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o valor de **mensagens adicionais passadas** .

- **Exibir dados por: arquivo**: o gráfico contém as seguintes informações:

  - **Anexos mal-intencionados do Excel**
  - **Anexos de flash mal-intencionados**
  - **Anexos PDF mal-intencionados**
  - **Anexos mal-intencionados do PowerPoint**
  - **URLs mal-intencionadas**
  - **Anexos de palavras maliciosas**
  - **Anexos executáveis maliciosos**
  - **Outros**

  Ao passar o mouse sobre um determinado dia (ponto de dados), você pode ver a divisão de tipos de arquivos mal-intencionados que foram detectados por [anexos seguros](atp-safe-attachments.md) e [proteção Antimalware no EOP](anti-malware-protection.md).

  ![Exibição de arquivo no relatório de tipos de arquivo ATP](../../media/atp-file-types-report-file-view.png)

  Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a>Exibição da tabela de detalhes para o relatório de disposição avançada de mensagens de proteção contra ameaças

Se você clicar em **Exibir tabela de detalhes**, o relatório fornecerá uma visão quase em tempo real de todos os cliques que acontecerem na organização pelos últimos 10 dias. As informações mostradas dependem do gráfico que você estava observando:

- **Exibir dados por: mensagem**:

  - **Date**
  - **Endereço do destinatário**
  - **Endereço do remetente**.
  - **ID da mensagem**
  - **Arquivo**
  - **Subject**

  Se você clicar em **filtros**, poderá modificar os resultados com os seguintes filtros:

  - **Data de início** e **data de término**
  - Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o valor de **mensagens adicionais passadas** .

- **Exibir dados por: arquivo**:

  - **Date**
  - **Endereço do destinatário**
  - **Endereço do remetente**.
  - **ID da mensagem**
  - **Arquivo**

  Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.

Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.

## <a name="threat-protection-status-report"></a>Relatório de status de proteção contra ameaças

O relatório de **status de proteção contra ameaças** é um modo de exibição único que reúne informações sobre conteúdo mal-intencionado e email mal-intencionado detectado e bloqueado pela [proteção do Exchange Online](exchange-online-protection-overview.md) (EOP) e pelo Office 365 ATP. Para obter mais informações, consulte [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>Relatório de proteção contra ameaças de URL

O **relatório de proteção de ameaças de URL** fornece as exibições de resumo e tendência para ameaças detectadas e ações tomadas em cliques de URL como parte de [links seguros](atp-safe-links.md). Este relatório não terá clique em dados de usuários em que a política de links seguros aplicada tenha a opção **não rastrear os cliques do usuário** selecionada.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione relatório de **proteção de URL**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![Widget relatório de proteção de URL no painel relatórios](../../media/url-protection-report-widget.png)

> [!NOTE]
> Este é um *relatório de tendências de proteção*, o que significa que os dados representam tendências em um conjunto de dados maior. Como resultado, os dados no modo de exibição de agregação não estão disponíveis em tempo real aqui, mas os dados no modo de exibição de tabela detalhes são, portanto, você pode ver uma pequena discrepância entre as duas exibições.

### <a name="report-view-for-the-url-threat-protection-report"></a>Exibição de relatório para o relatório de proteção contra ameaças de URL

O relatório de **proteção contra ameaças de URL** tem duas exibições agregadas que são atualizadas uma vez a cada quatro horas que mostram dados dos últimos 90 dias:

- **URL clique em ação de proteção**: mostra o número de cliques de URL por usuários na organização e os resultados do clique:

  - **Bloqueado** (o usuário foi impedido de navegar para a URL)
  - **Bloqueado e clicado**
  - **Clicado durante a verificação**

  Um clique indica que o usuário clicou através da página de bloqueio para o site mal-intencionado (os administradores podem desabilitar o clique em políticas de links seguros).

  Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - O disponível clique em ações de proteção, mais o valor **permitido** (o usuário tem permissão para navegar até a URL).

  ![URL clique em ação de proteção exibir no relatório de proteção contra ameaças de URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL clique por aplicativo**: mostra o número de cliques de URL por aplicativos que dão suporte a links seguros:

  - **Cliente de email**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Outros**

  Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - Os aplicativos disponíveis.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Exibição da tabela de detalhes para o relatório de proteção contra ameaças de URL

Se você clicar em **Exibir tabela de detalhes**, o relatório fornecerá uma visão quase em tempo real de todos os cliques que acontecerem na organização pelos últimos 7 dias com os seguintes detalhes:

- **Horário de clique**
- **Usuário**
- **URL**
- **Ação**
- **App**

Se você clicar em **filtros** no modo de exibição tabela de detalhes, poderá filtrar pelos mesmos critérios do modo de exibição relatório e também por **domínios** ou **destinatários** separados por vírgulas.

Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.

## <a name="additional-reports-to-view"></a>Relatórios adicionais para exibir

Além dos relatórios ATP descritos neste tópico, vários outros relatórios estão disponíveis, conforme descrito na tabela a seguir:

****

|Relatório|Tópico|
|---|---|
|**Explorer** (plano ATP 2) ou **detecções em tempo real** (plano ATP 1)|[Explorador de Ameaças (e detecções em tempo real)](threat-explorer.md)|
|**Relatórios de segurança de email**, como os principais remetentes e destinatários, o relatório de email de spoof e o relatório de detecções de spam.|[Exibir relatórios de segurança de email no centro de conformidade & segurança](view-email-security-reports.md)|
|**Relatórios de fluxo de email**, como o relatório de encaminhamento, o relatório de status do fluxo e o relatório de remetentes e destinatários principais.|[Exibir relatórios de fluxo de emails no centro de conformidade & segurança](view-mail-flow-reports.md)|
|**Rastreamento de URL para links seguros** (somente PowerShell). A saída deste cmdlet mostra os resultados das ações de links seguros nos últimos sete dias.|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**Resultados de tráfego de email para EOP e ATP** (somente PowerShell). A saída desse cmdlet contém informações sobre o domínio, a data, o tipo de evento, a direção, a ação e a contagem de mensagens.|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**Mail Detail Reports for EOP and ATP detecções** (somente PowerShell). A saída desse cmdlet contém detalhes sobre arquivos mal-intencionados ou URLs, tentativas de phishing, representação e outras ameaças potenciais em emails ou arquivos.|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Quais permissões são necessárias para exibir os relatórios ATP?

Para exibir e usar os relatórios descritos neste tópico, **você deve ter uma função apropriada atribuída para o centro de conformidade de segurança &amp; e o centro de administração do Exchange**.

- Para o centro de conformidade & segurança, você deve ter uma das seguintes funções atribuídas:

  - Gerenciamento de Organização
  - Administrador de segurança (pode ser atribuído no centro de administração do Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) )
  - Operador de segurança (pode ser atribuído no centro de administração do Azure Active Directory [https://aad.portal.azure.com](https://aad.portal.azure.com) )
  - Leitor de segurança

- Para o Exchange Online, você deve ter uma das seguintes funções atribuídas no centro de administração do Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) ou com cmdlets do PowerShell (Confira [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):

  - Gerenciamento de Organização
  - Gerenciamento de Organização Somente para Exibição
  - Função de Destinatários Somente para Exibição
  - Gerenciamento de Conformidade

Para saber mais, confira os seguintes recursos:

- [Permissões no Centro de Segurança e Conformidade](permissions-in-the-security-and-compliance-center.md)

- [Permissões de recursos no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>E se os relatórios não estiverem mostrando dados?

Se você não estiver vendo dados em seus relatórios ATP, verifique se as políticas estão configuradas corretamente. Sua organização deve ter [políticas de links seguros](set-up-atp-safe-links-policies.md) e [políticas de anexos seguros](set-up-atp-safe-attachments-policies.md) definidas para que a proteção ATP esteja funcionando. Consulte também [anti-spam and Anti-Malware Protection](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Tópicos relacionados

[Relatórios inteligentes e insights no Centro de Conformidade e Segurança](reports-and-insights-in-security-and-compliance.md)
  
[Permissões de função (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
