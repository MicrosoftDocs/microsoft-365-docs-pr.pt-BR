---
title: Implantar configurações configuráveis na área de trabalho gerenciada da Microsoft
description: Implantar e acompanhar alterações de configurações configuráveis na área de trabalho gerenciada da Microsoft.
keywords: Microsoft Managed desktop, Microsoft 365, serviço, documentação, implantação, implantação em estágios, configurações configuráveis
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7e3827dc12c04d2c7952f9321a70714691c5ed47
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012296"
---
# <a name="deploy-and-track-configurable-settings---microsoft-managed-desktop"></a>Implantar e acompanhar configurações configuráveis-Microsoft Managed desktop

Depois de fazer alterações nas categorias de configuração e testar uma implantação, a página status da implantação permite que você comece a implantar suas configurações para grupos. Esta página mostra um resumo de cada configuração configurável. Ao abrir uma categoria de configuração, você pode implantar configurações para agrupar e acompanhar o progresso dessas implantações.

## <a name="deployment-statuses"></a>Status de implantação 

Estes são os status que você verá para cada implantação.

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

1. Entrar no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja implantar e, em seguida, selecione a implantação em estágios a ser implantada.
4. Selecione **implantar** para implantar a alteração em um dos grupos de implantação.

![Configurações configuráveis status de](images/1deployedit.png) implantação visão geral da área de trabalho gerenciada da Microsoft recomenda a implantação de grupos de implantação nesta ordem: Test, First, Fast e, em seguida, ampla. 

Quando as alterações são concluídas em cada grupo, o status é alterado para **concluído**.

![Implantação de configurações configuráveis concluída](images/2completeedit.png)

## <a name="revert-deployment"></a>Reverter implantação

Depois de implantar uma alteração, você pode reverter do **status de implantação**. Ao reverter uma alteração **em andamento** ou **concluída**, a implantação atual é interrompida. A configuração será revertida para a última versão implantada em todos os grupos. 

Mostraremos as etapas para reverter uma alteração usando a imagem de plano de fundo da área de trabalho como um exemplo. 

**Para reverter uma alteração**
1. Entrar no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja reverter e selecione a implantação em estágios a ser revertida.
4. Em **precisa reverter essa alteração**, selecione **reverter implantação**.

![Reversão de implantação de configurações configurável](images/3revert.png) 

## <a name="additional-resources"></a>Recursos adicionais
- [Visão geral das configurações configuráveis](config-setting-overview.md)
- [Referência de configurações que podem ser alteradas](config-setting-ref.md) 
