---
title: Perguntas frequentes sobre a Implantação centralizada
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Revise as respostas para perguntas frequentes sobre a Implantação Centralizada no Centro de administração do Microsoft 365.
ms.openlocfilehash: 555496f15663b6607ebc785498bdc94b5e51b9c9
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948683"
---
# <a name="centralized-deployment-faq"></a>Perguntas frequentes sobre a Implantação centralizada

A Implantação Centralizada é a maneira recomendada para um administrador do Office 365 implantar os complementos do Office (Word, Excel, PowerPoint e Outlook) para usuários e grupos dentro de uma organização, desde que a organização atenda a todos os requisitos para usar a Implantação Centralizada, conforme descrito neste artigo.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Como saber se minha organização está configurada para Implantação Centralizada?  

A implantação centralizada de complementos exige que os usuários usem o Microsoft 365 Apps para empresas (e sejam assinados no Office usando suas credenciais de logoff organizacionais) e tenham caixas de correio do Exchange Online. Seu diretório de assinatura deve estar no Azure Active Directory ou federado.  
 
A Implantação Centralizada só é suportada para caixas de correio online. Ele não dá suporte à implantação em caixas de correio locais do Exchange.

Você pode usar o [Verificador de Compatibilidade de](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)Implantação   Centralizado para determinar se sua assinatura é qualificada. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Como direcionar atribuições de usuário de um complemento com a Implantação Centralizada?  

A Implantação Centralizada dá suporte a atribuições para usuários individuais, grupos e todos no locatário. A Implantação Centralizada pode ser usada para usuários em grupos de nível superior ou grupos sem grupos pai, mas não para usuários em grupos aninhados ou grupos que tenham grupos pai. A Implantação Centralizada também faz parte da maioria dos grupos do Azure Active Directory, incluindo Grupos do Office 365, listas de distribuição e grupos de segurança.  

É melhor usar atribuições de grupos em vez de atribuição de usuário individual para facilitar o gerenciamento.
 
Para obter mais detalhes, consulte [User and Group assignments](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Quanto tempo leva para os complementos aparecerem para todos os usuários?  

Pode levar até 24 horas para um complemento aparecer para todos os usuários. Pode levar o mesmo tempo para atualizações de add-in, alterações de ativar ou desativar ou remoção de complementos. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Como administrador, como faço para gerenciar o acesso do usuário aos complementos da minha organização?

Para facilitar a implantação de complementos para usuários, grupos ou para toda a sua organização, recomendamos que os administradores usem a Implantação Centralizada.

Para obter mais informações sobre como gerenciar o acesso do usuário, consulte:
 - [Impedir downloads de complementos ao desligar a Office Store em todos os clientes (exceto o Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Especificar os administradores e usuários que podem instalar e gerenciar aplicativos para o Outlook](https://docs.microsoft.com/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>A Implantação Centralizada fornecerá aos administradores a flexibilidade de escolher o método de implantação para os complementos do Outlook?  

Sim. A Implantação Centralizada oferece aos administradores a flexibilidade de escolher um dos três métodos de implantação para os complementos do Outlook durante a implantação do complemento:

**Fixo (Padrão)**   O complemento é implantado automaticamente para os usuários atribuídos, e eles não podem removê-lo.  
 
**Disponível** Os usuários podem instalar o complemento no Outlook escolhendo Home > Obter mais > **gerenciados pelo administrador.**
 
**Opcional** O complemento é implantado automaticamente para os usuários atribuídos, mas eles podem optar por removê-lo.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Os administradores podem atualizar os complementos de Linha de Negócios (LOB) ?  

Sim. Os administradores podem carregar um novo arquivo de manifesto para dar suporte a alterações de metadados para os complementos LOB implantados pelo administrador. O complemento será atualizado na próxima vez que os aplicativos do Office iniciarem. O aplicativo Web pode mudar a qualquer momento.  
 
Para obter mais informações, consulte o complemento de linha [de negócios.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#more-about-office-add-ins-security)  

## <a name="can-admins-turn-off-add-ins"></a>Os administradores podem desativar os complementos?  

Sim. Os administradores podem ativar ou desativar os complementos que implantam para todos os usuários do centro de administração da Microsoft.

Para obter mais informações, [consulte Estados do complemento.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#add-in-states)  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Os administradores podem excluir ou remover os complementos?

Sim. Os administradores podem excluir os complementos implantados para todos os usuários do Centro de administração da Microsoft.

Para saber mais, confira [Excluir um complemento.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center#delete-an-add-in) 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Os administradores podem implantar os complementos pagos da Office Store usando a Implantação Centralizada? 

Não. Não é possível implantar os complementos pagos da Office Store usando a Implantação Centralizada no momento.  
 
Sugerimos entrar em ação com o desenvolvedor de ISV para que o complemento pago solicite um arquivo de manifesto ou uma URL. Em seguida, o administrador de locatários pode implantar o complemento como um complemento LOB usando a Implantação Centralizada.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Qual função de administrador preciso para gerenciar os complementos da minha organização?  

O Administrador Global é a função recomendada com acesso completo ao ciclo de vida de gerenciamento de complementos. Outras funções de Administrador têm um acesso limitado ao ciclo de vida de implantação do add-in. Se você é a pessoa que comprou sua assinatura do Microsoft 365 para empresas, você é o administrador global. 
 
Sua assinatura vem com um conjunto de funções de administrador que você pode atribuir a outros usuários em sua organização. Cada função de administrador mapeia para funções comerciais comuns e concede permissões às pessoas em sua organização para executar tarefas específicas no centro de administração do Microsoft 365.  
 
Para obter mais informações, consulte [Atribuir funções de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide)  


