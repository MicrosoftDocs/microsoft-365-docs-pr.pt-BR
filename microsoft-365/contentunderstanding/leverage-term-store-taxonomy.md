---
title: Aproveitar a taxonomia do repositório de termos ao criar um extrator
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Use a taxonomia do repositório de termos ao criar um extrator no seu modelo de compreensão de documentos no Microsoft SharePoint Syntex.
ms.openlocfilehash: cf396d14a497981389cc336c5efd121f36392181
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709543"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Aproveitar a taxonomia do repositório de termos ao criar um extrator

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

Ao criar um extrator em seu modelo de compreensão de documento usando o SharePoint Syntex, você pode aproveitar os conjuntos de termos globais no [repositório de termos](https://docs.microsoft.com/sharepoint/managed-metadata) para exibir os termos preferenciais para os dados extraídos.  

Por exemplo, o modelo identifica e classifica todos os documentos de **Contrato** que são carregados na biblioteca de documentos.  Além disso, o modelo também extrai um valor de **Serviços contratados** de cada contrato e o exibirá em uma coluna no modo de exibição de biblioteca. Entre os vários valores dos Serviços contratados nos contratos, há vários valores mais antigos que a sua empresa não usa mais e foi renomeado. Por exemplo, todas as referências aos termos de serviços contratados *Design*, *Gráficos* ou *Topografia* devem agora ser chamados *Criativo*. Sempre que seu modelo extrai um dos termos desatualizados de um documento de contrato, você quer que ele exiba o termo atual - Criativo - no modo de exibição da biblioteca. No exemplo a seguir, enquanto treina o modelo, vemos que um documento de exemplo contém o termo desatualizado *Design*.

   ![Repositório de termos](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a>Usar uma coluna de metadados gerenciados no extrator

Os conjuntos de termos são configurados no repositório de termos de serviços de Metadados Gerenciados (MMS) no Centro de administração do SharePoint. No exemplo a seguir, o *conjunto de termos* dos [Serviços contratados](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) é configurado para incluir um número de termos, incluindo *Criativo*.  Os detalhes mostram que o termo tem três sinônimos (*Design*, *Gráficos* e *Topografia*) e os sinônimos devem ser traduzidos para *Criativo*. 

   ![Conjunto de termos](../media/content-understanding/term-store.png)</br>

Pode haver vários motivos pelos quais você pode querer usar um sinônimo em seu conjunto de termos. Por exemplo, pode haver termos desatualizados, termos renomeados ou variações de nome entre seus departamentos de organizações.

Para disponibilizar o campo de metadados gerenciados para seleção quando você cria o seu extrador em seu modelo, é necessário [adicioná-lo como uma coluna de site de metadados gerenciados](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f). Depois que você adicionar a coluna de site, ela estará disponível para você selecionar quando criar o extrator para o seu modelo.

   ![Serviços contratados](../media/content-understanding/contract-services.png)</br>


Depois de aplicar seu modelo à biblioteca de documentos, quando os documentos forem carregados na biblioteca, a coluna de *Serviços criativos* exibirá o termo preferido (*Criativo*) quando o extrator encontrar qualquer um dos valores de sinônimos (*Design*, *Gráficos* e *Topografia*).

   ![Coluna de serviços contratados](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a>Confira também
[Introdução a Metadados gerenciados](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[Criar um extrator](create-an-extractor.md)

[Criar uma coluna de metadados gerenciados](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





