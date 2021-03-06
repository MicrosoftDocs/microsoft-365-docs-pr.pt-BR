---
title: Adicionar blocos personalizados ao inicializador de aplicativos
f1.keywords:
- CSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: Crie links rápidos para seu email, documentos, aplicativos, SharePoint sites, sites externos e outros recursos adicionando blocos personalizados ao iniciador de aplicativos.
ms.openlocfilehash: 47f871d66f180225e877a521ef159fc745960507
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623768"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Adicionar blocos personalizados ao inicializador de aplicativos

Em Microsoft 365, você pode chegar rapidamente e facilmente aos seus emails, calendários, documentos e aplicativos usando o launcher de aplicativos ([saiba mais](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)). Esses são os aplicativos que você Microsoft 365, bem como aplicativos personalizados que você adiciona da SharePoint [Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) ou [do Azure AD](/previous-versions/office/office-365-api/).
  
Você pode adicionar blocos personalizados ao inicializador de aplicativos, que apontem para sites do SharePoint, sites externos, aplicativos herdados, e muito mais. O bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos, mas você pode fixá-lo junto aos aplicativos da guia **Página Inicial** e orientar os usuários a fazerem o mesmo. Isso facilita a localização de sites, aplicativos e recursos importantes para realizar o trabalho. No exemplo a seguir, o bloco personalizado Portal da Contoso serve para acessar o site de intranet do SharePoint da organização. 
  
![Inicializador de aplicativos](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Adicionar um bloco personalizado ao inicializador de aplicativos

1. Entre no centro de administração como Administrador Global, vá para o Configurações Org Configurações e escolha a  >  guia **Perfil da** Organização.
    
2. Na guia **Perfil da** Organização, escolha **Blocos personalizados do iniciador de aplicativos.**
  
3. Selecione **Adicionar um azulejo personalizado.** 
  
4. Insira o **Nome do bloco** para o novo bloco. O nome será exibido no bloco. 
    
5. Insira uma **URL do site** para o azulejo. Este é o local onde você deseja que seus usuários acessem quando eles selecionam o telha no launcher do aplicativo. Use HTTPS na URL.

    > [!TIP]
    > Se você estiver criando um bloco para um site do SharePoint, navegue até o site, copie a URL e cole-a aqui. A URL do site de equipe padrão tem esta aparência: `https://<company_name>.sharepoint.com` 
  
6. Insira uma **URL da imagem** do azulejo. A imagem é exibida na página Meus Aplicativos e no inicializador de aplicativos.

    > [!TIP]
    > A imagem deve ter 60 x 60 pixels e estar disponível para todos em sua organização sem a necessidade de autenticação.

7. Insira uma **Descrição** para o bloco. Você vê isso quando seleciona o azulejo na página Meus aplicativos e seleciona **Detalhes do aplicativo.** 
  
8. Selecione **Salvar alterações** para criar o azulejo personalizado. 
    
    Agora, o bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos para todas as pessoas. 

    > [!NOTE]
    > Se você não vir o bloco personalizado criado na etapa anterior, verifique se tem uma caixa de correio do Exchange Online atribuída e se você entrou em sua caixa de correio pelo menos uma vez. Essas etapas são necessárias para blocos personalizados Microsoft 365. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. No centro de administração, vá para **a** guia perfil Configurações  >  **Org Configurações**  >  **Organização.**
    
2. Na página **Perfil da** Organização, ao lado de   **Adicionar blocos personalizados para sua** organização, selecione **Editar**.

3. Atualize o **Nome do bloco**, a **URL**, a **Descrição** ou a **URL da imagem** do bloco personalizado (consulte a [Adicionar um bloco personalizado ao inicializador de aplicativos](#add-a-custom-tile-to-the-app-launcher)).
    
4. Selecione **Atualizar** \> **Fechar**. 
    
Para excluir um bloco personalizado, na janela **Blocos** personalizados, selecione o bloco, selecione **Remover excluir bloco**  >  . 
  
## <a name="next-steps"></a>Próximas etapas

Além de adicionar blocos ao launcher de aplicativos, você pode adicionar blocos do launcher de aplicativo à barra de navegação ([saiba mais](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)). Para personalizar a aparência da Microsoft 365 para corresponder à marca da sua organização, consulte [Customize the Microsoft 365 theme](../setup/customize-your-organization-theme.md).

## <a name="related-content"></a>Conteúdo relacionado

[Fixar aplicativos no iniciador de aplicativos](pin-apps-to-app-launcher.md) de seus usuários (artigo)\
[Atualize seu Microsoft 365 para usuários comerciais para o cliente Office mais recente](../setup/upgrade-users-to-latest-office-client.md) (artigo)\
[Gerenciar os complementos no centro de administração](../manage/manage-addins-in-the-admin-center.md) (artigo)
