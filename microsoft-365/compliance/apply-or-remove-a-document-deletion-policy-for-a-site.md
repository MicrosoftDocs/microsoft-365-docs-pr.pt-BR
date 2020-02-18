---
title: Aplicar ou remover uma política de exclusão de documentos de um site
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Com frequência, as organizações estão sujeitas a regulamentações de conformidade, legais ou outras que exigem que elas retenham documentos por um determinado período. No entanto, reter os documentos por mais tempo do que o necessário poderá expor a organização a riscos legais. Por esse motivo, sua organização pode ter criado uma política de exclusão de documentos para seu site. Por exemplo, pode ser necessário que documentos comerciais gerais sejam excluídos cinco anos após sua criação.
ms.openlocfilehash: f04b693a68da36b37524fe5c1fd2e00fab6c2bc6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42079818"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Aplicar ou remover uma política de exclusão de documentos de um site

As organizações geralmente estão sujeitas às normas de conformidade, jurídica ou outras que exigem a retenção de documentos por um determinado período de tempo. No entanto, reter os documentos por mais tempo do que o necessário poderá expor a organização a riscos legais. Por esse motivo, sua organização pode ter criado uma política de exclusão de documentos para&mdash;seu site, por exemplo, documentos de negócios gerais podem ser excluídos cinco anos após terem sido criados.
  
Dependendo da sua organização, uma política de exclusão de documentos pode ser:
  
- **Obrigatório** Um proprietário de site não pode recusar uma política obrigatória, que é automaticamente aplicada ao site. 
    
- **Padrão** Uma política padrão é automaticamente aplicada a um site, mas o proprietário do site pode: 
    
  - Escolher outra política, se disponível.
    
  - Cancele a política completamente se não for relevante para o conteúdo do site.
    
- **Nem obrigatória nem padrão** Neste caso, nenhuma política será automaticamente aplicada ao site, e o proprietário do site precisará tomar ação para aplicar uma. 
    
Uma política de exclusão de documentos pode conter mais de&mdash;uma regra por exemplo, uma regra pode dizer excluir documentos um ano após eles terem sido criados, mas outra regra pode dizer excluir documentos um ano após a última modificação. Se uma política contiver mais de uma regra, você poderá selecionar a regra que melhor se aplique ao seu site. A regra de exclusão será aplicada a todas as bibliotecas no site. Somente uma política e uma regra poderão estar ativas em um site ao mesmo tempo. Como uma política, uma regra pode ser definida como padrão, para que ela seja aplicada automaticamente quando a política é aplicada.
  
Por fim, as políticas de exclusão de documentos são herdadas. Quando você seleciona uma política ou uma regra para seu site, essa seleção é herdada por todos os subsites, embora o proprietário de um subsite possa interromper a herança ao selecionar uma política ou regra diferente. Quando você selecionar uma política ou uma regra, considere o conteúdo de qualquer subsite abaixo de seu site.
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a>Exibir as políticas de exclusão de documentos disponíveis em um conjunto de sites

Sua organização pode atribuir políticas diferentes a conjuntos de sites diferentes. No nível do conjunto de sites, o proprietário de um conjunto de sites pode exibir todas as políticas de exclusão de documentos disponíveis para aquele conjunto de sites. As políticas pode ter sido disponibilizadas para o modelo de conjunto de sites (e, portanto, para todos os conjuntos de sites criados a partir desse modelo) ou para este conjunto de sites específico.
  
1. No site de nível superior no conjunto de sites, no canto superior direito, escolha **configurações** [ícone de engrenagem] \> **configurações de site**.
    
2. Em **políticas de exclusão de documentos**da administração \> do conjunto de **sites** .
    
    > [!NOTE]
    > O link **políticas de exclusão de documentos** não aparecerá, a menos que as políticas tenham sido atribuídas ao conjunto de sites. Além disso, o link não aparece imediatamente após as políticas terem sido atribuídas ao site, pode levar até 24 horas a partir do momento em que as políticas são atribuídas quando o link de **políticas de exclusão de documentos** é exibido. 
  
3. Nesta página, você pode exibir:
    
  - As políticas atribuídas no momento e as regras associadas. Selecione uma política para exibir as regras no painel direito.
    
  - A política padrão, se houver, exibe **Sim** na coluna **Padrão**. 
    
  - Uma mensagem será exibida abaixo da lista caso a política tenha sido atribuída como **Obrigatória**.
    
Essa lista é somente para exibição, para que o proprietário de conjunto de sites veja todas as políticas e regras disponíveis. Para aplicar uma política, consulte a próxima seção.
  
![Exibição das políticas de exclusão de documentos atribuídas a um conjunto de sites](../media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Aplicar ou remover uma política de exclusão de documentos de um site

Como proprietário do site ou proprietário de conjunto de sites, sua organização pode ter criado políticas que você poderá aplicar a seu site ou recusar inteiramente.
  
1. No canto superior direito, escolha **configurações** [ícone de engrenagem] \> **configurações de site**.
    
2. Em **políticas de exclusão de documentos**da administração \> do **site** .
    
    > [!NOTE]
    > O link **políticas de exclusão de documentos** não aparecerá, a menos que as políticas tenham sido atribuídas ao conjunto de sites. Além disso, o link não aparece imediatamente após as políticas terem sido atribuídas ao site, pode levar até 24 horas a partir do momento em que as políticas são atribuídas quando o link de **políticas de exclusão de documentos** é exibido. 
  
3. Siga um destes procedimentos:
    
  - **Para aplicar uma política** Selecionar uma política \> selecione uma regra nessa política \> **salvar**.
    
    Somente uma política e uma regra poderão estar ativas em um site ao mesmo tempo. Sua organização pode oferecer várias opções de políticas e de regras ou somente uma política ou uma regra.
    
    ![Selecionar opção de política](../media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - **Para recusar uma política** Escolha **recusar: no note excluir** \> **salvar**.
    
    Como proprietário do site, você pode recusar uma política de exclusão de documentos se determinar que a política não se aplica ao conteúdo do seu site. No entanto, não é possível recusar uma política que tenha sido marcada como **obrigatória**.
    
    ![Opção recusar](../media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a>As políticas de exclusão de documentos substituem outras políticas

Um site pode usar outras políticas de retenção e exclusão de conteúdo:
  
- Políticas de tipo de conteúdo para o conjunto de sites.
    
- Políticas de gerenciamento de informações para uma lista ou biblioteca.
    
Se você aplicar uma política de exclusão de documentos a um site que já use políticas de tipo de conteúdo ou políticas de gerenciamento de informações para uma lista ou biblioteca, essas políticas serão ignoradas enquanto a política de exclusão de documentos estiver em vigor. Se outras políticas forem ignoradas, você verá a mensagem "o conteúdo deste site usa políticas de exclusão de documentos".
  
Isso significa que você deve planejar para que um site use somente políticas destinadas a conteúdo estruturado (políticas de gerenciamento de informações e políticas de tipo de conteúdo) ou a conteúdo não estruturado (políticas de exclusão de documentos), e não ambas. Se você optar por uma política de exclusão de documentos, o aviso não será exibido e outros tipos de políticas continuarão a funcionar.
  
As políticas de site não são afetadas por políticas de exclusão de documentos.
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a>Determinar se as políticas de tipo de conteúdo estão sendo ignoradas

Se o seu site estava usando políticas de tipo de conteúdo e agora você vê essa mensagem, essas políticas não estarão mais em vigor. Para restaurar as políticas de tipo de conteúdo, você pode remover a política de exclusão de documentos do seu site, conforme descrito anteriormente, se houver uma opção de recusa disponível. Se não houver opção para recusar, a política de exclusão de documentos será obrigatória e você precisará entrar em contato com o responsável pela conformidade em sua organização.
  
1. No canto superior direito, escolha **configurações** [ícone de engrenagem] \> **configurações de site**.
    
2. Em **modelos de política de tipo de conteúdo**da administração \> do **site** .
    
    ![Aviso no site em que as políticas de exclusão de documentos estão sendo usadas](../media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a>Determinar se as políticas de gerenciamento de informações estão sendo ignoradas

Se o seu site estava usando políticas de gerenciamento de informações e agora você vê essa mensagem, essas políticas não estarão mais em vigor. Para restaurar as políticas de gerenciamento de informações, você pode remover a política de exclusão de documentos do seu site, conforme descrito anteriormente, se houver uma opção de recusa disponível. Se não houver opção para recusar, a política de exclusão de documentos será obrigatória e você precisará entrar em contato com o responsável pela conformidade em sua organização.
  
- Para uma lista ou biblioteca, nas **configurações** \> da \> biblioteca de \> guias da **biblioteca** de faixa de **opções em configurações de política de gerenciamento de informações** **de gerenciamento** \> e permissões.
    
    ![Aviso no site em que as políticas de exclusão de documentos estão sendo usadas](../media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a>Confira também

[Visão geral das políticas de exclusão de documento](document-deletion-policies.md)
  
[Criar uma política de exclusão de documentos](create-a-document-deletion-policy.md)

