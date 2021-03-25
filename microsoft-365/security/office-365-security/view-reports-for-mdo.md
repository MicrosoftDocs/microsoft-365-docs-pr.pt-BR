---
title: Exibir relatórios do Defender para Office 365 no painel Relatórios
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Encontre e use relatórios para o Microsoft Defender para Office 365 no Centro de Conformidade & Segurança.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 28978dbca3f9e4039b4f8c21c49a2963802afa54
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203034"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>Exibir relatórios do Defender para o Office 365 no painel Relatórios no Centro de Conformidade & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

As organizações do Microsoft Defender para Office 365 (por exemplo, assinaturas do Microsoft 365 E5 ou Microsoft Defender para Office 365 Plano 1 ou complementos do Microsoft Defender para Office 365 Plan 2) contêm uma variedade de relatórios relacionados à segurança. Se você tiver as [permissões necessárias,](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)poderá exibir esses relatórios no Centro de Conformidade e Segurança & indo para **Painel de** \> **Relatórios.** Para ir diretamente para o painel Relatórios, abra <https://protection.office.com/insightdashboard> .

![O painel Relatórios no Centro de Conformidade & Segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>Relatório de tipos de arquivo do Defender for Office 365

O relatório de tipos de arquivo do **Defender for Office 365** mostra o tipo de arquivos detectados como mal-intencionados por [Anexos Seguros.](safe-attachments.md)

 A exibição agregada do relatório permite 90 dias de filtragem, enquanto a exibição de detalhes permite apenas 10 dias de filtragem.

Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e selecione Tipos de arquivo \>  do Defender para **Office 365.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ATPFileReport> .

![Widget de tipos de arquivo do Defender para Office 365 no painel Relatórios](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> As informações neste relatório também estão disponíveis no relatório de disposição de mensagens do [Defender for Office 365.](#defender-for-office-365-message-disposition-report)

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Exibição de relatório para o relatório de tipos de arquivo do Defender for Office 365

As exibições a seguir estão disponíveis:

- **Exibir dados por: Arquivo**: O gráfico contém as seguintes informações:

  - **Anexos mal-intencionados do Excel**
  - **Anexos flash mal-intencionados**
  - **Anexos PDF mal-intencionados**
  - **Anexos mal-intencionados do PowerPoint**
  - **URLs mal-intencionadas**
  - **Anexos mal-intencionados do Word**
  - **Anexos executáveis mal-intencionados**
  - **Outros**

  Ao passar o mouse sobre um determinado dia (ponto de dados), você pode ver a divisão de tipos de arquivos mal-intencionados que foram [detectados](safe-attachments.md) por Anexos Seguros e proteção [anti-malware no EOP](anti-malware-protection.md).

  ![Exibição de arquivo no relatório de tipos de arquivo do Defender for Office 365](../../media/atp-file-types-report-file-view.png)

  Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:

  - **Data de início** **e data de término**
  - Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.

- **Exibir dados por: Mensagem**: O gráfico contém as seguintes informações:

  - **Bloquear acesso**
  - **Mensagens substituídas**
  - **Mensagens monitoradas**
  - **Substituído por Entrega Dinâmica de Email**: Para obter mais informações, consulte Entrega Dinâmica em Políticas de [Anexos Seguros.](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)

  ![Exibição de mensagem no relatório de tipos de arquivo do Defender for Office 365](../../media/atp-file-types-report-message-view.png)

  Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:

  - **Data de início** **e data de término**
  - Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o **valor de Mensagens passadas** adicionais.

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>Exibição de tabela de detalhes para o relatório de tipos de arquivo do Defender for Office 365

Se você clicar em **Exibir** tabela de detalhes, o relatório fornece uma exibição quase em tempo real de todos os cliques que ocorrem na organização nos últimos 10 dias. As informações mostradas dependem do gráfico que você estava olhando:

- **Exibir dados por: Arquivo**:

  - **Date**
  - **Endereço do destinatário**
  - **Endereço do remetente**.
  - **ID da** mensagem : disponível no campo de header **Message-ID** no header da mensagem e deve ser exclusivo. Um valor de exemplo `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` é (observe os colchetes angulares).
  - **Arquivo**

  Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:

  - **Data de início** **e data de término**
  - Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.

- **Exibir dados por: Mensagem**:

  - **Date**
  - **Endereço do destinatário**
  - **Endereço do remetente**.
  - **ID da mensagem**
  - **Arquivo**
  - **Assunto**

  Se você clicar **em Filtros,** poderá modificar os resultados com os seguintes filtros:

  - **Data de início** **e data de término**
  - Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o **valor de Mensagens passadas** adicionais.

Para voltar à exibição de relatórios, clique em **Exibir relatório**.

## <a name="defender-for-office-365-message-disposition-report"></a>Relatório de disposição de mensagens do Defender for Office 365

O **relatório disposição de mensagens atp** mostra as ações que foram tomadas para mensagens de email que foram detectadas como tendo conteúdo mal-intencionado.

Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e selecione Disposição de mensagem do \>  Defender para **Office 365.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ATPMessageReport> .

![Widget de disposição de mensagens do Defender para Office 365 no painel Relatórios](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> As informações neste relatório também estão disponíveis no relatório de tipos de arquivo do [Defender for Office 365.](#defender-for-office-365-file-types-report)

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Relatório de exibição do relatório de disposição de mensagens do Defender for Office 365

As exibições a seguir estão disponíveis:

- **Exibir dados por: Mensagem**: O gráfico contém as seguintes informações:

  - **Bloquear acesso**
  - **Mensagens substituídas**
  - **Mensagens monitoradas**
  - **Substituído por Entrega Dinâmica de Email**: Para obter mais informações, consulte Entrega Dinâmica em Políticas de [Anexos Seguros.](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)

  ![Exibição de mensagem no relatório de tipos de arquivo do Defender for Office 365](../../media/atp-file-types-report-message-view.png)

  Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:

  - **Data de início** **e data de término**
  - Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o **valor de Mensagens passadas** adicionais.

- **Exibir dados por: Arquivo**: O gráfico contém as seguintes informações:

  - **Anexos mal-intencionados do Excel**
  - **Anexos flash mal-intencionados**
  - **Anexos PDF mal-intencionados**
  - **Anexos mal-intencionados do PowerPoint**
  - **URLs mal-intencionadas**
  - **Anexos mal-intencionados do Word**
  - **Anexos executáveis mal-intencionados**
  - **Outros**

  Ao passar o mouse sobre um determinado dia (ponto de dados), você pode ver a divisão de tipos de arquivos mal-intencionados que foram [detectados](safe-attachments.md) por Anexos Seguros e proteção [anti-malware no EOP](anti-malware-protection.md).

  ![Exibição de arquivo no relatório de tipos de arquivo do Defender for Office 365](../../media/atp-file-types-report-file-view.png)

  Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:

  - **Data de início** **e data de término**
  - Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Exibição de tabela de detalhes para o relatório de disposição de mensagens do Defender for Office 365

Se você clicar em **Exibir** tabela de detalhes, o relatório fornece uma exibição quase em tempo real de todos os cliques que ocorrem na organização nos últimos 10 dias. As informações mostradas dependem do gráfico que você estava olhando:

- **Exibir dados por: Mensagem**:

  - **Date**
  - **Endereço do destinatário**
  - **Endereço do remetente**.
  - **ID da mensagem**
  - **Arquivo**
  - **Assunto**

  Se você clicar **em Filtros,** poderá modificar os resultados com os seguintes filtros:

  - **Data de início** **e data de término**
  - Os mesmos valores de disposição de mensagem que estão disponíveis no gráfico e o **valor de Mensagens passadas** adicionais.

- **Exibir dados por: Arquivo**:

  - **Date**
  - **Endereço do destinatário**
  - **Endereço do remetente**.
  - **ID da mensagem**
  - **Arquivo**

  Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:

  - **Data de início** **e data de término**
  - Os mesmos valores de tipo de arquivo que estão visíveis no gráfico.

Para voltar à exibição de relatórios, clique em **Exibir relatório**.

## <a name="mail-latency-report"></a>Relatório de latência de email

O **relatório de latência de email** mostra uma exibição agregada da entrega de email e da latência de detonação experimentadas em sua organização. Os tempos de entrega de email no serviço são afetados por vários fatores, e o tempo de entrega absoluto em segundos geralmente não é um bom indicador de sucesso ou um problema. Um tempo de entrega lento em um dia pode ser considerado um tempo médio de entrega em outro dia ou vice-versa. O **relatório de latência de email** tenta qualificar a entrega de mensagens com base em dados estatísticos sobre os tempos de entrega observados de outras mensagens:

- **Percentil 50**: Este é o meio para os tempos de entrega da mensagem. Você pode considerar esse valor como um tempo médio de entrega.
- **Percentil 90**: Isso indica uma alta latência para entrega de mensagens. Apenas 10% das mensagens demoraram mais do que esse valor para ser entregue.
- **Percentil 99**: Isso indica a latência mais alta para entrega de mensagens.

O lado do cliente e a latência de rede não estão incluídos.

Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione Relatório **de latência de email.** Para ir diretamente para o relatório, abra <https://protection.office.com/mailLatencyReport?viewid=P50> .

![Widget de relatório de latência de email no painel Relatórios](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>Exibição de relatório para o relatório de latência de email

Quando você abre o relatório, a **guia percentils 50** é selecionada por padrão.

Por padrão, esse modo de exibição contém um gráfico configurado com os seguintes filtros:

- **Data**: Os últimos 7 dias
- **Exibição de Mensagem**:
  - Mensagens detonadas

Este gráfico mostra mensagens organizadas nas seguintes categorias:

- **Latência de entrega de email**
- **Latência de detonação**

Ao passar o mouse sobre uma categoria no gráfico, você pode ver uma divisão da latência em cada categoria.

![Relatório de latência de email](../../media/mail-latency-report.png)

Se você clicar **em Filtrar** no exibição de relatório, poderá modificar os resultados com os seguintes filtros:

- Todas as mensagens
- Mensagens que contêm anexos ou URLs

Se você clicar na guia **percentils 90** ou na guia **percentils 99,** os mesmos filtros padrão do modo de exibição de **percentis do 50º** serão usados.

### <a name="details-table-view-for-the-mail-latency-report"></a>Exibição de tabela de detalhes para o relatório de latência de email

As informações a seguir são mostradas na exibição de tabela de detalhes:

- **Date**
- **Percentis**
- **Contagem de mensagem**
- **Latência geral**

![Detalhes do relatório de latência de email](../../media/mail-latency-report-details.png)

O acima mostra que, em 14 de novembro, a latência média experimentada para todas as mensagens entregues e detonadas foi **de 108.033** segundos.

A tabela de detalhes contém as mesmas informações em cada guia.

## <a name="threat-protection-status-report"></a>Relatório de status de proteção contra ameaças

O **relatório de status** de proteção contra ameaças é uma exibição única que reúne informações sobre conteúdo mal-intencionado e emails mal-intencionados detectados e bloqueados pela Proteção do Exchange [Online](exchange-online-protection-overview.md) (EOP) e pelo Microsoft Defender para Office 365. Para obter mais informações, consulte [Relatório de status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)

## <a name="url-threat-protection-report"></a>Relatório de proteção contra ameaças de URL

O **relatório de proteção contra** ameaças de URL fornece exibições de resumo e tendência para ameaças detectadas e ações realizadas em cliques de URL como parte de Links [Seguros.](safe-links.md) Este relatório não terá clique em dados de usuários em que a política links seguros aplicada tenha a opção Não rastrear **cliques do** usuário selecionada.

Para exibir o relatório, abra o [Centro](https://protection.office.com)de Conformidade & segurança, vá **para** Painel de Relatórios e selecione Relatório de proteção \>  **de URL.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![Widget de relatório de proteção de URL no painel Relatórios](../../media/url-protection-report-widget.png)

> [!NOTE]
> Este é um relatório *de tendência de proteção*, o que significa que os dados representam tendências em um conjuntos de dados maior. Como resultado, os dados no modo de exibição agregado não estão disponíveis em tempo real aqui, mas os dados no modo de exibição de tabela de detalhes são, portanto, você pode ver uma leve discrepância entre os dois pontos de exibição.

### <a name="report-view-for-the-url-threat-protection-report"></a>Exibição de relatório para o relatório de proteção contra ameaças de URL

O **relatório de proteção contra** ameaças de URL tem duas exibições agregadas que são atualizadas uma vez a cada quatro horas que mostram dados dos últimos 90 dias:

- **Ação de proteção de clique em URL**: mostra o número de cliques de URL pelos usuários na organização e os resultados do clique:

  - **Bloqueado** (o usuário foi impedido de navegar para a URL)
  - **Bloqueado e clicado por meio**
  - **Clicado durante a verificação**

  Um clique indica que o usuário clicou na página de bloqueio para o site mal-intencionado (os administradores podem desabilitar o clique em políticas de Links Seguros).

  Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:

  - **Data de início** **e data de término**
  - As ações de proteção de clique disponíveis, mais o valor **Allowed** (o usuário teve permissão para navegar até a URL).

  ![Exibição de ação de proteção de clique em URL no relatório de proteção contra ameaças de URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL clique por aplicativo**: mostra o número de cliques de URL por aplicativos que suportam Links Seguros:

  - **Cliente de email**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Outros**

  Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:

  - **Data de início** **e data de término**
  - Os aplicativos disponíveis.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Exibição de tabela de detalhes para o relatório de proteção contra ameaças de URL

Se você clicar em **Exibir** tabela de detalhes, o relatório fornece uma exibição quase em tempo real de todos os cliques que ocorrem na organização nos últimos 7 dias com os seguintes detalhes:

- **Clique em hora**
- **User**
- **URL**
- **Ação**
- **App**

Se você clicar **em Filtros** no modo de exibição de tabela de detalhes, poderá filtrar pelos mesmos critérios do modo de exibição de relatório e também por **Domínios** ou **Destinatários separados** por vírgulas.

> [!NOTE]
> O **filtro Domínios** refere-se ao domínio URL listado nos resultados do relatório. 

Para voltar à exibição de relatórios, clique em **Exibir relatório**.

## <a name="additional-reports-to-view"></a>Relatórios adicionais para exibição

Além dos relatórios descritos neste artigo, vários outros relatórios estão disponíveis, conforme descrito na tabela a seguir:

****

|Relatório|Tópico|
|---|---|
|**Explorer** (Microsoft Defender para Office 365 Plano 2) ou detecções em **tempo real** (Microsoft Defender para Office 365 Plano 1)|[Explorador de Ameaças (e detecções em tempo real)](threat-explorer.md)|
|**Relatórios de segurança de** email , como o relatório principais remetentes e destinatários, o relatório de email Spoof e o relatório de detecções de spam.|[Exibir relatórios de segurança de email no Centro de Conformidade & Segurança](view-email-security-reports.md)|
|**Relatórios de fluxo de** emails , como o relatório de encaminhamento, o relatório de status de fluxo de emails e o relatório de principais destinatários e destinatários.|[Exibir relatórios de fluxo de emails no Centro de Conformidade & Segurança](view-mail-flow-reports.md)|
|**Rastreamento de URL para Links Seguros** (somente PowerShell). A saída deste cmdlet mostra os resultados das ações de Links Seguros nos últimos sete dias.|[Get-UrlTrace](/powershell/module/exchange/get-urltrace)|
|**Resultados do tráfego de email para o EOP e o Microsoft Defender para Office 365** (somente o PowerShell). A saída deste cmdlet contém informações sobre Domínio, Data, Tipo de Evento, Direção, Ação e Contagem de Mensagens.|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport)|
|**Relatórios de detalhes de email para detecções do EOP** e do Defender para Office 365 (somente PowerShell). A saída deste cmdlet contém detalhes sobre arquivos mal-intencionados ou URLs, tentativas de phishing, representação e outras possíveis ameaças em emails ou arquivos.|[Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Quais permissões são necessárias para exibir os relatórios do Defender para Office 365?

Para exibir e usar os relatórios descritos neste artigo, você precisa ser membro de um dos seguintes grupos de funções no Centro de Conformidade & Segurança:

- **Organization Management**
- **Administrador de Segurança**
- **Leitor de Segurança**
- **Leitor Global**

Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

**Observação**: a adição de usuários à função correspondente do Azure Active Directory no Centro de administração do  Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Conformidade & Segurança e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>E se os relatórios não mostrarem dados?

Se você não estiver vendo dados nos relatórios do Defender para Office 365, verifique duas vezes se suas políticas estão configuradas corretamente. Sua organização deve ter políticas [de Links Seguros](set-up-safe-links-policies.md) e políticas de Anexos Seguros [definidas](set-up-safe-attachments-policies.md) para que a proteção do Defender para o Office 365 seja realizada. Consulte também [Proteção anti-spam e anti-malware.](anti-spam-and-anti-malware-protection.md)

## <a name="related-topics"></a>Tópicos relacionados

[Relatórios inteligentes e insights no Centro de Conformidade e Segurança](reports-and-insights-in-security-and-compliance.md)

[Permissões de função (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)