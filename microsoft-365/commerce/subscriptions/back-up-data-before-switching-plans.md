---
title: Fazer backup dos dados antes de mudar de planos
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Faça backup do conteúdo do Outlook, do OneDrive, do Yammer e do SharePoint antes de mudar o Microsoft 365 Plans.
ms.openlocfilehash: 9acc97f65bb5b471cb992d7f01cd299192b74a52
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818526"
---
# <a name="back-up-data-before-switching-microsoft-365-for-business-plans"></a>Fazer backup dos dados antes de mudar o Microsoft 365 para planos de negócios

Se um usuário for alternado para outra assinatura que tenha menos serviços relacionados a dados ou um usuário saia da organização, uma cópia de seus dados armazenados no Microsoft 365 poderá ser baixada antes de ser comutada para a nova assinatura.
  
## <a name="save-a-copy-of-outlook-information"></a>Salvar uma cópia das informações do Outlook

Se os usuários tiverem o Outlook, eles poderão [exportar ou fazer backup de email, contatos e calendário para um arquivo. pst do Outlook](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) antes de seu plano ser comutado.
  
Após a conclusão da opção para o novo plano, os usuários podem [importar email, contatos e calendário de um arquivo. pst do Outlook](https://support.microsoft.com/office/431a8e9a-f99f-4d5f-ae48-ded54b3440ac).
  
## <a name="save-files-stored-in-onedrive-for-business"></a>Salvar arquivos armazenados no OneDrive for Business

Antes de ser alternado para uma assinatura diferente, os usuários podem [baixar arquivos e pastas do onedrive ou do SharePoint](https://support.microsoft.com/office/5c7397b7-19c7-4893-84fe-d02e8fa5df05) para um local diferente, como uma pasta no disco rígido do computador ou um compartilhamento de arquivos na rede da organização.
  
## <a name="save-yammer-information"></a>Salvar informações do Yammer

Os administradores podem exportar todas as mensagens, observações, arquivos, tópicos, usuários e grupos para um arquivo. zip. Para obter mais informações, consulte [exportar dados do Yammer Enterprise](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Os desenvolvedores também podem usar a [API do Yammer](https://go.microsoft.com/fwlink/p/?linkid=842495) .
  
## <a name="how-to-save-sharepoint-information"></a>Como salvar informações do SharePoint

Se um usuário tiver mudado de uma assinatura que tenha o SharePoint Online para um que não o tenha, o bloco do **SharePoint** deixará de aparecer no menu do Microsoft 365.
  
No entanto, desde que a nova assinatura esteja dentro da mesma organização que a de sua comutação, os usuários ainda poderão acessar o site de equipe do SharePoint. Eles podem exibir e atualizar blocos de anotações, documentos, tarefas e calendários usando a URL direta para o site de equipe.
  
> [!TIP]
> Recomendamos que os usuários acessem o site de equipe antes que sua assinatura seja alternada e salve a URL como um favorito ou indicador no navegador.
  
Por padrão, a URL do site de equipe está neste formato:
  
```html
https://<orgDomain>/_layouts/15/start.aspx#/SitePages/Home.aspx
```

em que _\<orgDomain\>_ é a URL da organização.
  
Por exemplo, se o domínio da organização for contoso.onmicrosoft.com, a URL direta para o site de equipe seria https://contoso.onmicrosoft.com/_layouts/15/start.aspx#/SitePages/Home.aspx .
  
Obviamente, os usuários também podem baixar documentos do SharePoint Online do site de equipe do SharePoint para o computador local ou para outro local a qualquer momento.