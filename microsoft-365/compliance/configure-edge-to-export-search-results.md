---
title: Usar a ferramenta de exportação de descoberta eletrônica do Office 365 no Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Você precisa habilitar o suporte do ClickOnce para usar o Microsoft Edge para exportar os resultados da pesquisa da pesquisa de conteúdo e da descoberta eletrônica no centro de segurança e conformidade.
ms.openlocfilehash: 896d39d81fa56b3a118b2bee450476e422ac3921
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595728"
---
# <a name="use-the-office-365-ediscovery-export-tool-in-microsoft-edge"></a>Usar a ferramenta de exportação de descoberta eletrônica do Office 365 no Microsoft Edge

Como resultado de alterações recentes no Microsoft Edge, o suporte do ClickOnce não está mais habilitado por padrão. Para continuar a usar a ferramenta de exportação de descoberta eletrônica do Microsoft Office 365 para baixar os resultados de pesquisa de descoberta eletrônica ou pesquisa de conteúdo, você precisa usar [o Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) ou habilitar o suporte do ClickOnce no Microsoft Edge.

## <a name="how-to-enable-clickonce-support-in-microsoft-edge"></a>Como habilitar o suporte do ClickOnce no Microsoft Edge

1. No Microsoft Edge, navegue até **edge://flags/#edge-Once**.

2. Se o valor existente for definido como **padrão** ou **desabilitado** na lista suspensa, altere-o para **habilitado**.
    
   ![](media/ClickOnceimage1.png)

3. Role para baixo até a parte inferior da janela do navegador e clique em **reiniciar** para reiniciar a borda.

   ![](media/ClickOnceimage2.png)

**Observação:** As organizações podem usar a política de grupo para desabilitar o suporte do ClickOnce. Para verificar se há uma política organizacional para o suporte do ClickOnce, navegue até **Edge://Policy**. A captura de tela a seguir mostra que o ClickOnce está habilitado em toda a organização. Se esse valor de política for definido como **false**, você precisará entrar em contato com um administrador na sua organização.

![](media/ClickOnceimage3.png)

## <a name="install-and-run-the-office-365-ediscovery-export-tool"></a>Instalar e executar a ferramenta de exportação de descoberta eletrônica do Office 365

1. Clique em **baixar resultados** na página de menu suspenso de uma exportação na pesquisa de conteúdo ou em um caso de descoberta eletrônica.

   ![Clique em baixar resultados na página do menu de atalho para baixar os resultados da pesquisa](media/ClickOnceExport1.png)

2. Você será solicitado a confirmar a inicialização da ferramenta, clique em **abrir**.

   ![Clique em abrir para iniciar a ferramenta de exportação de descoberta eletrônica](media/ClickOnceimage4.png)

   Se a ferramenta de exportação de descoberta eletrônica do Microsoft Office 365 não estiver instalada, você receberá um aviso de segurança 

   ![Clique em instalar para instalar a ferramenta de exportação de descoberta eletrônica](media/ClickOnceimage5.png)

3. Clique em **Instalar**. Após a instalação, a ferramenta de exportação será iniciada automaticamente.

Para obter mais informações, consulte os seguintes tópicos:

- [Exportar resultados de Pesquisa de Conteúdo](export-search-results.md)

- [Como habilitar os sinalizadores de experimento no Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
