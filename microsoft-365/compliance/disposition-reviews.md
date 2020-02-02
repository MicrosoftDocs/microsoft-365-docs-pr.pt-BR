---
title: Visão geral das revisões de disposição
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Ao criar um rótulo de retenção que mantém o conteúdo no Microsoft 365, você pode optar por acionar uma análise de disposição no final do período de retenção.
ms.openlocfilehash: 267b2bc7a8bc65e3a816c2d3d88397589734b55d
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/01/2020
ms.locfileid: "41661927"
---
# <a name="overview-of-disposition-reviews"></a>Visão geral das revisões de disposição

Quando o conteúdo atinge o final do período de retenção, há vários motivos para que você possa querer revisar o conteúdo para decidir se ele pode ser excluído com segurança ("descartado"). Por exemplo, você pode precisar:
  
- Suspender a exclusão ("disposição") de conteúdo relevante no caso de litígio ou auditoria.
    
- Remova o conteúdo da lista de descarte para armazenar em um arquivo morto, se esse conteúdo tiver um valor de pesquisa ou histórico.
    
- Atribua um período de retenção diferente ao conteúdo, se a política original era uma solução temporária ou provisionada.
    
- Retornar o conteúdo aos clientes ou transferi-lo para outra organização.
    
Ao criar um rótulo de retenção no centro de conformidade da Microsoft 365, no centro de segurança da Microsoft 365 ou no centro de conformidade & segurança do Office 365, você pode optar por acionar uma análise de disposição no final do período de retenção. Em uma revisão de disposição:
  
- As pessoas escolhidas recebem uma notificação por email de que o conteúdo deve ser revisado. Esses revisores podem ser usuários individuais, grupos de distribuição ou segurança ou grupos do Office 365. Observe que as notificações são enviadas semanalmente.
    
- Os revisores vão para a página de **disposição** no centro &amp; de conformidade de segurança para analisar o conteúdo. Os revisores podem ver quantos itens de cada rótulo de retenção estão aguardando disposição e, em seguida, selecione um rótulo de retenção para ver todo o conteúdo com esse rótulo.
    
- Para cada documento ou email, o revisor pode:
    
  - Aplicar um rótulo de retenção diferente.
    
  - Estenda seu período de retenção.
    
  - Excluí-la permanentemente.
    
- Os revisores podem exibir as desposições pendentes ou concluídas e exportar essa lista como um arquivo. csv.

> [!NOTE]
> Revisões de disposição exigem uma assinatura do Office 365 Enterprise e5.
  
Uma análise de disposição pode incluir conteúdo em caixas de correio do Exchange, sites do SharePoint, contas do OneDrive e grupos do Office 365. O conteúdo que está aguardando uma revisão de disposição nesses locais é excluído somente depois que um revisor escolhe excluir permanentemente o conteúdo.
  
![Página de desposições no centro de conformidade e segurança](media/Retention-Dispositions-v2-page.png)


## <a name="setting-up-the-disposition-review-by-creating-a-retention-label"></a>Configurando a análise de disposição criando um rótulo de retenção

Este é o fluxo de trabalho básico para configurar uma revisão de disposição. Observe que esse fluxo mostra um rótulo de retenção sendo publicado e, em seguida, aplicado manualmente por um usuário; Como alternativa, um rótulo de retenção que dispara uma análise de disposição pode ser aplicado automaticamente ao conteúdo.
  
![Gráfico mostrando o fluxo de como o descarte funciona](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
Uma revisão de disposição é uma opção quando você cria um rótulo de retenção no Office 365. Essa opção não está disponível em uma política de retenção, mas somente em um rótulo de retenção que é configurado para reter conteúdo.
  
Para obter mais informações sobre rótulos de retenção, consulte [Overview of Retention Labels](labels.md).
  
![Configurações de retenção para um rótulo](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> Quando você especifica a opção **notifique estas pessoas quando há itens prontos para revisão**, especifique um usuário ou um grupo de segurança habilitado para email. Os grupos do Office 365 não têm suporte para essa opção.

## <a name="disposing-content"></a>Descartando conteúdo

Quando um revisor é notificado por email que o conteúdo está pronto para revisão, eles podem ir até a página de **disposição** no &amp; centro de conformidade de segurança. Os revisores podem ver quantos itens de cada rótulo de retenção estão aguardando disposição e, em seguida, selecione um rótulo de retenção para ver todo o conteúdo com esse rótulo.

Depois que você selecionar um rótulo de retenção, a próxima página mostrará todas as desposições pendentes para esse rótulo.

![Opções de disposição](media/Retention-Disposition-options-v2.png)

O revisor pode então: 
  
- Aplicar um rótulo de retenção diferente.
    
- Estenda o período de retenção.
    
- Excluir permanentemente o item.

Observe que um revisor pode selecionar vários itens e descartá-los ao mesmo tempo.
    
Um revisor também pode usar o link para exibir o documento em seu local original, se o revisor tiver permissões para esse local. Durante uma revisão de disposição, o conteúdo nunca se move do local original e nunca é excluído até que o revisor opte por fazê-lo.
  
Observe que as notificações por email são enviadas automaticamente aos revisores de forma semanal. Portanto, quando o conteúdo atinge o final do período de retenção, pode levar até sete dias para que os revisores recebam a notificação por email de que o conteúdo está aguardando disposição.
  
Observe também que todas as ações de disposição são auditadas. Para garantir isso, você deve ativar a auditoria pelo menos um dia antes da primeira ação de disposição: para saber mais, confira [Pesquisar o log de auditoria no centro de conformidade &amp; de segurança do Office 365](search-the-audit-log-in-security-and-compliance.md). 
  
## <a name="permissions-for-disposition"></a>Permissões para descarte

Para obter acesso à página de **disposição** , os revisores devem ser membros da função de **Gerenciamento de descarte** e da função de logs de **auditoria somente para exibição** . Recomendamos criar um novo grupo de função chamado **revisores de disposição**e adicionar essas duas funções a esse grupo de função. 

Específico para a função de **logs de auditoria somente para exibição** :

- Como o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet do Exchange Online, você deve atribuir essa função aos usuários usando o [centro de administração do Exchange no Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center), em vez de usar a página de **permissões** no centro de conformidade de segurança &. Para obter instruções, consulte [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Os grupos do Office 365 não têm suporte para essa função. Em vez disso, atribua caixas de correio de usuário, usuários de email ou grupos de segurança habilitados para email.

Para obter instruções para conceder aos usuários a função de **Gerenciamento de descarte** e criar sua nova função de **revisores de disposição** , consulte [dar aos &amp; usuários acesso ao centro de conformidade de segurança do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Quanto tempo até o conteúdo Descartado é excluído permanentemente

O conteúdo que está aguardando uma análise de disposição é excluído somente depois que um revisor escolhe excluir permanentemente o conteúdo. Quando o revisor escolhe essa opção, o conteúdo do site do SharePoint ou da conta do OneDrive fica qualificado para o processo de limpeza padrão descrito nesta seção: [como funciona uma política de retenção com conteúdo in-loco](retention-policies.md#how-a-retention-policy-works-with-content-in-place).
  
Isso significa que:
  
- O conteúdo de uma biblioteca de documentos será movido para a lixeira de primeiro estágio **dentro de sete dias** de disposição e, em seguida, excluído permanentemente **93 dias** após isso. A lixeira não é indexada pela pesquisa e, portanto, seu conteúdo não está disponível para um bloqueio de descoberta eletrônica.

- O conteúdo da biblioteca de retenção de preservação será excluído permanentemente **dentro de 7 dias** após o descarte.

- Os itens em uma caixa de correio do Exchange serão excluídos permanentemente **dentro de 14 dias** de disposição. (Observe que 14 dias é a configuração padrão, mas ela pode ser configurada até 30 dias).
    
## <a name="view-pending-dispositions-and-disposed-items"></a>Exibir desposições pendentes e itens descartados

Na página de **disposição pendente** , você pode exibir as desposições pendentes e concluídas para um rótulo de retenção específico: 
  
- A **disposição pendente** mostra itens que atingiram o final do período de retenção e exigem uma revisão de disposição. Após a revisão de cada item, decida se deseja aplicar um rótulo de retenção diferente a ele, estenda o período de retenção ou exclua-o permanentemente. Você pode selecionar vários itens.
    
- A guia **itens descartados** mostra itens excluídos permanentemente que já foram transferidos por uma análise de disposição. Eles são exibidos aqui porque o processo de exclusão permanente pode levar vários dias, conforme indicado na seção acima. Itens que tiveram um rótulo de retenção diferente aplicado ou tiveram seu período de retenção estendido como parte de uma revisão, não aparecerão aqui.

![Guias de disposição](media/Retention-Disposition-tabs.png)
    
### <a name="filter-the-disposition-views"></a>Filtrar as exibições de disposição

Você pode filtrar esses modos de exibição por rótulo de retenção ou intervalo de tempo. Para desposições pendentes, o intervalo de tempo é baseado na data de expiração. Para itens descartados, o intervalo de tempo é baseado na data de exclusão.
  
![Opções de filtro de disposição](media/Retention-filter-options.png)

### <a name="export-the-disposition-items"></a>Exportar os itens de disposição

Além disso, você pode exportar os itens em um modo de exibição como um arquivo. csv que pode ser aberto no Excel.
  
![Dados de disposição exportados no Excel](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

