---
title: Criar um centro de conteúdo no Microsoft SharePoint Syntex
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
description: Aprenda a criar um centro de conteúdo.
ms.openlocfilehash: 34ba45cd62214743e5a6784893e0f24e9815fdfb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905819"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>Criar um centro de conteúdo no Microsoft SharePoint Syntex


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

Para criar e gerenciar modelos de compreensão de documentos, primeiro é necessário um centro de conteúdo. O centro de conteúdo é a interface de criação do modelo e também contém informações sobre as bibliotecas de documentos às quais os modelos publicados foram aplicados.</br>

   ![Selecionar uma biblioteca de documentos](../media/content-understanding/content-center-page.png)</br>

Você cria um centro de conteúdo padrão durante a[configuração](set-up-content-understanding.md). No entanto, um administrador do SharePoint também pode optar por criar centros adicionais conforme necessário. Embora um único centro de conteúdo possa ser bom para ambientes para os quais você deseja obter uma distribuição de todas as atividades do modelo, talvez você queira ter centros adicionais para vários departamentos dentro da organização, o que pode ter necessidades e requisitos de permissão diferentes para seus modelos.

> [!NOTE]
> Em um [Ambiente Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md), se você tiver um único centro de conteúdo padrão em seu local central, só poderá fornecer uma rolagem da atividade do modelo de dentro desse local. Atualmente, você não pode obter um roll-up da atividade do modelo através dos limites da fazenda em um ambiente Multi-Geo. 


## <a name="create-a-content-center"></a>Criar um centro de conteúdo

Um administrador do SharePoint pode criar um site de centro de conteúdo como [criar qualquer outro site do SharePoint](/sharepoint/create-site-collection) por meio do painel de provisionamento do site do centro de administração.

Para criar um novo tipo de conteúdo:

1. No centro de administração do Microsoft 365, acesse o centro de administração do SharePoint.

2. No novo Centro de administração do SharePoint, em **Sites**, selecione **Sites Ativos**.

3. Na página **Sites Ativos**, clique em **Criar** e selecione **Outras opções**.

4. No menu **Escolha um modelo**, selecione **Centro de Conteúdo**.

5. Forneça um **Nome de Site**, **Administrador principal** e um **Idioma** para o novo site.</br>

   > [!NOTE] 
   > Você pode selecionar um site de centro de conteúdo para renderizar em qualquer um dos idiomas disponíveis, mas observe que modelos, no momento, só podem ser criados para arquivos em inglês. Além disso, observe que, como outros modelos de site, o idioma padrão do site não é editável após o site ser criado.</br>

6. Marque **Concluído**.
 
Depois de criar um site de centro de conteúdo, você o verá listado na página **Sites Ativos** no centro de administração do SharePoint. 

### <a name="give-access-to-additional-users"></a>Conceder acesso a usuários adicionais
 
Depois de criar o site, você pode permitir que os usuários adicionais acessem o site por meio do[modelo de permissões de site do SharePoint.](/sharepoint/modern-experience-sharing-permissions)

## <a name="see-also"></a>Confira também
[Criar um classificador](create-a-classifier.md)

[Criar um extrator](create-an-extractor.md)

[Criar um centro de conteúdo](create-a-content-center.md)

[Visão geral compreensão de documentos](document-understanding-overview.md)

[Criar um modelo de processamento de formulário](create-a-form-processing-model.md)

[Aplicar um modelo](apply-a-model.md)