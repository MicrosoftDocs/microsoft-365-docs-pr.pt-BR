---
title: Implantar configurações configuráveis na área de trabalho gerenciada da Microsoft
description: Implantar e acompanhar alterações de configurações configuráveis na área de trabalho gerenciada da Microsoft.
keywords: Microsoft Managed desktop, Microsoft 365, serviço, documentação, implantação, implantação em estágios, configurações configuráveis
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 244070c7fd2d5c98f87990bcb4ef6de96ca5a90c
ms.sourcegitcommit: b65c80051e53d9be223f4769f4d42a39f5a07735
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962238"
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

![Espaço de trabalho de status de implantação. Painel de sites confiáveis à direita. Na seção grupos de implantação há três colunas: grupos de implantação, dispositivos e status. Na coluna status, "implantar" é realçado.](images/1deployedit.png)
Recomendamos a implantação de grupos de implantação nesta ordem: Test, First, Fast e, em seguida, ampla. 

Quando as alterações são concluídas em cada grupo, o status é alterado para **concluído**.

![Espaço de trabalho de status de implantação com colunas para data atualizada, versão, teste, primeiro, rápida e ampla. A linha de proxy é expandida, mostrando uma configuração com data sinalizada como "completa" em cada um dos quatro grupos de implantação.](images/2completeedit.png)

## <a name="revert-deployment"></a>Reverter implantação

Depois de implantar uma alteração, você pode reverter do **status de implantação**. Ao reverter uma alteração **em andamento** ou **concluída**, a implantação atual é interrompida. A configuração será revertida para a última versão implantada em todos os grupos. 

Mostraremos as etapas para reverter uma alteração usando a imagem de plano de fundo da área de trabalho como um exemplo. 

**Para reverter uma alteração**
1. Entrar no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mwaasportal)
2. Em **configurações**, selecione **configurável**.
3. Em espaço de trabalho de **status da implantação** , selecione a configuração que você deseja reverter e selecione a implantação em estágios a ser revertida.
4. Em **precisa reverter essa alteração?**, selecione **reverter implantação**.

![Espaço de trabalho de status de implantação. As páginas iniciais do navegador estão selecionadas, abrindo um painel do lado direito com dados sobre a alteração enviada e seu status. Na parte inferior é a área "precisa reverter esta alteração", onde você pode selecionar "reverter a implantação".](images/3revert.png) 

## <a name="additional-resources"></a>Recursos adicionais
- [Visão geral das configurações configuráveis](config-setting-overview.md)
- [Referência de configurações que podem ser alteradas](config-setting-ref.md) 
