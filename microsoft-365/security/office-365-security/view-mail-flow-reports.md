---
title: Exibir relatórios de fluxo de emails no painel Relatórios
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender sobre os relatórios de fluxo de emails disponíveis no painel Relatórios no Centro de Conformidade & Segurança.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38beac44af191a027db722ade25ca7fd0e505d9b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245667"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Exibir relatórios de fluxo de emails no painel Relatórios no Centro de Conformidade & Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Além dos relatórios de fluxo de emails [](mail-flow-insights-v2.md) que estão disponíveis no painel de fluxo de email no Centro de Conformidade e segurança, uma variedade de relatórios de fluxo de emails adicionais estão disponíveis no painel Relatórios para ajudá-lo a monitorar sua organização Microsoft 365. &

Se você tiver as [permissões](#what-permissions-are-needed-to-view-these-reports)necessárias, poderá exibir esses relatórios no Centro de Conformidade e Segurança [&](https://protection.office.com) indo para **Painel de** \> **Relatórios.** Para ir diretamente para o painel Relatórios, abra <https://protection.office.com/insightdashboard> .

![Painel de relatórios no Centro de Conformidade & Segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Relatório do conector

O **relatório conector** mostra a atividade de fluxo de emails nos conectores de entrada e de saída [configurados](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) para sua organização.

Para exibir o relatório, abra o Centro de Conformidade & [Segurança,](https://protection.office.com)vá **para** Painel de Relatórios e selecione \>  Relatório do **Conector.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ConnectorReport> .

![Widget de relatório do conector no painel Relatórios](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Exibição de relatório para o relatório conector

Os gráficos a seguir estão disponíveis no relatório:

- **Exibir dados por: Fluxo de emails**: Este gráfico mostra o número de mensagens de entrada e de saída organizadas por:

  - **Total**
  - **Da Internet sem um conector**
  - **Para a Internet sem um conector**
  - Um conector específico que você configurou.

  Para isolar os dados no gráfico, use o **controle Mostrar dados** para selecionar uma dessas opções ou Todo o fluxo de **emails.**

  ![Exibir dados por fluxo de emails no relatório conector](../../media/connector-report-view-data-by-mail-flow.png)

- **Exibir dados por: uso de TLS**: Este gráfico mostra a porcentagem de uso da versão TLS (Transport Layer Security) para o fluxo de emails.

  Para isolar os dados no gráfico, use o **controle Mostrar dados** para selecionar uma das seguintes opções:

  - **Todo o fluxo de emails**
  - **Da Internet sem um conector**
  - **Para a Internet sem um conector**
  - Um conector específico que você configurou.

  ![Exibir dados por uso TLS no relatório conector](../../media/connector-report-view-data-by-tls-usage.png)

Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**

### <a name="details-table-view-for-the-connector-report"></a>Exibição de tabela de detalhes para o relatório conector

Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:

- **Date**
- **Nome e direção do conector**
- **Tipo de conector**
- **TLS forçado?**: O valor **True** ou **False**.
- **Sem TLS** (porcentagem)
- **TLS 1.0** (porcentagem)
- **TLS 1.1** (porcentagem)
- **TLS 1.2** (porcentagem)
- **Volume**: o número de mensagens.

Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**

Para voltar à exibição de relatório, clique em **Exibir relatório**.

## <a name="exchange-transport-rule-report"></a>Exchange relatório de regra de transporte

O **Exchange** de regra de transporte mostra o efeito das regras de fluxo de emails (também conhecidas como regras de transporte) em mensagens de entrada e saída em sua organização.

Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & Segurança, vá para Painel de Relatórios e \>  selecione Exchange Regra **de Transporte.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Exchange de regra de transporte no painel Relatórios](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Exibição de relatório para o relatório Exchange regra de transporte

Os gráficos a seguir estão disponíveis no relatório:

- **Exibir dados por: Exchange de transporte** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by transport rules.

- **Exibir dados por: Exchange de transporte** \> **Break down by: Severity**: This chart shows the number of **High severity** and **Medium severity**, and **Low severity** messages. Você definirá o nível de gravidade como uma ação na regra (**Audite essa** regra com nível de gravidade ou _SetAuditSeverity_). Para obter mais informações, consulte [Ações de regra de fluxo de email em Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Exibir dados por: DLP Exchange de transporte** \> **Break down by: Direction**: This chart shows the number of **Inbound** and **Outbound** messages that were affected by data loss prevention (DLP) transport rules. Você pode refinar ainda mais o gráfico selecionando as seguintes opções:

  - **Mostrar dados para: Todas as regras de transporte de DLP**
  - **Mostrar dados para: usuários comprometidos**
  - **Mostrar dados para: Baixo volume de conteúdo detectado na Lei Patriot Dos EUA**

- **Exibir dados por: DLP Exchange de transporte** \> **Break down by: Direction**: This view shows the number of **High severity** and **Medium severity**, and **Low severity** messages that were affected by DLP transport rules. Você pode refinar ainda mais o gráfico selecionando as seguintes opções:

  - **Mostrar dados para: Todas as regras de transporte de DLP**
  - **Mostrar dados para: usuários comprometidos**
  - **Mostrar dados para: Baixo volume de conteúdo detectado na Lei Patriot Dos EUA**

Se você clicar **em Filtros** em um exibição de relatório, poderá modificar os resultados com os seguintes filtros::

- **Data de início** **e data de término**
- Valores de direção
- Valores de severidade

![Exibir relatório no relatório Exchange regra de transporte](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Exibição de tabela de detalhes para o relatório Exchange regra de transporte

Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:

- **Exibir dados por: Exchange Regras de Transporte**:

  - **Date**
  - **Regra de transporte**
  - **Assunto**
  - **Endereço do remetente**.
  - **Endereço do destinatário**
  - **Gravidade**
  - **Direção**

- **Exibir dados por: DLP Exchange de transporte**:

  - **Date**
  - **Política DLP**
  - **Regra de transporte**
  - **Assunto**
  - **Endereço do remetente**.
  - **Endereço do destinatário**
  - **Gravidade**
  - **Direção**

Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:

- **Data de início** **e data de término**
- Valores de direção
- Valores de severidade

Para voltar à exibição de relatório, clique em **Exibir relatório**.

## <a name="forwarding-report"></a>Relatório de encaminhamento

O **relatório de encaminhamento** mostra as mensagens encaminhadas automaticamente da sua organização para domínios externos Exchange Online caixas de correio. As mensagens encaminhadas podem representar um risco de segurança ou conformidade e podem indicar uma conta comprometida.

Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & Segurança, vá para Painel de \>  Relatórios e selecione Relatório **de Encaminhamento.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Widget de relatório de encaminhamento no painel Relatórios](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Exibição de relatório para o relatório de encaminhamento

Os gráficos a seguir estão disponíveis na exibição de relatório:

- **Mostrar dados para: métodos de encaminhamento**: Os seguintes métodos são mostrados:

  - **Regra de transporte**: Também conhecidas como regras [de fluxo de emails.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - **Regra de caixa de** correio : Também conhecidas como [regras de Caixa de Entrada](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).

  ![Modo de exibição de métodos de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-methods.png)

- **Mostrar dados para: Domínios de** encaminhamento : Esta exibição mostra os domínios do destinatário que são os destinos para encaminhamento.

  ![Exibição de domínios de encaminhamento no relatório de encaminhamento](../../media/forwarding-report-forwarding-domains.png)

- **Mostrar dados para: Encaminhadores**: Os seguintes encaminhadores são mostrados:

  - **Regra de transporte**
  - A caixa de correio que contém a regra de Caixa de Entrada de encaminhamento.

  ![Exibição de encaminhadores no relatório de encaminhamento](../../media/forwarding-report-forwarders.png)

Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**

### <a name="details-table-view-for-the-forwarding-report"></a>Exibição de tabela de detalhes para o relatório de encaminhamento

Se você clicar em **Exibir tabela de detalhes** em uma exibição de relatório, as seguintes informações serão mostradas:

- **Encaminhadores**: a regra **de transporte de** valor ou a caixa de correio que contém a regra de Caixa de Entrada de encaminhamento.
- **Tipo de encaminhamento**: a regra **de caixa de correio de** valor ou a regra de **Transporte.**
- **Nome do destinatário**
- **Domínio de destinatário**
- **Detalhes**: este é o valor GUID da regra de fluxo de emails ou o valor RuleIdentity da regra caixa de entrada.
- **Count**
- **Primeira data de encaminhamento**

Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**

Para voltar à exibição de relatórios, clique em **Exibir relatório**.

## <a name="mailflow-status-report"></a>Relatório de status de fluxo de emails

O **relatório de status de fluxo** de emails é semelhante ao relatório de [email](#sent-and-received-email-report)Enviado e recebido, com informações adicionais sobre emails permitidos ou bloqueados na borda. Este é o único relatório que contém informações de proteção de borda e mostra a quantos emails são bloqueados antes de serem permitidos no serviço para avaliação por Proteção do Exchange Online (EOP). É importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes e não uma mensagem.
Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione Relatório de status de fluxo **de emails.** Para ir diretamente para o relatório de **status de fluxo de email**, abra <https://protection.office.com/mailflowStatusReport> .

![Widget de relatório de status de fluxo de emails no painel Relatórios](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Exibição de tipo para o relatório de status de fluxo de emails

Quando você abre o relatório, a guia **Tipo** é selecionada por padrão. Por padrão, esse modo de exibição contém um gráfico e uma tabela de dados configurada com os seguintes filtros:

- **Data**: os últimos 7 dias.
- **Direção**:

  - **Entrada**
  - **Saída**
  - **Intra-org**: essa contagem é para mensagens dentro de um locatário ou seja, remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de **Entrada** e **Saída**)

- **Tipo**:

  - **Bom email**
  - **Malware**
  - **Spam**
  - **Proteção de borda**
  - **Mensagens de regra**
  - **Email de phishing**

O gráfico é organizado pelos valores **Type.**

Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico.

A tabela de dados contém as seguintes informações:

- **Direção**
- **Tipo**
- **24 horas**
- **3 dias**
- **7 dias**
- **15 dias**
- **30 dias**

Se você clicar **em Escolher uma categoria para obter** mais detalhes, você poderá selecionar entre os seguintes valores:

- **Email de phishing**: essa seleção o leva ao relatório de [status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)
- **Malware no email**: essa seleção o leva ao relatório de [status de proteção contra ameaças.](view-email-security-reports.md#threat-protection-status-report)
- **Detecções de** spam: essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)
- **Spam bloqueado de borda:** essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)

**Exportar**:

Para a exibição de detalhes, você só pode exportar dados por um dia. Portanto, se você quiser exportar dados por 7 dias, precisará fazer 7 ações de exportação diferentes.

Cada arquivo .csv é limitado a 150.000 linhas. Se os dados desse dia contiver mais de 150.000 linhas, vários arquivos .csv serão criados.

![Type view in the Mailflow status report](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Exibição de direção para o relatório de status de fluxo de emails

Se você clicar na guia **Direção,** os mesmos filtros padrão do modo de exibição **Tipo** serão usados.

O gráfico é organizado pelos **valores Direction.**

Você pode alterar esses filtros clicando em **Filtrar** ou clicando em um valor na legenda do gráfico. Os mesmos filtros do modo **de exibição Type** são usados.

A tabela de dados contém as mesmas informações do modo **de exibição Tipo.**

A **opção Escolher uma categoria para obter** mais detalhes sobre as seleções e o comportamento disponíveis são os mesmos que o modo de **exibição Tipo.**

**Exportar**:

Para a exibição de detalhes, você só pode exportar dados por um dia. Portanto, se você quiser exportar dados por 7 dias, precisará fazer 7 ações de exportação diferentes.

Cada arquivo .csv é limitado a 150.000 linhas. Se os dados desse dia contiver mais de 150.000 linhas, vários arquivos .csv serão criados.

![Exibição de direção no relatório de status de fluxo de emails](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Exibição de funil para o relatório de status de fluxo de emails

A **exibição** Funil mostra como os recursos de proteção contra ameaças de email da Microsoft filtram emails de entrada e saída em sua organização. Ele fornece detalhes sobre a contagem total de emails e como os recursos de proteção contra ameaças configurados, incluindo proteção de borda, anti-malware, anti-phishing, anti-spam e anti-spoofing afetam essa contagem.

Se você clicar na guia **Funil,** por padrão, esse modo de exibição conterá um gráfico e uma tabela de dados configurada com os seguintes filtros:

- **Data**: os últimos 7 dias.

- **Direção**:

  - **Entrada**
  - **Saída**
  - **Intra-org**: esta contagem é para mensagens enviadas dentro de um locatário; Ou seja, o remetente abc@domain.com envia para o destinatário xyz@domain.com (contado separadamente de Entrada e Saída).

A exibição agregada e a exibição da tabela de dados permitem 90 dias de filtragem.

Se você clicar **em Filtrar,** poderá filtrar o gráfico e a tabela de dados.

Este gráfico mostra a contagem de emails organizada por:

- **Total de emails**
- **Email após proteção de borda**
- **Email após anti-malware, reputação de arquivo, bloco de tipo de arquivo**
- **Email após anti-phishing, reputação de URL, representação de marca, anti-spoof**
- **Email após anti-spam, filtragem de email em massa**
- **Email após a representação de usuário e domínio**<sup>1</sup>
- **Email após a detonação de arquivo e URL**<sup>1</sup>
- **Email detectado como benigno após a proteção pós-entrega (proteção de tempo de clique na URL)**

<sup>1</sup> Defender para Office 365 somente

Para exibir o email filtrado por EOP ou Defender Office 365 separadamente, clique no valor na legenda do gráfico.

A tabela de dados contém as seguintes informações, mostradas na ordem de data decrescente:

- **Date**
- **Total de emails**
- **Proteção de borda**
- **Anti-malware, reputação de arquivo, bloco de tipo de arquivo**:
  - **Reputação do** arquivo : Mensagens filtradas devido à identificação de um arquivo anexado por outros clientes da Microsoft.
  - **Bloco de tipo de** arquivo : Mensagens filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.
- **Anti-phish, reputação de URL, representação de marca, anti-spoof**:
  - **Reputação da URL**: Mensagens filtradas devido à identificação da URL por outros clientes da Microsoft.
  - **Representação de marca**: Mensagens filtradas devido à mensagem proveniente de uma marca conhecida que representa os senders.
  - **Anti-spoof**: Mensagens filtradas devido à mensagem que está tentando fazer a spoof de um domínio que o destinatário pertence ou a um domínio que o remetente da mensagem não possui.
- **Anti-spam, filtragem de email em massa:**
  - **Filtragem em massa de** emails : Mensagens filtradas devido a uma tentativa de entregar emails em massa para seus destinatários.
- **Representação de usuário e domínio (Defender para Office 365)**:
  - **Representação do** usuário : Mensagens filtradas devido a uma tentativa de representar um usuário (remetente de mensagem) definido nas configurações de proteção de representação de uma política anti-phishing.
  - **Representação de domínio**: Mensagens filtradas devido a uma tentativa de representar um domínio definido nas configurações de proteção de representação de uma política anti-phishing.
- **Detonação de arquivo e URL (Defender para Office 365)**:
  - **Detonação de** arquivo : Mensagens filtradas por uma política Cofre Anexos.
  - **Detonação de URL**: Mensagem filtrada por uma política Cofre Links.
- **Proteção pós-entrega e ZAP (ATP) ou ZAP (EOP)**: ZAP indica limpeza automática de zero hora.

Se você selecionar uma linha na tabela de dados, uma nova divisão das contagens de email será mostrada no sobrevoo.

**Exportar**:

Depois de clicar **em Exportar** **em Opções,** selecione um dos seguintes valores:

- **Resumo (com dados dos últimos 90 dias no máximo)**
- **Detalhes (com dados dos últimos 30 dias no máximo)**

Em **Data**, escolha um intervalo e clique em **Aplicar**. Os dados dos filtros atuais serão exportados para um arquivo .csv.

Cada arquivo .csv é limitado a 150.000 linhas. Se os dados contiver mais de 150.000 linhas, vários arquivos .csv serão criados.

 ![Exibição de funil no relatório de status de fluxo de emails](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a>Exibição técnica do relatório de status mailflow

O **modo de exibição** Tech é semelhante ao modo de exibição **Funil,** fornecendo detalhes mais granulares para os recursos configurados de proteções contra ameaças. No gráfico, você pode ver como as mensagens são categorizadas nos diferentes estágios da proteção contra ameaças.

Se você clicar na **guia Modo de** Exibição de Tecnologia, por padrão, esse modo de exibição conterá um gráfico e uma tabela de dados configurada com os seguintes filtros:

- **Data**: os últimos 7 dias.

- **Direção**:

  - **Entrada**
  - **Saída**
  - **Intra-org**: essa contagem é para mensagens dentro de um locatário ou seja, remetente abc@domain.com envia ao destinatário xyz@domain.com (contado separadamente de Entrada e Saída)

A exibição agregada e a exibição da tabela de dados permitem 90 dias de filtragem.

Se você clicar **em Filtrar,** poderá filtrar o gráfico e a tabela de dados.

Este gráfico mostra mensagens organizadas nas seguintes categorias:

- **Total de emails**
- **Permitir borda** e **Borda filtrada**
- **Não malware,** **Cofre de anexos,** <sup>\*</sup> detecção de mecanismo **anti-malware** e **mensagens de regra**
- **Não phish**, **falha de DMARC,** detecção de **representação,** detecção **de spoof** e **detecção de phishing**
- **Nenhuma detecção com detonação de URL** e detecção **de detonação de URL**<sup>\*</sup>
- **Não spam** e  **spam**
- **Email não mal-intencionado,** **Cofre de links** e <sup>\*</sup> **ZAP**

<sup>\*</sup>Defender para Office 365

Ao passar o mouse sobre uma categoria no gráfico, você pode ver o número de mensagens nessa categoria.

A tabela de dados contém as seguintes informações, mostradas na ordem de data decrescente:

- **Date**
- **Total de emails**
- **Borda filtrada**
- **Mecanismo anti-malware, Cofre anexos, regra filtrada**:
  - **Regra filtrada**: Mensagens filtradas devido a regras de fluxo de emails (também conhecidas como regras de transporte).
- **DMARC, representação, spoof, phish filtered**:
  - **DMARC**: Mensagens filtradas devido à falha da mensagem em sua verificação de autenticação DMARC.
- **Detecção de detonação de URL**
- **Anti-spam filtrado**
- **ZAP removido**
- **Detecção por Cofre Links**

Se você selecionar uma linha na tabela de dados, uma nova divisão das contagens de email será mostrada no sobrevoo.

**Exportar**:

Ao clicar em **Exportar**, em **Opções,** você pode selecionar um dos seguintes valores:

- **Resumo (com dados dos últimos 90 dias no máximo)**
- **Detalhes (com dados dos últimos 30 dias no máximo)**

Em **Data**, escolha um intervalo e clique em **Aplicar**. Os dados dos filtros atuais serão exportados para um arquivo .csv.

Cada arquivo .csv é limitado a 150.000 linhas. Se os dados contiver mais de 150.000 linhas, vários arquivos .csv serão criados.

 ![Exibição técnica no relatório de status do fluxo de mensagens](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>Relatório de email enviado e recebido

O **relatório de email** enviado e recebido é um relatório inteligente que mostra informações sobre emails de entrada e saída, incluindo detecções de spam, malware e email identificados como "bons". A diferença entre este relatório e o relatório de status de [fluxo](#mailflow-status-report) de emails é: este relatório não inclui dados sobre mensagens bloqueadas pela proteção de borda. É importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como uma mensagem.

A exibição agregada e a exibição detalhada do relatório permitem 90 dias de filtragem.

Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione Enviar e **receber emails**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![Widget de email enviado e recebido no painel Relatórios](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Exibição de relatório para o relatório de email enviado e recebido

Os gráficos a seguir estão disponíveis na exibição de relatório:

- **Break down by: Type**: O gráfico mostra todas as categorias disponíveis:

  - **Total**
  - **Bom email**
  - **Malware (anti-malware)** (EOP)
  - **Detecções de spam**
  - **Mensagens de regra**
  - **Malware avançado** (Microsoft Defender para Office 365)

  Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes para esse dia.

  ![Type view in the Sent and received email report](../../media/sent-and-received-email-report-type-view.png)

- **Break down by: Direction**: The chart shows **Total**, **Inbound**, and **Outbound** data. Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver detalhes para esse dia.

  ![Exibição de direção no relatório de email enviado e recebido](../../media/sent-and-received-email-report-direction-view.png)

- **Detalhar por** \> **Malware (anti-malware)**: essa seleção leva você para as detecções [de malware no relatório de email.](view-email-security-reports.md#malware-detections-in-email-report)

- **Detalhar por** \> **Detecções de spam)**: essa seleção o leva ao relatório de [Detecções de Spam.](view-email-security-reports.md#spam-detections-report)

Se você clicar **em Filtros** em um exibição de relatório, poderá modificar os resultados com os seguintes filtros:

- **Data de início** **e data de término**
- Valores de direção
- Valores de tipo

Para voltar à exibição de relatório, clique em **Exibir relatório**.

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Exibição de tabela de detalhes para o relatório de email enviado e recebido

Se você clicar **em Exibir tabela de** detalhes na tabela Break down **by: Direction** or Break down **by: Direction** view, the following information is shown:

- **Data (UTC)**
- **Tipo**
- **Direção**
- **Contagem de mensagem**

Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:

- **Data de início** **e data de término**
- Valores de direção
- Valores de tipo

Para voltar à exibição de relatório, clique em **Exibir relatório**.

## <a name="top-senders-and-recipients-report"></a>Relatório de destinatários e destinatários principais

O **relatório Principais destinatários e destinatários** é um gráfico de pizza mostrando seus principais destinatários e destinatários de email.

Para exibir o relatório, abra o [Centro](https://protection.office.com)de  Conformidade & segurança, vá para Painel de Relatórios e \>  selecione **Principais destinatários e destinatários.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![Principais destinatários e destinatários do widget no painel Relatórios](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Exibição de relatório para os principais destinatários e destinatários

Os gráficos a seguir estão disponíveis na exibição de relatório:

- **Mostrar dados para \> os principais envios de email**
- **Mostrar dados para \> os principais destinatários de email**
- **Mostrar dados para \> os principais destinatários de spam**
- **Mostrar dados para \> Principais destinatários de malware** (EOP)
- **Mostrar dados para \> os principais destinatários de malware (Defender para Office 365)**

A composição do gráfico de pizza muda com base nessas seleções.

Ao passar o mouse sobre uma cunha no gráfico de pizza, você pode ver uma contagem de mensagens enviadas ou recebidas.

Se você clicar **em Filtros** em um exibição de relatório, poderá especificar um intervalo de datas com **Data de** Início e Data **de Término.**

![Gráfico de pizza no relatório no relatório Principais destinatários e destinatários](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Exibição de tabela de detalhes para o relatório de destinatários e destinatários principais

Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:

- **Mostrar dados para \> os principais envios de email**

  - **Principais envios de email**
  - **Count**

- **Mostrar dados para \> os principais destinatários de email**

  - **Principais destinatários de email**
  - **Count**

- **Mostrar dados para \> os principais destinatários de spam**

  - **Principais destinatários de spam**
  - **Count**

- **Mostrar dados para \> Principais destinatários de malware** (EOP)

  - **Principais destinatários de malware**
  - **Count**

- **Mostrar dados para \> os principais destinatários de malware (Defender para Office 365)**

  - **Principais destinatários de malware (Defender para Office 365)**
  - **Count**

Se você clicar **em Filtros** em um exibição de tabela de detalhes, poderá especificar um intervalo de datas com **Data de** início e data **de término.**

Para voltar à exibição de relatório, clique em **Exibir relatório**.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Quais permissões são necessárias para exibir esses relatórios?

Para exibir e usar os relatórios descritos neste artigo, você precisa ser membro de um dos seguintes grupos de funções no Centro de Conformidade & Segurança:

- **Organization Management**
- **Administrador de Segurança**
- **Leitor de Segurança**
- **Leitor Global**

Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="related-topics"></a>Tópicos relacionados

[Relatórios inteligentes e insights no Centro de Conformidade e Segurança](reports-and-insights-in-security-and-compliance.md)

[Insights de fluxo de emails no Centro de Conformidade e Segurança](mail-flow-insights-v2.md)

[Exibir relatórios de segurança de email no Centro de Conformidade & Segurança](view-email-security-reports.md)

[Exibir relatórios do Microsoft Defender para Office 365](view-reports-for-mdo.md)
