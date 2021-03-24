---
title: Investigar alertas do Microsoft Defender para Pontos de Extremidade
description: Use as opções de investigação para obter detalhes sobre alertas que afetam sua rede, o que significam e como resolvê-los.
keywords: investigar, investigação, dispositivos, dispositivo, fila de alertas, painel, endereço IP, arquivo, envio, envios, análise profunda, linha do tempo, pesquisa, domínio, URL, IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 498f2d83af6e2eb7fc56b232bafd9fc49d9d4fd9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054269"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>Investigar alertas no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

Investigue alertas que estão afetando sua rede, entenda o que significam e como resolvê-los.

Selecione um alerta na fila de alertas para ir para a página de alerta. Essa exibição contém o título do alerta, os ativos afetados, o painel de detalhes e o texto do alerta.

Na página de alerta, comece sua investigação selecionando os ativos afetados ou qualquer uma das entidades sob a exibição da árvore de histórias de alerta. O painel de detalhes preenche automaticamente com mais informações sobre o que você selecionou. Para ver que tipo de informação você pode exibir aqui, leia [Review alerts in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/review-alerts).

## <a name="investigate-using-the-alert-story"></a>Investigar usando o artigo de alerta

O story de alerta detalha por que o alerta foi disparado, eventos relacionados que aconteceram antes e depois, bem como outras entidades relacionadas.

As entidades são clicáveis e todas as entidades que não são um alerta podem ser expandidas usando o ícone de expansão no lado direito do cartão dessa entidade. A entidade em foco será indicada por uma faixa azul no lado esquerdo do cartão dessa entidade, com o alerta no título em foco inicialmente.

Expanda entidades para exibir detalhes rapidamente. Selecionar uma entidade alterna o contexto do painel de detalhes para essa entidade e permitirá que você revise mais informações, bem como gerencie essa entidade. Selecionar *...* à direita do cartão de entidade revelará todas as ações disponíveis para essa entidade. Essas mesmas ações aparecem no painel de detalhes quando essa entidade está em foco.

> [!NOTE]
> A seção de texto do alerta pode conter mais de um alerta, com alertas adicionais relacionados à mesma árvore de execução que aparece antes ou depois do alerta selecionado.

![Um exemplo de um artigo de alerta com um alerta em foco e alguns cartões expandidos](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a>Tomar medidas do painel de detalhes

Depois de selecionar uma entidade de interesse, o painel de detalhes mudará para exibir informações sobre o tipo de  entidade selecionado, informações históricas quando estiver disponível e oferecer controles para tomar medidas nessa entidade diretamente na página de alerta.

Depois de terminar de investigar, volte para o alerta que você começou com, marque o status do alerta como **Resolvido** e classifique-o como alerta **False** ou **True.** Classificar alertas ajuda a ajustar esse recurso para fornecer alertas mais verdadeiros e menos alertas falsos.

Se você classificá-lo como um alerta verdadeiro, também poderá selecionar uma determinação, conforme mostrado na imagem abaixo.

![Um trecho do painel de detalhes com um alerta resolvido e o drop-down de determinação expandido](images/alert-details-resolved-true.png)

Se você estiver enfrentando um alerta falso com um aplicativo de linha de negócios, crie uma regra de supressão para evitar esse tipo de alerta no futuro.

![ações e classificação no painel de detalhes com a regra de supressão realçada](images/alert-false-suppression-rule.png)

> [!TIP]
> Se você estiver enfrentando problemas não descritos acima, use o botão para fornecer 🙂 comentários ou abrir um tíquete de suporte.


## <a name="related-topics"></a>Tópicos relacionados
- [Exibir e organizar a fila de alertas do Microsoft Defender for Endpoint](alerts-queue.md)
- [Gerenciar alertas do Microsoft Defender para Pontos de Extremidade](manage-alerts.md)
- [Investigar um arquivo associado a um alerta do Defender para Ponto de Extremidade](investigate-files.md)
- [Investigar dispositivos na lista Defender para Dispositivos de Ponto de Extremidade](investigate-machines.md)
- [Investigar um endereço IP associado a um alerta do Defender para Ponto de Extremidade](investigate-ip.md)
- [Investigar um domínio associado a um alerta do Defender para Ponto de Extremidade](investigate-domain.md)
- [Investigar uma conta de usuário no Defender para Ponto de Extremidade](investigate-user.md)


