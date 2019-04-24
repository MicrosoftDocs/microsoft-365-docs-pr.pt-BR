---
title: Implantar configurações configuráveis na área de trabalho gerenciada da Microsoft
description: Implantar e acompanhar alterações de configurações configuráveis na área de trabalho gerenciada da Microsoft.
keywords: Microsoft Managed desktop, Microsoft 365, serviço, documentação, implantação, implantação em estágios, configurações configuráveis
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4662373b926d07558ecedd05c9dfcf472ceb6357
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278406"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Implantar e acompanhar configurações configuráveis-Microsoft Managed desktop

Depois de fazer alterações nas categorias de configuração e testar uma implantação, a página status da implantação permite que você comece a implantar suas configurações para grupos. Esta página mostra um resumo de cada configuração configurável. Ao abrir uma categoria de configuração, você pode implantar configurações para agrupar e acompanhar o progresso dessas implantações.

## <a name="deployment-statuses"></a>Status de implantação 

Estes são os Statues que você verá para cada implantação.

Status  | Explicação 
--- | --- 
Implantar | Sua alteração está aguardando para ser implantada nesse grupo.
Em andamento | A alteração está sendo aplicada aos dispositivos ativos desse grupo. 
Completo | A alteração foi concluída em todos os dispositivos ativos desse grupo. 
Falhou | A alteração falhou em 10 por cento de dispositivos ativos no grupo, portanto, a implantação foi interrompida.<br><br> Uma solicitação de suporte será aberta automaticamente com as operações de área de trabalho gerenciada da Microsoft para solucionar problemas de implantação. 
Revertidos | A alteração foi revertida para a última alteração implantada com êxito em todos os grupos de implantação.

## <a name="deploy-changes"></a>Implantar alterações

Mostraremos a imagem de plano de fundo da área de trabalho nessas instruções. Depois de testar uma implantação, implante as alterações da página status da implantação. 

**Para implantar alterações**

1. Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja implantar e, em seguida, selecione a implantação em estágios a ser implantada.
4. Selecione **implantar** para implantar a alteração em um dos grupos de implantação.

![Visão geral do status de implantação de configurações configuráveis](images/deploy-cs-overview.png)

A área de trabalho gerenciada da Microsoft recomenda a implantação de grupos de implantação nesta ordem: Test, First, Fast e, em seguida, ampla. 

Quando as alterações são concluídas em cada grupo, o status é alterado para **concluído**.

![Implantação de configurações configuráveis concluída](images/config-setting-complete.png)

## <a name="revert-deployment"></a>Reverter implantação

Depois de implantar uma alteração, você pode reverter do **status de implantação**. Ao reverter uma alteração **em andamento** ou **concluída**, a implantação atual é interrompida. A configuração será revertida para a última versão implantada em todos os grupos. 

Mostraremos as etapas para reverter uma alteração usando a imagem de plano de fundo da área de trabalho como um exemplo. 

**Para reverter uma alteração**
1. Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja reverter e selecione a implantação em estágios a ser revertida.
4. Em **precisa reverter essa alteração**, selecione **reverter implantação**.

![Reversão de implantação de configurações configurável](images/config-setting-revert.png) 

## <a name="additional-resources"></a>Recursos adicionais
- [Visão geral das configurações configuráveis](config-setting-overview.md)
- [Referência de configurações configuráveis](config-setting-ref.md) 
