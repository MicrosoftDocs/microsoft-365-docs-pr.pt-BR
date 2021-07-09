---
title: Verificar o local de armazenamento de dados e atualizar as configurações de retenção de dados
description: Verificar o local de armazenamento de dados e atualizar as configurações de retenção de dados do Microsoft Defender para Ponto de Extremidade
keywords: dados, armazenamento, configurações, retenção, atualização
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: eb9e4b905112d3d144b10d68418695df3cda29cb
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339245"
---
# <a name="verify-data-storage-location-and-update-data-retention-settings-for-microsoft-defender-for-endpoint"></a>Verificar o local de armazenamento de dados e atualizar as configurações de retenção de dados do Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-gensettings-abovefoldlink)

Durante o processo de integração, um assistente o leva pelas configurações de armazenamento e retenção de dados do Defender para Ponto de Extremidade. 

Após concluir a integração, você pode verificar sua seleção na página de configurações de retenção de dados.

## <a name="verify-data-storage-location"></a>Verificar o local de armazenamento de dados
Durante a [fase Configurar](production-deployment.md), você teria selecionado o local para armazenar seus dados. 

Você pode verificar o local dos dados navegando para Configurações  >    >  **Retenção de dados de pontos de extremidade.**

## <a name="update-data-retention-settings"></a>Atualizar configurações de retenção de dados

Você pode atualizar as configurações de retenção de dados. Por padrão, o período de retenção é de 180 dias. 

1. No painel de navegação, **selecione** Configurações  >  **Retenção** de dados de pontos de  >  **extremidade.**

2. Selecione a duração da retenção de dados na lista lista listada.

    > [!NOTE]
    > Outras configurações não podem ser editáveis.

3. Clique **em Salvar preferências**.


## <a name="related-topics"></a>Tópicos relacionados
- [Atualizar configurações de retenção de dados](data-retention-settings.md)
- [Configurar notificações de alerta no Defender para Ponto de Extremidade](configure-email-notifications.md)
- [Configurar recursos avançados](advanced-features.md)
