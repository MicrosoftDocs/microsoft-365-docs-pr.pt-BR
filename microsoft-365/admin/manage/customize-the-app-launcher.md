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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1136115a-75af-4497-b693-640c4ce70bc6
description: 'Crie links rápidos para seus emails, documentos, aplicativos, sites do SharePoint, sites externos e outros recursos adicionando blocos personalizados ao inicializador de aplicativos. '
ms.openlocfilehash: f099eabef7a22e9ebd8f20b23ccd3d8da142f07f
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262358"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Adicionar blocos personalizados ao inicializador de aplicativos

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

No Microsoft 365, você pode acessar seus emails, calendários, documentos e aplicativos com rapidez e facilidade usando o inicializador de aplicativos ([saiba mais](https://support.office.com/article/79f12104-6fed-442f-96a0-eb089a3f476a.aspx)). Estes são os aplicativos que você obtém com o Microsoft 365, bem como aplicativos personalizados que você adiciona do [SharePoint Store](https://support.office.com/article/dd98e50e-d3db-4ecb-9bb7-82b189822d43.aspx) ou [do Azure ad](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher).
  
Você pode adicionar blocos personalizados ao inicializador de aplicativos, que apontem para sites do SharePoint, sites externos, aplicativos herdados, e muito mais. O bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos, mas você pode fixá-lo junto aos aplicativos da guia **Página Inicial** e orientar os usuários a fazerem o mesmo. Isso facilita a localização de sites, aplicativos e recursos importantes para realizar o trabalho. No exemplo a seguir, o bloco personalizado Portal da Contoso serve para acessar o site de intranet do SharePoint da organização. 
  
![Inicializador de aplicativos](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Adicionar um bloco personalizado ao inicializador de aplicativos

1. No centro de administração, vá para as configurações de organização de **configurações**  >  **Org Settings** e escolha a guia **perfil da organização** .
    
2. Na guia **perfil da organização** , escolha **blocos personalizados do inicializador de aplicativos**.
  
3. Selecione **Adicionar um bloco personalizado**. 
  
4. Insira o **Nome do bloco** para o novo bloco. O nome será exibido no bloco. 
    
5. Insira uma **URL do site** para o bloco. Este é o local onde você deseja que seus usuários sigam quando selecionarem o bloco no inicializador de aplicativos. Use HTTPS na URL.<br/>Dica: se você estiver criando um bloco para um site do SharePoint, navegue até esse site, copie a URL e cole-o aqui. A URL do site de equipe padrão tem a seguinte aparência:`https://<company_name>.sharepoint.com` 
  
6. Insira uma **URL da imagem** para o bloco. A imagem é exibida na página Meus Aplicativos e no inicializador de aplicativos.<br/>Dica: a imagem deve ser 60x60 pixels e estar disponível para todos em sua organização sem exigir autenticação.

7. Insira uma **Descrição** para o bloco. Você verá isso quando selecionar o bloco na página meus aplicativos e selecionar detalhes do **aplicativo**. 
  
8. Selecione **salvar alterações** para criar o bloco personalizado. 
    
Agora, o bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos para todas as pessoas. 
  
## <a name="promote-the-tile-to-app-launcher"></a>Promover o bloco para o inicializador de aplicativos

1. Selecione o ícone do inicializador de aplicativos e selecione **todos os aplicativos**. 
    
2. Localize o novo bloco para o seu aplicativo, selecione as reticências e escolha **fixar no iniciador**.
  
    > [!NOTE]
    > Se você não vir o bloco personalizado criado na etapa anterior, verifique se tem uma caixa de correio do Exchange Online atribuída e se você entrou em sua caixa de correio pelo menos uma vez. Estas etapas são necessárias para blocos personalizados no Microsoft 365. 
  
> [!IMPORTANT]
> Você e seus usuários devem realizar essas etapas para promover os blocos personalizados na página Meus Aplicativos para o inicializador de aplicativos. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. No centro de administração, vá para a **Settings**  >  **Org Settings**  >  guia**perfil da organização** configurações da org Settings </a> .
    
2. Na página **perfil da organização** , ao lado de **Adicionar blocos personalizados para sua organização**, selecione **Editar**.

3. Atualize o **Nome do bloco**, a **URL**, a **Descrição** ou a **URL da imagem** do bloco personalizado (consulte a [Adicionar um bloco personalizado ao inicializador de aplicativos](#add-a-custom-tile-to-the-app-launcher)).
    
4. Selecione **Atualizar** \> **Fechar**. 
    
Para excluir um bloco personalizado, da janela **blocos personalizados** , selecione o bloco, selecione **remover**  >  **exclusão**de bloco. 
  
## <a name="whats-next"></a>O que vem a seguir?

Além de adicionar blocos ao inicializador de aplicativos, você pode adicionar blocos de inicializador de aplicativos à barra de navegação ([saiba mais](https://support.office.com/article/personalize-your-office-365-experience-eb34a21b-52fa-4fbf-a8d5-146132242985)). Para personalizar a aparência do Microsoft 365 para corresponder à marca da sua organização, consulte [Customize The Microsoft 365 Theme](../setup/customize-your-organization-theme.md).
  

