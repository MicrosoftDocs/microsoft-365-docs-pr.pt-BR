---
title: Configurar o Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Saiba como configurar o Microsoft 365 Business.
ms.openlocfilehash: e635b828609fc47cd8b92bb179a25bcc43cb0a1a
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660710"
---
# <a name="set-up-microsoft-365-business"></a>Configurar o Microsoft 365 Business

Antes de começar, veja obter os detalhes de inscrição do [Microsoft 365 Business](get-microsoft-365-business.md) .

Assista a um [pequeno vídeo sobre como configurar o Microsoft 365 Business](https://support.office.com/article/38003e30-9d10-44cf-b596-f1b5f662bfa1) usando o assistente de configuração e quando você não tem um Active Directory local
  

## <a name="overview"></a>Visão Geral

A maioria das etapas de configuração pode ser feita no assistente de configuração, mas as outras opções também são listadas.

1. [Adicionar seu domínio](#add-your-domain-to-personalize-sign-in) (se você comprou seu domínio durante a [inscrição](sign-up.md), esta etapa já foi feita.)
2. Adicionar usuários. Você pode fazer isso de uma das três maneiras:
    - No [Assistente de configuração](#add-users-in-the-wizard).
    - Use a sincronização de diretórios para [Adicionar usuários usando o Azure ad Connect](#add-users-by-using-azure-ad-connect) se você tiver um Active Directory local.
    - Você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração.
3. Configurar políticas de segurança e configurar dispositivos. Você pode fazer isso de uma das três maneiras:
    - No [Assistente de configuração](#set-up-policies-in-the-wizard).  
    - No [centro de administração](#modify-or-add-policies-in-the-admin-center).
    - No [centro de administração do Intune](https://docs.microsoft.com/intune/what-is-device-management).
4. Configurar e gerenciar dispositivos Windows 10.

    Quando você ingressa em um dispositivo WIndows 10 no Azure AD, todas as políticas são aplicadas a ela.
    - Configurar as configurações de dispositivo do Windows 10 no [Assistente de configuração](#set-up-policies-in-the-wizard).
    - Ingressar em um [novo dispositivo Windows 10](set-up-windows-devices.md#for-a-brand-new-or-newly-upgraded-windows-10-pro-device) no Azure AD.
    - Ingresse um [dispositivo existente do Windows 10](set-up-windows-devices.md#for-a-device-already-set-up-and-running-windows-10-pro) para o Azure AD.
1. Instale o Office 365 Business.
    - Você pode instalar automaticamente o Office nos dispositivos Windows usando o [Assistente de configuração](#set-up-policies-in-the-wizard).
    - Instale automaticamente o [Office](auto-install-or-uninstall-office.md) a partir do centro de administração.
    - Permitir que os usuários [instalem aplicativos do Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows e dispositivos.
     
1. Configurar segurança adicional.
    - O assistente de configuração adiciona políticas para proteger seus dispositivos, mas você também pode aproveitar os recursos de [segurança adicionais](#additional-security-settings) para ajudar a proteger seus dados, contas e emails. 

## <a name="add-your-domain-users-and-set-up-policies"></a>Adicionar seu domínio, usuários e configurar políticas

![Faixa que aponta para https://aka.ms/aboutM365preview.](media/m365admincenterchanging.png)

Ao comprar o Microsoft 365 Business, você tem a opção de usar um domínio de sua propriedade ou comprar um durante a [inscrição](sign-up.md).

- Se você comprou um novo domínio ao se inscrever, seu domínio está configurado e você pode mover para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Adicionar seu domínio para personalizar a entrada

1. Entre no [centro de administração do Microsoft 365](https://admin.microsoft.com) usando suas credenciais de administrador global. 

2. Escolha **Adicionar um domínio** para iniciar o assistente.

    ![Selecione Adicionar um domínio.](media/addadomainadmincenter.png)
    
3. No assistente, digite o nome de domínio que você deseja usar (como contoso.com).


    ![Captura de tela da página personalizar sua sessão de entrada.](media/personalizesignin.png)

    
4. Siga as etapas no Assistente para [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifica se você é o proprietário do domínio. Se você souber seu host de domínio, consulte também as [instruções específicas do host](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se o seu provedor de hospedagem for o GoDaddy, o processo será fácil e você será solicitado a entrar e permitir que a Microsoft autentique em seu nome:

    ![Na página Confirmar acesso do GoDaddy, selecione autorizar.](media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Adicionar usuários e atribuir licenças

Você pode adicionar usuários no assistente, mas você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração. Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Adicionar usuários no assistente

Todos os usuários adicionados ao assistente recebem automaticamente uma licença de negócios do Microsoft 365.
Se você tiver um controlador de domínio local e estiver usando o Active Directory, consulte [How to DDD Users by using Azure ad Connect](#add-users-by-using-azure-ad-connect).

![Captura de tela da página Adicionar novos usuários no assistente](media/addnewuserspage.png)

1. Se sua assinatura do Microsoft 365 Business tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você verá uma opção para atribuir licenças a eles agora. Adicione licenças para eles também.

3. Depois de adicionar os usuários, você também terá uma opção para compartilhar credenciais com os novos usuários que você adicionou. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.

4. Ignore a migração de mensagens de email e escolha **Avançar** na página **Migrar mensagens de email**. 

    Se você estiver migrando de outro provedor de email e deseja copiar os dados mais tarde, poderá [migrar emails e contatos para o Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).

#### <a name="add-users-by-using-azure-ad-connect"></a>Adicionar usuários usando o Azure AD Connect

 Se você tiver um controlador de domínio local com o Active Directory, sincronize seus usuários com o Microsoft 365 Business usando o [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express). Conclua isso antes de iniciar o assistente de configuração. Você pode baixá-lo no centro de administração:

- Vá para usuários **ativos**do **usuário** \> , selecione as reticências na parte superior da página e, em seguida, selecione **sincronização de diretório** para baixar o Azure ad Connect.

    ![Na página usuários ativos, selecione reticências > Directory snchronization.](media/setupdirsync.png)

    > [!IMPORTANT]
    > Se você criar usuários dessa forma, ainda terá que atribuir licenças a eles no centro de administração.

##### <a name="continue-to-access-domain-joined-apps-and-devices"></a>Continuar a acessar aplicativos e dispositivos associados ao domínio

Se você quiser continuar a acessar os aplicativos e dispositivos associados ao domínio, leia os seguintes artigos para duas maneiras diferentes de habilitar esse:
  
- [Habilitar os dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business](manage-windows-devices.md)
    - Essa é a maneira recomendada.

- [Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business](access-resources.md)

### <a name="connect-your-domain"></a>Conectar seu domínio

> [!NOTE]
> Se você optar por usar o domínio. onmicrosoft ou usado o Azure AD Connect para configurar usuários, esta etapa não será exibida.
  
Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.
  
1. O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador. Caso contrário, [altere os nameservers para configurar o Office 365 com qualquer registrador de domínio](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2). 

    - Se você tiver registros DNS existentes, por exemplo, um site existente, será necessário gerenciar seus próprios registros DNS para garantir que os serviços existentes permaneçam conectados. Confira [noções básicas sobre domínios](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.

        ![Conectar sua página de domínio com gerenciar meus próprios registros DNS.](media/connectyourdomainpage.png)

2. Siga as etapas do assistente e email e outros serviços serão configurados para você.

### <a name="set-up-security-policies-and-device-configurations"></a>Configurar políticas de segurança e configurações de dispositivos 

Essas políticas se aplicam a todos os usuários aos quais você fornece uma licença ou a um grupo de usuários se você decidir atribuir políticas diferentes a um conjunto de usuários.

#### <a name="set-up-policies-in-the-wizard"></a>Configurar políticas no assistente

As políticas configuradas no assistente são aplicadas automaticamente a um [grupo de segurança](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) chamado *todos os usuários*.

1. Na lista **proteger seus arquivos de trabalho em dispositivos móveis** , a opção **proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** será selecionada por padrão. Você pode ativar a opção **gerenciar como os usuários acessam arquivos do Office em dispositivos móveis**e isso é recomendável.

    ![Captura de tela da página proteger arquivos de trabalho em dispositivos móveis.](media/protectworkfilesondevices.png)

     - Se você expandir **proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados**, os [valores padrão](protect-work-files-on-lost-or-stolen-device.md) serão previamente selecionados:

        ![Captura de tela dos valores padrão para proteção de arquivos em dispositivos perdidos.](media/protectworkfilesondevicesdefault.png)

    - Se você selecionar **gerenciar como os usuários acessarão arquivos do Office em dispositivos móveis** e o expandirem, os [valores padrão](manage-user-access-on-mobile-devices.md) serão exibidos. Recomendamos aceitar os valores padrão durante a instalação para criar políticas de aplicativo para Android, iOS e Windows 10 que se apliquem a todos os usuários. Você pode criar mais políticas após concluir a instalação.

        ![Captura de tela das configurações de proteção para arquivos do Office em dispositivos móveis.](media/useraccessonmobile.png)

2. A última etapa para proteger dados e dispositivos permite que você configure políticas para proteger dispositivos Windows 10. Essas configurações são aplicadas automaticamente quando o Windows 10 de um usuário se conecta à sua organização. Você pode expandir **dispositivos Windows 10 seguros** para ver e modificar os [valores padrão](secure-windows-10-devices.md).
3. Você também pode optar por [instalar automaticamente o Office](install-office-on-windows-10-during-setup.md) em dispositivos Windows 10.

    ![Captura de tela da página definir configuração de dispositivo do Windows 10.](media/setwin10config.png)

#### <a name="modify-or-add-policies-in-the-admin-center"></a>Modificar ou adicionar políticas no centro de administração

Consulte [Manage Microsoft 365 Business](manage.md) para links para tópicos sobre como exibir e modificar políticas de proteção de dispositivos e aplicativos, e como remover dados de ou redefinir dispositivos de usuário.

## <a name="deploy-and-manage-windows-10"></a>Implantar e gerenciar o Windows 10
Confira [configurar dispositivos Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) para se conectar manualmente ao Azure AD, seja durante a configuração de novos computadores ou alterando o perfil de logon para computadores existentes. 

### <a name="use-autopilot-to-set-up-new-devices"></a>Usar o piloto automático para configurar novos dispositivos

Você pode usar o [Windows AutoPilot](add-autopilot-devices-and-profile.md) para configurar automaticamente **novos** dispositivos Windows 10 para um usuário, mas pode ser mais fácil obter um [parceiro](https://www.microsoft.com/solution-providers/search) que pode fazer isso para você. Você também pode ir para a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) e solicitar que um especialista em tecnologia de nuvem configure novos dispositivos que você comprou para você.

### <a name="access-on-premises-resources"></a>Acessar recursos locais

Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10 e ainda manter o acesso a recursos locais que exigem autenticação local. Siga as etapas em [habilitar dispositivos do Windows 10 associados ao domínio para serem gerenciados pela Microsoft 365 Business](manage-windows-devices.md) para configurar isso. Este é o método preferencial e os dispositivos nesse estado são chamados de dispositivos do Azure AD associados híbridos.

Se sua empresa tiver um Active Directory local que contenha alguns recursos locais (como compartilhamento de arquivos e impressoras), você poderá dar aos seus dispositivos associados ao AD do Azure acesso a esses recursos seguindo as etapas aqui: [acessar recursos locais de um Dispositivo ingressado no AD do Azure no Microsoft 365 Business](access-resources.md).

## <a name="deploy-office-365-client-apps"></a>Implantar aplicativos cliente do Office 365

Se você optar por instalar automaticamente os aplicativos do Office no durante a configuração, os aplicativos serão instalados nos dispositivos Windows 10 depois que eles entrarem no Azure AD de seus dispositivos Windows com suas credenciais de trabalho.
Para instalar o Office no Mobile iOS ou dispositivos Android, consulte [set up Mobile Devices for Microsoft 365 business users](set-up-mobile-devices.md).

Você também pode instalar o Office individualmente. Confira [instalar o Office em um PC ou Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc471665) para obter instruções.

## <a name="additional-security-settings"></a>Configurações de segurança adicionais

Além da configuração de segurança e conformidade no assistente de instalação, você também pode definir as seguintes configurações adicionais:
  
- **Proteção contra malware de email**
- **Anexos seguros de proteção avançada contra ameaças (ATP)**
- **Links seguros da ATP**
- **Anti-phishing da APT**
- **Arquivamento do Exchange Online**
- **Prevenção de perda de dados (DLP)**
- **Proteção de informações do Azure** (Plano 1)
- **Disponibilidade do portal do Intune**

Para começar, veja [Configurar políticas avançadas de segurança](set-up-advanced-security.md).

Confira também [as 10 maneiras principais de proteger o Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para um mapa de práticas recomendadas de segurança.