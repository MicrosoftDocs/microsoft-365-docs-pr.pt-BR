---
title: Exibir relatórios de segurança de email no Centro de Conformidade e Segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Saiba como encontrar e usar relatórios de segurança de email para sua organização. Os relatórios de segurança de email estão disponíveis no Centro de Conformidade & Segurança.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6d9f149c9e1c71532018e6b43a6e9e31eb04607
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290794"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Exibir relatórios de segurança de email no Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Vários relatórios estão disponíveis no Centro de Conformidade e Segurança para ajudá-lo [& a](https://protection.office.com) ver como os recursos de segurança de email, como anti-spam, anti-malware e criptografia no Microsoft 365, estão protegendo sua organização. Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-these-reports)&, poderá exibir esses relatórios no Centro de Conformidade e Segurança indo para o Painel **de** \> **Relatórios.** Para ir diretamente para o painel Relatórios, abra <https://protection.office.com/insightdashboard> .

![Painel relatórios no Centro de Conformidade & segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Relatório de usuários comprometidos

> [!NOTE]
> Esse relatório está disponível em organizações do Microsoft 365 com caixas de correio do Exchange Online. Ele não está disponível em organizações autônomas do Exchange Online Protection (EOP).

O **relatório De usuários** comprometidos mostra o  número de contas de usuário que foram marcadas como **Suspeitas** ou Restritas nos últimos 7 dias. As contas em qualquer um desses estados são problemáticas ou até mesmo comprometidas. Com o uso frequente, você pode usar o relatório para detectar picos e até tendências, em contas suspeitas ou restritas. Para obter mais informações sobre usuários comprometidos, consulte [Respondendo a uma conta de email comprometida.](responding-to-a-compromised-email-account.md)

![Widget de usuários comprometidos no painel Relatórios](../../media/compromised-users-report-widget.png)

A exibição agregada mostra os dados dos últimos 90 dias e a exibição detalhada mostra os dados dos últimos 30 dias.

Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione Usuários  \>  **comprometidos.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=CompromisedUsers> .

Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando um ou mais dos seguintes valores:

- **Data de início** e **data de término**

- **Suspeito:** a conta de usuário enviou emails suspeitos e corre o risco de ser restringida de enviar emails.

- **Restrito:** a conta de usuário foi restringida de enviar emails devido a padrões altamente suspeitos.

![Exibição de relatório no relatório De usuários comprometidos](../../media/compromised-users-report-activity-view.png)

Se você clicar **em Exibir tabela de** detalhes, poderá ver os seguintes detalhes:

- **Hora de criação**
- **ID de usuário**
- **Ação**

Para voltar para a exibição de relatório, clique em **Exibir relatório**.

## <a name="encryption-report"></a>Relatório de criptografia

O **relatório de criptografia** está disponível no EOP (assinaturas com caixas de correio no Exchange Online ou no EOP autônomo sem caixas de correio do Exchange Online). A equipe de segurança da sua organização pode usar as informações nesse relatório para identificar padrões e aplicar ou ajustar proativamente políticas para mensagens de email confidenciais. Por exemplo:

- Se você vir um grande número de mensagens de email criptografadas por usuários, talvez queira adicionar uma política de criptografia para automatizar a criptografia para determinados casos de uso. Para saber mais, confira [Definir regras de fluxo de emails para criptografar mensagens de email no Microsoft 365.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)

- Se você tiver vários modelos de criptografia disponíveis, mas ninguém os estiver usando, poderá explorar se os usuários precisam de treinamento de recursos.

A exibição agregada permite a filtragem dos últimos 90 dias, enquanto a exibição de detalhes permite a filtragem por 10 dias.

Para exibir o relatório, abra o [Centro de Conformidade & Segurança,](https://protection.office.com)vá para o Painel de Relatórios e selecione Relatório de  \>  **criptografia.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=EncryptionReport> .

Para saber mais sobre criptografia, confira [Criptografia de email no Microsoft 365.](../../compliance/email-encryption.md)

### <a name="report-view-for-the-encryption-report"></a>Exibição de relatório para o relatório de criptografia

Você pode usar os seguintes filtros no gráfico:

- **Exibir dados por: Message Encryption Report** and **Break down by: Encryption method**: The following encryption methods are available:

  - **Criptografia por usuário**
  - **Criptografia por política**

  Se você clicar **em Filtros,** poderá modificar o gráfico com os seguintes filtros:

  - **Data de início** e **data de término**
  - Método de criptografia.
  - Modelo de criptografia.

- **Exibir dados por: Relatório de criptografia de** mensagens e **métrica por:** modelo de criptografia: os seguintes métodos de criptografia estão disponíveis:

  - **Não encaminhar**
  - **Somente criptografar**
  - **OME anterior**
  - **Personalizados**

  Se você clicar **em Filtros,** poderá modificar o gráfico com os seguintes filtros:

  - **Data de início** e **data de término**
  - Método de criptografia
  - Modelo de criptografia

- **Exibir dados por: 5** principais domínios de destinatários: esta exibição mostra um gráfico de pizza com contagens de mensagens enviadas para os 5 principais domínios de destinatários.

  Se você clicar em **Filtros,** poderá selecionar a data **de início** e a **data de término.**

### <a name="details-table-view-for-the-encryption-report"></a>Exibição de tabela de detalhes para o relatório de criptografia

Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:

- **Quebra por: método de criptografia** **ou quebra por: modelo de criptografia**: as seguintes informações são mostradas:

  - **Date**
  - **Endereço do remetente**.
  - **Modelo de criptografia**
  - **Método de criptografia**
  - **Endereço do destinatário**
  - **Assunto**

- **Exibir dados por: 5 domínios de destinatário principais:**

  - **Date**
  - **Domínio do destinatário**
  - **Contagem de mensagem**

Se você clicar em **Filtros** em uma exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:

- **Data de início** e **data de término**
- Método de criptografia
- Modelo de criptografia

Para voltar para a exibição de relatório, clique em **Exibir relatório**.

## <a name="mailflow-status-report"></a>Relatório de status do fluxo de mensagens

O **relatório de status do fluxo de mensagens** contém informações sobre malware, spam, phishing e mensagens bloqueadas por borda. Para obter mais detalhes, consulte [Mailflow status report](view-mail-flow-reports.md#mailflow-status-report).

## <a name="malware-detections-in-email-report"></a>Detecções de malware no relatório de email

O **relatório de detecções de malware** no email mostra informações sobre detecções de malware em mensagens de email de entrada e saída (malware detectado pela Proteção do Exchange Online ou EOP). Para obter mais informações sobre a proteção contra malware no EOP, consulte [Proteção anti-malware no EOP](anti-malware-protection.md).

 O filtro de exibição agregado permite 90 dias, enquanto o filtro de tabela de detalhes só permite 10 dias.

Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione detecções de malware no  \>  **email.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MalwareDetections> .

![Detecções de malware no widget de email no painel Relatórios](../../media/malware-detections-widget.png)

Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando:

- **Data de início** e **data de término**
- **Entrada**
- **Saída**

![Exibição de relatório na detecção de malware no relatório de email](../../media/malware-detections-report-view.png)

Se você clicar **em Exibir tabela de** detalhes, poderá ver os seguintes detalhes:

- **Date**
- **Endereço do remetente**.
- **Endereço do destinatário**
- **ID da** mensagem: disponível no campo de header **Message-ID** no header da mensagem e deve ser exclusivo. Um valor de exemplo `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` é (observe os colchetes angulares).
- **Assunto**
- **Filename**
- **Nome do malware**

Para voltar para a exibição de relatório, clique em **Exibir relatório**.

## <a name="mail-latency-report"></a>Relatório de latência de email

O **relatório de latência de email** contém informações sobre a entrega de email e a latência de detonação experimentado em sua organização. Para obter mais informações, consulte [Relatório de latência de email.](view-reports-for-atp.md#mail-latency-report)

## <a name="sent-and-received-email-report"></a>Relatório de emails enviados e recebidos

O **relatório de emails** enviados e recebidos contém informações sobre malware, spam, regras de fluxo de emails (também conhecidas como regras de transporte) e detecções avançadas de malware depois que o email entra no serviço. Para obter mais informações, consulte [Relatório de emails enviados e recebidos.](view-mail-flow-reports.md#sent-and-received-email-report)

## <a name="spam-detections-report"></a>Relatório de detecções de spam

O **relatório de detecções de** spam mostra mensagens de email de spam bloqueadas pelo EOP. As mensagens são contadas individualmente, não por destinatário. Por exemplo, se a mesma mensagem de spam foi enviada para 100 destinatários em sua organização, ela conta como uma mensagem.

A exibição agregada permite a filtragem por 90 dias, enquanto a tabela de detalhes permite a filtragem de 10 dias.

Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione  \>  **detecções de spam.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget de detecções de spam no painel Relatórios](../../media/spam-detections-report-widget.png)

Para obter mais informações sobre proteção anti-spam, consulte [Proteção anti-spam no EOP.](anti-spam-protection.md)

### <a name="report-view-for-the-spam-detections-report"></a>Exibição de relatório para o relatório de detecções de spam

Os gráficos a seguir estão disponíveis na exibição de relatório:

- **Abaixo por: Ação:** os seguintes tipos de evento são mostrados:

  - **Conteúdo de spam filtrado**
  - **Bloqueio de IP de spam**
  - **Bloqueio de envelope de spam**
  - **Filtro DBEB de spam:** bloqueio de borda baseado em diretório (DBEB)

  Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantos itens foram bloqueados naquele dia, bem como como esses itens são categorizados.

  ![Exibição de ação no relatório de detecções de spam](../../media/spam-detections-report-action-view.png)

- **Down by: Direction**: The following directions are shown:

  - **Entrada**
  - **Saída**

  ![Exibição de direção no relatório de detecções de spam](../../media/spam-detections-report-direction-view.png)

Se você clicar **em Filtros** em uma exibição de relatório, poderá modificar os resultados com os seguintes filtros:

- **Data de início** e **data de término**
- Valores de direção
- Valores de tipo de evento

### <a name="details-table-view-for-the-spam-detections-report"></a>Exibição de tabela de detalhes para o relatório de detecções de spam

Se você clicar em **Exibir tabela de detalhes** em qualquer exibição de relatório, as seguintes informações serão mostradas:

- **Date**
- **Endereço do remetente**.
- **Endereço do destinatário**
- **Tipo de evento**
- **Ação**
- **Assunto**

Se você clicar **em Filtros** em uma tabela de detalhes, poderá modificar os resultados com os seguintes filtros:

- **Data de início** e **data de término**
- Valores de direção
- Valores de tipo de evento

Para voltar para a exibição de relatório, clique em **Exibir relatório**.

## <a name="spoof-detections-report"></a>Relatório de detecções de spoof

O relatório de detecções de Spoof mostra quantas mensagens de email falsas foram detectadas e quais foram consideradas "boas" (emails de **spoof** feitos por motivos comerciais legítimos). Para obter mais informações sobre a spoofing, consulte [Proteção anti-spoofing no EOP](anti-spoofing-protection.md).

A exibição agregada do relatório permite 90 dias de filtragem, enquanto a exibição de detalhes só permite dez dias de filtragem.

Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione  \>  **detecções de Spoof**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget de detecções de spoof no painel Relatórios](../../media/spoof-detections-widget.png)

Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantas mensagens de email falsas passaram.

Você pode filtrar o gráfico e a tabela de detalhes clicando em **Filtros** e selecionando um ou mais dos seguintes valores:

- **Data de início** e **data de término**

- **Email bom**

- **Capturado como spam**

![Exibição de relatório no relatório de detecções de Spoof](../../media/spoof-detections-report-view.png)

Se você clicar **em Exibir tabela de** detalhes, poderá ver os seguintes detalhes:

- **Date**
- **Remetente spoofed**
- **Remetente verdadeiro**
- **IP do remetente**
- **Ação**
- **Contagem de mensagem**

Para voltar para a exibição de relatório, clique em **Exibir relatório**.

## <a name="threat-protection-status-report"></a>Relatório de status de proteção contra ameaças

O **relatório de status de** proteção contra ameaças está disponível no EOP e no Microsoft Defender para Office 365; no entanto, os relatórios contêm dados diferentes. Por exemplo, os clientes do EOP podem exibir informações sobre malware detectado no email, mas não informações sobre arquivos mal-intencionados detectados por Anexos seguros para [o SharePoint, o OneDrive](atp-for-spo-odb-and-teams.md)e o Microsoft Teams.

O relatório fornece a contagem de mensagens de email com conteúdo mal-intencionado, como arquivos ou endereços de site (URLs) que foram bloqueados pelo mecanismo anti-malware, zap [(limpeza automática zero hora)](zero-hour-auto-purge.md)e recursos do Defender para Office 365, como links [seguros,](atp-safe-links.md) [anexos](atp-safe-attachments.md)seguros e [anti-phishing.](set-up-anti-phishing-policies.md) Você pode usar essas informações para identificar tendências ou determinar se as políticas da organização precisam de ajuste.

**Observação:** é importante entender que, se uma mensagem for enviada a cinco destinatários, a contaremos como cinco mensagens diferentes, e não como uma mensagem.

Para exibir o relatório, abra o [Centro de Conformidade &](https://protection.office.com)segurança, vá para o Painel de Relatórios e selecione o status de proteção contra  \>  **ameaças.** Para ir diretamente para o relatório, abra uma das seguintes URLs:

- Microsoft Defender para Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport>

![Widget de status de proteção contra ameaças no painel Relatórios](../../media/threat-protection-status-report-widget.png)

Por padrão, o gráfico mostra dados dos últimos 7 dias. Se você clicar **em Filtros,** poderá selecionar um intervalo de datas de 90 dias (as assinaturas de avaliação podem ser limitadas a 30 dias). A exibição de tabela de detalhes permite a filtragem por 30 dias.

### <a name="report-view-for-the-threat-protection-status-report"></a>Exibição de relatório para o relatório de status de proteção contra ameaças

Os seguintes exibições estão disponíveis:

- **Exibir dados por: Visão geral:** as seguintes informações de detecção são mostradas:

  - **Malware de email**
  - **Phishing de email**
  - **Malware de conteúdo**

  ![Visão geral no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-overview-view.png)

- **Exibir dados por: Conteúdo \> Malware**<sup>1</sup>: as seguintes informações são mostradas para organizações do Microsoft Defender para Office 365:

  - **Mecanismo anti-malware:** arquivos mal-intencionados detectados no Sharepoint, no OneDrive e no Microsoft Teams pela detecção de vírus interna no [Microsoft 365.](virus-detection-in-spo.md)
  - **Detonação** de arquivo: arquivos mal-intencionados detectados pelos Anexos Seguros [para o SharePoint, o OneDrive e o Microsoft Teams.](atp-for-spo-odb-and-teams.md)

  ![Exibição de malware de conteúdo no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-content-malware-view.png)

- **Exibir dados por: Substituição de Mensagem:** as informações do motivo da substituição a seguir são mostradas:

  - **Ignorar no local**
  - **IP Allow**
  - **Regra de fluxo de emails**
  - **Permitir remetente**
  - **Permitir domínio**
  - **ZAP não habilitado**
  - **Pasta Lixo Eletrônico não habilitada**
  - **Remetente Seguro do Usuário**
  - **Domínio seguro do usuário**

  ![Exibição de substituição de mensagem no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-message-override-view.png)

- **Confira abaixo: Tecnologia de detecção e** exibir dados **por: \> Phishing** de email: as seguintes informações são mostradas:

  - **Reputação de URL** gerada pela ATP <sup>1:</sup>reputação de URL mal-intencionada gerada pelo Defender para ataques do Office 365 em outros clientes do Microsoft 365.
  - **Filtro de phishing** avançado: sinais de phishing com base no aprendizado de máquina.
  - **Anti-spoof - Falha do DMARC:** falha de autenticação do DMARC em mensagens.
  - **Anti-spoof - dentro da organização**: o remetente está tentando fazer spoof do domínio do destinatário.
  - **Anti-spoof - domínio externo**: o remetente está tentando fazer spoof de algum outro domínio.
  - **Representação de marca**: representação de marcas conhecidas com base em senders.
  - **Representação de domínio**<sup>1:</sup>Representação de domínios que o cliente possui ou define.
  - **Reputação da URL do EOP:** reputação de URL mal-intencionada.
  - **Filtro de phishing** geral: sinais de phishing com base em regras de analista.
  - **Outros**
  - **ZAP de phishing**<sup>2:</sup>limpeza automática zero hora de mensagens de phishing.
  - **Detonação de URL**<sup>1</sup>
  - **Representação de usuário**<sup>1:</sup>Representação de usuários definida pelo administrador ou aprendida por meio da inteligência de caixa de correio.

  ![Exibição de tecnologia de detecção para email de phishing no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Confira: Tecnologia de detecção e** exibir dados **por: Malware \> de email:** as seguintes informações são mostradas:

  - **Reputação de arquivo gerada pela ATP**<sup>1:</sup>toda a reputação de arquivo mal-intencionado gerada pelo Defender para ataques do Office 365.
  - **Mecanismo anti-malware**<sup>1:</sup>detecção de mecanismos anti-malware.
  - **Bloqueio de tipo de arquivo de política anti-malware:** são mensagens de email filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.
  - **Detonação**<sup>de arquivo 1:</sup>detecção por anexos seguros.
  - **Reputação de arquivos mal-intencionados**
  - **ZAP**<sup>2 de</sup> malware
  - **Outros**

  ![Exibição de tecnologia de detecção para malware no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Intervalo por: Tipo de** política e Exibir dados **por: Email \> Phish** or **Exibir dados por: Malware \>** de Email : As seguintes informações são mostradas:

  - **Anti-malware**
  - **Anexos seguros**<sup>1</sup>
  - **Anti-phishing**
  - **Anti-spam**
  - **Regra de fluxo de** emails (também conhecida como regra de transporte)
  - **Outros**

  ![Exibição de tipo de política para email de phishing no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Intervalo por: Status de entrega** e Exibir dados **por: \> Phishing** de email ou exibir dados **por: \> Malware** de email: as seguintes informações são mostradas:

  - **Falha na entrega**
  - **Dropped**
  - **Encaminhado**
  - **Caixa de correio hospedada: pasta personalizada**
  - **Caixa de correio hospedada: Itens excluídos**
  - **Caixa de correio hospedada: Caixa de Entrada**
  - **Caixa de correio hospedada: Lixo eletrônico**
  - **Servidor local: Entregue**
  - **Quarentena**

  ![Exibição de status de entrega para email de phishing no relatório de status de Proteção contra Ameaças](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> Defender para Office 365 somente

<sup>A</sup> ZAP (Limpeza Automática Zero Hora) não está disponível no EOP autônomo (funciona apenas em caixas de correio do Exchange Online).

Se você clicar **em Filtros,** os filtros disponíveis dependerão do gráfico que você estava olhando:

- Para **exibir dados por: \> Malware** de conteúdo, você pode modificar o relatório **por** data de início e **data** de término e o valor **de** detecção.

- Para **exibir dados por: Substituição de Mensagem,** você pode modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - **Motivo da substituição**
  - **Marca:** filtrar os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias). Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário.](user-tags.md)
  - **Domínio**

- Para todos os outros, você pode modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - **Detecção**
  - **Protegido por:** **ATP** **ou EOP**
  - **Marca:** filtrar os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias). Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário.](user-tags.md)
  - **Domínio**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Visão de tabela de detalhes do relatório de status de Proteção contra Ameaças

Se você clicar **em Exibir tabela de** detalhes, as informações mostradas dependerão do gráfico que você estava olhando:

- **Exibir dados por: Visão geral:** o botão **Tabela de detalhes** Sem Exibição está disponível.

- **Exibir dados por: Conteúdo \> Malware**:

  - **Date**
  - **Location**
  - **Direcionado por**
  - **Nome do malware**

  Se você clicar **em Filtros** nesta exibição, poderá modificar o relatório por data de início e **data** de término e o **valor de** detecção. 

- **Exibir dados por: Substituição de Mensagem:**

  - **Date**
  - **Assunto**
  - **Sender**
  - **Destinatários**
  - **Detectado por**
  - **Motivo da substituição**
  - **Fonte de comprometimento**
  - **Marcas**

  Se você clicar **em Filtros** nesta exibição, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - **Motivo da substituição**
  - **Marca:** filtrar os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias). Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário.](user-tags.md)
  - **Domínio**
  - **Destinatários** (observe que essa propriedade filtável só está disponível no exibição de tabela de detalhes)

- Todos os outros gráficos:

  - **Date**
  - **Assunto**
  - **Sender**
  - **Destinatários**
  - **Detectado por**
  - **Status de Entrega**
  - **Fonte de comprometimento**
  - **Marcas**

  Se você clicar **em Filtros,** poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - **Detecção**
  - **Protegido por:** **Defender para Office 365** **ou EOP**
  - **Marca:** filtrar os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas prioritárias). Para obter mais informações sobre marcas de usuário, consulte [Marcas de usuário.](user-tags.md)
  - **Domínio**
  - **Destinatários** (observe que essa propriedade filtável só está disponível no exibição de tabela de detalhes)

## <a name="top-malware-report"></a>Relatório de malware principal

O **relatório de malware** principal mostra os vários tipos de malware detectados pela proteção [anti-malware no EOP.](anti-malware-protection.md)

Para exibir o relatório, abra o [Centro de Conformidade e Segurança &,](https://protection.office.com)vá para o Painel de Relatórios e selecione Malware  \>  **principal.** Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopMalware> .

![Principal widget de malware no painel Relatórios](../../media/top-malware-report-widget.png)

Quando você passar o mouse sobre um 100o no gráfico de pizza, poderá ver o nome de um tipo de malware e quantas mensagens foram detectadas como tendo esse malware.

![Exibição do relatório de malware principal](../../media/top-malware-report-view.png)

Se você clicar **em Exibir tabela de** detalhes, poderá ver os seguintes detalhes:

- **Principais malwares**
- **Count**

Se você clicar em **Filtros** na exibição de relatório ou na exibição de tabela de detalhes, poderá especificar um intervalo de datas com data **de** início **e data de término.**

## <a name="url-threat-protection-report"></a>Relatório de proteção contra ameaças de URL

O **relatório de proteção contra ameaças de URL** está disponível no Microsoft Defender para Office 365. Para obter mais informações, consulte o [relatório de proteção contra ameaças de URL.](view-reports-for-atp.md#url-threat-protection-report)

## <a name="user-reported-messages-report"></a>Relatório de mensagens relatadas pelo usuário

O  relatório de mensagens relatadas pelo usuário mostra informações sobre mensagens de email que [](enable-the-report-message-add-in.md) os usuários relataram como lixo eletrônico, tentativas de phishing ou emails bons usando o complemento Mensagem de Relatório ou o complemento Phishing de [Relatório.](enable-the-report-phish-add-in.md)

Os detalhes estão disponíveis para cada mensagem, incluindo o motivo da entrega, como uma exceção de política de spam ou uma regra de fluxo de emails configurada para sua organização. Para exibir detalhes, selecione um item na lista de relatórios  do usuário e, em seguida, veja as informações nas **guias** Resumo e Detalhes.

![O User-Reported mensagens mostra mensagens rotuladas como lixo eletrônico, não tentativas de lixo eletrônico ou phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Para exibir esse relatório, no Centro [de Conformidade & segurança,](https://protection.office.com)faça um dos seguintes:

- Vá para **o Painel de Gerenciamento** de \> **Ameaças** Mensagens \> **relatadas pelo usuário.**

- Vá para **Análise de gerenciamento de** ameaças \> **Mensagens** \> **relatadas pelo usuário.**

![No Centro de Conformidade & segurança, escolha Revisar ameaças Mensagens relatadas \> \> pelo usuário](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> Para que o relatório de mensagens relatadas  pelo usuário funcione corretamente, o log de auditoria deve estar ligado para seu ambiente do Office 365. Isso geralmente é feito por alguém que tem a função Logs de Auditoria atribuída no Exchange Online. Para saber mais, confira Ativar ou desativar a pesquisa de log de [auditoria do Microsoft 365.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Quais permissões são necessárias para exibir esses relatórios?

Para exibir e usar os relatórios descritos neste artigo &, você precisa ser membro de um dos seguintes grupos de função no Centro de Conformidade e Segurança:

- **Organization Management**
- **Administrador de Segurança**
- **Leitor de Segurança**
- **Leitor Global**

Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

**Observação:** a adição de usuários à função do Azure Active Directory correspondente no Centro de administração do  Microsoft 365 oferece aos usuários as permissões necessárias no Centro de Conformidade e Segurança & e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>E se os relatórios não mostrarem dados?

Se você não estiver vendo dados em seus relatórios, verifique se as políticas estão configuradas corretamente. Para saber mais, confira [Proteger contra ameaças.](protect-against-threats.md)

## <a name="related-topics"></a>Tópicos relacionados

[Proteção anti-spam e anti-malware no EOP](anti-spam-and-anti-malware-protection.md)

[Relatórios inteligentes e insights no Centro de Conformidade e Segurança](reports-and-insights-in-security-and-compliance.md)

[Exibir relatórios de fluxo de emails no Centro de Conformidade & segurança](view-mail-flow-reports.md)

[Exibir relatórios do Defender para Office 365](view-reports-for-atp.md)
