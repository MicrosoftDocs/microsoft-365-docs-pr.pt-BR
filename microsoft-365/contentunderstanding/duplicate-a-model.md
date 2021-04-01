---
title: Duplicar um modelo no Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Aprenda como e por que duplicar um modelo no Microsoft SharePoint Syntex.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445931"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a>Duplicar um modelo no Microsoft SharePoint Syntex

A duplicação de um modelo de compreensão de documento pode economizar tempo e esforço se você precisar criar um novo modelo e saber que um modelo existente é muito semelhante ao que você precisa.

Por exemplo, um modelo existente denominado “Contratos” classifica os mesmos arquivos com os quais você precisa trabalhar. Seu novo modelo extrairá alguns dos dados existentes, mas precisará ser atualizado para extrair alguns dados adicionais. Em vez de criar e treinar um novo modelo do zero, você pode usar o recurso de modelo duplicado para fazer uma cópia do modelo de Contratos, que também copiará todos os itens de treinamento associados, como arquivos de exemplo e extratores de entidade.

Ao duplicar o modelo, depois de renomeá-lo (por exemplo, para “Renovações de contrato”), você pode fazer atualizações nele. Por exemplo, você pode escolher remover alguns dos campos extraídos existentes que você não precisa e, em seguida, treinar o modelo para extrair um novo (por exemplo, "Data de renovação").

## <a name="duplicate-a-model"></a>Duplicar um modelo

Siga estas etapas para duplicar um modelo de compreensão de documento.

1. No centro de conteúdo, selecione **Modelos** para ver sua lista de modelos.

2. Na página **Modelos**, selecione o modelo que deseja duplicar.

3. Usando a faixa de opções ou o botão **Mostrar ações** (próxima ao nome do modelo), selecione **Duplicar**.</br>

    ![Captura de tela da página Modelos mostrando um modelo selecionado com as opções Duplicar destacadas.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. No painel **Modelo duplicado**:

   a. Em **Nome**, insira o novo nome do modelo que deseja duplicar.</br>

    ![Captura de tela mostrando o painel do modelo duplicado.](../media/content-understanding/duplicate-model-panel.png) </br>

   b. Em **Descrição**, adicione uma descrição de seu novo modelo.

   c. (Opcional) Em **Configurações avançadas**, selecione se deseja associar um tipo de [conteúdo existente](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview).

5. Selecione **Duplicar**.

## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)

[Renomear um modelo](rename-a-model.md)

[Criar um extrator](create-an-extractor.md)

[Visão geral sobre Compreensão de Documentos](document-understanding-overview.md).

[Tipos de explicação](explanation-types-overview.md)

[Aplicar um modelo](apply-a-model.md) 

[Modo de Acessibilidade do SharePoint Syntex](accessibility-mode.md)