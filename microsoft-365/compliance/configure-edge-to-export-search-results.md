---
title: Use a Ferramenta de Exportação de Descoberta Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Você precisa habilitar ClickOnce suporte para usar a versão mais recente do Microsoft Edge para baixar os resultados da pesquisa de Pesquisa de Conteúdo e Descoberta Digital no centro de segurança e conformidade.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546815"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a>Use a Ferramenta de Exportação de Descoberta Microsoft Edge

Como resultado de alterações recentes na versão mais recente do Microsoft Edge, ClickOnce suporte não está mais habilitado por padrão. Para continuar usando a Ferramenta de Exportação de Descoberta Digital para baixar os resultados da Pesquisa de Conteúdo ou da Pesquisa de Descoberta ClickOnce, você precisa usar o [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) ou habilitar o suporte ClickOnce na versão mais recente do Microsoft Edge.

## <a name="enable-clickonce-support-in-microsoft-edge"></a>Habilitar ClickOnce suporte em Microsoft Edge

1. Em Microsoft Edge, vá para **edge://flags/#edge-click-once**.

2. Se o valor existente estiver definido como **Padrão** ou **Desabilitado** na lista de menus suspenso, altere-o para **Habilitado**.

   ![Selecionar Habilitado na lista suspenso](../media/ClickOnceimage1.png)

3. Role para baixo até a parte inferior da janela do navegador e clique em **Reiniciar** para reiniciar Borda.

   ![Clique em Reiniciar](../media/ClickOnceimage2.png)

**Observação:** As organizações podem usar a Política de Grupo para desabilitar ClickOnce suporte. Para verificar se há uma política organizacional para suporte ClickOnce, vá para **edge://policy**. A captura de tela a seguir mostra que ClickOnce está habilitado em toda a organização. Se esse valor de política for definido como **false,** você precisará entrar em contato com um administrador em sua organização.

![Lista de políticas organizacionais de Borda](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a>Instalar e executar a Ferramenta de Exportação de Descoberta Digital

1. Clique **em Baixar resultados** na página de sobrevoo de uma exportação na Pesquisa de Conteúdo ou em um caso de Descoberta eDiscovery.

   ![Clique em Baixar resultados na página de sobrevoo para baixar resultados da pesquisa](../media/ClickOnceExport1.png)

2. Você será solicitado com uma confirmação para iniciar a ferramenta, Clique em **Abrir**.

   ![Clique em Abrir para iniciar a Ferramenta de Exportação de Descoberta Digital](../media/ClickOnceimage4.png)

   Se a Ferramenta de Exportação de Descoberta Digital não estiver instalada, você será solicitado com um Aviso de Segurança, 

   ![Clique em Instalar para instalar a Ferramenta de Exportação de Descoberta Digital](../media/ClickOnceimage5.png)

3. Clique em **Instalar**. Depois de instalada, a ferramenta de exportação será lançada automaticamente.

Para mais informações, confira os seguintes tópicos:

- [Exportar resultados de Pesquisa de Conteúdo](export-search-results.md)

- [Como habilitar sinalizadores de experimento em Microsoft Edge](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
