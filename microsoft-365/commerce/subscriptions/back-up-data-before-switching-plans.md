---
title: Fazer o back up de dados antes de alterar os planos
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: a1da52c9-2167-4973-9e6d-492314a79b87
description: Faça backup do conteúdo do Outlook, do OneDrive, do Yammer e do SharePoint antes de alterar os planos do Microsoft 365.
ms.openlocfilehash: f74acee03a21f2dfdf01c10017346b81a2885b3b
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647850"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Fazer o back up de dados antes de mudar de plano do Microsoft 365 para empresas

Se um usuário for alternado para outra assinatura que tenha menos serviços relacionados a dados ou um usuário sair da organização, uma cópia dos dados armazenados no Microsoft 365 poderá ser baixada antes de mudar para a nova assinatura.

Se você estiver movendo um usuário para uma assinatura que tenha os mesmos serviços ou mais, não será necessário fazer o back up dos dados do usuário. Consulte [Mover usuários para uma assinatura diferente.](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/move-users-different-subscription)
  
## <a name="save-a-copy-of-outlook-information"></a>Salvar uma cópia das informações do Outlook

Se os usuários têm o Outlook, eles podem exportar ou fazer backup de email, contatos e calendário para um arquivo [.pst do Outlook](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) antes de seu plano ser mudado.
  
Depois que a mudança para o novo plano for concluída, os usuários poderão importar emails, contatos e calendário de um arquivo [.pst do Outlook.](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Salvar arquivos armazenados no OneDrive for Business

Antes de mudar para uma assinatura diferente, os usuários podem baixar arquivos e pastas do OneDrive ou [do SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) para um local diferente, como uma pasta no disco rígido do computador ou um compartilhamento de arquivos na rede da organização.
  
## <a name="save-yammer-information"></a>Salvar informações do Yammer

Os administradores podem exportar todas as mensagens, anotações, arquivos, tópicos, usuários e grupos para um arquivo .zip. Para saber mais, confira [Exportar dados do Yammer Enterprise.](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data) Os desenvolvedores também podem usar a [API do Yammer](https://go.microsoft.com/fwlink/p/?linkid=842495) para fazer isso.
  
## <a name="how-to-save-sharepoint-information"></a>Como salvar informações do SharePoint

Se um usuário for trocado de uma assinatura que tenha o SharePoint Online para uma que não o tenha, o lado do **sharePoint** não aparecerá mais no menu do Microsoft 365.
  
No entanto, desde que a nova assinatura esteja dentro da mesma organização da qual eles são trocados, os usuários ainda poderão acessar o site de equipe do SharePoint. Eles podem exibir e atualizar blocos de anotações, documentos, tarefas e calendários usando a URL direta para o site de equipe.
  
> [!TIP]
> Recomendamos que os usuários acessem o site de equipe antes que sua assinatura seja alternada e salvem a URL como um favorito ou indicador no navegador.
  
Por padrão, a URL do site da equipe está neste formato:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

onde  _\<orgDomain\>_ está a URL da organização.
  
Por exemplo, se o domínio da organização for contoso.onmicrosoft.com, a URL direta para o site de equipe seria https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx .
  
Obviamente, os usuários também podem baixar documentos do SharePoint Online do site de equipe do SharePoint para seu computador local ou para outro local a qualquer momento.
