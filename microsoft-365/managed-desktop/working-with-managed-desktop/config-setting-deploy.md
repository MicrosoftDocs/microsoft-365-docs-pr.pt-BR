---
title: Implantar configurações configuráveis na Área de Trabalho Gerenciada da Microsoft
description: Implante e acompanhe as alterações de configurações configuráveis na Área de Trabalho Gerenciada da Microsoft.
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação, implantar, implantação em estágios, configurações configuráveis
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a24d0dc64e2262a8b208119c45a4a6bade701c10
ms.sourcegitcommit: adaedd1418a3bd6e4875b77fd9e008b47e0b2a51
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/18/2020
ms.locfileid: "48104529"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Implantar e controlar configurações configuráveis - Área de Trabalho Gerenciada da Microsoft

Depois de fazer alterações em suas categorias de configuração e preparar uma implantação, a página status de implantação permite que você comece a implantar suas configurações em grupos. Esta página mostra um resumo de cada configuração configurável. Ao abrir uma categoria de configuração, você pode implantar configurações em grupos e acompanhar o progresso dessas implantações.

## <a name="deployment-statuses"></a>Status de implantação 

Estes são os status que você verá para cada implantação.

Status  | Explicação 
--- | --- 
Implantar | Sua alteração está aguardando para ser implantada nesse grupo.
Em andamento | A alteração está sendo aplicada a dispositivos ativos nesse grupo. 
Completo | A alteração foi concluída em todos os dispositivos ativos neste grupo. 
Falhou | A alteração falhou em 10% dos dispositivos ativos no grupo, portanto, a implantação foi interrompida.<br><br> Uma solicitação de suporte será aberta automaticamente com as operações da Área de Trabalho Gerenciada da Microsoft para solucionar problemas de implantação. 
Revertida | A alteração foi revertida para a última alteração que foi implantada com êxito em todos os grupos de implantação.

## <a name="deploy-changes"></a>Implantar alterações

Mostraremos a imagem de plano de fundo da área de trabalho nestas instruções. Depois de preparar uma implantação, implante as alterações da página Status da implantação. 

**Para implantar alterações**

1. Entre no [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações.**
3. No espaço de trabalho **de status** de Implantação, selecione a configuração que você deseja implantar e selecione a implantação em estágios a ser implantada.
4. Selecione **Implantar** para implantar a alteração em um dos grupos de implantação.

> [!NOTE] 
> O ícone de cuidado laranja indica que há um grupo anterior disponível para implantação, pois é recomendável a distribuição em ordem. 

<!-- Needs picture updated to show MEM ![Deployment status workspace. Trusted sites pane on the right. In the Deployment groups section are three columns: deployment groups, devices, and status. In the status column, "deploy" is highlighted.](../../media/1deployedit.png) -->

Recomendamos a implantação em grupos de implantação nesta ordem: Test, First, Fast e, em seguida, Broad. 

Quando as alterações são concluídas em cada grupo, o status muda para **Concluído.**

<!-- Needs picture updated to show MEM ![Deployment status workspace with columns for date updated, version, test, first, fast, and broad. The Proxy row is expanded, showing a dated setting flagged as "complete" in each of the four deployment groups.](../../media/2completeedit.png) -->

## <a name="revert-deployment"></a>Reverter implantação

Depois de ter implantado uma alteração, você pode reverter do **status de implantação.** Quando você reverte uma alteração que está **em** andamento ou **Concluída,** a implantação atual é interrompida. A configuração será revertida para a última versão que foi implantada em todos os grupos. 

Mostraremos as etapas para reverter uma alteração usando a imagem de plano de fundo da área de trabalho como exemplo. 

**Para reverter uma alteração**
1. Entre no [Microsoft Endpoint Manager e](https://endpoint.microsoft.com/) navegue até o menu **Dispositivos**
2. Procure a seção Área de Trabalho Gerenciada da Microsoft, selecione **Configurações.**
3. No espaço de trabalho **de status** de Implantação, selecione a configuração que você deseja reverter e selecione a implantação em estágios a ser revertida.
4. Em **Precisa reverter essa alteração?**, selecione Reverter **implantação**.

<!-- Needs picture updated to show MEM ![Deployment status workspace. Browser start pages is selected, opening a pane on the right side with data about the submitted change and its status. At the bottom is the "need to revert this change" area where you can select "Revert deployment."](../../media/3revert.png) -->

## <a name="additional-resources"></a>Recursos adicionais
- [Visão geral de configurações configuráveis](config-setting-overview.md)
- [Referência de configurações que podem ser alteradas](config-setting-ref.md) 
