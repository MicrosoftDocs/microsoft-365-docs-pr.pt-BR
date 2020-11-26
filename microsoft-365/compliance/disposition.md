---
title: Disposição de conteúdo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Monitore e gerencie a disposição do conteúdo, se você usa uma revisão de disposição ou o conteúdo é excluído automaticamente de acordo com as configurações definidas.
ms.openlocfilehash: 9900bbc58818a98ad41f4f796184ccf21041bbfe
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409208"
---
# <a name="disposition-of-content"></a>Disposição de conteúdo

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

Use a guia **Disposição** do **Gerenciamento de Registros** no Centro de conformidade do Microsoft 365 para gerenciar análises de disposição e exibir [registros](records-management.md#records) que foram excluídos automaticamente no final do período de retenção. 

## <a name="prerequisites-for-viewing-content-dispositions"></a>Pré-requisitos para exibir disposições de conteúdo

Para gerenciar as revisões de disposição e confirmar que os registros foram excluídos, você deve ter permissões suficientes e a auditoria deve ser habilitada.

### <a name="permissions-for-disposition"></a>Permissões para disposição

Para acessar a guia **Disposição** no Centro de conformidade do Microsoft 365, os usuários devem ter função de administrador **Gerenciamento de disposição**. Esta função é incluída nos grupos de funções de administrador padrão, **Administrador de Conformidade** e **Administrador de conformidade de dados**.

Para conceder aos usuários a função de Gerenciamento de Disposição necessária, você pode adicioná-los a um desses grupos de função padrão ou criar um grupo de função personalizada (por exemplo, chamado "Revisores de disposição") e conceder a esse grupo a função de Gerenciamento de Disposição.  

> [!NOTE]
> Até mesmo um administrador global precisa ter a função de **Gerenciamento de Disposição**. 

Além disso, para exibir o conteúdo dos itens durante o processo de disposição, adicione usuários aos dois grupos de funções a seguir: **Visualizador de conteúdo do Gerenciador de Conteúdo** e **Visualizador de lista de Gerenciador de Conteúdo**. Se os usuários não tiverem as permissões desses grupos de função, ainda poderão selecionar uma ação de revisão de disposição para concluir a revisão de disposição, mas deve fazê-lo sem a capacidade de exibir o conteúdo do item do centro de conformidade.

Para obter instruções, confira [Fornecer aos usuários acesso ao Centro de Segurança e Conformidade do Office 365](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

### <a name="enable-auditing"></a>Habilitar auditoria

Verifique se a auditoria está habilitada pelo menos um dia antes da primeira ação de disposição. Para saber mais, confira [Pesquisar o log de auditoria no Centro de Conformidade &amp; e Segurança do Office 365](search-the-audit-log-in-security-and-compliance.md). 

## <a name="disposition-reviews"></a>Revisões de disposição

Quando o conteúdo atinge o fim do período de retenção, existem vários motivos pelos quais você pode querer revisar o conteúdo para decidir se ele pode ser excluído com segurança ("descartado"). Por exemplo, talvez você precise:
  
- Suspender a exclusão de conteúdo relevante no caso de litígio ou auditoria.
    
- Remover conteúdo da lista de disposição para armazenar em um arquivo morto, se esse conteúdo tiver um valor de pesquisa ou histórico.
    
- Atribuir um período de retenção diferente ao conteúdo, talvez porque as configurações originais de retenção fossem uma solução temporária ou provisória.
    
- Retornar o conteúdo aos clientes ou transferi-lo para outra organização.

Quando uma revisão de disposição é disparada no final do período de retenção:
  
- As pessoas que você escolher receberão uma notificação por email com o conteúdo a ser revisado. Esses revisores podem ser usuários individuais ou grupos de segurança habilitados para email. As notificações são enviadas semanalmente.
    
- Os revisores vão para a guia **Disposição**, no Centro de conformidade do Microsoft 365, para revisar o conteúdo e decidir se desejam ou não excluí-lo permanentemente, estender o período de retenção ou aplicar um rótulo de retenção diferente.

Uma revisão de disposição pode incluir conteúdo nas caixas de correio do Exchange, sites do SharePoint, contas do OneDrive e grupos do Microsoft 365. O conteúdo que aguarda uma revisão de disposição nesses locais é excluído apenas após um revisor optar por excluir permanentemente o conteúdo.

> [!NOTE]
> Uma caixa de correio deve ter pelo menos 10 MB de dados para suportar revisões de disposição.

Você pode ver uma visão geral de todas as disposições pendentes na guia **Visão Geral**. Por exemplo:

![Disposições pendentes na visão geral do Gerenciamento de registros](../media/dispositions-overview.png)

Ao selecionar **Exibir todas as disposições pendentes**, você será levado à página **Disposição**. Por exemplo:

![Página Disposições no Centro de conformidade do Microsoft 365](../media/disposition-tab.png)


### <a name="workflow-for-a-disposition-review"></a>Fluxo de trabalho de revisão de disposição

O diagrama a seguir mostra o fluxo de trabalho básico para uma revisão de disposição quando um rótulo de retenção é publicado e aplicado manualmente por um usuário. Como alternativa, um rótulo de retenção configurado para uma revisão de disposição poderá ser aplicado automaticamente ao conteúdo.
  
![Gráfico mostrando o fluxo de como a disposição funciona](../media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
Disparar uma revisão de disposição ao fim do período de retenção é uma opção de configuração disponível somente com um rótulo de retenção. Esta opção não está disponível para política de retenção. Para obter mais informações sobre essas duas soluções de retenção, consulte [Saber mais sobre as políticas de retenção e os rótulos de retenção](retention.md).

Da página **Definir configurações de retenção** para um rótulo de retenção:

![Configurações de retenção para um rótulo](../media/disposition-review-option.png)
 
Depois de selecionar esta opção **Disparar uma revisão de disposição**, especifique os revisores de disposição na próxima página do assistente:

![Especificando revisores de disposição](../media/disposition-reviewers.png)

Para os revisores, especifique um usuário ou um grupo de segurança habilitado para email. Grupos do Microsoft 365 ([antigo Grupos do Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)) não têm suporte para essa opção.

### <a name="viewing-and-disposing-of-content"></a>Exibir e descartar o conteúdo

Quando um revisor é notificado por email informando que o conteúdo está pronto para ser revisado, ele vai para a guia **Disposição** em **Gerenciamento de Registros** no Centro de conformidade do Microsoft 365. Os revisores podem ver quantos itens de cada rótulo de retenção estão aguardando disposição e, em seguida, selecionar um rótulo de retenção para ver todo o conteúdo com esse rótulo.

Depois de selecionar um rótulo de retenção, você verá todas as suas disposições pendentes na guia **Disposição pendente**. Selecione um ou mais itens em que você pode escolher uma ação e inserir um comentário de justificação:

![Opções de disposição](../media/retention-disposition-options.png)

Como você pode ver na imagem, as ações com suporte são: 
  
- Excluir permanentemente o item
- Estender o período de retenção
- Aplicar um rótulo de retenção diferente

Fornecendo permissões para o local e o conteúdo, você pode usar o link na coluna **Local** para exibir os documentos no local original. Durante uma revisão de disposição, o conteúdo nunca se moverá do local original e nunca será excluído até que o revisor opte por fazê-lo.

As notificações de email são enviadas automaticamente para os revisores semanalmente. Esse processo agendado significa que, quando o conteúdo atinge o fim do período de retenção, pode levar até sete dias para que os revisores recebam a notificação de email informando que o conteúdo está aguardando a disposição.
  
Todas as ações podem ser auditadas, e o texto de justificativa digitado pelo revisor é salvo e exibido na coluna **Comentário** na página **Itens Descartados**.
  
### <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Quanto tempo leva até que o conteúdo seja permanentemente excluído

O conteúdo que aguarda uma revisão de disposição é excluído apenas após um revisor optar por excluir permanentemente o conteúdo. Quando o revisor escolhe essa opção, o conteúdo no site do SharePoint ou na conta do OneDrive fica qualificado para o processo de limpeza padrão descrito em [Como as configurações de retenção funcionam com o conteúdo no local](retention.md#how-retention-settings-work-with-content-in-place).

## <a name="disposition-of-records"></a>Disposição de registros

Use a guia **Disposição** da página **Gerenciamento de registros** para identificar os registros excluídos, automaticamente ou após uma revisão de disposição. Esses itens exibem **Registros Descartados** na coluna **Tipo**. Por exemplo:

![Itens que foram descartados sem uma revisão de disposição](../media/records-disposed2.png)

Os itens mostrados na guia **Itens descartados** de rótulos de registro serão mantidos por até sete anos após o item ter sido descartado, com um limite de 1 milhão itens por registro para esse período. Se você vir que o número de **Contagem** se aproxima desse limite de 1 milhão e precisar de prova de disposição para seus registros, contate o [Suporte da Microsoft](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).

> [!NOTE]
> Esta funcionalidade baseia-se em informações do[Log de auditoria unificada](search-the-audit-log-in-security-and-compliance.md) e, portanto, exige que a auditoria seja [habilitada e pesquisável](turn-audit-log-search-on-or-off.md), para que os eventos correspondentes sejam capturados.

Para auditoria, pesquise **Arquivo excluído marcado como registro** na categoria **Arquivo e atividades de página**. Esse evento de auditoria é aplicável a documentos e emails.

## <a name="filter-and-export-the-views"></a>Filtrar e exportar os modos de exibição

Quando você seleciona um rótulo de retenção na página **Disposição**, a guia **Disposição pendente** (se aplicável) e a guia **Itens descartados** permitem filtrar os modos de exibição para facilitar a localização de itens. 

Para as disposições pendentes, o intervalo de tempo se baseia na data de vencimento. Para itens descartados, o intervalo de tempo se baseia na data de exclusão.
  
Você pode exportar informações sobre os itens no modo de exibição como um arquivo .csv, que pode ser classificado e gerenciado usando o Excel:

![Opção de exportação para disposição](../media/retention-export-option.png)

