---
title: Configurar o Microsoft 365 Business Premium
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Descubra as etapas de configuração do Microsoft 365 Business Premium, incluindo adicionar um domínio e usuários, configurar políticas de segurança e muito mais.
ms.openlocfilehash: e7ebe179c67077dc71ae4873b0711d0e810c701a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044721"
---
# <a name="set-up-microsoft-365-business-premium-in-the-setup-wizard"></a>Configurar o Microsoft 365 Business Premium no assistente de configuração

Assista a este vídeo para ter uma visão geral da configuração do Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

## <a name="add-your-domain-users-and-set-up-policies"></a>Adicionar seu domínio, usuários e configurar políticas

Ao comprar o Microsoft 365 Business Premium, você tem a opção de usar um domínio de sua propriedade ou comprar um durante a [assinatura.](sign-up.md)

- Se você comprou um novo domínio quando se inscreveu, seu domínio está configurado e você pode passar para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).

### <a name="add-your-domain-to-personalize-sign-in"></a>Adicione seu domínio para personalizar o login

1. Acesse [Centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de administrador global. 

2. Clique em **Ir para a Configuração** pra iniciar o assistente.

    ![Selecione Ir para a instalação.](../media/gotosetupinadmincenter.png)

3. Na página **Instalar aplicativos do Office**, você pode, opcionalmente, instalar os aplicativos no seu próprio computador.
    
4. Na etapa **Adicionar domínio**, digite o nome do domínio que você deseja usar (como contoso.com).

    > [!IMPORTANT]
    > Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** aqui. Em vez disso, acesse [Adicionar usuários](#add-users-and-assign-licenses).

    ![Screenshot of the Personalize your sign-in page.](../media/adddomain.png)

    
4. Siga as etapas no assistente para criar registros DNS em qualquer provedor de hospedagem DNS para [o Microsoft 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifica se você é o próprio domínio. Se você conhece o host do seu domínio, também consulte as [instruções específicas do organizador](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se o seu provedor de hospedagem for GoDaddy ou outro host habilitado com [conexão ao domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e será pedido que você entre automaticamente e deixe a Microsoft autenticar em seu nome.

    ![Na página Confirmar Acesso do GoDaddy, selecione Autorizar.](../media/godaddyauth.png)

### <a name="add-users-and-assign-licenses"></a>Adicionar usuários e atribuir licenças

Você pode adicionar usuários no assistente, mas também pode [adicionar usuários posteriormente](add-users-m365b.md) no centro de administração. Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

#### <a name="add-users-in-the-wizard"></a>Adicionar usuários ao assistente

Todos os usuários que você adicionar no assistente receberão automaticamente uma licença do Microsoft 365 Business Premium.

![Captura de tela da página Adicionar novos usuários no assistente](../media/addnewuserspage.png)

1. Se sua assinatura do Microsoft 365 Business Premium tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você terá a opção de atribuir licenças a eles agora. Também adicione licenças para eles.

2. Depois de adicionar os usuários, você também terá a opção de compartilhar credenciais com os novos usuários adicionados. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.

### <a name="connect-your-domain"></a>Conectar seu domínio

> [!NOTE]
> Se você optou por usar o domínio .onmicrosoft ou usou o Azure AD Connect para configurar usuários, não verá esta etapa.
  
Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.
  
1. O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador. Se isso não tiver, [altere os nameservers para configurar o Microsoft 365 com qualquer registrador de domínios.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) 

    - Se você possui registros DNS existentes, por exemplo, um site existente, mas seu organizador DNS está ativado para [conexão com o domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), clique em **Adicionar registros para mim**. Na página **Escolha seus serviços on-line**, aceite todos os padrões, clique em **Avançar** e clique em **Autorizar** na página do organizador DNS.
    - Se você possui registros DNS existentes com outros organizadores DNS (não habilitados para conexão ao domínio), convém gerenciar seus próprios registros DNS para garantir que os serviços existentes fiquem conectados. Consulte [noções básicas de domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.

        ![Ativar página de registros.](../media/activaterecords.png)

2. Siga as etapas no assistente e o e-mail e outros serviços serão configurados para você.

### <a name="protect-your-organization"></a>Proteger sua organização 

As políticas configuradas no assistente são aplicadas automaticamente a um grupo [de Segurança](https://docs.microsoft.com/office365/admin/create-groups/compare-groups#security-groups) chamado *Todos os Usuários.* Você também pode criar grupos adicionais para atribuir políticas no centro de administração.

1. Em Aumentar **a** proteção contra ameaças cibernéticas avançadas, é recomendável que você aceite os padrões para permitir que a Proteção Avançada contra Ameaças do [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) digitalizar arquivos e links em aplicativos do Office.

    ![Captura de tela da página Aumentar proteção.](../media/increasetreatprotection.png)


2. Na página Evitar vazamentos de dados confidenciais, aceite os padrões para ativar a Prevenção contra Perda de Dados (DLP) do Office 365 para controlar dados confidenciais em **aplicativos** do Office e evitar o compartilhamento acidental desses dados fora da sua organização.

3. Na página **Proteger dados** no Office para dispositivos móveis, mantenha o gerenciamento de aplicativos móveis, expanda as configurações e revise-as e selecione Criar política de gerenciamento de aplicativo **móvel.**

    ![Captura de tela da página Proteger dados no Office para dispositivos móveis.](../media/protectdatainmobile.png)


## <a name="secure-windows-10-pcs"></a>Proteger computadores com Windows 10

Na janela de acesso à esquerda, selecione **Instalação** e, em **Entrar e** segurança, escolha Proteger seus computadores com **Windows 10.** Escolha **Exibir** para começar. Consulte [proteger seus computadores Windows 10 para](secure-win-10-pcs.md) obter instruções completas.

## <a name="deploy-office-365-client-apps"></a>Implantar aplicativos cliente do Office 365

Se você optar por instalar automaticamente os aplicativos do Office durante a instalação, os aplicativos serão instalados nos dispositivos Windows 10 depois que os usuários entrarem no Azure AD a partir de seus dispositivos Windows, usando suas credenciais de trabalho.

Para instalar o Office em dispositivos móveis iOS ou Android, confira Configurar dispositivos móveis para usuários do [Microsoft 365 Business Premium.](set-up-mobile-devices.md)

Você também pode instalar o Office individualmente. Consulte [instalar o Office em um PC ou Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) para obter instruções.

## <a name="see-also"></a>Confira também

[Vídeos de treinamento do Microsoft 365 Business ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
