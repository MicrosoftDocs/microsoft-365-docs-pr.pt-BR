---
title: Visão geral das políticas de exclusão de documentos
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 55e8d858-f278-482b-a198-2e62d6a2e6e5
description: Sua organização pode ser necessária para reter documentos por um período de tempo por causa de conformidade, legal ou outras necessidades de negócios. No entanto, se sua organização mantém documentos mais do que o necessário, você cria um risco legal desnecessário. Com uma política de exclusão de documentos, você pode reduzir o risco de forma proativa, excluindo documentos em um site após um período específico de tempo — por exemplo, você pode excluir documentos nos sites dos usuários do OneDrive for Business cinco anos depois que os documentos foram criados.
ms.openlocfilehash: 85a8a4464a14cb2e0b9e901fbf3912c7ff3faa8d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40806044"
---
# <a name="overview-of-document-deletion-policies"></a>Visão geral das políticas de exclusão de documentos

> [!IMPORTANT]
> Em frente, recomendamos usar uma política de retenção ou rótulos criados no centro de conformidade da Microsoft 365, no centro de segurança da Microsoft 365 ou no &amp; centro de conformidade de segurança do Office 365, em vez de uma política de exclusão de documentos. As políticas de exclusão de documentos continuarão a funcionar lado a lado com políticas de retenção, mas se você precisar reter ou excluir conteúdo em qualquer lugar no Office 365, recomendamos que você use uma política de retenção. Para obter mais informações, consulte [usar uma política de retenção em vez desses recursos](retention-policies.md#use-a-retention-policy-instead-of-these-features).
  
Sua organização pode ser necessária para reter documentos por um período de tempo por causa de conformidade, legal ou outras necessidades de negócios. No entanto, se sua organização mantém documentos mais do que o necessário, você cria um risco legal desnecessário. Com uma política de exclusão de documentos, você pode reduzir o risco de forma proativa, excluindo documentos em um site após um período específico de tempo — por exemplo, você pode excluir documentos nos sites dos usuários do OneDrive for Business cinco anos depois que os documentos foram criados.
  
As políticas de exclusão de documentos são poderosas, mas flexíveis — por exemplo, você pode:
  
- Permitir que os proprietários de sites escolham políticas a partir das políticas que você criar e gerenciar centralmente. Também pode permitir que os proprietários de sites recusem aplicar uma política se decidirem que ela não se aplica aos seus conteúdos.
    
- Aplicar uma única política obrigatória a todos os sites de um conjunto de sites, como sites do OneDrive for Business, ou aplicar uma política a todos os conjuntos de sites criados a partir de um modelo específico de conjunto de sites, como o modelo Site da Equipe.
    
- Fornecer uma política padrão com uma regra padrão que será aplicada automaticamente, sem exigir qualquer ação por parte dos proprietários de site.
    
- Criar uma política que inclua várias regras de exclusão que possam ser escolhidas por um proprietário de site.
    
Você cria e gerencia políticas de exclusão de documentos usando o centro de políticas de exclusão de documentos. Como alternativa, você pode criar a central de políticas manualmente [criando o conjunto de sites](https://go.microsoft.com/fwlink/p/?LinkID=404342) e escolhendo **central de políticas de conformidade** na guia **empresa** . Cada locatário pode ter apenas uma central de política de exclusão de documentos. 
  
![Página inicial do Centro de Políticas de Exclusão de Documentos](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="when-to-use-document-deletion-policies"></a>Quando usar as políticas de exclusão de documentos

Além das políticas de exclusão de documentos, o Office 365 fornece estas políticas de retenção para conteúdos de sites:
  
- [Records management](https://go.microsoft.com/fwlink/p/?LinkID=404250)
    
- [Políticas de gerenciamento de informações para tipos de conteúdo, listas e bibliotecas](https://go.microsoft.com/fwlink/p/?LinkID=404239)
    
- [Políticas de site](https://go.microsoft.com/fwlink/p/?LinkID=404242)
    
Cada tipo de política funciona melhor para um tipo específico de site ou dados. Por exemplo, a sua organização pode ter um site altamente estruturado que use tipos de conteúdo, como um site financeiro para contratos ou uma base de dados de conhecimento para artigos. Nesse caso, você pode usar políticas de tipo de conteúdo. Ou a sua organização pode ter que reter documentos legais, em cujo caso você poderá usar tipos de conteúdo e uma Central de Registros para implementar um planejamento de arquivos.
  
As políticas de exclusão de documentos não substituem as políticas de gerenciamento de registros ou de gerenciamento de informações, que funcionam melhor com dados estruturados e tipos de conteúdo. Em vez disso, você deverá usar políticas de exclusão de documentos quando precisar gerenciar amplamente a exclusão automática de dados não estruturados, como sites do OneDrive for Business e sites de equipe.
  
![Diagrama mostrando opções de retenção para conteúdos de site](media/IP-Retention-policies-for-site-content.png)
  
Se você aplicar uma política de exclusão de documentos a um site que já usa políticas de tipo de conteúdo ou de gerenciamento de informações para uma lista ou biblioteca, essas políticas serão ignoradas enquanto a política de exclusão de documentos estiver em vigor. Isso significa que você deverá fazer um plano para que um site use somente políticas feitas para conteúdos estruturados ou não estruturados, e não ambos. Para obter mais informações sobre como as políticas de exclusão de documentos substituem outras políticas, consulte [Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md).
  
Ao contrário de outras políticas, as políticas de exclusão de documentos funcionam somente em bibliotecas de documentos, e não em listas.
  
## <a name="deletion-policies-and-rules"></a>Políticas e regras de exclusão

Uma política de exclusão de documentos contém uma ou mais regras de exclusão que especificam:
  
- O período de tempo até a exclusão.
    
- Se a data de exclusão será calculada com base em quando o documento foi criado ou na data da última alteração.
    
- Se deseja excluir o documento permanentemente ou para a Lixeira.
    
Se uma política contiver mais do que uma regra, os proprietários de sites podem selecionar a regra que melhor se aplique ao seu conteúdo.
  
![Nova página de regra de exclusão](media/IP-New-deletion-rule.png)
  
## <a name="policies-and-assignments"></a>Políticas e atribuições

Depois de criar uma política de exclusão de documentos, você pode atribuí-la a um modelo de conjunto de sites — por exemplo, você pode atribuir uma política ao modelo do OneDrive for Business para que ela inclua todos os sites do OneDrive de cada usuário. Quando você atribui uma política a um modelo de conjunto de sites, isso se aplica a todos os conjuntos de sites já criados a partir desse modelo, além de quaisquer conjuntos de sites criados a partir desse modelo no futuro.
  
![Escolha uma página modelo exibindo a opção do OneDrive](media/IP-Choose-a-template.png)
  
Você pode ainda atribuir uma política a um conjunto específico de sites, fazer isso substitui quaisquer políticas que tenham sido atribuídas a esse modelo de conjunto de sites. Por exemplo, você pode atribuir políticas ao modelo Site de Equipe, mas depois substituí-las aplicando um conjunto de políticas diferente a um conjunto de sites específico criado a partir daquele modelo.
  
### <a name="one-mandatory-policy-or-several-policies-to-choose-from"></a>Uma política obrigatória ou várias políticas à sua escolha

Quando você atribui uma política, pode escolher torná-la obrigatória, para que apenas essa política possa ser atribuída e para que seja aplicada a todos os sites no conjunto de sites. Os proprietários de sites podem optar por não usar uma política obrigatória, o que significa que os documentos no site estarão inevitavelmente sujeitos à política de exclusão.
  
Em vez de tornar uma única política obrigatória, você também pode atribuir várias políticas a um conjunto de sites, o que permite que cada proprietário de site escolha qual política aplicar a seu site, ou ainda cancelar todas as políticas. Por exemplo, você pode criar uma política para documentos corporativos gerais e outra política para documentos financeiros que tenham agendas de retenção diferentes. Um proprietário de site saberá melhor que conteúdo o seu site contém e, consequentemente, qual política de exclusão de documentos aplicar. Cada site pode ter somente uma política aplicada a ele.
  
### <a name="one-rule-or-several-rules-to-choose-from"></a>Uma regra ou várias regras à sua escolha

Por sua vez, cada política pode conter muitas regras — por exemplo, uma política de exclusão para documentos de negócios gerais podem ter duas regras:
  
- Documentos que não precisam de retenção com base em obrigações legais ou necessidades comerciais contínuas não devem ser mantidos por mais de um ano a partir da criação.
    
- Os documentos necessários para uso ativo e recorrente da empresa, que sejam precisos por mais do que um ano, não deverão ser retidos por mais do que três anos a partir da sua data de criação.
    
Um proprietário de site pode determinar que o seu conjunto de sites contém documentos corporativos gerais, selecionar essa política de exclusão e, em seguida, escolher a regra apropriada a partir da política. Você só pode selecionar uma regra na política aplicada atualmente ao site (não de qualquer política) e a regra se aplica a todas as bibliotecas de documentos no site.
  
## <a name="the-relationship-of-site-collections-policies-and-rules"></a>A relação entre conjuntos de sites, políticas e regras

O relacionamento básico é o seguinte:
  
Um conjunto de sites ou um modelo de conjunto de sites pode conter uma ou mais políticas associadas a ele, e cada uma dessas políticas pode conter uma ou mais regras. No entanto, pode haver apenas uma política ativa por site e pode haver apenas uma regra de exclusão ativa a qualquer momento para as bibliotecas no site.
  
![Diagrama mostrando a relação entre as políticas](media/IP-Two-policies-four-rules.png)
  
## <a name="document-deletion-policies-are-inherited"></a>As políticas de exclusão de documentos são herdadas

Como as permissões, a navegação e muitos outros recursos de sites, as políticas de exclusão de documentos são herdadas. Um proprietário pode selecionar uma política de exclusão de documentos para seu site e, consequentemente, todos os subsites herdarão a política do site principal. O proprietário de um subsite pode interromper a herança selecionando uma combinação diferente de políticas e regras, desse modo a política será aplicada a todos os subsites até que a herança seja interrompida novamente.
  
## <a name="assigning-document-deletion-policies-for-the-first-time"></a>Atribuir políticas de exclusão de documentos pela primeira vez

É importante entender que o período de tempo especificado para uma política de exclusão de documentos significa o tempo desde que o documento foi criado ou modificado, não o tempo desde que a política foi atribuída. Por exemplo, você pode criar uma política de exclusão de documentos que exclua permanentemente os documentos dois anos após terem sido criados e, em seguida, atribuir essa política a um modelo de conjunto de sites a partir do qual vários conjuntos de sites foram criadas há quatro ou cinco anos. Nesse caso, é provável que os conjuntos de sites existentes contenham muitos documentos que já tenham sido mais antigos do que os dois anos especificados pela política de exclusão, isso significa que muitos conteúdos serão excluídos logo após a atribuição da política de exclusão de documentos para o primeiro temporais.
  
Quando você atribui uma política pela primeira vez, todos os documentos no site são avaliados, e são excluídos se atenderem aos critérios. Isto se aplica a todos os documentos existentes, e não somente aos novos documentos criados desde que a política foi atribuída. E lembre-se de que o período de tempo é relativo à idade de cada documento, e não ao tempo passado desde que a política foi atribuída pela primeira vez.
  
Portanto, antes de adicionar uma política a um site pela primeira vez, você deverá primeiro considerar a idade dos conteúdos existentes e de que modo a política poderá afetá-los. Você também poderá informar os proprietários de sites sobre a nova política antes de atribuí-la, para que eles tenham tempo para avaliar o possível impacto.
  
## <a name="time-lag-for-propagating-policies"></a>Intervalo de tempo para propagação de políticas

Após atribuir políticas a um conjunto de sites, os proprietários de sites podem usar o link **Políticas de exclusão de documentos** na página **Configurações do Site** para ver e aplicar as políticas disponíveis para o site. 
  
O link **políticas de exclusão de documentos** não aparecerá, a menos que as políticas tenham sido atribuídas ao conjunto de sites. Além disso, o link não aparece imediatamente após as políticas terem sido atribuídas ao site, pode levar até 24 horas a partir do momento em que as políticas são atribuídas quando o link de **políticas de exclusão de documentos** é exibido. 
  
## <a name="permissions"></a>Permissões

Os membros da sua equipe de conformidade que utilizam o Centro de Política de Exclusão de Documento precisam ter permissões para o centro de políticas e para os conjuntos de sites a que as políticas serão aplicadas. Recomendamos que você:
  
1. Crie um grupo de segurança que contenha todos os usuários do centro de políticas de exclusão de documentos, que é provavelmente sua equipe de gerenciamento de políticas de conformidade. Confira [gerenciar grupos de segurança habilitados para email](https://go.microsoft.com/fwlink/p/?LinkID=404345) para obter mais informações. 
    
2. No Centro de Política de Exclusão de Documento, atribua permissões de proprietário do conjunto de sites ao grupo de segurança. Consulte [permissões para administradores de conjunto de sites](https://go.microsoft.com/fwlink/p/?LinkID=404346) para obter mais informações. 
    
3. Em cada conjunto de sites a que você precisa atribuir políticas de exclusão de documentos, atribua permissões de proprietário de conjunto de sites ao grupo de segurança.
    
## <a name="how-document-deletion-policies-work-with-hold-policies"></a>Como as políticas de exclusão de documentos funcionam com políticas de retenção

Uma política de retenção garante que todo o conteúdo seja preservado por um período específico de tempo, enquanto que uma política de exclusão de documentos garante que todo o conteúdo seja excluído após um período específico de tempo.
  
Se você deseja reter documentos por um período fixo de tempo, pode utilizar uma política de retenção com uma política de exclusão. Por exemplo, pode reter documentos por três anos após eles terem sido modificados e, depois, configurar uma política de exclusão para excluir esses documentos três anos após a última modificação.
  
Observe que uma política de exclusão não substitui uma retenção. Se um site estiver em retenção e uma política de exclusão de documentos excluir um documento, ele será preservado na Biblioteca de Retenções para Preservação exatamente como se tivesse sido excluído manualmente.
  
## <a name="see-also"></a>Confira também

[Aplicar ou remover uma política de exclusão de documentos de um site](apply-or-remove-a-document-deletion-policy-for-a-site.md)

[Criar uma política de exclusão de documentos](create-a-document-deletion-policy.md)


