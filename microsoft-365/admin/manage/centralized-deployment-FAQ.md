---
title: Perguntas frequentes sobre Implantação Centralizada
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Revise as respostas para perguntas frequentes sobre a implantação centralizada no centro de administração do Microsoft 365.
ms.openlocfilehash: c389ab07136b8a6e625db9ecfeff514a6899cd7d
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011730"
---
# <a name="centralized-deployment-faq"></a>Perguntas frequentes sobre Implantação Centralizada

A implantação centralizada é a maneira recomendada para o administrador do Office 365 implantar suplementos do Office (Word, Excel, PowerPoint e Outlook) para usuários e grupos em uma organização, desde que a organização atenda a todos os requisitos para usar a implantação centralizada, conforme descrito neste artigo.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Como saber se minha organização está configurada para implantação centralizada?  

A implantação centralizada de suplementos requer que os usuários estejam usando o Microsoft 365 aplicativos para empresas (e estejam conectados ao Office usando suas credenciais de login organizacionais) e tenham caixas de correio do Exchange Online. O diretório de assinatura deve estar no Azure Active Directory ou federado a ele.  
 
A implantação centralizada só é suportada para caixas de correio online. Ele não oferece suporte à implantação em caixas de correio locais do Exchange.
 
Você pode usar o [Verificador de compatibilidade de implantação centralizada do Office 365](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker)para determinar se sua assinatura está qualificada. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Como você direciona as atribuições de usuário de suplemento com a implantação centralizada?  

A implantação centralizada oferece suporte a atribuições para usuários individuais, grupos e todos no locatário. A implantação centralizada pode ser usada para usuários em grupos de nível superior ou grupos sem grupos pai, mas não para usuários em grupos aninhados ou grupos com grupos pai. A implantação centralizada também faz parte da maioria dos grupos do Active Directory do Azure, incluindo grupos do Office 365, listas de distribuição e grupos de segurança.  

É melhor usar atribuições de grupos em vez de atribuição de usuário individual para facilitar o gerenciamento.
 
Para obter mais detalhes, consulte [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Quanto tempo leva para que suplementos sejam mostrados para todos os usuários?  

Pode levar até 24 horas para que um suplemento seja exibido para todos os usuários. Pode levar a mesma quantidade de tempo para atualizações de suplemento, alterações de ativar ou desativar ou de remoções de suplemento. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Como administrador, como gerenciar o acesso do usuário aos suplementos da minha organização?

Para facilitar a implantação de suplementos para usuários, grupos ou para toda a sua organização, recomendamos que os administradores usem a implantação centralizada.

Para obter mais informações sobre como gerenciar o acesso do usuário, consulte </br>[Impedir downloads de suplementos desativando a Office Store em todos os clientes (exceto Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) e </br>[Especifique os administradores e usuários que podem instalar e gerenciar suplementos para o Outlook](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>A implantação centralizada oferece aos administradores a flexibilidade para escolher o método de implantação para os suplementos do Outlook?  

Sim. A implantação centralizada oferece aos administradores a flexibilidade para escolher um dos três métodos de implantação para suplementos do Outlook durante a implantação do suplemento:

**Fixo (padrão)**   o suplemento é implantado automaticamente para os usuários atribuídos e não pode removê-lo.  
 
**Disponível** Os usuários podem instalar o suplemento no Outlook escolhendo Home > obter mais suplementos > administração gerenciada.   
 
**Opcional** O suplemento é implantado automaticamente para os usuários atribuídos, mas eles podem optar por removê-lo.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Os administradores podem atualizar suplementos de linha de negócios (LOB)?  

Sim. Os administradores podem carregar um novo arquivo de manifesto para dar suporte às alterações de metadados para suplementos LOB implantados pelo administrador. O suplemento é atualizado na próxima vez que os aplicativos do Office são iniciados. O aplicativo Web pode mudar a qualquer momento.  
 
Para obter mais informações, consulte [suplemento de linha de negócios](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).  

## <a name="can-admins-turn-off-add-ins"></a>Os administradores podem desativar os suplementos?  

Sim. Os administradores podem ativar ou desativar os suplementos implantados para todos os usuários do centro de administração da Microsoft.

Para mais informações, confira [Estados de suplementos](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Os administradores podem excluir ou remover suplementos?

Sim. Os administradores podem excluir os suplementos implantados para todos os usuários do centro de administração da Microsoft.

Para obter mais informações, consulte [excluir o suplemento](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Os administradores podem implantar os suplementos pagos da Office Store usando a implantação centralizada? 

Não. Você não pode implantar os suplementos pagos da Office Store usando a implantação centralizada no momento.  
 
Sugerimos acessar o desenvolvedor de ISV do suplemento pago para solicitar um arquivo de manifesto ou uma URL. O administrador de locatários pode implantar o suplemento como um suplemento de LOB usando a implantação centralizada.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Qual função de administrador preciso gerenciar suplementos para minha organização?  

Você deve ter a função de administrador global para gerenciar suplementos. Se você é a pessoa que comprou sua assinatura do Microsoft 365 for Business, você é o administrador global. 
 
Sua assinatura vem com um conjunto de funções de administrador que você pode atribuir a outros usuários em sua organização. Cada função de administrador mapeia para funções comuns de negócios e dá às pessoas de suas permissões de organização a execução de tarefas específicas no centro de administração do Microsoft 365.  
 
Para obter mais informações, consulte [assign admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).  