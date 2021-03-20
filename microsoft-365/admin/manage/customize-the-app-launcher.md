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
description: 'Crie links rápidos para seu email, documentos, aplicativos, sites do SharePoint, sites externos e outros recursos adicionando blocos personalizados ao iniciador de aplicativos. '
ms.openlocfilehash: cc4edbfadc5c9555e04d04de8f7368dd86aa9974
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915429"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Adicionar blocos personalizados ao inicializador de aplicativos

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

No Microsoft 365, você pode chegar rapidamente e facilmente aos seus emails, calendários, documentos e aplicativos usando o iniciador de aplicativos ([saiba mais](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)). Esses são os aplicativos que você tem com o Microsoft 365, bem como aplicativos personalizados que você adiciona da Loja do [SharePoint](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) ou [do Azure AD](/previous-versions/office/office-365-api/).
  
Você pode adicionar blocos personalizados ao inicializador de aplicativos, que apontem para sites do SharePoint, sites externos, aplicativos herdados, e muito mais. O bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos, mas você pode fixá-lo junto aos aplicativos da guia **Página Inicial** e orientar os usuários a fazerem o mesmo. Isso facilita a localização de sites, aplicativos e recursos importantes para realizar o trabalho. No exemplo a seguir, o bloco personalizado Portal da Contoso serve para acessar o site de intranet do SharePoint da organização. 
  
![Launcher de aplicativos](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Adicionar um bloco personalizado ao inicializador de aplicativos

1. Entre no centro de administração como Administrador Global, acesse **Configurações** da Organização Configurações e escolha a  >  guia **Perfil da** Organização.
    
2. Na guia **Perfil da** Organização, escolha **Blocos personalizados do iniciador de aplicativos.**
  
3. Selecione **Adicionar um azulejo personalizado.** 
  
4. Insira o **Nome do bloco** para o novo bloco. O nome será exibido no bloco. 
    
5. Insira uma **URL do site** para o azulejo. Este é o local onde você deseja que seus usuários acessem quando eles selecionam o telha no launcher do aplicativo. Use HTTPS na URL.<br/>DICA: Se você estiver criando um azulejo para um site do SharePoint, navegue até esse site, copie a URL e a colará aqui. A URL do site de equipe padrão tem esta aparência: `https://<company_name>.sharepoint.com` 
  
6. Insira uma **URL da imagem** do azulejo. A imagem é exibida na página Meus Aplicativos e no inicializador de aplicativos.<br/>DICA: a imagem deve ter 60 x 60 pixels e estar disponível para todos na sua organização sem a necessidade de autenticação.

7. Insira uma **Descrição** para o bloco. Você vê isso quando seleciona o azulejo na página Meus aplicativos e seleciona **Detalhes do aplicativo.** 
  
8. Selecione **Salvar alterações** para criar o azulejo personalizado. 
    
Agora, o bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos para todas as pessoas. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. No centro de administração, vá para a guia **Configurações** da Organização  >  **Configurações**  >  **Perfil da** </a> organização.
    
2. Na página **Perfil da** Organização, ao lado de   **Adicionar blocos personalizados para sua** organização, selecione **Editar**.

3. Atualize o **Nome do bloco**, a **URL**, a **Descrição** ou a **URL da imagem** do bloco personalizado (consulte a [Adicionar um bloco personalizado ao inicializador de aplicativos](#add-a-custom-tile-to-the-app-launcher)).
    
4. Selecione **Atualizar** \> **Fechar**. 
    
Para excluir um bloco personalizado, na janela **Blocos** personalizados, selecione o bloco, selecione **Remover excluir bloco**  >  . 
  
## <a name="whats-next"></a>O que vem a seguir?

Além de adicionar blocos ao launcher de aplicativos, você pode adicionar blocos do launcher de aplicativo à barra de navegação ([saiba mais](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)). Para personalizar a aparência do Microsoft 365 para corresponder à marca da sua organização, consulte Personalizar o [tema do Microsoft 365](../setup/customize-your-organization-theme.md).
