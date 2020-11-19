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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Saiba como localizar e usar relatórios de segurança de email da sua organização. Relatórios de segurança de email estão disponíveis no centro de conformidade e segurança &.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 038f310d8690652a3aefb2eab5ac01f76986d210
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357930"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Exibir relatórios de segurança de email no Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Vários relatórios estão disponíveis no [centro de conformidade & segurança](https://protection.office.com) para ajudá-lo a ver como os recursos de segurança de email, como os recursos antispam, Antimalware e de criptografia no Microsoft 365 estão protegendo sua organização. Se você tiver as [permissões necessárias](#what-permissions-are-needed-to-view-these-reports), poderá exibir esses relatórios no centro de conformidade & de segurança acessando **Reports** o \> **painel** relatórios. Para ir diretamente para o painel relatórios, abra <https://protection.office.com/insightdashboard> .

![Painel de relatórios no centro de conformidade & segurança](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Relatório de usuários comprometidos

> [!NOTE]
> Este relatório está disponível nas organizações do Microsoft 365 com caixas de correio do Exchange Online. Ele não está disponível em organizações autônomas do Exchange Online Protection (EOP).

O relatório **usuários comprometidos** mostra o número de contas de usuário que foram marcadas como **suspeitas** ou **restritas** nos últimos sete dias. As contas em um desses Estados são problemáticas ou até mesmo comprometidas. Com o uso frequente, você pode usar o relatório para identificar picos e até mesmo tendências, em contas suspeitas ou restritas. Para obter mais informações sobre usuários comprometidos, consulte [responder a uma conta de email comprometida](responding-to-a-compromised-email-account.md).

![Widget usuários comprometidos no painel relatórios](../../media/compromised-users-report-widget.png)

O modo de exibição de agregação mostra os dados dos últimos 90 dias e o modo de exibição de detalhes mostra os dados dos últimos 30 dias.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **usuários comprometidos**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=CompromisedUsers> .

Você pode filtrar tanto o gráfico quanto a tabela detalhes clicando em **filtros** e selecionando um ou mais dos seguintes valores:

- **Data de início** e **data de término**

- **Suspeito**: a conta de usuário enviou emails suspeitos e está correndo o risco de ser restrito a enviar emails.

- **Restricted**: a conta de usuário foi restrita ao envio de emails devido a padrões altamente suspeitos.

![Exibição de relatório no relatório de usuários comprometidos](../../media/compromised-users-report-activity-view.png)

Se você clicar em **Exibir tabela de detalhes**, poderá ver os seguintes detalhes:

- **Hora de criação**
- **ID de usuário**
- **Ação**

Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.

## <a name="encryption-report"></a>Relatório de criptografia

O **relatório de criptografia** está disponível em EOP (inscrições com caixas de correio no Exchange Online ou EOP autônomo sem caixas de correio do Exchange Online). A equipe de segurança da sua organização pode usar informações neste relatório para identificar padrões e aplicar proativamente ou ajustar políticas para mensagens de email confidenciais. Por exemplo:

- Se você vir um grande número de mensagens de email criptografadas por usuários, talvez queira adicionar uma política de criptografia para automatizar a criptografia para determinados casos de uso. Para obter mais informações, consulte [definir regras de fluxo de email para criptografar mensagens de email no Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).

- Se você tiver vários modelos de criptografia disponíveis, mas nenhum estiver usando, você poderá explorar se os usuários precisam de treinamento de recurso.

O modo de exibição agregado permite a filtragem dos últimos 90 dias, enquanto o modo de exibição de detalhes permite filtragem por 10 dias.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **relatório de criptografia**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=EncryptionReport> .

Para saber mais sobre criptografia, confira [criptografia de email no Microsoft 365](../../compliance/email-encryption.md).

### <a name="report-view-for-the-encryption-report"></a>Exibição de relatório para o relatório de criptografia

Você pode usar os seguintes filtros no gráfico:

- **Exibir dados por: relatório de criptografia de mensagens** e **dividir por: método** de criptografia: os seguintes métodos de criptografia estão disponíveis:

  - **Criptografia por usuário**
  - **Criptografia por política**

  Se você clicar em **filtros**, poderá modificar o gráfico com os seguintes filtros:

  - **Data de início** e **data de término**
  - Método de criptografia.
  - Modelo de criptografia.

- **Exibir dados por: relatório de criptografia de mensagens** e **dividir por: modelo** de criptografia: os seguintes métodos de criptografia estão disponíveis:

  - **Não encaminhar**
  - **Criptografar apenas**
  - **OME anterior**
  - **Personalizados**

  Se você clicar em **filtros**, poderá modificar o gráfico com os seguintes filtros:

  - **Data de início** e **data de término**
  - Método de criptografia
  - Modelo de criptografia

- **Exibir dados por: 5 principais domínios de destinatário**: este modo de exibição mostra um gráfico de pizza com contagens de mensagens enviadas para os cinco domínios de destinatários principais.

  Se você clicar em **filtros**, poderá selecionar uma **data de início** e uma **data de término**.

### <a name="details-table-view-for-the-encryption-report"></a>Exibição da tabela de detalhes para o relatório de criptografia

Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:

- **Dividir em: método de criptografia** ou **dividir por: modelo de criptografia**: as seguintes informações são mostradas:

  - **Date**
  - **Endereço do remetente**.
  - **Modelo de criptografia**
  - **Método de criptografia**
  - **Endereço do destinatário**
  - **Assunto**

- **Exibir dados por: cinco domínios principais de destinatários**:

  - **Date**
  - **Domínio do destinatário**
  - **Contagem de mensagem**

Se você clicar em **filtros** em um modo de exibição de tabela de detalhes, poderá modificar os resultados com os seguintes filtros:

- **Data de início** e **data de término**
- Método de criptografia
- Modelo de criptografia

Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.

## <a name="mailflow-status-report"></a>Relatório de status do fluxo

O **relatório de status do fluxo** contém informações sobre malware, spam, phishing e mensagens bloqueadas de borda. Para obter mais detalhes, consulte [fluxo status Report](view-mail-flow-reports.md#mailflow-status-report).

## <a name="malware-detections-in-email-report"></a>Detecções de malware no relatório de email

O relatório **detecções de malware no email** mostra informações sobre detecções de malware em mensagens de email de entrada e saída (malware detectado pelo Exchange Online Protection ou EOP). Para obter mais informações sobre proteção contra malware no EOP, consulte [Anti-Malware Protection in EOP](anti-malware-protection.md).

 O filtro de exibição agregada permite 90 dias, enquanto o filtro da tabela detalhes permite apenas 10 dias.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **detecções de malware no email**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=MalwareDetections> .

![Detecções de malware no widget de email no painel relatórios](../../media/malware-detections-widget.png)

Você pode filtrar tanto o gráfico quanto a tabela detalhes clicando em **filtros** e selecionando:

- **Data de início** e **data de término**
- **Entrada**
- **Saída**

![Exibição de relatório no relatório de detecção de malware no email](../../media/malware-detections-report-view.png)

Se você clicar em **Exibir tabela de detalhes**, poderá ver os seguintes detalhes:

- **Date**
- **Endereço do remetente**.
- **Endereço do destinatário**
- **ID da mensagem**: disponível no campo de cabeçalho **Message-ID** no cabeçalho da mensagem e deve ser exclusivo. Um valor de exemplo é `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Observe os colchetes angulares).
- **Assunto**
- **Filename**
- **Nome do malware**

Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.

## <a name="mail-latency-report"></a>Relatório de latência de email

O **relatório de latência de email** contém informações sobre a entrega de emails e a latência de acionamento em sua organização. Para obter mais informações, consulte [relatório de latência de email](view-reports-for-atp.md#mail-latency-report).

## <a name="sent-and-received-email-report"></a>Relatório de email enviado e recebido

O relatório de **email enviado e recebido** contém informações sobre malware, spam, regras de fluxo de emails (também conhecidas como regras de transporte) e detecções de malware avançadas após o email entrar no serviço. Para obter mais informações, consulte [envio e recebimento de email Report](view-mail-flow-reports.md#sent-and-received-email-report).

## <a name="spam-detections-report"></a>Relatório de detecções de spam

O relatório **detecções de spam** mostra mensagens de email de spam que foram bloqueadas pelo EOP. As mensagens são contadas individualmente, e não por destinatário. Por exemplo, se a mesma mensagem de spam tiver sido enviada para 100 destinatários em sua organização, ela contará como uma mensagem.

O modo de exibição agregado permite filtragem de 90 dias, enquanto a tabela detalhes permite a filtragem de 10 dias.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **detecções de spam**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget detecções de spam no painel relatórios](../../media/spam-detections-report-widget.png)

Para obter mais informações sobre proteção antispam, consulte [proteção antispam no EOP](anti-spam-protection.md).

### <a name="report-view-for-the-spam-detections-report"></a>Exibição de relatório para o relatório de detecções de spam

Os gráficos a seguir estão disponíveis no modo de exibição de relatório:

- **Dividir por: ação**: os seguintes tipos de eventos são mostrados:

  - **Conteúdo de spam filtrado**
  - **Bloqueio de IP de spam**
  - **Bloco de envelope de spam**
  - **Filtro de DBEB de spam**: bloqueio de borda baseado em diretório (DBEB)

  Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantos itens foram bloqueados naquele dia, bem como os itens que foram categorizados.

  ![Exibição de ação no relatório de detecções de spam](../../media/spam-detections-report-action-view.png)

- Dividido **por: direção**: as seguintes direções são exibidas:

  - **Entrada**
  - **Saída**

  ![Modo de exibição de direção no relatório de detecções de spam](../../media/spam-detections-report-direction-view.png)

Se você clicar em **filtros** em um modo de exibição de relatório, poderá modificar os resultados com os seguintes filtros:

- **Data de início** e **data de término**
- Valores de direção
- Valores de tipo de evento

### <a name="details-table-view-for-the-spam-detections-report"></a>Exibição da tabela de detalhes para o relatório de detecções de spam

Se você clicar em **Exibir tabela de detalhes** em qualquer modo de exibição de relatório, as seguintes informações serão exibidas:

- **Date**
- **Endereço do remetente**.
- **Endereço do destinatário**
- **Tipo de evento**
- **Ação**
- **Assunto**

Se você clicar em **filtros** em uma tabela de detalhes, poderá modificar os resultados com os seguintes filtros:

- **Data de início** e **data de término**
- Valores de direção
- Valores de tipo de evento

Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.

## <a name="spoof-detections-report"></a>Relatório de detecções falsas

O relatório de **detecções falsas** mostra quantas mensagens de email de falsificação foram detectadas, e dessas, quais foram consideradas "boas" (emails falsos realizados por motivos de negócios legítimos). Para obter mais informações sobre falsificação, consulte [proteção contra falsificação no EOP](anti-spoofing-protection.md).

O modo de exibição de agregação do relatório permite 90 dias de filtragem, enquanto o modo de exibição de detalhes permite apenas dez dias de filtragem.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **detecções falsas**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget detecções de spoof no painel relatórios](../../media/spoof-detections-widget.png)

Ao passar o mouse sobre um dia (ponto de dados) no gráfico, você pode ver quantas mensagens de email de falsificação vieram.

Você pode filtrar tanto o gráfico quanto a tabela detalhes clicando em **filtros** e selecionando um ou mais dos seguintes valores:

- **Data de início** e **data de término**

- **Boa mensagem**

- **Detectado como spam**

![Exibição de relatório no relatório de detecções de spoof](../../media/spoof-detections-report-view.png)

Se você clicar em **Exibir tabela de detalhes**, poderá ver os seguintes detalhes:

- **Date**
- **Remetente falsificado**
- **Remetente verdadeiro**
- **IP do remetente**
- **Ação**
- **Contagem de mensagem**

Para voltar para o modo de exibição de relatório, clique em **Exibir relatório**.

## <a name="threat-protection-status-report"></a>Relatório de status de proteção contra ameaças

O relatório de **status de proteção contra ameaças** está disponível no EOP e no Microsoft defender para Office 365; no entanto, os relatórios contêm dados diferentes. Por exemplo, os clientes do EOP podem exibir informações sobre malware detectado no email, mas não informações sobre arquivos mal-intencionados detectados pela [ATP para SharePoint, onedrive ou Microsoft Teams](atp-for-spo-odb-and-teams.md).

O relatório fornece a contagem de mensagens de email com conteúdo mal-intencionado, como arquivos ou endereços de sites (URLs) que foram bloqueados pelo Mecanismo Antimalware, [exclusão automática de zero horas (zap)](zero-hour-auto-purge.md)e recursos do defender para Office 365, como [links seguros](atp-safe-links.md), [anexos seguros](atp-safe-attachments.md)e [anti-phishing](set-up-anti-phishing-policies.md). Você pode usar essas informações para identificar tendências ou determinar se as políticas da organização precisam de ajuste.

**Observação**: é importante entender que, se uma mensagem for enviada para cinco destinatários, contaremos como cinco mensagens diferentes e não uma mensagem.

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **status de proteção contra ameaças**. Para ir diretamente para o relatório, abra uma das seguintes URLs:

- Microsoft defender para Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP <https://protection.office.com/reportv2?id=TPSAggregateReport>

![Widget status de proteção contra ameaças no painel relatórios](../../media/threat-protection-status-report-widget.png)

Por padrão, o gráfico mostra os dados dos últimos 7 dias. Se você clicar em **filtros**, poderá selecionar um intervalo de data de 90 dias (as assinaturas de avaliação podem ser limitadas a 30 dias). O modo de exibição tabela de detalhes permite a filtragem por 30 dias.

### <a name="report-view-for-the-threat-protection-status-report"></a>Exibição de relatório para o relatório de status de proteção contra ameaças

Os seguintes modos de exibição estão disponíveis:

- **Exibir dados por: visão geral**: as seguintes informações de detecção são exibidas:

  - **Malware de email**
  - **Phishing de email**
  - **Malware de conteúdo**

  ![Visão geral do relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-overview-view.png)

- **Exibir dados por: conteúdo \> Malware**<sup>1</sup>: as informações a seguir são mostradas para as organizações do Microsoft Defender para Office 365:

  - **Mecanismo Antimalware**: arquivos mal-intencionados detectados no SharePoint, no onedrive e no Microsoft Teams pela [detecção de vírus interna no Microsoft 365](virus-detection-in-spo.md).
  - **Arquivo acionamento**: arquivos mal-intencionados detectados pela [ATP para SharePoint, onedrive e Microsoft Teams](atp-for-spo-odb-and-teams.md).

  ![Exibição de malware de conteúdo no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-content-malware-view.png)

- **Exibir dados por: substituição de mensagens**: as seguintes informações de motivo de substituição são exibidas:

  - **Ignorar local**
  - **Permissão de IP**
  - **Regra de fluxo de emails**
  - **Permissão de remetente**
  - **Permissão de domínio**
  - **ZAP não habilitado**
  - **Pasta lixo eletrônico não habilitada**
  - **Remetente seguro do usuário**
  - **Domínio seguro do usuário**

  ![Exibição de substituição de mensagens no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-message-override-view.png)

- **Divida por: tecnologia de detecção** e **exibir dados por: \> Phish de email**: as informações a seguir são exibidas:

  - **Reputação de URL gerada por ATP**<sup>: reputação</sup>de URL mal-intencionado gerada a partir do defender para Office 365 detonations em outros clientes da Microsoft 365.
  - **Filtro avançado de Phish**: sinais de phishing baseados no Machine Learning.
  - **Falha antifalsificação do DMARC**: falha na autenticação do DMARC nas mensagens.
  - **Anti-spoof-intra-org**: o remetente está tentando falsificar o domínio do destinatário.
  - **Antifalsificação-domínio externo**: o remetente está tentando falsificar outro domínio.
  - **Representação da marca**: representação de marcas conhecidas com base nos remetentes.
  - **Representação de domínio**<sup>1</sup>: representação de domínios pertencentes ao cliente ou definição.
  - **Reputação da URL do EOP**: reputação de URL mal-intencionado.
  - **Filtro de phishing geral**: sinais de phishing com base em regras de analista.
  - **Outros**
  - **Phish zap**<sup>2</sup>: limpeza automática de zero hora de mensagens de phishing.
  - **URL acionamento**<sup>1</sup>
  - **Representação de usuário**<sup>1</sup>: representação de usuários definidos por administrador ou aprendidos por meio da inteligência de caixa de correio.

  ![Exibição de tecnologia de detecção para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Divida por: tecnologia de detecção** e **exibir dados por: \> malware de email**: as informações a seguir são exibidas:

  - **Reputação de arquivo gerado por ATP**<sup>: toda a reputação de</sup>arquivos mal-intencionados gerada pelo defender para Office 365 detonations.
  - **Mecanismo anti-malware**<sup>1</sup>: detecção de mecanismos antimalware.
  - **Bloqueio de tipo de arquivo de política Antimalware**: Estas são mensagens de email filtradas devido ao tipo de arquivo mal-intencionado identificado na mensagem.
  - **Arquivo acionamento**<sup>1</sup>: detecção por anexos seguros.
  - **Reputação de arquivos mal-intencionados**
  - **Malware zap**<sup>2</sup>
  - **Outros**

  ![Exibição de tecnologia de detecção para malware no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Divida por: tipo de política** e **exibir dados por: \> Phish de emails** ou **exibir dados por: \> malware de email**: as seguintes informações são mostradas:

  - **Anti-malware**
  - **Anexos seguros**<sup>1</sup>
  - **Anti-Phish**
  - **Antispam**
  - **Regra de fluxo de emails** (também conhecida como regra de transporte)
  - **Outros**

  ![Modo de exibição tipo de política para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Dividir em: status de entrega** e **exibir dados por: \> Phish de emails** ou **exibir dados por: \> malware de email**: as informações a seguir são exibidas:

  - **Falha na entrega**
  - **Abandonado**
  - **Encaminhadas**
  - **Caixa de correio hospedada: pasta personalizada**
  - **Caixa de correio hospedada: itens excluídos**
  - **Caixa de correio hospedada: caixa de entrada**
  - **Caixa de correio hospedada: lixo eletrônico**
  - **Servidor local: entregue**
  - **Quarentena**

  ![Exibição do status de entrega para email de phishing no relatório de status de proteção contra ameaças](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> defender apenas para o Office 365

<sup>2</sup> a limpeza automática de zero horas (zap) não está disponível no EOP autônomo (funciona apenas em caixas de correio do Exchange Online).

Se você clicar em **filtros**, os filtros disponíveis dependerão do gráfico que você estava examinando:

- Para **exibir dados por: \> malware de conteúdo**, você pode modificar o relatório por **data de início** e data de **término** e o valor de **detecção** .

- Para **exibir dados por: substituição de mensagem**, você pode modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - **Motivo da substituição**
  - **Marca**: filtra os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas de prioridade). Para obter mais informações sobre marcas de usuário, consulte [User Tags](user-tags.md).
  - **Domínio**

- Para todos os outros modos de exibição, você pode modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - **Detecção**
  - **Protegido por**: **ATP** ou **EOP**
  - **Marca**: filtra os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas de prioridade). Para obter mais informações sobre marcas de usuário, consulte [User Tags](user-tags.md).
  - **Domínio**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Exibição da tabela de detalhes para o relatório de status de proteção contra ameaças

Se você clicar em **Exibir tabela de detalhes**, as informações mostradas dependem do gráfico que você estava observando:

- **Exibir dados por: visão geral**: não há botão **Exibir tabela detalhes** disponível.

- **Exibir dados por: conteúdo \> Malware**:

  - **Date**
  - **Location**
  - **Direcionado por**
  - **Nome do malware**

  Se você clicar em **filtros** neste modo de exibição, poderá modificar o relatório por **data de início** e data de **término** e o valor de **detecção** .

- **Exibir dados por: substituição de mensagem**:

  - **Date**
  - **Assunto**
  - **Sender**
  - **Destinatários**
  - **Detectado por**
  - **Motivo da substituição**
  - **Origem de comprometimento**
  - **Marcas**

  Se você clicar em **filtros** neste modo de exibição, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - **Motivo da substituição**
  - **Marca**: filtra os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas de prioridade). Para obter mais informações sobre marcas de usuário, consulte [User Tags](user-tags.md).
  - **Domínio**
  - **Destinatários** (Observe que essa propriedade Filterable só está disponível no modo de exibição tabela de detalhes)

- Todos os outros gráficos:

  - **Date**
  - **Assunto**
  - **Sender**
  - **Destinatários**
  - **Detectado por**
  - **Status de entrega**
  - **Origem de comprometimento**
  - **Marcas**

  Se você clicar em **filtros**, poderá modificar o relatório com os seguintes filtros:

  - **Data de início** e **data de término**
  - **Detecção**
  - **Protegido por**: **Defender para Office 365** ou **EOP**
  - **Marca**: filtra os resultados por usuários ou grupos que tiveram a marca de usuário especificada aplicada (incluindo contas de prioridade). Para obter mais informações sobre marcas de usuário, consulte [User Tags](user-tags.md).
  - **Domínio**
  - **Destinatários** (Observe que essa propriedade Filterable só está disponível no modo de exibição tabela de detalhes)

## <a name="top-malware-report"></a>Relatório de malware superior

O relatório de **malware superior** mostra os vários tipos de malware detectados pela [proteção Antimalware no EOP](anti-malware-protection.md).

Para exibir o relatório, abra o [centro de conformidade & segurança](https://protection.office.com), vá **Reports** para \> **painel** relatórios e selecione **malware superior**. Para ir diretamente para o relatório, abra <https://protection.office.com/reportv2?id=TopMalware> .

![Widget malware superior no painel relatórios](../../media/top-malware-report-widget.png)

Ao passar o mouse sobre uma fatia no gráfico de pizza, você pode ver o nome de um tipo de malware e quantas mensagens foram detectadas como tendo esse malware.

![Exibição de relatório de malware superior](../../media/top-malware-report-view.png)

Se você clicar em **Exibir tabela de detalhes**, poderá ver os seguintes detalhes:

- **Principais malware**
- **Count**

Se você clicar em **filtros** no modo de exibição relatório ou tabela de detalhes, poderá especificar um intervalo de datas com **data de início** e data de **término**.

## <a name="url-threat-protection-report"></a>Relatório de proteção contra ameaças de URL

O **relatório de proteção contra ameaças de URL** está disponível no Microsoft defender para Office 365. Para saber mais, confira [relatório de proteção contra ameaças de URL](view-reports-for-atp.md#url-threat-protection-report).

## <a name="user-reported-messages-report"></a>Relatório de mensagens relatadas pelo usuário

O relatório de **mensagens relatadas pelo usuário** mostra informações sobre as mensagens de email que os usuários relataram como lixo eletrônico, tentativas de phishing ou emails de boa qualidade usando o [suplemento de mensagem de relatório](enable-the-report-message-add-in.md).

Os detalhes estão disponíveis para cada mensagem, incluindo o motivo da entrega, como uma exceção de política de spam ou uma regra de fluxo de email configurada para sua organização. Para exibir detalhes, selecione um item na lista relatórios do usuário e, em seguida, exiba as informações nas guias **Resumo** e **detalhes** .

![O relatório mensagens de User-Reported mostra as mensagens que os usuários rotularam como lixo eletrônico, não lixo eletrônico ou tentativas de phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Para exibir esse relatório, no [centro de conformidade & segurança](https://protection.office.com), siga um destes procedimentos:

- Vá para o painel **Gerenciamento** \> **Dashboard** \> **de ameaças mensagens relatadas pelo usuário**.

- Vá para **Gerenciamento de ameaças** \> **revise** \> **mensagens relatadas pelo usuário**.

![No centro de conformidade & segurança, escolha revisão de gerenciamento de ameaças \> \> mensagens relatadas pelo usuário](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> Para que o relatório de mensagens relatadas pelo usuário funcione corretamente, o **log de auditoria deve estar ativado** para o seu ambiente do Office 365. Isso geralmente é feito por alguém que tenha a função de logs de auditoria atribuída no Exchange Online. Para obter mais informações, consulte [Ativar ou desativar a pesquisa de log de auditoria da Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Quais permissões são necessárias para exibir esses relatórios?

Para exibir e usar os relatórios, você precisa ser membro do grupo de função especificado no centro de conformidade e segurança & **e** no Exchange Online.

- No centro de conformidade & segurança, você precisa ser membro de um dos seguintes grupos de função:

  – Gerenciamento de organização-administrador de segurança (você também pode fazer isso no [centro de administração do Azure Active Directory](https://aad.portal.azure.com) -leitor de segurança

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

- No Exchange Online, você precisa ser membro de um dos grupos de função a seguir:

  – Gerenciamento de organização – gerenciamento de organização somente de exibição-somente os destinatários do gerenciamento de conformidade

Para obter mais informações, consulte [permissões no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) e [gerenciar grupos de função no Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

## <a name="what-if-the-reports-arent-showing-data"></a>E se os relatórios não estiverem mostrando dados?

Se você não estiver vendo dados nos seus relatórios, verifique se as suas políticas estão configuradas corretamente. Para saber mais, confira [proteção contra ameaças](protect-against-threats.md).

## <a name="related-topics"></a>Tópicos relacionados

[Proteção antispam e antimalware no EOP](anti-spam-and-anti-malware-protection.md)

[Relatórios inteligentes e insights no Centro de Conformidade e Segurança](reports-and-insights-in-security-and-compliance.md)

[Exibir relatórios de fluxo de emails no centro de conformidade & segurança](view-mail-flow-reports.md)

[Exibir relatórios do defender para Office 365](view-reports-for-atp.md)
