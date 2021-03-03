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
ms.openlocfilehash: 2d6d4a710878d65462110f317cafeeef64617667
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406683"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Detalhes e resultados de uma investigação automatizada no Microsoft 365

**Aplica-se a**
- [Plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Quando ocorre [uma investigação](office-365-air.md) automatizada no Microsoft Defender para [Office 365](office-365-atp.md), os detalhes sobre essa investigação ficam disponíveis durante e após o processo de investigação automatizado. Se você tiver as permissões necessárias, poderá exibir esses detalhes no centro de segurança do Microsoft 365. Os detalhes da investigação fornecem o status atualizado e a capacidade de aprovar ações pendentes.

> [!TIP]
> Confira a nova página de investigação unificada no centro de segurança do Microsoft 365. Para saber mais, consulte [(NEW!) Página de investigação unificada](../mtp/mtp-autoir-results.md#new-unified-investigation-page).

## <a name="investigation-status"></a>Status da investigação

O status da investigação indica o andamento da análise e das ações. À medida que a investigação é executado, o status muda para indicar se as ameaças foram encontradas e se as ações foram aprovadas.

|Status|Descrição|
|:---|:---|
|**Iniciando**|A investigação foi disparada e aguardando para começar a ser executado.|
|**Em execução**|O processo de investigação foi iniciado e está em andamento. Esse estado também ocorre quando [as ações pendentes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) são aprovadas.|
|**Nenhuma ameaça encontrada**|A investigação foi concluída e nenhuma ameaça (conta de usuário, mensagem de email, URL ou arquivo) foi identificada. <p> **DICA:** se você suspeitar que algo foi perdido (como um falso negativo), poderá tomar medidas usando [o Explorador de Ameaças.](threat-explorer.md)|
|**Ameaça Encontrada**|A investigação automatizada encontrou problemas, mas não há ações de correção específicas para resolver esses problemas. <p> O status **Ameaças Encontradas** pode ocorrer quando algum tipo de atividade do usuário foi identificado, mas nenhuma ação de limpeza está disponível. Exemplos incluem qualquer uma das seguintes atividades do usuário: <br/>- Um [evento de prevenção contra](../../compliance/data-loss-prevention-policies.md) perda de dados (DLP)<br/>- Uma anomalia de envio de email<br/>- Malware enviado<br/>- Phishing enviado <p> A investigação não encontrou URLs mal-intencionadas, arquivos ou mensagens de email para corrigir e nenhuma atividade de caixa de correio a ser corrigida, como a reação de regras de encaminhamento ou delegação. <p> **DICA**: se você suspeitar que algo foi perdido (como um falso negativo), poderá investigar e tomar medidas usando [o Explorador de Ameaças.](threat-explorer.md)|
|**Encerrado pelo sistema**|A investigação foi interrompida. Uma investigação pode parar por vários motivos: <br/>- As ações pendentes da investigação expiraram. Tempo de espera das ações pendentes após aguardar aprovação por uma semana.<br/>- Há muitas ações. Por exemplo, se houver muitos usuários clicando em URLs mal-intencionadas, ela poderá exceder a capacidade da investigação de executar todos os analisadores, para que a investigação pare.<p> **DICA**: Se uma investigação for interrompida antes que as ações fossem tomadas, tente usar [o Explorador](threat-explorer.md) de Ameaças para encontrar e resolver ameaças.|
|**Ação Pendente**|A investigação encontrou uma ameaça, como um email mal-intencionado, uma URL mal-intencionada ou uma configuração de caixa de correio arriscada e uma ação para correção dessa ameaça está aguardando [aprovação.](air-review-approve-pending-completed-actions.md) <p> O **estado ação pendente** é disparado quando qualquer ameaça com uma ação correspondente é encontrada. No entanto, a lista de ações pendentes pode aumentar à medida que uma investigação é executado. Exibir detalhes da investigação para ver se outros itens ainda estão pendentes de conclusão.|
|**Remediado**|A investigação foi concluída e todas as ações de correção foram aprovadas (notadas como totalmente remediadas). <p> **OBSERVAÇÃO**: As ações de correção aprovadas podem ter erros que impedem que as ações tenham sido tomadas. Independentemente de as ações de correção foram concluídas com êxito, o status da investigação não muda. Exibir detalhes da investigação.|
|**Parcialmente Remediado**|A investigação resultou em ações de correção e algumas foram aprovadas e concluídas. Outras ações ainda [estão pendentes](air-review-approve-pending-completed-actions.md).|
|**Falhou**|Pelo menos um analisador de investigação encontrou um problema em que ele não pôde ser concluído corretamente. <p> **OBSERVAÇÃO**: se uma investigação falhar após a aprovação das ações de correção, as ações de correção ainda poderão ter êxito. Exibir os detalhes da investigação. |
|**En fila por throttling**|Uma investigação está sendo realizada em uma fila. Quando outras investigações são concluídas, as investigações em fila começam. A coação ajuda a evitar um desempenho de serviço ruim.  <p> **DICA**: Ações pendentes podem limitar quantas novas investigações podem ser realizadas. Certifique-se [de aprovar (ou rejeitar) ações pendentes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions).|
|**Encerrado por throttling**|Se uma investigação for mantida na fila por muito tempo, ela será interrompida. <p> **DICA**: Você pode [iniciar uma investigação do Explorador de Ameaças.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Exibir detalhes de uma investigação

1. Vá para o Centro de Segurança do Microsoft 365 ( <https://security.microsoft.com> ) e entre.
2. No painel de navegação, selecione **Centro de ações**.
3. Nas guias **Pendentes ou** **Histórico,** selecione uma ação. Seu painel de sobrevoo é aberto.
4. No painel de sobrevoos, selecione **Abrir página de investigação**. 
5. Use as várias guias para saber mais sobre a investigação.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Exibir detalhes sobre um alerta relacionado a uma investigação

Certos tipos de alertas disparam investigação automatizada no Microsoft 365. Para saber mais, confira [políticas de alerta que disparam investigações automatizadas.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Vá para o Centro de Segurança do Microsoft 365 ( <https://security.microsoft.com> ) e entre.
2. No painel de navegação, selecione **Centro de ações**.
3. Nas guias **Pendentes ou** **Histórico,** selecione uma ação. Seu painel de sobrevoo é aberto.
4. No painel de sobrevoos, selecione **Abrir página de investigação**. 
5. Selecione a **guia Alertas** para exibir uma lista de todos os alertas associados a essa investigação.
6. Selecione um item na lista para abrir seu painel de sobrevoos. Lá, você pode exibir mais informações sobre o alerta.

## <a name="keep-the-following-points-in-mind"></a>Lembre-se dos seguintes pontos

- As contagens de email são calculadas no momento da investigação e algumas contagens são recalculadas quando você abre sub-controles de investigação (com base em uma consulta subjacente).

- As contagens de email mostradas  para os clusters de email na guia Email e o valor de quantidade de email mostrado no sobrevoo de cluster são calculados no momento da investigação e não mudam.

- A contagem de emails mostrada  na parte inferior da guia Email do cluster de email e a contagem de mensagens de email mostradas no Explorer refletem as mensagens de email recebidas após a análise inicial da investigação.

  Assim, um cluster de email que mostra uma quantidade original de 10 mensagens de email mostraria um total de 15 listas de emails quando mais cinco mensagens de email chegarem entre a fase de análise de investigação e quando o administrador revisar a investigação. Da mesma forma, as investigações antigas podem começar a mostrar contagens mais altas do que as consultas do Explorer mostram, porque os dados no Microsoft Defender para o Plano 2 do Office 365 expiram após sete dias para testes e após 30 dias para licenças pagas.

  Mostrar contagens históricas e atuais em diferentes exibições é feita para indicar o impacto do email no momento da investigação e o impacto atual até o momento em que a correção é executado.

- No contexto do email, você pode ver uma superfície de ameaça de anomalia de volume como parte da investigação. Uma anomalia de volume indica um pico em mensagens de email semelhantes ao redor do tempo do evento de investigação em comparação com os períodos de tempo anteriores. Um pico no tráfego de email junto com determinadas características (por exemplo, domínio de assunto e remetente, semelhança de corpo e IP do remetente) é típico do início de campanhas de email ou ataques. No entanto, campanhas de email em massa, spam e legítimas normalmente compartilham essas características.

- As anomalias de volume representam uma ameaça potencial e, portanto, podem ser menos graves em comparação a ameaças de malware ou phishing identificadas usando mecanismos anti-vírus, detonação ou reputação mal-intencionada.

- Você não precisa aprovar todas as ações. Se você não concordar com a ação recomendada ou sua organização não escolher  determinados tipos de ações, escolha Rejeitar as ações ou simplesmente ignorá-las e não tomar nenhuma ação.

- Aprovar e/ou rejeitar todas as ações permite que a investigação seja totalmente fechada (o status é remediado), deixando algumas ações incompletas resulta no status da investigação mudando para um estado parcialmente remediado.

## <a name="next-steps"></a>Próximas etapas

- [Revisar e aprovar ações pendentes](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
