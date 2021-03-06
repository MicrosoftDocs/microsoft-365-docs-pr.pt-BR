---
title: Aproveitar a taxonomia do repositório de termos ao criar um extrator
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Utilize a taxonomia de repositório de termos ao criar um extrator em seu modelo de compreensão de documento no Microsoft SharePoint Syntex.
ms.openlocfilehash: b8dfc028e0a18f3345fec466ec5e0079ed2d11ce
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925339"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Aproveitar a taxonomia do repositório de termos ao criar um extrator

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

Ao criar um extrator em seu modelo de compreensão de documento usando o SharePoint Syntex, você pode aproveitar os conjuntos de termos globais no [repositório de termos](/sharepoint/managed-metadata) para exibir os termos preferenciais para os dados extraídos.  

Por exemplo, o modelo identifica e classifica todos os documentos de **Contrato** que são carregados na biblioteca de documentos.  Além disso, o modelo também extrai um valor de **Serviços contratados** de cada contrato e o exibirá em uma coluna no modo de exibição de biblioteca. Entre os vários valores dos Serviços contratados nos contratos, há vários valores mais antigos que a sua empresa não usa mais e foi renomeado. Por exemplo, todas as referências aos termos de serviços contratados *Design*, *Gráficos* ou *Topografia* devem agora ser chamados *Criativo*. Sempre que seu modelo extrai um dos termos desatualizados de um documento de contrato, você quer que ele exiba o termo atual - Criativo - no modo de exibição da biblioteca. No exemplo a seguir, enquanto treina o modelo, vemos que um documento de exemplo contém o termo desatualizado *Design*.

   ![Repositório de termos](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a>Usar uma coluna de metadados gerenciados no extrator

Os conjuntos de termos são configurados no repositório de termos de serviços de Metadados Gerenciados (MMS) no Centro de administração do SharePoint. No exemplo abaixo, o *Contrato de Serviços* [conjunto de termos](/sharepoint/managed-metadata#term-set) está configurado para incluir vários termos, incluindo o *Criativo*.  Os detalhes mostram que o termo tem três sinônimos (*Design*, *Gráficos* e *Topografia*) e os sinônimos devem ser traduzidos para *Criativo*. 

   ![Conjunto de termos](../media/content-understanding/term-store.png)</br>

Pode haver muitos motivos pelos quais você pode querer usar um sinônimo em seu conjunto de termos. Por exemplo, pode haver termos desatualizados, termos renomeados ou variações de nome entre seus departamentos de organizações.

Para disponibilizar o campo de metadados gerenciados para seleção ao criar seu extrator em seu modelo, você precisa [adicioná-lo como uma coluna de site de metadados gerenciados](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f). Depois de adicionar a coluna do site, você pode selecioná-la ao criar o extrator para o seu modelo.

   ![Serviços contratados](../media/content-understanding/contract-services.png)</br>


Depois de aplicar seu modelo à biblioteca de documentos, quando os documentos forem carregados na biblioteca, a coluna de *Serviços criativos* exibirá o termo preferido (*Criativo*) quando o extrator encontrar qualquer um dos valores de sinônimos (*Design*, *Gráficos* e *Topografia*).

   ![Coluna de serviços contratados](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>Confira também
[Introdução a Metadados gerenciados](/sharepoint/managed-metadata#terms)

[Criar um extrator](create-an-extractor.md)

[Criar uma coluna de metadados gerenciados](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)