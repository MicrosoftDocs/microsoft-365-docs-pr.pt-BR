---
title: Configurar o Microsoft 365 Business
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Saiba como configurar o Microsoft 365 Business.
ms.openlocfilehash: d33839693001f36fbb56541775015f739300b043
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288486"
---
# <a name="set-up-microsoft-365-business-in-the-setup-wizard"></a>Configurar o Microsoft 365 Business no assistente de instalação

## <a name="add-your-domain-users-and-set-up-policies"></a>Adicionar o domínio, os usuários e as políticas de configuração

[![Rótulo para permitir que o centro de administração esteja mudando e você pode encontrar mais detalhes em aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Ao comprar o Microsoft 365 Business, você tem a opção de usar um domínio de sua propriedade ou comprar um durante a [inscrição](sign-up.md).

- Se você comprou um novo domínio ao se inscrever, seu domínio está configurado e você pode mover para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Adicionar seu domínio para personalizar a entrada

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando suas credenciais de administrador global. 

2. Escolha **Adicionar um domínio** ou **Adicionar usuários** para iniciar o assistente.
    > [!IMPORTANT]
    > Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** . Em vez disso, vá para [Adicionar usuários](#add-users-and-assign-licenses) .

    ![Selecione Adicionar um domínio.](media/addadomainadmincenter.png)
    
3. No assistente, digite o nome de domínio que você deseja usar (como contoso.com).


    ![Captura de tela da página personalizar sua sessão de entrada.](media/personalizesignin.png)

    
4. Siga as etapas no Assistente para [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifica se você é o proprietário do domínio. Se você souber seu host de domínio, consulte também as [instruções específicas do host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se o seu provedor de hospedagem for GoDaddy ou outro host habilitado com o [domínio Connect](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e você será solicitado a entrar novamente e permitir que a Microsoft autentique em seu nome:

    ![Na página Confirmar acesso do GoDaddy, selecione autorizar.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Adicionar usuários e atribuir licenças

Você pode adicionar usuários no assistente, mas você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração. Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Adicionar usuários no assistente

Todos os usuários adicionados ao assistente recebem automaticamente uma licença de negócios do Microsoft 365.

![Captura de tela da página Adicionar novos usuários no assistente](media/addnewuserspage.png)

1. Se sua assinatura do Microsoft 365 Business tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você terá uma opção para atribuir licenças a eles agora. Adicione licenças para eles também.

3. Depois de adicionar os usuários, você também terá uma opção para compartilhar credenciais com os novos usuários que você adicionou. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.

4. Ignore a migração de mensagens de email e escolha **Avançar** na página **Migrar mensagens de email**. 

    Se você estiver migrando de outro provedor de email e deseja copiar os dados mais tarde, poderá [migrar emails e contatos para o Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).


### <a name="connect-your-domain"></a>Conectar seu domínio

> [!NOTE]
> Se você optar por usar o domínio. onmicrosoft ou usado o Azure AD Connect para configurar usuários, esta etapa não será exibida.
  
Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.
  
1. O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador. Caso contrário, [altere os nameservers para configurar o Office 365 com qualquer registrador de domínio](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Se você tiver registros DNS existentes, por exemplo, um site existente, mas seu host DNS estiver habilitado para [conexão de domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), escolha **adicionar registros para mim**. 
    - Se você tiver registros DNS existentes com outros hosts DNS (não habilitados para conexão de domínio), será necessário gerenciar seus próprios registros DNS para garantir que os serviços existentes permaneçam conectados. Confira [noções básicas sobre domínios](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.

        ![Conectar sua página de domínio com gerenciar meus próprios registros DNS.](media/connectyourdomainpage.png)

2. Siga as etapas do assistente e email e outros serviços serão configurados para você.

### <a name="set-up-security-policies-and-device-configurations"></a>Configurar políticas de segurança e configurações de dispositivos 

As políticas configuradas no assistente são aplicadas automaticamente a um [grupo de segurança](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) chamado *todos os usuários*. Você também pode criar grupos adicionais para atribuir políticas ao centro de administração.

1. Na lista **proteger seus arquivos de trabalho em dispositivos móveis** , a opção **proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** será selecionada por padrão. Você pode ativar a opção **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis**e isso é recomendável.

    ![Captura de tela da página proteger arquivos de trabalho em dispositivos móveis.](media/protectworkfilesondevices.png)

     - Expanda **proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** para exibir os [valores padrão](protect-work-files-on-lost-or-stolen-device.md):

        ![Captura de tela dos valores padrão para proteção de arquivos em dispositivos perdidos.](media/protectworkfilesondevicesdefault.png)

    - Selecione **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e expanda-o para exibir os [valores padrão](manage-user-access-on-mobile-devices.md). Recomendamos que você aceite os valores padrão durante a instalação para criar políticas de aplicativo para Android, iOS e Windows 10 que se apliquem a todos os usuários. Você pode criar mais políticas após concluir a instalação.

        ![Captura de tela das configurações de proteção para arquivos do Office em dispositivos móveis.](media/useraccessonmobile.png)

2. A última etapa para proteger dados e dispositivos permite que você configure políticas para proteger dispositivos Windows 10. Essas configurações são aplicadas automaticamente quando o Windows 10 de um usuário se conecta à sua organização. Você pode expandir **dispositivos Windows 10 seguros** para ver e modificar os [valores padrão](secure-windows-10-devices.md).
3. Você também pode optar por [instalar automaticamente o Office](install-office-on-windows-10-during-setup.md) em dispositivos Windows 10.

    ![Captura de tela da página definir configuração de dispositivo do Windows 10.](media/setwin10config.png)



## <a name="deploy-office-365-client-apps"></a>Implantar aplicativos cliente do Office 365

Se você optar por instalar automaticamente os aplicativos do Office no durante a configuração, os aplicativos serão instalados nos dispositivos Windows 10 depois que eles entrarem no Azure AD de seus dispositivos Windows com suas credenciais de trabalho.
Para instalar o Office no Mobile iOS ou dispositivos Android, consulte [set up Mobile Devices for Microsoft 365 business users](set-up-mobile-devices.md).

Você também pode instalar o Office individualmente. Confira [instalar o Office em um PC ou Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658) para obter instruções.
