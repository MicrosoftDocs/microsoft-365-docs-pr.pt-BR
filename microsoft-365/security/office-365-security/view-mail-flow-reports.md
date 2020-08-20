---
title: Exibir relatórios de fluxo de emails no painel relatórios
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem saber mais sobre os relatórios de fluxo de emails disponíveis no painel de relatórios no centro de conformidade do & de segurança.
ms.custom: ''
ms.openlocfilehash: 98b27497b758a202ccbb741f6cb10e4ec65570e9
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814489"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Exibir relatórios de fluxo de emails no painel de relatórios no centro de conformidade e segurança &

Além dos relatórios de fluxo de emails disponíveis no painel de [fluxo de emails](mail-flow-insights-v2.md) no centro de conformidade com segurança &, vários relatórios de fluxo de email adicionais estão disponíveis no painel de relatórios para ajudá-lo a monitorar sua organização do Microsoft 365.

Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-these-reports), poderá exibir esses relatórios no centro de [conformidade & de segurança](https://office.protection.com) acessando **Reports** o \> **painel**relatórios. Para ir diretamente para o painel relatórios, abra <https://office.protection.office.com/insightdashboard> .

![Painel de relatórios no centro de conformidade & segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Relatório do conector

O **relatório do conector** mostra a atividade de fluxo de emails nos [conectores de entrada e saída](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) que estão configurados para sua organização.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **relatório do conector**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ConnectorReport> .

![Widget relatório do conector no painel relatórios](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Exibição de relatório para o relatório do conector

Os gráficos a seguir estão disponíveis no modo de exibição relatório:

- **Exibir dados por: fluxo de email**: Este gráfico mostra o número de mensagens de entrada e de saída organizadas por:

  - **Total**
  - **Da Internet sem um conector**
  - **Para a Internet sem um conector**
  - Um conector específico que você configurou.
  
  Para isolar os dados no gráfico, use o recurso **Mostrar dados do** controle para selecionar uma destas opções ou **todo o fluxo de emails**.

  ![Exibir dados por fluxo de emails no relatório do conector](../../media/connector-report-view-data-by-mail-flow.png)

- **Exibir dados por: uso de TLS**: Este gráfico mostra a porcentagem de uso da versão do protocolo TLS para o fluxo de emails.

  Para isolar os dados no gráfico, use a opção **Mostrar dados do** controle para selecionar uma das seguintes opções:

  - **Todo o fluxo de email**
  - **Da Internet sem um conector**
  - **Para a Internet sem um conector**
  - Um conector específico que você configurou.

  ![Exibir dados por uso de TLS no relatório do conector](../../media/connector-report-view-data-by-tls-usage.png)

Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.

### <a name="details-table-view-for-the-connector-report"></a>Exibição da tabela de detalhes para o relatório do conector

Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:

- **Date**
- **Direção e nome do conector**
- **Tipo de conector**
- **TLS forçado?**: o valor **true** ou **false**.
- **Sem TLS** (porcentagem)
- **TLS 1,0** (porcentagem)
- **TLS 1,1** (porcentagem)
- **TLS 1,2** (porcentagem)
- **Volume**: o número de mensagens.

Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.

Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.

## <a name="exchange-transport-rule-report"></a>Relatório de regras de transporte do Exchange

O **relatório** de regras de transporte do Exchange mostra o efeito das regras de fluxo de emails (também conhecidas como regras de transporte) em mensagens de entrada e de saída em sua organização.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione regra de **transporte do Exchange**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Widget regra de transporte do Exchange no painel relatórios](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Exibição de relatório para o relatório de regra de transporte do Exchange

Os gráficos a seguir estão disponíveis no modo de exibição relatório:

- **Exibir dados por: regras** \> de transporte do Exchange **Dividir em: direção**: Este gráfico mostra o número de mensagens de **entrada** e de **saída** que foram afetadas por regras de transporte.

- **Exibir dados por: regras** \> de transporte do Exchange **Dividir em: severidade**: Este gráfico mostra o número de **alta gravidade** e **severidade média**e mensagens de **baixa gravidade** . Você define o nível de severidade como uma ação na regra (**auditar esta regra com nível de severidade** ou _SetAuditSeverity_). Para obter mais informações, consulte [Mail Flow Rule Actions in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Exibir dados por: regras** \> de transporte do Exchange DLP **Divisão por: direção**: Este gráfico mostra o número de mensagens de **entrada** e de **saída** que foram afetadas pelas regras de transporte de prevenção de perda de dados (DLP). Você pode refinar ainda mais o gráfico selecionando uma das seguintes opções:

  - **Mostrar dados de: todas as regras de transporte DLP**
  - **Mostrar dados de: usuários comprometidos**
  - **Mostrar dados de: baixo volume de conteúdo detectado Patriot lei americano**

- **Exibir dados por: regras** \> de transporte do Exchange DLP **Divisão por: direção**: este modo de exibição mostra o número de **alta** gravidade e **severidade média**e mensagens de **baixa gravidade** que foram afetadas pelas regras de transporte DLP. Você pode refinar ainda mais o gráfico selecionando uma das seguintes opções:

  - **Mostrar dados de: todas as regras de transporte DLP**
  - **Mostrar dados de: usuários comprometidos**
  - **Mostrar dados de: baixo volume de conteúdo detectado Patriot lei americano**

Se você clicar em **filtros** em um modo de exibição de relatório, poderá modificar os resultados com os seguintes filtros:

- **Data de início** e **data de término**
- Valores de direção
- Valores de gravidade

![Exibição de relatório no relatório de regra de transporte do Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Exibição da tabela de detalhes para o relatório de regras de transporte do Exchange

Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:

- **Exibir dados por: regras de transporte do Exchange**:

  - **Date**
  - **Regra de transporte**
  - **Assunto**
  - **Endereço do remetente**.
  - **Endereço do destinatário**
  - **Severidade**
  - **Direção**

- **Exibir dados por: regras de transporte do Exchange DLP**:

  - **Date**
  - **Política de DLP**
  - **Regra de transporte**
  - **Assunto**
  - **Endereço do remetente**.
  - **Endereço do destinatário**
  - **Severidade**
  - **Direção**

Se você clicar em **filtros** em um modo de exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:

- **Data de início** e **data de término**
- Valores de direção
- Valores de gravidade

Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.

## <a name="forwarding-report"></a>Encaminhando relatório

O **relatório de encaminhamento** mostra as mensagens automaticamente encaminhadas de sua organização para domínios externos de caixas de correio do Exchange Online. As mensagens encaminhadas podem representar um risco de segurança ou de conformidade e podem indicar uma conta comprometida.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **relatório de encaminhamento**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Widget de encaminhamento de relatório no painel relatórios](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Exibição de relatório para o relatório de encaminhamento

Os gráficos a seguir estão disponíveis no modo de exibição de relatório:

- **Mostrar dados para: métodos de encaminhamento**: os seguintes métodos são mostrados:

  - **Regra de transporte**: também conhecida como [regras de fluxo de emails](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
  - **Regra de caixa de correio**: também conhecida como [regras de caixa de entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).

  ![Exibição de métodos de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-methods.png)

- **Mostrar dados para: encaminhar domínios**: este modo de exibição mostra os domínios de destinatário que são os destinos para encaminhamento.

  ![Exibição de domínios de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-domains.png)

- **Mostrar dados para: encaminhadores**: os seguintes encaminhadores são mostrados:

  - **Regra de transporte**
  - A caixa de correio que contém a regra de caixa de entrada de encaminhamento.

  ![Exibição de encaminhadores no relatório de encaminhamento](../../media/forwarding-report-forwarders.png)

Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.

### <a name="details-table-view-for-the-forwarding-report"></a>Exibição da tabela de detalhes para o relatório de encaminhamento

Se você clicar em **Exibir tabela de detalhes** em um modo de exibição de relatório, as seguintes informações serão exibidas:

- **Encaminhadores**: a **regra de transporte** de valor ou a caixa de correio que contém a regra de caixa de entrada de encaminhamento.
- **Tipo de encaminhamento**: a **regra de caixa de correio** de valor ou a **regra de transporte**.
- **Nome do destinatário**
- **Domínio do destinatário**
- **Detalhes**: Este é o valor de GUID da regra de fluxo de emails ou o valor RuleIdentity da regra de caixa de entrada.
- **Count**
- **Primeira data de encaminhamento**

Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.

Para voltar para o modo de exibição relatórios, clique em **Exibir relatório**.

## <a name="mailflow-status-report"></a>Relatório de status do fluxo

O **relatório de status do fluxo** é semelhante ao [relatório de email enviado e recebido](#sent-and-received-email-report), com informações adicionais sobre o email permitido ou bloqueado na borda. Este é o único relatório que contém as informações de proteção de borda e mostra o quanto o email é bloqueado antes de ser permitido ao serviço para avaliação pelo Exchange Online Protection (EOP). É importante entender que, se uma mensagem for enviada para cinco destinatários, contaremos como cinco mensagens diferentes e não uma mensagem.  
Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **fluxo relatório de status**. Para ir diretamente para o **relatório de status de fluxo de emails**, abra <https://protection.office.com/mailflowStatusReport> .

![Widget relatório de status do fluxo no painel relatórios](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Modo de exibição de tipo para o relatório de status fluxo

Quando você abre o relatório, a guia **tipo** é selecionada por padrão. Por padrão, este modo de exibição contém um gráfico e uma tabela de dados que é configurada com os seguintes filtros:

- **Data**: os últimos 7 dias.
- **Direção**:

  - **Entrada**
  - **Saída**
  - **Intra-org**: essa contagem é para mensagens dentro de um locatário, ou seja, o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de **entrada** e **saída**)

- **Tipo**:

  - **Boa mensagem**
  - **Malware**
  - **Spam**
  - **Proteção de borda**
  - **Mensagens de regra**
  - **Email de phishing**

O gráfico é organizado pelos valores de **tipo** .

Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.

A tabela de dados contém as seguintes informações:

- **Direção**
- **Tipo**
- **24 horas**
- **3 dias**
- **7 dias**
- **15 dias**
- **30 dias**

Se você clicar em **escolher uma categoria para obter mais detalhes**, poderá selecionar os seguintes valores:

- **Email de phishing**: esta seleção leva você para o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).
- **Malware em email**: esta seleção leva você para o [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report).
- **Detecções de spam**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).
- **Bloqueio de spam bloqueado**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).

**Exportar**:

Para o modo de exibição de detalhes, você só pode exportar dados por um dia. Portanto, se você quiser exportar dados por 7 dias, precisará de sete diferentes ações de exportação.

Cada arquivo. csv exportado está limitado a 150.000 linhas. Se os dados desse dia contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.

![Modo de exibição de tipo no relatório de status do fluxo ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Exibição de direção para o relatório de status do fluxo

Se você clicar na guia **direção** , os mesmos filtros padrão do modo de exibição de **tipo** serão usados.

O gráfico é organizado por valores de **direção** .

Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico. Os mesmos filtros do **tipo** de exibição são usados.

A tabela de dados contém as mesmas informações do **tipo** de exibição.

A **escolha uma categoria para obter detalhes sobre** as seleções e o comportamento disponíveis são os mesmos que o modo de exibição de **tipo** .

**Exportar**:

Para o modo de exibição de detalhes, você só pode exportar dados por um dia. Portanto, se você quiser exportar dados por 7 dias, precisará de sete diferentes ações de exportação.

Cada arquivo. csv exportado está limitado a 150.000 linhas. Se os dados desse dia contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.

![Exibição de direção no relatório de status do fluxo ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Exibição de funil para o relatório de status fluxo

O modo de exibição do **funil** mostra como os recursos de proteção contra ameaças de email da Microsoft filtram os emails de entrada e de saída em sua organização. Ele fornece detalhes sobre a contagem total de emails e como os recursos de proteção contra ameaças configuradas, incluindo proteção de borda, Antimalware, anti-phishing, antispam e anti-falsificação, afetam essa contagem.

Se você clicar na guia **funil** , por padrão, este modo de exibição contém um gráfico e uma tabela de dados que é configurada com os seguintes filtros:

- **Data**: os últimos 7 dias.

- **Direção**:

  - **Entrada**
  - **Saída**
  - **Intra-org**: essa contagem é para mensagens enviadas dentro de um locatário; ou seja, o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de entrada e saída).

O modo de exibição de agregação e o modo de exibição de tabela de dados permitem 90 dias de filtragem.

Se você clicar em **filtro**, poderá filtrar tanto o gráfico quanto a tabela de dados.

Este gráfico mostra a contagem de emails organizada por:

  - **Email total**
  - **Email após proteção de borda**
  - **Email após anti-malware, reputação de arquivo, bloco de tipo de arquivo**
  - **Email após anti-Phish, reputação da URL, representação da marca, antifalsificação**
  - **Email após anti-spam, filtragem de email em massa**
  - **Email após representação de usuário e domínio**<sup>1</sup>
  - **Email após arquivo e URL acionamento**<sup>1</sup>
  - **Email detectado como benigno após a proteção após a entrega (URL clique em proteção de tempo)**

<sup>1</sup> somente o Office 365 ATP

Para exibir o email filtrado por EOP ou ATP separadamente, clique no valor na legenda do gráfico.

A tabela de dados contém as informações a seguir, mostradas em ordem decrescente de data:

 - **Date**
 - **Email total**
 - **Proteção de borda**
 - **Anti-malware, reputação de arquivo, bloco de tipo de arquivo**
 - **Anti-Phish, reputação da URL, representação da marca, anti-falsificação**
 - **Anti-spam, filtragem de email em massa**
 - **Personificação de usuário e domínio (ATP)**
 - **Arquivo e URL acionamento (ATP)**
 - **Proteção de post-entrega e ZAP (ATP) ou ZAP (EOP)**

Se você selecionar uma linha na tabela de dados, uma divisão adicional das contagens de email será mostrada no submenu.

**Exportar**:

Depois de clicar em **Exportar** em **Opções**, você pode selecionar um dos seguintes valores:

- **Resumo (com dados dos últimos 90 dias no máximo)**
- **Detalhes (com dados nos últimos 30 dias)**

Em **Data**, escolha um intervalo e clique em **aplicar**. Os dados dos filtros atuais serão exportados para um arquivo. csv.

Cada arquivo. csv exportado está limitado a 150.000 linhas. Se os dados contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.

 ![Exibição do funil no relatório de status do fluxo ](../../media/mail-flow-status-report-funnel-view.png)

 ### <a name="tech-view-for-the-mailflow-status-report"></a>Exibição de Tech para o relatório de status do fluxo

O **modo de exibição técnico** é semelhante ao modo de exibição do **funil** , fornecendo detalhes mais granulares para os recursos configurados de proteção contra ameaças. No gráfico, você pode ver como as mensagens são categorizadas em diferentes estágios de proteção contra ameaças.

Se você clicar na guia **Tech View** , por padrão, este modo de exibição contém um gráfico e uma tabela de dados que é configurada com os seguintes filtros:

- **Data**: os últimos 7 dias.

- **Direção**:

  - **Entrada**
  - **Saída**
  - **Intra-org**: essa contagem é para mensagens dentro de um locatário, ou seja, o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de entrada e saída)

O modo de exibição de agregação e o modo de exibição de tabela de dados permitem 90 dias de filtragem.

Se você clicar em **filtro**, poderá filtrar tanto o gráfico quanto a tabela de dados.

Este gráfico mostra as mensagens organizadas nas seguintes categorias:

  - **Email total**
  - **Permitir borda, borda filtrada**
  - **Não é malware, detecção de anexos seguros (ATP), detecção de mecanismo Antimalware, bloco de regras**
  - **Não Phish, falha DMARC, detecção de personificação, detecção de falsificação, detecção de phishing**
  - **Nenhuma detecção com a URL acionamento, detecção de acionamento de URL (ATP)**
  - **Não spam, spam**
  - **Email não mal-intencionado, detecção de links seguros (ATP), ZAP**

Ao passar o mouse sobre uma categoria no gráfico, você pode ver o número de mensagens nessa categoria.

A tabela de dados contém as informações a seguir, mostradas em ordem decrescente de data:

  - **Date**  
  - **Email total**
  - **Borda filtrada**
  - **Mecanismo Antimalware, anexos seguros, regra filtrada**
  - **DMARC, representação, falsificação, phishing filtrado**
  - **Detecção de URL acionamento**
  - **Filtrado por antispam**
  - **ZAP removido**
  - **Detecção por links seguros**

Se você selecionar uma linha na tabela de dados, uma divisão adicional das contagens de email será mostrada no submenu.

**Exportar**:

Ao clicar em **Exportar**, em **Opções** , você pode selecionar um dos seguintes valores:

- **Resumo (com dados dos últimos 90 dias no máximo)**
- **Detalhes (com dados nos últimos 30 dias)**

Em **Data**, escolha um intervalo e clique em **aplicar**. Os dados dos filtros atuais serão exportados para um arquivo. csv.

Cada arquivo. csv exportado está limitado a 150.000 linhas. Se os dados contiverem mais de 150.000 linhas, vários arquivos. csv serão criados.

 ![Exibição de Tech no relatório de status do fluxo ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>Relatório de email enviado e recebido

O relatório de **email enviado e recebido** é um relatório inteligente que mostra informações sobre emails de entrada e saída, incluindo detecções de spam, malware e email identificados como "bom". A diferença entre este relatório e o [relatório de status do fluxo](#mailflow-status-report) é: este relatório não inclui dados sobre mensagens bloqueadas pela proteção de borda.

O modo de exibição de agregação e o modo de exibição de detalhes do relatório permitem que 90 dias de filtragem.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **email enviado e recebido**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![Widget email enviado e recebido no painel relatórios](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Exibição de relatório para o relatório de email enviado e recebido

Os gráficos a seguir estão disponíveis no modo de exibição de relatório:

- **Divisão por: digite**: o gráfico mostra todas as categorias disponíveis:

  - **Total**
  - **Boa mensagem**
  - **Malware (anti-malware)** (EOP)
  - **Detecções de spam**
  - **Mensagens de regra**
  - **Malware avançado** (Office 365 ATP)

  Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes desse dia.

  ![Exibição de tipo no relatório de email enviado e recebido](../../media/sent-and-received-email-report-type-view.png)

- **Divisão por: direção**: o gráfico mostra os dados **total**, de **entrada**e de **saída** . Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes desse dia.

  ![Exibição de direção no relatório de email enviado e recebido](../../media/sent-and-received-email-report-direction-view.png)

- **Aprofundar por** \> **Malware (Antimalware)**: esta seleção leva você para as [detecções de malware no relatório de email](view-email-security-reports.md#malware-detections-in-email-report).

- **Aprofundar por** \> **Detecções de spam)**: esta seleção leva você para o [relatório de detecções de spam](view-email-security-reports.md#spam-detections-report).

Se você clicar em **filtros** em um modo de exibição de relatório, poderá modificar os resultados com os seguintes filtros:

- **Data de início** e **data de término**
- Valores de direção
- Valores de tipo

Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Exibição da tabela de detalhes para o relatório de email enviado e recebido

Se você clicar em **Exibir tabela de detalhes** na tela **dividir por: direção** ou **dividir em: direção** , as seguintes informações são mostradas:

- **Data (UTC)**
- **Tipo**
- **Direção**
- **Contagem de mensagem**

Se você clicar em **filtros** em um modo de exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:

- **Data de início** e **data de término**
- Valores de direção
- Valores de tipo

Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.

## <a name="top-senders-and-recipients-report"></a>Relatório de principais remetentes e destinatários

O relatório de **remetentes e destinatários principais** é um gráfico de pizza mostrando seus principais remetentes e destinatários de email.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **os principais remetentes e destinatários**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![Widget principais remetentes e destinatários no painel relatórios](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Exibição de relatório para os principais remetentes e o relatório de destinatários

Os gráficos a seguir estão disponíveis no modo de exibição de relatório:

- **Mostrar dados para os \> principais remetentes de email**
- **Mostrar dados para \> destinatários de email principais**
- **Mostrar dados para \> os principais destinatários de spam**
- **Mostrar dados para \> Principais destinatários de malware** (EOP)
- **Mostrar dados para \> Principais destinatários de malware (ATP)** (Office 365 ATP)

A composição do gráfico de pizza é alterada com base nessas seleções.

Ao passar o mouse sobre uma fatia no gráfico de pizza, você pode ver uma contagem de mensagens enviadas ou recebidas.

Se você clicar em **filtros** em um modo de exibição de relatório, poderá especificar um intervalo de datas com **data de início** e data de **término**.

![Gráfico de pizza no modo de exibição de relatório no relatório de remetentes e destinatários principais](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Exibição da tabela de detalhes para os principais remetentes e o relatório de destinatários

Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:

- **Mostrar dados para os \> principais remetentes de email**

  - **Principais remetentes de email**
  - **Count**

- **Mostrar dados para \> destinatários de email principais**

  - **Principais destinatários de email**
  - **Count**

- **Mostrar dados para \> os principais destinatários de spam**

  - **Principais destinatários de spam**
  - **Count**

- **Mostrar dados para \> Principais destinatários de malware** (EOP)

  - **Principais destinatários de malware**
  - **Count**

- **Mostrar dados para \> Principais destinatários de malware (ATP)** (Office 365 ATP)

  - **Principais destinatários de malware (ATP)**
  - **Count**

Se você clicar em **filtros** em um modo de exibição de tabela detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.

Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Quais permissões são necessárias para exibir esses relatórios?

Para exibir e usar os relatórios, você precisa ser membro do grupo de função especificado no centro de conformidade e segurança & **e** no Exchange Online.

- No centro de conformidade & segurança, você precisa ser membro de um dos seguintes grupos de função:

  – Gerenciamento de organização-administrador de segurança (você também pode fazer isso no [centro de administração do Azure Active Directory](https://aad.portal.azure.com) -leitor de segurança

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

- No Exchange Online, você precisa ser membro de um dos grupos de função a seguir:

  – Gerenciamento de organização – gerenciamento de organização somente de exibição-somente os destinatários do gerenciamento de conformidade

Para obter mais informações, consulte [permissões no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) e [gerenciar grupos de função no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

## <a name="related-topics"></a>Tópicos relacionados

[Relatórios inteligentes e insights no Centro de Conformidade e Segurança](reports-and-insights-in-security-and-compliance.md)

[Insights de fluxo de emails no Centro de Conformidade e Segurança](mail-flow-insights-v2.md)

[Exibir relatórios de segurança de email no centro de conformidade & segurança](view-email-security-reports.md)

[Exibir relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md)
