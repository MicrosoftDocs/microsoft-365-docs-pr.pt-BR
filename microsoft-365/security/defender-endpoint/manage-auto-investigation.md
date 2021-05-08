---
title: Revisar ações de correção após investigações automatizadas
description: Revise e aprove (ou rejeite) ações de correção após uma investigação automatizada.
keywords: autoir, automatizado, investigação, detecção, correção, ação, pendente, aprovado
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.date: 01/29/2021
ms.technology: mde
ms.openlocfilehash: b0c983f4ba939cee6485570af774c8a728c73944
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274923"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>Revisar ações de correção após uma investigação automatizada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a>Ações de correção

Quando uma [investigação automatizada é](automated-investigations.md) executado, um veredito é gerado para cada prova investigada. Os vereditos podem ser *Mal-intencionados,* *Suspeitos* ou *Nenhuma ameaça encontrada.* 

Dependendo

- o tipo de ameaça, 
- o veredito resultante e 
- como os grupos de [dispositivos da](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) sua organização são configurados, 

As ações de correção podem ocorrer automaticamente ou somente após a aprovação pela equipe de operações de segurança da sua organização. 

Veja alguns exemplos:

- **Exemplo 1**: Os grupos de dispositivos da Fabrikam são definidos como **Completos - correção de ameaças automaticamente** (a configuração recomendada). Nesse caso, as ações de correção são tomadas automaticamente para artefatos considerados mal-intencionados após uma investigação automatizada (consulte [Review completed actions](#review-completed-actions)).

- **Exemplo 2**: Os dispositivos da Contoso estão incluídos em um grupo de dispositivos definido para Semi - exige aprovação **para qualquer correção**. Nesse caso, a equipe de operações de segurança da Contoso deve revisar e aprovar todas as ações de correção após uma investigação automatizada (consulte [Review pending actions](#review-pending-actions)).

- **Exemplo 3:** Tailspin Toys tem seus grupos de dispositivos definidos como **Nenhuma resposta automatizada** (não recomendada). Nesse caso, investigações automatizadas não ocorrem. Nenhuma ação de correção é realizada ou pendente e [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) nenhuma ação é registrada no Centro de Ações para seus dispositivos (consulte [Gerenciar grupos de dispositivos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)).

Seja realizada automaticamente ou após a aprovação, uma investigação automatizada pode resultar em uma ou mais ações de correção:
- Colocar em quarentena um arquivo
- Remover uma chave do Registro 
- Kill a process 
- Parar um serviço 
- Desabilitar um driver 
- Remover uma tarefa agendada

## <a name="review-pending-actions"></a>Revisar ações pendentes

1. Vá para o Microsoft 365 de segurança ( [https://security.microsoft.com](https://security.microsoft.com) ) e entre.
2. No painel de navegação, escolha **Central de ações**. 
3. Revise os itens na **guia Pendente.** 
4. Selecione uma ação para abrir seu painel de flyout.
5. No painel de sobrevoos, revise as informações e, em seguida, dê uma das seguintes etapas:
   - Selecione **Abrir página de investigação** para exibir mais detalhes sobre a investigação.
   - Selecione **Aprovar** para iniciar uma ação pendente.
   - Selecione **Rejeitar** para impedir que uma ação pendente seja tomada.
   - Selecione **Ir procurar** para entrar em Busca [Avançada](advanced-hunting-overview.md). 

## <a name="review-completed-actions"></a>Revisar ações concluídas

1. Vá para o Microsoft 365 de segurança ( [https://security.microsoft.com](https://security.microsoft.com) ) e entre.
2. No painel de navegação, escolha **Central de ações**. 
3. Revise os itens na guia **Histórico.** 
4. Selecione um item para exibir mais detalhes sobre essa ação de correção.
 
## <a name="undo-completed-actions"></a>Desfazer ações concluídas

Se você tiver determinado que um dispositivo ou um arquivo não é uma ameaça, poderá desfazer as ações de correção que foram tomadas, se essas ações foram tomadas automaticamente ou manualmente. Na central de ações, na guia **Histórico,** você pode desfazer qualquer uma das seguintes ações:  

| Origem da ação | Ações com suporte |
|:---|:---|
| - Investigação automatizada <br/>- Microsoft Defender Antivírus <br/>- Ações de resposta manual | - Isolar dispositivo <br/>- Restringir a execução de código <br/>- Colocar em quarentena um arquivo <br/>- Remover uma chave do Registro <br/>- Interromper um serviço <br/>- Desabilitar um driver <br/>- Remover uma tarefa agendada |

### <a name="to-undo-multiple-actions-at-one-time"></a>Para desfazer várias ações ao mesmo tempo

1. Vá para a Central de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.
2. Na guia **Histórico,** selecione as ações que você deseja desfazer. Certifique-se de selecionar itens que tenham o mesmo tipo de Ação. Um painel de sobrevoo é aberto.
3. No painel de sobrevoos, selecione **Desfazer**.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Para remover um arquivo da quarentena em vários dispositivos 

1. Vá para a Central de Ações ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e entre.
2. Na guia **Histórico,** selecione um item que tenha o arquivo De quarentena tipo **ação.**
3. No painel de sobrevoos, selecione **Aplicar a X mais instâncias deste** arquivo e selecione **Desfazer**.

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>Níveis de automação, resultados de investigação automatizados e ações resultantes

Os níveis de automação afetam se determinadas ações de correção são realizadas automaticamente ou somente após aprovação. Às vezes, sua equipe de operações de segurança tem mais etapas a serem tomadas, dependendo dos resultados de uma investigação automatizada. A tabela a seguir resume níveis de automação, resultados de investigações automatizadas e o que fazer em cada caso. 

|Configuração do grupo de dispositivos | Resultados automatizados da investigação | O que fazer |
|:---|:---|:---|
|**Completo - correção de ameaças automaticamente** (a configuração recomendada) |Um veredito de *Mal-intencionado* é atingido por uma evidência. <br/><br/>As ações de correção apropriadas são tomadas automaticamente. |[Revisar ações concluídas](#review-completed-actions) |
|**Completo - correção de ameaças automaticamente** |Um veredito de *Suspicious* é atingido para uma evidência. <br/><br/>As ações de correção estão aguardando aprovação para continuar. | [Aprovar (ou rejeitar) ações pendentes](#review-pending-actions) |
|**Semi - exigir aprovação para qualquer correção**  |Um veredito de *mal-intencionado* *ou suspeito* é atingido para uma evidência. <br/><br/>As ações de correção estão aguardando aprovação para continuar.  |[Aprovar (ou rejeitar) ações pendentes](#review-pending-actions) |
|**Semi - exigir aprovação para correção de pastas principais** |Um veredito de *Mal-intencionado* é atingido por uma evidência. <br/><br/>Se o artefato for um arquivo ou executável e estiver em um diretório do sistema operacional, como a pasta Windows ou a pasta Arquivos do programa, as ações de correção estão pendentes de aprovação. <br/><br/>Se o artefato não *estiver em* um diretório do sistema operacional, as ações de correção serão tomadas automaticamente. |1. [Aprovar (ou rejeitar) ações pendentes](#review-pending-actions)<br/><br/>2. [Revisar ações concluídas](#review-completed-actions) |
|**Semi - exigir aprovação para correção de pastas principais** |Um veredito de *Suspicious* é atingido para uma evidência. <br/><br/>As ações de correção estão pendentes de aprovação.  |[Aprovar (ou rejeitar) ações pendentes](#review-pending-actions).|
|**Semi - exigir aprovação para correção de pastas não temporárias** |Um veredito de *Mal-intencionado* é atingido por uma evidência. <br/><br/>Se o artefato for um arquivo ou executável que não esteja em uma pasta temporária, como a pasta de downloads do usuário ou pasta temporária, as ações de correção estão pendentes de aprovação. <br/><br/>Se o artefato for um arquivo ou executável que *esteja* em uma pasta temporária, as ações de correção serão executadas automaticamente.  |1. [Aprovar (ou rejeitar) ações pendentes](#review-pending-actions)<br/><br/>2. [Revisar ações concluídas](#review-completed-actions)  |
|**Semi - exigir aprovação para correção de pastas não temporárias** |Um veredito de *Suspicious* é atingido para uma evidência. <br/><br/>As ações de correção estão pendentes de aprovação. |[Aprovar (ou rejeitar) ações pendentes](#review-pending-actions)  | 
|Qualquer um dos níveis **de automação Completo** ou **Semi** |Um veredito de *Nenhuma ameaça encontrada* é alcançado para uma evidência. <br/><br/>Nenhuma ação de correção é tomada e nenhuma ação está pendente de aprovação. |[Exibir detalhes e resultados das investigações automatizadas](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center) |
|**Nenhuma resposta automatizada** (não recomendada)|Nenhuma investigação automatizada é realizada, portanto, nenhum veredito é atingido e nenhuma ação de correção é tomada ou aguarda aprovação. |[Considere configurar ou alterar seus grupos de dispositivos para usar **automação completa** ou **semi**](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups) |

No Microsoft Defender para Ponto de Extremidade, todos os vereditos são rastreados no [Centro de Ações](auto-investigation-action-center.md#new-a-unified-action-center).

## <a name="next-steps"></a>Próximas etapas

- [Saiba mais sobre os recursos de resposta ao vivo](live-response.md)
- [Busca proativamente por ameaças com busca avançada](advanced-hunting-overview.md)
- [Endereços falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>Confira também

- [Visão geral das investigações automatizadas](automated-investigations.md)
