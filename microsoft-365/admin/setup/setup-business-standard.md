---
title: Configurar o Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
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
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
- BEA160
description: Saiba como configurar sua assinatura do Microsoft 365 Business Standard.
ms.openlocfilehash: b42dd0779c708410614ea2ab0d134aa3dcf0c7e9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778920"
---
# <a name="set-up-microsoft-business-standard"></a>Configurar o Microsoft Business Standard
  
 *Estas etapas são para empresas e [entidades sem fins lucrativos](https://go.microsoft.com/fwlink/p/?LinkId=627221) que têm o **[Plano padrão de negócios da Microsoft 365 Business Standard.](https://go.microsoft.com/fwlink/p/?LinkId=627220)***

Assista a um vídeo curto sobre como configurar o Microsoft 365 Business Standard (antes conhecido como Office 365 Business Premium).<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/913be1ad-bae1-40c0-9ded-15bb477b828b]

Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="add-your-domain-to-personalize-sign-in"></a>Adicione seu domínio para personalizar o login

Ao comprar o Microsoft 365 Business Standard, você tem a opção de usar um domínio que possui ou comprar um durante a inscrição.

- Se você comprou um novo domínio quando se inscreveu, seu domínio está configurado e você pode passar para [Adicionar usuários e atribuir licenças](#add-users-and-assign-licenses).

1. Acesse [Centro de administração do Microsoft 365](https://admin.microsoft.com) usando as credenciais de administrador global. 

2. Clique em **Ir para a Configuração** pra iniciar o assistente.

3. Na página **Instalar aplicativos do Office**, você pode, opcionalmente, instalar os aplicativos no seu próprio computador.
    
4. Na etapa **Adicionar domínio**, digite o nome do domínio que você deseja usar (como contoso.com).

    > [!IMPORTANT]
    > Se você comprou um domínio durante a inscrição, não verá a etapa **Adicionar um domínio** aqui. Em vez disso, acesse [Adicionar usuários](#add-users-and-assign-licenses).

    
4. Siga as etapas no assistente para [Criar registros DNS em qualquer provedor de hospedagem DNS do Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) que verifique se você é o proprietário do domínio. Se você conhece o host do seu domínio, também consulte as [instruções específicas do organizador](https://docs.microsoft.com/office365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions).

    Se o seu provedor de hospedagem for GoDaddy ou outro host habilitado com [conexão ao domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), o processo será fácil e será pedido que você entre automaticamente e deixe a Microsoft autenticar em seu nome.

    ![Na página Confirmar Acesso do GoDaddy, selecione Autorizar.](../../media/godaddyauth.png)

## <a name="add-users-and-assign-licenses"></a>Adicionar usuários e atribuir licenças

Você pode adicionar usuários no assistente, mas também pode [adicionar usuários posteriormente](../add-users/add-users.md) no centro de administração. Além disso, se você tiver um controlador de domínio local, poderá adicionar usuários com [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-express).

## <a name="add-users-in-the-wizard"></a>Adicionar usuários ao assistente

Todos os usuários que você adicionar no assistente recebem automaticamente uma licença do Microsoft 365 Business Standard.

1. Se sua assinatura do Microsoft 365 Business Standard tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você terá a opção de atribuir-lhes licenças agora. Também adicione licenças para eles.

2. Depois de adicionar os usuários, você também terá a opção de compartilhar credenciais com os novos usuários adicionados. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.

## <a name="connect-your-domain"></a>Conectar seu domínio

> [!NOTE]
> Se você optou por usar o domínio .onmicrosoft ou usou o Azure AD Connect para configurar usuários, não verá esta etapa.
  
Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.
  
1. O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador. Caso contrário, [Alterar os servidores de nomes para configurar o Office 365 com qualquer registrador de domínio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar). 

    - Se você possui registros DNS existentes, por exemplo, um site existente, mas seu organizador DNS está ativado para [conexão com o domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/domain-connect), clique em **Adicionar registros para mim**. Na página **Escolha seus serviços on-line**, aceite todos os padrões, clique em **Avançar**e clique em **Autorizar** na página do organizador DNS.
    - Se você possui registros DNS existentes com outros organizadores DNS (não habilitados para conexão ao domínio), convém gerenciar seus próprios registros DNS para garantir que os serviços existentes fiquem conectados. Consulte [noções básicas de domínio](https://docs.microsoft.com/office365/admin/get-help-with-domains/dns-basics) para obter mais informações.

2. Siga as etapas no assistente e o e-mail e outros serviços serão configurados para você.

    Quando o processo de inscrição for concluído, você será direcionado para o centro de administração, onde acompanhará um assistente para instalar os aplicativos do Office, adicionar seu domínio, adicionar usuários e atribuir licenças. Depois de concluir a configuração inicial, você poderá usar a página de **configuração** no centro de administração para continuar a instalar e configurar os serviços que vêm com as assinaturas.

    Para obter mais informações sobre o assistente de configuração e a página de **instalação** do centro de administração, confira [Diferença entre o assistente de configuração e a página de configuração](o365-setup-wizard-and-setup-page.md).

## <a name="finish-setting-up"></a>Concluir a configuração

### <a name="set-up-outlook-for-email"></a>Configurar o Outlook para e-mail

1. No menu Iniciar do Windows, procure Outlook e selecione-o.

    (Se estiver usando um Mac, abra o Outlook na barra de ferramentas ou localize-o usando o Finder).

    Se você tiver acabado de instalar o Outlook, na página inicial, selecione **Avançar**.

2. Escolha **Arquivo** \>**Informações **\>** Adicionar Conta**.

3. Digite seu endereço de e-mail do Microsoft e selecione **conectar**.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/9fe86884-8a83-42cc-bca9-61a12e6dad31?autoplay=false]
  
Veja mais em [Configurar o Outlook para email](https://support.microsoft.com/office/f5bf0cd1-e1f3-4b0d-a022-ecab17efe86f).
  
### <a name="import-email"></a>Importar e-mail

Se você estava usando o Outlook com outra conta de email, poderá importar seus emails, calendário e contatos antigos para sua nova conta da Microsoft.
  
1. **Exportar seus emails antigos**

    In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export**.

    Selecione **Exportar para um Arquivo** e siga as etapas para exportar o Arquivo de Dados do Outlook (.pst) e quaisquer subpastas.

2. **Importar seus emails antigos**

    In Outlook, choose **File** \> **Open &amp; Export** \> **Import/Export** again.

    Desta vez, selecione **Importar de outro programa ou arquivo** e siga as etapas para importar o arquivo de backup criado ao exportar os emails antigos.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/40f7df36-9e24-44e5-8791-e9ed0dd8fd21?autoplay=false]
  
Veja mais em [Importar emails com o Outlook](https://support.microsoft.com/office/6a3771d4-4c1d-4a25-92a6-0b8e476335de).

Você também pode usar o centro de administração do Exchange para importar e-mails de todos os usuários. Para obter mais informações, consulte [migrar várias contas de e-mail](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).
  
### <a name="use-a-public-website"></a>Usar um site público

Microsoft 365 doesn't include a public website for your business. If you want to set one up, consider using a Microsoft partner, such as GoDaddy or WIX.
  
1. No Centro de Administração, vá para **Recursos** e selecione**Site público**.

2. Selecione **Saiba mais** em uma das opções e depois inscreva-se com um parceiro de site e use as ferramentas dele para configurar e projetar seu site.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/4839abc6-9323-4cbf-a79d-2907235f9ebb]

Veja mais em [Usar um site público](https://support.microsoft.com/office/3325d50e-d131-403c-a278-7f3296fe33a9).