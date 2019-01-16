---
title: Configurar o Microsoft 365 Business usando o assistente de configuração
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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Saiba como configurar o Microsoft 365 Business ao concluir as quatro etapas.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864685"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>Configurar o Microsoft 365 Business usando o assistente de configuração

Conclua as etapas 1-4 abaixo.
  
### <a name="set-up-microsoft-365-business"></a>Configurar o Microsoft 365 Business

Assista a um vídeo sobre como configurar o Microsoft 365 Business quando não há um Active Directory no local:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
As etapas de configuração incluem informações de configurações que incluem o Active Directory local. Se você deseja continuar a acessar dispositivos associados a um domínio, leia os seguintes artigos para duas de maneira diferente da habilitação que e conclua as etapas antes de executar o Assistente de instalação:
  
- [Permitir que os dispositivos Windows 10 associados a um domínio a ser gerenciado pelo Microsoft 365 Business](manage-windows-devices.md)
    
    -Essa é a maneira recomendada.
    
- [Acesso a recursos de um dispositivo associado ao AD Azure no Microsoft 365 Business local](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>Etapa 1: Personalizar entrar

1. Acesse o [Microsoft 365 Business](https://portal.microsoft.com) usando suas credenciais de administrador global. Escolha o bloco **Administrador** para ir para o centro de administração. 
    
2. Escolha **Iniciar a instalação** (dependendo do seu estado, você poderá ver **Continuar instalação**) no centro de administração para iniciar o assistente. 
    
3. Insira o nome do domínio que você deseja usar (como contoso.com).
    
    Vá em frente e insira seu domínio, mesmo se você verificou durante a utilização de conectar do Azure AD, por exemplo. As duas etapas a seguintes não se aplicam a você se você usou Connect do Azure AD para verificar seu domínio.
    
4. Siga as etapas no Assistente para [criar registros DNS em qualquer provedor de hospedagem de DNS para o Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) verifica que você é proprietário do domínio. 
    
    Você pode exibir um vídeo de exemplo da [vídeo: instalação do Office 365 no Centro de administração do novo](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Observe que este vídeo não inclui as etapas de proteção de dados do Microsoft 365 Business.
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>Etapa 2: Adicionar usuários e atribuir licenças

1. Você pode adicionar usuários aqui ou [adicionar usuários posteriormente](add-users-m365b.md) no centro de administração. 
    
    Os usuários que você adiciona automaticamente recebem uma licença do Microsoft 365 Business.
    
2. Se sua assinatura do Microsoft 365 Business tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você verá uma opção para atribuir licenças a eles agora. Adicione licenças para eles também.
    
3. Você também terá uma opção para compartilhar as credenciais com os novos usuários adicionados. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.
    
4. Ignore a migração de mensagens de email e escolha **Avançar** na página **Migrar mensagens de email**. 
    
    Se você estiver movendo de outro provedor de email e deseja copiar os dados mais tarde, você pode [migrar email e contatos para o Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>Etapa 3: Conectar seu domínio

> [!NOTE]
> Se você optar por usar o domínio .onmicrosoft ou usado Connect do Azure AD, você não verá esta etapa. 
  
Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.
  
1. Normalmente, o Assistente de instalação detecta seu registrador e fornece um link para instruções passo a passo para atualizar seus registros NS no website da registrador. Caso contrário, [nameservers de alteração para configurar o Office 365 com qualquer registrador de domínio](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).
    
2. O email e outros serviços serão configurados para você
    
### <a name="step-4-manage-devices-and-work-files"></a>Etapa 4: Gerenciar dispositivos e arquivos de trabalho

1. Nos **arquivos de trabalho Protect em seus dispositivos móveis** página Definir as configurações de **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** e **proteger arquivos de trabalho quando dispositivos são perdidos ou roubados** para **ativado**. Você também pode acessar cada definição sub-recursos clicando nas divisas ao lado de cada configuração.
  
  Todos os arquivos de trabalho dos usuários licenciados agora estão protegidos em iOS e dispositivos com Android, assim que eles [instalar aplicativos do Office](set-up-mobile-devices.md) (e autenticar com suas credenciais do Microsoft 365 Business). 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. Na página **configuração de dispositivo definir Windows 10** , defina a configuração de **Dispositivos do Windows 10 seguro** para **ativado**.
  
   Você também pode acessar cada definição sub-recursos clicando na divisa ao lado dela.
  
3. Defina a configuração de **Instalar o Office em dispositivos do Windows 10** como **Sim** se todos os usuários tiverem computadores Windows 10, e instala o Office não existente, ou instalações do Office click-to-run. Se isso não for o caso, defina essa opção como **não**. Você pode [instalar o Office automaticamente](auto-install-or-uninstall-office.md) posterior a partir do Centro de administração após ter preparado os computadores do usuário. Para obter instruções, consulte [preparar para instalação de cliente do Office](prepare-for-office-client-deployment.md).
  
    Arquivos de trabalho dos usuários licenciados em dispositivos Windows 10 serão projetados assim que eles [ingressar em seus dispositivos Windows 10](set-up-windows-devices.md) a um domínio do Microsoft 365 Business Azure AD ou a [instalar o Windows 10 em um novo computador](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) ao ingressar simultaneamente o 365 da Microsoft Domínio do Azure AD de negócios. 
  
4. Clique em **Avançar** e a instalação foi concluída. 
  
    Envie-nos comentários nesta etapa para nos ajudar a melhorar a experiência.
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>Configurações de segurança adicionais

Além da segurança e configuração de conformidade no Assistente de instalação, você também pode configurar as seguintes configurações adicionais:
  
- Configure a proteção contra anexos não seguros. **Proteção de ameaça avançada** (ATP) identifica o conteúdo mal-intencionado e, em seguida, bloqueia a entrega de anexos não seguros, ajudando a protegê-lo contra os esquemas de phishing e ransomware infecções. Para ativar a proteção de anexo, consulte [Configurar políticas de anexos do Office 365 ATP seguros](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).
    
- Protege o ambiente quando usuários clicarem em links mal-intencionado. ATP examina links no email no momento em que um usuário clica neles. Se não for um link não seguro, o usuário é advertido não a visitar o site ou informado que o site foi bloqueado. Isso ajuda a proteger contra esquemas de phishing. [Configurar políticas de vínculos do Office 365 ATP seguros](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) ou [Configurar políticas de vínculos do Office 365 ATP seguros](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
- Você pode preservar todo o conteúdo da caixa de correio incluindo itens excluídos colocando-se a caixa de correio inteira do usuário na **retenção de litígio**. Para obter instruções, consulte 
- [Configurar a retenção de email com o arquivamento do Exchange Online](security-features.md#set-up-email-retention-with-exchange-online-archiving).
    
- Configure **políticas de retenção**de personalizada, por exemplo, para preservar por um período específico ou excluir o conteúdo permanentemente no final do período de retenção. Você pode habilitar diretivas de retenção personalizada no Centro de conformidade, vá até a **governança de dados** de títulos e \> **retenção**e, em seguida, siga as etapas no assistente. Para saber mais, consulte [Visão geral das políticas de retenção](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
    
## <a name="next-steps"></a>Próximas etapas

Para os usuários que têm licenças, a próxima etapa será configurar dispositivos.<br/> Confira [Configurar dispositivos Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) e [Configurar dispositivos móveis para usuários do Microsoft 365 Business](set-up-mobile-devices.md). <br/>Confira [Gerenciar o Microsoft 365 Business](manage.md) para links de tópicos sobre como configurar políticas de proteção de dispositivos e aplicativos e como remover dados de dispositivos de usuários. 
  


