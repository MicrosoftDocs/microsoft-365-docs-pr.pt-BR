---
title: Configurar o Microsoft 365 Business Premium
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Descubra as etapas de instalação para Microsoft 365 Business Premium, incluindo adicionar um domínio e usuários, configurar políticas de segurança e muito mais.
ms.openlocfilehash: 37607b483686fc12ac6253ae9f693ec86c073c4e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245035"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Configurar Microsoft 365 Business Premium no assistente de configuração

Assista a este vídeo para ver uma visão geral Microsoft 365 Business Premium configuração.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a>Adicionar seu domínio, usuários e configurar políticas

Ao comprar Microsoft 365 Business Premium, você tem a opção de usar um domínio que você possui ou comprar um durante a [assinatura](sign-up.md).

- Se você comprou um novo domínio quando se inscreveu, seu domínio está configurado e você pode passar para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Adicione seu domínio para personalizar o login

1. Acesse [Centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de administrador global. 

2. Clique em **Ir para a Configuração** pra iniciar o assistente.

    ![Selecione Ir para a instalação.](../media/gotosetupinadmincenter.png)

3. Na página **Instalar aplicativos do Office**, você pode, opcionalmente, instalar os aplicativos no seu próprio computador.
    
4. Na etapa **Adicionar domínio**, digite o nome do domínio que você deseja usar (como contoso.com).

    > [!IMPORTANT]
    > Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** aqui. Em vez disso, acesse [Adicionar usuários](#add-users-and-assign-licenses).

    ![Captura de tela da página Personalizar sua assinatura.](../media/adddomain.png)

    
4. Siga as etapas no assistente para Criar [registros DNS](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) em qualquer provedor de hospedagem DNS para Microsoft 365 que verifica se você é o próprio domínio. Se você conhece o host do seu domínio, também consulte as [instruções específicas do organizador](/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se o seu provedor de hospedagem for GoDaddy ou outro host habilitado com [conexão ao domínio](/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e será pedido que você entre automaticamente e deixe a Microsoft autenticar em seu nome.

    ![Na página Confirmar Acesso do GoDaddy, selecione Autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Adicionar usuários e atribuir licenças

Você pode adicionar usuários no assistente, mas também pode [adicionar usuários posteriormente](../admin/add-users/add-users.md) no centro de administração. Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com [Azure AD Connect](/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Adicionar usuários ao assistente

Todos os usuários que você adicionar no assistente receberão automaticamente uma Microsoft 365 Business Premium de usuário.

![Captura de tela da página Adicionar novos usuários no assistente](../media/addnewuserspage.png)

1. Se sua assinatura Microsoft 365 Business Premium tiver usuários existentes (por exemplo, se você usou o Azure AD Conexão), você terá a opção de atribuir licenças a eles agora. Também adicione licenças para eles.

2. Depois de adicionar os usuários, você também terá a opção de compartilhar credenciais com os novos usuários adicionados. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.

### <a name="connect-your-domain"></a>Conectar seu domínio

> [!NOTE]
> Se você optou por usar o domínio .onmicrosoft ou usou o Azure AD Connect para configurar usuários, não verá esta etapa.
  
Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.
  
1. O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador. Caso não seja, [altere os nameservers](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md)para configurar Microsoft 365 com qualquer registrador de domínios. 

    - Se você possui registros DNS existentes, por exemplo, um site existente, mas seu organizador DNS está ativado para [conexão com o domínio](/office365/admin/get-help-with-domains/domain-connect), clique em **Adicionar registros para mim**. Na página **Escolha seus serviços on-line**, aceite todos os padrões, clique em **Avançar** e clique em **Autorizar** na página do organizador DNS.
    - Se você possui registros DNS existentes com outros organizadores DNS (não habilitados para conexão ao domínio), convém gerenciar seus próprios registros DNS para garantir que os serviços existentes fiquem conectados. Consulte [noções básicas de domínio](/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.

        ![Ativar a página de registros.](../media/activaterecords.png)

2. Siga as etapas no assistente e o e-mail e outros serviços serão configurados para você.

### <a name="protect-your-organization"></a>Proteger sua organização 

As políticas configuradas no assistente são aplicadas automaticamente a um grupo [de Segurança](/office365/admin/create-groups/compare-groups#security-groups) chamado *Todos os Usuários.* Você também pode criar grupos adicionais para atribuir políticas no centro de administração.

1. Em Aumentar [a](../security/office-365-security/defender-for-office-365.md) **proteção contra** ameaças cibernéticas avançadas, é recomendável que você aceite os padrões para permitir Office 365 Proteção Avançada contra Ameaças examinar arquivos e links em Office aplicativos.

    ![Captura de tela da página Aumentar proteção.](../media/increasetreatprotection.png)


2. Na página Impedir vazamentos de dados confidenciais, aceite os padrões para ativar Office 365 DLP (Prevenção contra Perda de Dados) para rastrear dados confidenciais em **aplicativos** Office e impedir o compartilhamento acidental desses dados fora da sua organização.

3. Na página **Proteger dados Office** para dispositivos móveis, deixe o gerenciamento de aplicativos móveis, expanda as configurações e revise-os e selecione Criar política de gerenciamento de aplicativo **móvel.**

    ![Captura de tela de proteger dados Office página móvel.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Proteger computadores com Windows 10

À esquerda, selecione  Instalação e, em Logon e **segurança,** escolha Proteger seus computadores **Windows 10 .** Escolha **Exibir** para começar. Consulte [proteger seus computadores Windows 10 para](secure-win-10-pcs.md) obter instruções completas.

## <a name="deploy-office-365-client-apps"></a>Implantar Office 365 aplicativos cliente

Se você optar por instalar automaticamente Office aplicativos durante a instalação, os aplicativos serão instalados nos dispositivos Windows 10 depois que os usuários entrarem no Azure AD a partir de seus dispositivos Windows, usando suas credenciais de trabalho.

Para instalar Office em dispositivos móveis iOS ou Android, consulte Configurar dispositivos móveis [para Microsoft 365 Business Premium usuários](set-up-mobile-devices.md).

Você também pode instalar Office individualmente. Consulte [install Office on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para obter instruções.

## <a name="see-also"></a>Confira também

[Vídeos de treinamento do Microsoft 365 Business ](../business-video/index.yml)
