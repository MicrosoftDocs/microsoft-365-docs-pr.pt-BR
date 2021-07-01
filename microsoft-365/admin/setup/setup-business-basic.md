---
title: Configurar o Microsoft 365 Business Basic
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
- TRN_SMB
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Saiba como configurar sua assinatura do Microsoft 365 Business Basic.
ms.openlocfilehash: d0ac9835be25377496893d62076a5cdc426f3b9e
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227734"
---
# <a name="set-up-microsoft-365-business-basic"></a>Configurar o Microsoft 365 Business Basic

## <a name="watch-set-up-microsoft-365-business-basic"></a>Assista: configurar o Microsoft 365 Business Basic

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vk3W]

Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](../../business-video/index.yml).

## <a name="add-your-domain-to-personalize-sign-in"></a>Adicione seu domínio para personalizar o login

Ao comprar o Microsoft 365 Business Basic, você tem a opção de usar um domínio que você possui ou comprar um durante a inscrição.

- Se você comprou um novo domínio quando se inscreveu, seu domínio está configurado e você pode passar para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).

 ::: moniker range="o365-worldwide"

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Clique em **Ir para a Configuração** pra iniciar o assistente.
    
3. Na etapa **Adicionar domínio**, digite o nome do domínio que você deseja usar (como contoso.com).

    > [!IMPORTANT]
    > Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** aqui. Vá para [Adicionar usuários](#add-users-and-assign-licenses) em vez disso.

    
4. Siga as etapas no assistente para [Criar registros DNS em qualquer provedor de hospedagem DNS do Office 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifique se você é o proprietário do domínio. Se você souber o seu host de domínio, confira também como [Adicionar um domínio ao Microsoft 365](/microsoft-365/admin/setup/add-domain).

    Se o seu provedor de hospedagem for GoDaddy ou outro host habilitado com [conexão ao domínio](/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e será pedido que você entre automaticamente e deixe a Microsoft autenticar em seu nome.

    ![Na página Confirmar Acesso do GoDaddy, selecione Autorizar.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Adicionar usuários e atribuir licenças

Você pode adicionar usuários no assistente, mas também pode [adicionar usuários posteriormente](../add-users/add-users.md) no centro de administração. Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Adicionar usuários ao assistente

Todos os usuários adicionados ao assistente recebem automaticamente uma licença do Microsoft 365 Business Basic.

1. Se sua assinatura do Microsoft 365 Business Basic tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você terá uma opção para atribuir licenças a eles agora. Adicione licenças para eles também.

2. Depois de adicionar os usuários, você também terá uma opção para compartilhar as credenciais com os novos usuários adicionados. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.

## <a name="connect-your-domain"></a>Conectar seu domínio

> [!NOTE]
> Se você optou por usar o domínio .onmicrosoft ou usou o Azure AD Connect para configurar usuários, não verá esta etapa.
  
Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.
  
1. O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador. Caso contrário, [Alterar os servidores de nomes para configurar o Office 365 com qualquer registrador de domínio](../get-help-with-domains/change-nameservers-at-any-domain-registrar.md). 

    - Se você possui registros DNS existentes, por exemplo, um site existente, mas seu organizador DNS está ativado para [conexão com o domínio](/office365/admin/get-help-with-domains/domain-connect), clique em **Adicionar registros para mim**. Na página **Escolha seus serviços on-line**, aceite todos os padrões, clique em **Avançar** e clique em **Autorizar** na página do organizador DNS.
    - Se você tiver registros DNS existentes com outros hosts DNS (não habilitados para conexão de domínio), você irá desejar gerenciar seus próprios registros DNS para garantir que os serviços existentes fiquem conectados. Veja [domínios básicos](/office365/admin/get-help-with-domains/dns-basics) para mais informações.

2. Siga as etapas no assistente e o e-mail e outros serviços serão configurados para você.

    Quando o processo de inscrição estiver concluído, você será direcionado ao centro de administração, onde poderá adicionar usuários e atribuir licenças. Depois de concluir a configuração inicial, você poderá usar a página de **configuração** no centro de administração para continuar a instalar e configurar os serviços que vêm com as assinaturas.

    Para obter mais informações sobre o assistente de configuração e a página de **instalação** do centro de administração, confira [Diferença entre o assistente de configuração e a página de configuração](o365-setup-wizard-and-setup-page.md).