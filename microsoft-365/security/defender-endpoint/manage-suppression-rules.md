---
title: Gerenciar regras de supressão do Microsoft Defender para Pontos de Extremidade
description: Talvez seja necessário impedir que alertas apareçam no portal usando regras de supressão. Saiba como gerenciar suas regras de supressão no Microsoft Defender ATP.
keywords: gerenciar supressão, regras, nome da regra, escopo, ação, alertas, ativar, desativar
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d2ff8fa1f07f82c3cc719f49f50ee25937aea243
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187560"
---
# <a name="manage-suppression-rules"></a>Gerenciar regras de supressão

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


Pode haver cenários em que você precisa suprimir alertas de aparecer no portal. Você pode criar regras de supressão para alertas específicos conhecidos como ferramentas ou processos conhecidos em sua organização. Para obter mais informações sobre como suprimir alertas, consulte [Suppress alerts](manage-alerts.md).

Você pode exibir uma lista de todas as regras de supressão e gerenciá-las em um só lugar. Você também pode ativar ou desativar uma regra de supressão de alerta.


1. No painel de navegação, selecione **Configurações**  >  **Supressão de alerta**. A lista de regras de supressão criadas pelos usuários em sua organização é exibida.

2. Selecione uma regra clicando na caixa de seleção ao lado do nome da regra.

3. Clique **em Ativar regra,** **Editar regra** ou Excluir  **regra**. Ao fazer alterações em uma regra, você pode optar por liberar alertas que já foram suprimidos, independentemente de esses alertas corresponderem ou não aos novos critérios. 


## <a name="view-details-of-a-suppression-rule"></a>Exibir detalhes de uma regra de supressão

1. No painel de navegação, selecione **Configurações**  >  **Supressão de alerta**. A lista de regras de supressão criadas pelos usuários em sua organização é exibida.

2. Clique em um nome de regra. Os detalhes da regra são exibidos. Você verá os detalhes da regra, como status, escopo, ação, número de alertas correspondentes, criado por e data quando a regra foi criada. Você também pode exibir alertas associados e as condições de regra.

## <a name="related-topics"></a>Tópicos relacionados

- [Gerenciar alertas](manage-alerts.md)
