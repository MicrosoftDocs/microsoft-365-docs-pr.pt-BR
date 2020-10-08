---
title: Tipos de informações confidenciais personalizadas para o DLP
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Obtenha uma visão geral dos tipos de informações confidenciais personalizados para a prevenção contra perda de dados (DLP), como o padrão principal, a proximidade de caractere e o nível de confiança.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d21d0be23847a8fbd27b6082ca28cdca2d4eed05
ms.sourcegitcommit: 5e40c760c1af2a4cc6d85cb782b17f5c979677c5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48379177"
---
# <a name="custom-sensitive-information-types"></a>Tipos de informações confidenciais personalizadas

O Microsoft 365 inclui muitos tipos de informações confidenciais integrados que estão prontos para usar em sua organização, como para a [DLP (prevenção de perda de dados)](data-loss-prevention-policies.md) ou com o [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security). Os tipos de informações confidenciais integrados podem ajudar a identificar e proteger números de cartão de crédito, números de contas bancárias, números de passaporte e muito mais, com base em padrões definidos por uma expressão regular (regex) ou por uma função. Para saber mais, consulte [O que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).

Mas e se você precisar identificar e proteger um tipo diferente de informações confidenciais, como IDs de funcionários ou números de projetos, usando um formato específico para sua organização? Para fazer isso, você pode criar um tipo de informação confidencial personalizado.

As partes fundamentais de um tipo personalizado de informações confidenciais são:

- **Padrão principal**: números de ID de funcionário, números de projeto etc. Isso geralmente é identificado por uma expressão regular (RegEx), mas também pode ser uma lista de palavras-chave.

- **Evidências adicionais**: digamos que você esteja procurando por um número de ID de funcionário de nove dígitos. Nem todos os números de nove dígitos são números de ID de funcionário. Portanto, você pode pesquisar por texto adicional: palavras-chave como "funcionário", "crachá", "ID" ou outros padrões de texto com base em expressões regulares adicionais. Evidências de suporte (também chamadas de _suporte_ ou evidências _comprobatórias_) aumentam a probabilidade de que o número de nove dígitos no conteúdo seja realmente um número de ID de funcionário.

- **Caractere de proximidade**: faz sentido que quanto mais próximos o padrão principal e as evidências de suporte estejam entre si, mais provável seja que o conteúdo detectado seja o que você está procurando. Você pode especificar a distância de caracteres entre o padrão principal e as evidências de suporte (também conhecido como a _janela de proximidade_), conforme mostrado no seguinte diagrama:

    ![Diagrama da janela de proximidade e evidências comprobatórias](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- **Nível de confiança**: quanto mais evidências de suporte você tiver, maior será a probabilidade de que uma correspondência contenha as informações confidenciais que está procurando. Você pode atribuir níveis mais altos de confiança para correspondências detectadas usando mais evidências.

  Quando satisfeito, um padrão retorna uma contagem e um nível de confiança, que você pode usar nas condições de políticas DLP. Ao adicionar uma condição para detectar um tipo de informação confidencial a uma política DLP, você poderá editar o nível de confiança e a contagem, conforme mostrado no seguinte diagrama:

    ![Contagem de instâncias e opções de precisão de correspondência](../media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a>Criando tipos de informações confidenciais personalizadas

Para criar tipos de informações confidenciais personalizadas no Centro de Conformidade e Segurança, você pode escolher entre várias opções:

- **Use EDM** Você pode configurar tipos de informações confidenciais personalizadas usando a classificação baseada em EDM (Exact Data Match). Esse método permite criar um tipo de informações confidenciais dinâmico usando um banco de dados seguro que você pode atualizar periodicamente. Confira [Criar um tipo de informações confidenciais personalizadas com classificação baseada em Exact Data Match](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Use o PowerShell** Você pode configurar tipos de informações confidenciais personalizadas usando o PowerShell. Embora esse método seja mais complexo do que usar a interface do usuário, você tem mais opções de configuração. Consulte [Criar um tipo de informações confidenciais personalizadas no Centro de Conformidade e Segurança do PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).

- **Usar a interface do usuário** Você pode configurar um tipo de informações confidenciais personalizadas usando o a interface do usuário do Centro de Conformidade e Segurança. Com esse método, você pode usar expressões comuns, palavras-chave e dicionários de palavras-chave. Para saber mais, confira [Criar um tipo de informações confidenciais personalizadas](create-a-custom-sensitive-information-type.md).

> [!NOTE]
> A Proteção de Informações do Microsoft 365 agora oferece suporte a idiomas de conjunto de caracteres de byte duplo de visualização:
> - Chinês (simplificado)
> - Chinês (tradicional)
> - Coreano
> - Japonês
> 
>Esta visualização está apenas na nuvem comercial e a implementação está limitada para:
> - Japão
> - Coreia
> - China
> - Hong Kong
> - Macau
> - Taiwan
>
>Este suporte está disponível para tipos de informações confidenciais. Para obter mais informações, confira [Suporte à proteção de informações para notas de versão de conjuntos de caracteres de byte duplo (visualização)](mip-dbcs-relnotes.md).

