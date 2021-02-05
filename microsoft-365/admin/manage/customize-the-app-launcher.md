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
ms.openlocfilehash: 96d059b252b63e48e20edb29861cf8233e220e34
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114184"
---
# <a name="add-custom-tiles-to-the-app-launcher"></a>Adicionar blocos personalizados ao inicializador de aplicativos

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

No Microsoft 365, você pode obter seus emails, calendários, documentos e aplicativos de forma rápida e fácil usando o iniciador de aplicativos ([saiba mais](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a)). Esses são aplicativos que você pode obter com o Microsoft 365, bem como aplicativos personalizados que você adiciona do [SharePoint Store](https://support.microsoft.com/office/dd98e50e-d3db-4ecb-9bb7-82b189822d43) ou [do Azure AD.](https://msdn.microsoft.com/office/office365/howto/connect-your-app-to-o365-app-launcher)
  
Você pode adicionar blocos personalizados ao inicializador de aplicativos, que apontem para sites do SharePoint, sites externos, aplicativos herdados, e muito mais. O bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos, mas você pode fixá-lo junto aos aplicativos da guia **Página Inicial** e orientar os usuários a fazerem o mesmo. Isso facilita a localização de sites, aplicativos e recursos importantes para realizar o trabalho. No exemplo a seguir, o bloco personalizado Portal da Contoso serve para acessar o site de intranet do SharePoint da organização. 
  
![Iniciador de aplicativos](../../media/7acc06cc-ac7a-4c6e-8ea7-81570a5bdbab.png)
  
## <a name="add-a-custom-tile-to-the-app-launcher"></a>Adicionar um bloco personalizado ao inicializador de aplicativos

1. Entre no centro de administração como Administrador Global, acesse Configurações da Organização e escolha a  >  guia Perfil **da** Organização.
    
2. Na guia **Perfil da organização,** escolha **blocos personalizados do iniciador de aplicativos.**
  
3. Selecione **Add a custom tile**. 
  
4. Insira o **Nome do bloco** para o novo bloco. O nome será exibido no bloco. 
    
5. Insira uma **URL do site** para o tile. Esse é o local para onde você deseja que os usuários acessem quando eles selecionarem o tile no iniciador de aplicativos. Use HTTPS na URL.<br/>DICA: se você estiver criando um tile para um site do SharePoint, navegue até esse site, copie a URL e copie-a aqui. A URL do seu site de equipe padrão tem esta aparência: `https://<company_name>.sharepoint.com` 
  
6. Insira uma **URL da imagem** para o lado. A imagem é exibida na página Meus Aplicativos e no inicializador de aplicativos.<br/>DICA: a imagem deve ter 60 x 60 pixels e estar disponível para todos em sua organização sem a necessidade de autenticação.

7. Insira uma **Descrição** para o bloco. Você verá isso quando selecionar o tile na página Meus aplicativos e selecionar detalhes **do aplicativo.** 
  
8. Selecione **Salvar alterações** para criar oile personalizado. 
    
Agora, o bloco personalizado é exibido na guia **Tudo** do inicializador de aplicativos para todas as pessoas. 
  
## <a name="promote-the-tile-to-app-launcher"></a>Promover o tile para o Iniciador de Aplicativos

1. Selecione o ícone do iniciador de aplicativos e selecione todos **os aplicativos.** 
    
2. Localize o novo tile para seu aplicativo, selecione as recepses e escolha **Fixar no iniciador.**
  
    > [!NOTE]
    > Se você não vir o bloco personalizado criado na etapa anterior, verifique se tem uma caixa de correio do Exchange Online atribuída e se você entrou em sua caixa de correio pelo menos uma vez. Essas etapas são necessárias para blocos personalizados no Microsoft 365. 
  
> [!IMPORTANT]
> Você e seus usuários devem realizar essas etapas para promover os blocos personalizados na página Meus Aplicativos para o inicializador de aplicativos. 
  
## <a name="edit-or-delete-a-custom-tile"></a>Edit or delete a custom tile

1. No centro de administração, vá para a **guia Configurações** da Organização  >  **de Configurações**  >  **da** </a> Organização.
    
2. Na página **Perfil da** organização, ao lado de   **Adicionar blocos personalizados para sua organização,** selecione **Editar**.

3. Atualize o **Nome do bloco**, a **URL**, a **Descrição** ou a **URL da imagem** do bloco personalizado (consulte a [Adicionar um bloco personalizado ao inicializador de aplicativos](#add-a-custom-tile-to-the-app-launcher)).
    
4. Selecione **Fechar** \> **Atualização.** 
    
Para excluir um bloco personalizado, na janela **Blocos** personalizados, selecione o bloco, selecione **Remover exclusão de**  >  **bloco.** 
  
## <a name="whats-next"></a>O que vem a seguir?

Além de adicionar blocos ao iniciador de aplicativos, você pode adicionar blocos do iniciador de aplicativos à barra de navegação ([saiba mais](https://support.microsoft.com/office/eb34a21b-52fa-4fbf-a8d5-146132242985)). Para personalizar a aparência do Microsoft 365 para corresponder à marca da sua organização, confira Personalizar o tema [do Microsoft 365.](../setup/customize-your-organization-theme.md)
  
