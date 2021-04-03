---
title: Perguntas frequentes sobre a Implantação centralizada
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Revise as respostas para perguntas frequentes sobre Implantação Centralizada do Centro de administração do Microsoft 365.
ms.openlocfilehash: 60d7a91da738803976b6823009450124d7b57814
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579297"
---
# <a name="centralized-deployment-faq"></a>Perguntas frequentes sobre a Implantação centralizada

A Implantação Centralizada é a maneira recomendada para um administrador do Office 365 implantar os complementos do Office (Word, Excel, PowerPoint e Outlook) para usuários e grupos dentro de uma organização, desde que a organização atenda a todos os requisitos para usar a Implantação Centralizada conforme descrito neste artigo.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Como saber se minha organização está configurada para Implantação Centralizada?  

A implantação centralizada de complementos exige que os usuários estão usando o Microsoft 365 Apps para empresas (e são assinados no Office usando suas credenciais de logoff organizacionais) e têm caixas de correio do Exchange Online. Seu diretório de assinatura deve estar no Azure Active Directory ou federado.  
 
A Implantação Centralizada só é suportada para caixas de correio online. Ele não dá suporte à implantação para caixas de correio locais do Exchange.

Você pode usar o [Verificador de Compatibilidade](centralized-deployment-of-add-ins.md#centralized-deployment-compatibility-checker)de Implantação Centralizado   para determinar se sua assinatura está qualificada. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Como você direciona as atribuições de usuário do complemento com a Implantação Centralizada?  

A Implantação Centralizada dá suporte a atribuições para usuários individuais, grupos e todos no locatário. A Implantação Centralizada pode ser usada para usuários em grupos de nível superior ou grupos sem grupos pai, mas não para usuários em grupos aninhados ou grupos que têm grupos pai. A Implantação Centralizada também faz parte da maioria dos grupos do Azure Active Directory, incluindo grupos do Office 365, listas de distribuição e grupos de segurança.  

É melhor usar atribuições de grupos em vez de atribuição de usuário individual para facilitar o gerenciamento.
 
Para obter mais detalhes, consulte [User and Group assignments](./centralized-deployment-of-add-ins.md?view=o365-worldwide#user-and-group-assignments).  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Quanto tempo leva para os complementos aparecerem para todos os usuários?  

Pode levar até 24 horas para um complemento aparecer para todos os usuários. Pode levar o mesmo tempo para atualizações de complementos, alterações de ativar ou desativar ou remoção de complementos. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Como administrador, como gerencio o acesso do usuário aos complementos da minha organização?

Para facilitar a implantação de complementos para usuários, grupos ou para toda a sua organização, recomendamos que os administradores usem a Implantação Centralizada.

Para obter mais informações sobre como gerenciar o acesso do usuário, consulte:
 - [Impedir downloads de complementos ao desligar a Office Store em todos os clientes (exceto o Outlook)](./manage-addins-in-the-admin-center.md#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook)
 - [Especificar os administradores e usuários que podem instalar e gerenciar aplicativos para o Outlook](/Exchange/specify-who-can-install-and-manage-add-ins-2013-help)

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>A Implantação Centralizada fornecerá aos administradores a flexibilidade para escolher o método de implantação para os complementos do Outlook?  

Sim. A Implantação Centralizada oferece aos administradores a flexibilidade de escolher um dos três métodos de implantação para os complementos do Outlook durante a implantação do complemento:

**Fixo (Padrão)**   O complemento é implantado automaticamente para os usuários atribuídos, e eles não podem removê-lo.  
 
**Disponível** Os usuários podem instalar o add-in no Outlook escolhendo **Home > Obter mais > admin-managed**.
 
**Opcional** O complemento é implantado automaticamente para os usuários atribuídos, mas eles podem optar por removê-lo.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Os administradores podem atualizar os complementos de Linha de Negócios (LOB)?  

Sim. Os administradores podem carregar um novo arquivo de manifesto para dar suporte a alterações de metadados para os complementos LOB implantados pelo administrador. O complemento é atualizado na próxima vez que os aplicativos do Office são iniciados. O aplicativo Web pode mudar a qualquer momento.  
 
Para obter mais informações, consulte [line-of-business add-in](./manage-addins-in-the-admin-center.md).  

## <a name="can-admins-turn-off-add-ins"></a>Os administradores podem desativar os complementos?  

Sim. Os administradores podem ativar ou desativar os complementos implantados para todos os usuários do centro de administração da Microsoft.

Para obter mais informações, consulte [Estados de complemento](./manage-addins-in-the-admin-center.md#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Os administradores podem excluir ou remover os complementos?

Sim. Os administradores podem excluir os complementos implantados para todos os usuários do centro de administração da Microsoft.

Para obter mais informações, consulte [Delete an add-in](./manage-addins-in-the-admin-center.md#delete-an-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Os administradores podem implantar os complementos pagos da Office Store usando a Implantação Centralizada? 

Não. Não é possível implantar os complementos pagos da Office Store usando a Implantação Centralizada no momento.  
 
Sugerimos entrar em ação com o Desenvolvedor ISV para que o complemento pago solicite um arquivo de manifesto ou uma URL. Em seguida, o administrador do locatário pode implantar o add-in como um complemento LOB usando a Implantação Centralizada.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Qual função de administrador preciso gerenciar os complementos para minha organização?  

Administrador Global é a função recomendada com acesso completo ao ciclo de vida de gerenciamento de complementos. Outras funções de administrador têm acesso limitado ao ciclo de vida de implantação do complemento. Se você for a pessoa que comprou sua assinatura do Microsoft 365 para empresas, você será o administrador global. 
 
Sua assinatura vem com um conjunto de funções de administrador que você pode atribuir a outros usuários em sua organização. Cada função de administrador mapeia para funções comerciais comuns e dá às pessoas em sua organização permissões para executar tarefas específicas no centro de administração do Microsoft 365.  
 
Para obter mais informações, consulte [Atribuir funções de administrador](../add-users/assign-admin-roles.md?view=o365-worldwide). 