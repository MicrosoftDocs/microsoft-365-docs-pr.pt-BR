---
title: Configurar o Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Descubra as etapas de configuração para o Microsoft 365 Business, incluindo a adição de um domínio e usuários, a configuração de políticas de segurança e muito mais.
ms.openlocfilehash: 99994b6f1e9e817b4858aeafe4ce3ceaaf4c3c37
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633869"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Configurar o Microsoft 365 Business no assistente de instalação

Assista a este vídeo para obter uma visão geral da instalação do Microsoft 365 Business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-users-and-set-up-policies"></a>Adicionar o domínio, os usuários e as políticas de configuração

[![Rótulo para informar que o centro de administração está mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Ao comprar o Microsoft 365 Business, você tem a opção de usar um domínio de sua propriedade ou comprar um durante a [inscrição](sign-up.md).

- Se você comprou um novo domínio ao se inscrever, seu domínio está configurado e você pode mover para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Adicionar seu domínio para personalizar a entrada

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando suas credenciais de administrador global. 

2. Escolha **ir para a configuração** para iniciar o assistente.

    ![Selecione ir para a configuração.](../media/gotosetupinadmincenter.png)

3. Na página **instalar aplicativos do Office** , você pode, opcionalmente, instalar os aplicativos no seu próprio computador.
    
4. Na etapa **Adicionar domínio** , insira o nome de domínio que você deseja usar (como contoso.com).

    > [!IMPORTANT]
    > Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** . Em vez disso, vá para [Adicionar usuários](#add-users-and-assign-licenses) .

    ![Captura de tela da página personalizar sua sessão de entrada.](../media/adddomain.png)

    
4. Siga as etapas no Assistente para [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifica se você é o proprietário do domínio. Se você souber seu host de domínio, consulte também as [instruções específicas do host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se o seu provedor de hospedagem for o GoDaddy ou outro host habilitado com o [domínio Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e você será solicitado a entrar novamente e permitir que a Microsoft autentique em seu nome.

    ![Na página Confirmar acesso do GoDaddy, selecione autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Adicionar usuários e atribuir licenças

Você pode adicionar usuários no assistente, mas você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração. Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Adicionar usuários no assistente

Todos os usuários adicionados ao assistente recebem automaticamente uma licença de negócios do Microsoft 365.

![Captura de tela da página Adicionar novos usuários no assistente](../media/addnewuserspage.png)

1. Se sua assinatura do Microsoft 365 Business tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você terá uma opção para atribuir licenças a eles agora. Adicione licenças para eles também.

2. Depois de adicionar os usuários, você também terá uma opção de compartilhar credenciais com os novos usuários que você adicionou. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.

### <a name="connect-your-domain"></a>Conectar seu domínio

> [!NOTE]
> Se você optar por usar o domínio. onmicrosoft ou usado o Azure AD Connect para configurar usuários, esta etapa não será exibida.
  
Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.
  
1. O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador. Caso contrário, [altere os nameservers para configurar o Office 365 com qualquer registrador de domínio](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Se você tiver registros DNS existentes, por exemplo, um site existente, mas seu host DNS estiver habilitado para [conexão de domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), escolha **adicionar registros para mim**. Na página **escolha seus serviços online** , aceite todos os padrões e escolha **Avançar**e escolha **autorizar** na página do seu host DNS.
    - Se você tiver registros DNS existentes com outros hosts DNS (não habilitados para conexão de domínio), será necessário gerenciar seus próprios registros DNS para garantir que os serviços existentes permaneçam conectados. Confira [noções básicas sobre domínios](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.

        ![Página ativar registros.](../media/activaterecords.png)

2. Siga as etapas do assistente e email e outros serviços serão configurados para você.

### <a name="protect-your-organization"></a>Proteger sua organização 

As políticas configuradas no assistente são aplicadas automaticamente a um [grupo de segurança](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) chamado *todos os usuários*. Você também pode criar grupos adicionais para atribuir políticas ao centro de administração.

1. Com o **aumento da proteção contra ameaças avançadas da Cyber**, é recomendável que você aceite os padrões para permitir a [proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) examinar arquivos e links em aplicativos do Office.

    ![Captura de tela da página aumentar proteção.](../media/increasetreatprotection.png)


2. Na página **evitar vazamentos de dados confidenciais** , aceite os padrões para ativar a prevenção de perda de dados (DLP) do Office 365 para rastrear dados confidenciais em aplicativos do Office e impedir o compartilhamento acidental desses fora da sua organização.

3. Na página **proteger dados no Office para celular** , deixe gerenciamento de aplicativo móvel, expanda as configurações e revise-as e selecione **criar política de gerenciamento de aplicativo móvel**.

    ![Captura de tela de proteger dados no Office para páginas móveis.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Proteger computadores com Windows 10

Na barra de navegação esquerda, selecione **configuração** e, em **entrada e segurança**, escolha **proteger seus computadores com Windows 10**. Escolha **Exibir** para começar. Confira [proteger seus computadores com Windows 10](secure-win-10-pcs.md) para obter instruções completas.

## <a name="deploy-office-365-client-apps"></a>Implantar aplicativos cliente do Office 365

Se você optar por instalar automaticamente aplicativos do Office durante a instalação, os aplicativos serão instalados nos dispositivos Windows 10 depois que eles entrarem no Azure AD de seus dispositivos Windows, usando suas credenciais de trabalho.

Para instalar o Office no Mobile iOS ou dispositivos Android, consulte [set up Mobile Devices for Microsoft 365 business users](set-up-mobile-devices.md).

Você também pode instalar o Office individualmente. Confira [instalar o Office em um PC ou Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) para obter instruções.

## <a name="see-also"></a>Confira também

[Vídeos de treinamento do Microsoft 365 Business ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
