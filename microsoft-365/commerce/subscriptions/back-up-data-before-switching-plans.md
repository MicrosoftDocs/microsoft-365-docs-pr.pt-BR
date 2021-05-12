---
title: Fazer o back up de dados antes de alterar os planos
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Faça Outlook, OneDrive, Yammer e SharePoint antes de alterar Microsoft 365 planos.
ms.date: 03/17/2021
ms.openlocfilehash: 86953f3235d8725ecdd6b5294611c0e5a378b17d
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333345"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Fazer o back up de dados antes de alternar Microsoft 365 para planos de negócios

Se um usuário for alternado para outra assinatura que tenha menos serviços relacionados a dados ou um usuário sair da organização, uma cópia de seus dados armazenados no Microsoft 365 poderá ser baixada antes de ser alternada para a nova assinatura.

Se você estiver movendo um usuário para uma assinatura que tenha os mesmos ou mais serviços, não será necessário fazer o back up de dados do usuário. Consulte [Mover usuários para uma assinatura diferente.](./move-users-different-subscription.md)
  
## <a name="save-a-copy-of-outlook-information"></a>Salvar uma cópia de Outlook informações

Se os usuários Outlook, eles podem exportar ou fazer backup de emails, contatos e calendários para um arquivo [.pst](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) Outlook antes que seu plano seja comutado.
  
Depois que a opção para o novo plano for concluída, os usuários poderão importar email, contatos e calendário de um arquivo [.pst Outlook .pst.](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac)
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Salvar arquivos armazenados em OneDrive for Business

Antes de serem [trocados](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) para uma assinatura diferente, os usuários podem baixar arquivos e pastas do OneDrive ou SharePoint para um local diferente, como uma pasta no disco rígido do computador ou um compartilhamento de arquivos na rede da organização.
  
## <a name="save-yammer-information"></a>Salvar Yammer informações

Os administradores podem exportar todas as mensagens, anotações, arquivos, tópicos, usuários e grupos para um arquivo .zip. Para obter mais informações, [consulte Export data from Yammer Enterprise](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Os desenvolvedores também podem [usar Yammer API](https://go.microsoft.com/fwlink/p/?linkid=842495) de Yammer para fazer isso.
  
## <a name="how-to-save-sharepoint-information"></a>Como salvar SharePoint informações

Se um usuário for trocado de uma assinatura que tenha SharePoint Online para uma que não o tenha, o SharePoint **de** SharePoint não aparecerá mais no menu Microsoft 365.
  
No entanto, enquanto a nova assinatura estiver dentro da mesma organização da qual eles são trocados, os usuários ainda poderão acessar o site SharePoint equipe. Eles podem exibir e atualizar blocos de anotações, documentos, tarefas e calendários usando a URL direta para o site da equipe.
  
> [!TIP]
> Recomendamos que os usuários acessem o site da equipe antes que sua assinatura seja comutado e salvem a URL como um favorito ou indicador em seu navegador.
  
Por padrão, a URL do site da equipe está neste formulário:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

onde  _\<orgDomain\>_ é a URL da organização.
  
Por exemplo, se o domínio da organização for contoso.onmicrosoft.com, a URL direta para o site de equipe seria `https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx` .
  
Obviamente, os usuários também podem baixar documentos SharePoint Online do site de equipe SharePoint para seu computador local ou para outro local a qualquer momento.
