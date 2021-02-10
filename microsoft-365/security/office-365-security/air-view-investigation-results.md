---
title: Exibir os resultados de uma investigação automatizada no Microsoft 365
keywords: AIR, autoIR, ATP, automatizado, investigação, correção, ações
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Durante e após uma investigação automatizada no Microsoft 365, você pode exibir os resultados e as principais descobertas.
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 36cce42d0986cc793753d247d97315616f86f986
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175592"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Detalhes e resultados de uma investigação automatizada no Microsoft 365

**Aplica-se a**
- [Microsoft Defender para Office 365 plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Quando ocorre [uma investigação automatizada](office-365-air.md) no Microsoft Defender para Office [365,](office-365-atp.md)detalhes sobre essa investigação estão disponíveis durante e após o processo de investigação automatizada. Se você tiver as permissões necessárias, poderá exibir esses detalhes na central de segurança do Microsoft 365. Os detalhes da investigação fornecem o status atualizado e a capacidade de aprovar ações pendentes.

> [!TIP]
> Confira a nova página de investigação unificada no centro de segurança do Microsoft 365. Para saber mais, consulte [(NOVO!) Página de investigação unificada.](../mtp/mtp-autoir-results.md#new-unified-investigation-page)

## <a name="investigation-status"></a>Status da investigação

O status da investigação indica o progresso da análise e ações. À medida que a investigação é realizada, o status muda para indicar se foram encontradas ameaças e se as ações foram aprovadas.

|Status|Descrição|
|:---|:---|
|**Iniciando**|A investigação foi disparada e está aguardando para começar a execução.|
|**Em execução**|O processo de investigação foi iniciado e está em andamento. Esse estado também ocorre quando [ações pendentes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) são aprovadas.|
|**Nenhuma ameaça encontrada**|A investigação foi concluída e nenhuma ameaça (conta de usuário, mensagem de email, URL ou arquivo) foi identificada. <p> **DICA:** se você suspeitar de que algo foi perdido (como um falso negativo), poderá tomar medidas usando o [Explorador de Ameaças.](threat-explorer.md)|
|**Ameaça Encontrada**|A investigação automatizada encontrou problemas, mas não há ações de correção específicas para resolver esses problemas. <p> O **status Ameaças Encontradas** pode ocorrer quando algum tipo de atividade do usuário foi identificado, mas nenhuma ação de limpeza está disponível. Exemplos incluem qualquer uma das seguintes atividades de usuário: <br/>- Um [evento de prevenção de](https://docs.microsoft.com/Microsoft-365/compliance/data-loss-prevention-policies) perda de dados (DLP)<br/>- Um email enviando anomalias<br/>- Malware enviado<br/>- Phishing enviado <p> A investigação não encontrou URLs mal-intencionadas, arquivos ou mensagens de email para corrigir e nenhuma atividade de caixa de correio a ser corrigida, como a retração de regras ou delegação. <p> **DICA:** se você suspeitar de que algo foi perdido (como um falso negativo), poderá investigar e tomar medidas usando o [Explorador de Ameaças.](threat-explorer.md)|
|**Encerrado pelo sistema**|A investigação foi interrompida. Uma investigação pode parar por vários motivos: <br/>- As ações pendentes da investigação expiraram. Tempo de espera das ações pendentes após aguardar aprovação por uma semana.<br/>- Há muitas ações. Por exemplo, se houver muitos usuários clicando em URLs mal-intencionadas, ela poderá exceder a capacidade da investigação de executar todos os analisadores, portanto, a investigação será interrompida.<p> **DICA:** se uma investigação parar antes que as ações foram tomadas, tente usar o [Explorador](threat-explorer.md) de Ameaças para encontrar e resolver ameaças.|
|**Ação Pendente**|A investigação encontrou uma ameaça, como um email mal-intencionado, uma URL mal-intencionada ou uma configuração de caixa de correio arriscada, e uma ação para remediar essa ameaça está aguardando [aprovação.](air-review-approve-pending-completed-actions.md) <p> O **estado Ação Pendente** é disparado quando qualquer ameaça com uma ação correspondente é encontrada. No entanto, a lista de ações pendentes pode aumentar à medida que uma investigação é realizada. Exibir detalhes da investigação para ver se outros itens ainda estão pendentes de conclusão.|
|**Remediado**|A investigação foi concluída e todas as ações de correção foram aprovadas (notadas como totalmente remediadas). <p> **OBSERVAÇÃO:** as ações de correção aprovadas podem ter erros que impedem que as ações são tomadas. Independentemente de as ações de correção ter sido concluídas com êxito, o status da investigação não muda. Exibir detalhes da investigação.|
|**Parcialmente Remediado**|A investigação resultou em ações de correção, e algumas foram aprovadas e concluídas. Outras ações ainda estão [pendentes.](air-review-approve-pending-completed-actions.md)|
|**Falhou**|Pelo menos um analisador de investigação teve um problema em que não pôde ser concluído corretamente. <p> **OBSERVAÇÃO:** se uma investigação falhar após a aprovação das ações de correção, as ações de correção ainda poderão ter sido bem-sucedidas. Exibir os detalhes da investigação. |
|**Na fila por throttling**|Uma investigação está sendo mantida em uma fila. Quando outras investigações são concluídas, as investigações na fila começam. A throttling ajuda a evitar um desempenho ruim do serviço.  <p> **DICA:** Ações pendentes podem limitar quantas novas investigações podem ser realizadas. Certifique-se [de aprovar (ou rejeitar) ações pendentes.](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)|
|**Encerrado por Throttling**|Se uma investigação for mantida na fila por muito tempo, ela será interrompida. <p> **DICA:** você pode [iniciar uma investigação no Explorador de Ameaças.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Exibir detalhes de uma investigação

1. Vá para a central de segurança do Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) ) e entre.
2. No painel de navegação, selecione Central **de ações.**
3. Nas guias **Pendentes** **ou Histórico,** selecione uma ação. Seu painel de sobrevoo é aberto.
4. No painel do flyout, selecione **a página Abrir investigação.** 
5. Use as várias guias para saber mais sobre a investigação.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Exibir detalhes sobre um alerta relacionado a uma investigação

Certos tipos de alertas acionam a investigação automatizada no Microsoft 365. Para saber mais, consulte [políticas de alerta que disparam investigações automatizadas.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Vá para a central de segurança do Microsoft 365 [https://security.microsoft.com](https://security.microsoft.com) ) e entre.
2. No painel de navegação, selecione Central **de ações.**
3. Nas guias **Pendentes** **ou Histórico,** selecione uma ação. Seu painel de sobrevoo é aberto.
4. No painel do flyout, selecione **a página Abrir investigação.** 
5. Selecione a **guia Alertas** para exibir uma lista de todos os alertas associados a essa investigação.
6. Selecione um item na lista para abrir o painel do seu flyout. Lá, você pode exibir mais informações sobre o alerta.

## <a name="keep-the-following-points-in-mind"></a>Lembre-se dos seguintes pontos

- As contagens de email são calculadas no momento da investigação, e algumas contagens são recalculadas quando você abre subsulações de investigação (com base em uma consulta subjacente).

- As contagens de email mostradas  para os clusters de email na guia Email e o valor de quantidade de email mostrado no flyout do cluster são calculadas no momento da investigação e não mudam.

- A contagem de emails mostrada  na parte inferior da guia Email do flyout do cluster de email e a contagem de mensagens de email mostradas no Explorer refletem as mensagens de email recebidas após a análise inicial da investigação.

  Assim, um cluster de email que mostra uma quantidade original de 10 mensagens de email mostraria um total de 15 listas de emails quando mais cinco mensagens de email chegarem entre a fase de análise de investigação e quando o administrador analisar a investigação. Da mesma forma, investigações antigas podem começar a mostrar contagens maiores do que as consultas do Explorer, pois os dados no Microsoft Defender para Office 365 Plano 2 expiram após sete dias para avaliação e após 30 dias para licenças pagas.

  Mostrar contagens históricas e atuais em diferentes exibições é feita para indicar o impacto do email no momento da investigação e o impacto atual até o momento em que a correção é realizada.

- No contexto de email, você pode ver uma superfície de ameaça de anomalia de volume como parte da investigação. Uma anomalia de volume indica um pico em mensagens de email semelhantes em relação ao tempo do evento de investigação em comparação com períodos anteriores. Um pico no tráfego de email junto com determinadas características (por exemplo, domínio de assunto e remetente, similaridade de corpo e IP do remetente) é típico do início de campanhas ou ataques de email. No entanto, campanhas de email em massa, spam e legítimas normalmente compartilham essas características.

- Anomalias de volume representam uma ameaça em potencial e, portanto, podem ser menos graves em comparação com ameaças de malware ou phishing identificadas usando mecanismos de antivírus, detonação ou reputação mal-intencionada.

- Você não precisa aprovar todas as ações. Se você não concorda com a ação recomendada ou sua organização não escolhe  certos tipos de ações, você pode optar por Rejeitar as ações ou simplesmente ignorá-las e não tomar nenhuma ação.

- Aprovar e/ou rejeitar todas as ações permite que a investigação seja totalmente fechada (o status é remediado), enquanto algumas ações incompletas resulta na alteração do status da investigação para um estado parcialmente remediado.

## <a name="next-steps"></a>Próximas etapas

- [Revisar e aprovar ações pendentes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
