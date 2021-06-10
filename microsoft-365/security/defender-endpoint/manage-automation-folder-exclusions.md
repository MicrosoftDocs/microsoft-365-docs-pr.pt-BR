---
title: Gerenciar exclusões de pasta de automação
description: Adicione exclusões de pastas de automação para controlar os arquivos excluídos de uma investigação automatizada.
keywords: gerenciar, automação, exclusão, bloquear, limpar, mal-intencionado
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
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185832"
---
# <a name="manage-automation-folder-exclusions"></a>Gerenciar exclusões de pasta de automação 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

As exclusões de pastas de automação permitem que você especifique pastas que a investigação automatizada ignorará. 

Você pode controlar os seguintes atributos sobre a pasta que você gostaria de ser ignorada:
- Pastas 
- Extensões dos arquivos
- Nomes de arquivos


**Pastas**<br>
Você pode especificar uma pasta e suas subpastas a serem ignoradas. 


>[!NOTE]
>No momento, ainda não há suporte para o uso de cartões curinga como uma maneira de excluir arquivos em um diretório. 


**Extensões**<br>
Você pode especificar as extensões a excluir em um diretório específico. As extensões são uma maneira de impedir que um invasor use uma pasta excluída para ocultar uma exploração. As extensões definem explicitamente quais arquivos serão ignorados. 

**Nomes de arquivos**<br>
Você pode especificar os nomes de arquivo que deseja excluir em um diretório específico. Os nomes são uma maneira de impedir que um invasor use uma pasta excluída para ocultar uma exploração. Os nomes definem explicitamente quais arquivos serão ignorados. 



## <a name="add-an-automation-folder-exclusion"></a>Adicionar uma exclusão de pasta de automação
1. No painel de navegação, **selecione** Configurações  >  **exclusões de pasta de automação.**  

2. Clique **em Nova exclusão de pasta**.  

3. Insira os detalhes da pasta:

    - Pasta
    - Extensões
    - Nomes de arquivos
    - Descrição
    

4. Clique em **Salvar**.

>[!NOTE]
> Comandos de Resposta Ao Vivo para coletar ou examinar arquivos excluídos falharão com o erro: "O arquivo é excluído". Além disso, as investigações automatizadas ignorarão os itens excluídos.

## <a name="edit-an-automation-folder-exclusion"></a>Editar uma exclusão de pasta de automação 
1. No painel de navegação, **selecione** Configurações  >  **exclusões de pasta de automação.** 

2. Clique **em Editar** na exclusão de pasta.  

3. Atualize os detalhes da regra e clique em **Salvar**.

## <a name="remove-an-automation-folder-exclusion"></a>Remover uma exclusão de pasta de automação 
1. No painel de navegação, **selecione** Configurações  >  **exclusões de pasta de automação.**  
2. Clique **em Remover exclusão**. 


## <a name="related-topics"></a>Tópicos relacionados
- [Gerenciar listas permitidas/bloqueadas de automação](manage-indicators.md)
- [Gerenciar uploads de arquivo de automação](manage-automation-file-uploads.md)
