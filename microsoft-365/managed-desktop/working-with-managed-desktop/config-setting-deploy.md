---
title: Implantar configurações configuráveis na área de trabalho gerenciada da Microsoft
description: Implantar e acompanhar alterações de configurações configuráveis na área de trabalho gerenciada da Microsoft.
keywords: Microsoft Managed desktop, Microsoft 365, serviço, documentação, implantação, implantação em estágios, configurações configuráveis
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 62a17c95f5dc6b11f446a27684c507d7aaa95b7b
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414160"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Implantar e acompanhar configurações configuráveis-Microsoft Managed desktop

Depois de fazer alterações nas categorias de configuração e testar uma implantação, você pode implantar e controlar o progresso da implantação no status da implantação. Esta página mostra um resumo de cada configuração configurável. Abra uma categoria de configuração para ver cada implantação e seus detalhes, para implantar as alterações. 

## <a name="deployment-statuses"></a>Status de implantação 

Estes são os Statues que você verá para cada implantação.

Status  | Explicação 
--- | --- 
Implantar | Sua alteração está aguardando para ser implantada neste anel.
Em andamento | A alteração está sendo aplicada aos dispositivos ativos neste toque. 
Completo | A alteração foi concluída em todos os dispositivos ativos neste anel. 
Failed | A alteração falhou em 10 por cento de dispositivos ativos no anel, portanto, a implantação foi interrompida.<br><br> Uma solicitação de suporte será aberta automaticamente com as operações de área de trabalho gerenciada da Microsoft para solucionar problemas de implantação. 
Revertidos | A alteração foi revertida para a última alteração implantada com êxito em todos os toques de implantação.

## <a name="deploy-changes"></a>Implantar alterações

Mostraremos a imagem de plano de fundo da área de trabalho nessas instruções. Depois de testar uma implantação, implante as alterações do status de implantação. 

**Para implantar alterações**

1. Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja implantar e, em seguida, selecione a implantação em estágios a ser implantada.
4. Selecione **implantar** para implantar a alteração em um dos toques de implantação.

![Visão geral do status de implantação de configurações configuráveis](images/deploy-cs-overview.png)

A área de trabalho gerenciada da Microsoft recomenda a implantação de toques de implantação nesta ordem: Test, First, Fast e, em seguida, ampla. 

Quando as alterações são concluídas em cada anel, o status é alterado para **concluído**.

![Implantação de configurações configuráveis concluída](images/config-setting-complete.png)

## <a name="revert-deployment"></a>Reverter implantação

Mostraremos a imagem de plano de fundo da área de trabalho nessas instruções. 

Depois de implantar uma alteração, você pode reverter do **status de implantação**. Ao reverter uma alteração **em andamento** ou **concluída**, a implantação atual é interrompida. A configuração será revertida para a última versão implantada em todos os toques. 

**Para reverter uma alteração**
1. Entrar no [portal de administração de área de trabalho gerenciaDa da Microsoft](http://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja reverter e selecione a implantação em estágios a ser revertida.
4. Em **precisa reverter essa alteração**, selecione **reverter implantação**.

![Reversão de implantação de configurações configurável](images/config-setting-revert.png) 

## <a name="additional-resources"></a>Recursos adicionais
- [Visão geral das configurações configuráveis](config-setting-overview.md)
- [Referência de configurações configuráveis](config-setting-ref.md) 