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
description: Saiba como configurar o Microsoft 365 Business executando quatro etapas.
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283866"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>Configurar o Microsoft 365 Business usando o assistente de configuração

Siga as etapas 1-4 abaixo.
  
### <a name="set-up-microsoft-365-business"></a>Configurar o Microsoft 365 Business

Assista a um vídeo sobre como configurar o Microsoft 365 Business quando você não tem um Active Directory local:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
As etapas de configuração incluem informações para configurações que incluem o Active Directory local. Se você quiser continuar a acessar dispositivos que ingressaram no domínio, leia os seguintes artigos para ter duas maneiras diferentes de habilitar esse recurso e conclua as etapas antes de executar o assistente de configuração:
  
- [Habilitar os dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business](manage-windows-devices.md)
    
    -Esta é a maneira recomendada.
    
- [Acessar recursos locais de um dispositivo associado ao Azure AD no Microsoft 365 Business](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>Etapa 1: personalizar a entrada

1. Acesse o [Microsoft 365 Business](https://portal.microsoft.com) usando suas credenciais de administrador global. Escolha o bloco **Administrador** para ir para o centro de administração. 
    
2. Escolha **Iniciar a instalação** (dependendo do seu estado, você poderá ver **Continuar instalação**) no centro de administração para iniciar o assistente. 
    
3. Insira o nome do domínio que você deseja usar (como contoso.com).
    
    Digite seu domínio, mesmo que você o tenha verificado enquanto usava o Azure AD Connect, por exemplo. As duas etapas a seguir não se aplicam a você se você usou o Azure AD Connect para verificar seu domínio.
    
4. Siga as etapas no Assistente para [criar registros DNS em qualquer provedor de Hospedagem de DNS para o Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) que verifica se você é o proprietário do domínio. 
    
    Você pode exibir um vídeo de exemplo do [vídeo: instalar o Office 365 no novo centro de administração](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Observe que este vídeo não inclui as etapas de proteção de dados do Microsoft 365 Business.
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>Etapa 2: adicionar usuários e atribuir licenças

1. Você pode adicionar usuários aqui ou [adicionar usuários posteriormente](add-users-m365b.md) no centro de administração. 
    
    Os usuários que você adiciona automaticamente recebem uma licença do Microsoft 365 Business.
    
2. Se sua assinatura do Microsoft 365 Business tiver usuários existentes (por exemplo, se você usou o Azure AD Connect), você verá uma opção para atribuir licenças a eles agora. Adicione licenças para eles também.
    
3. Você também terá uma opção para compartilhar as credenciais com os novos usuários adicionados. Você pode optar por imprimi-las, enviá-las por email ou baixá-las.
    
4. Ignore a migração de mensagens de email e escolha **Avançar** na página **Migrar mensagens de email**. 
    
    Se você estiver migrando de outro provedor de email e deseja copiar os dados mais tarde, poderá [migrar emails e contatos para o Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>Etapa 3: conectar seu domínio

> [!NOTE]
> Se você optar por usar o domínio. onmicrosoft ou usado o Azure AD Connect, você não verá esta etapa. 
  
Para configurar serviços, você deve atualizar alguns registros no registrador de domínios ou no host DNS.
  
1. O assistente de configuração normalmente detecta o registrador e proporciona um link para as instruções passo a passo para atualizar seus registros NS no site do registrador. Caso contrário, [altere os nameservers para configurar o Office 365 com qualquer registrador de domínio](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).
    
2. O email e outros serviços serão configurados para você
    
### <a name="step-4-manage-devices-and-work-files"></a>Etapa 4: gerenciar dispositivos e arquivos de trabalho

1. Na página **Proteger arquivos de trabalho em dispositivos móveis**, defina as configurações **Proteger arquivos de trabalho quando dispositivos forem perdidos ou roubados** e **Gerenciar como os usuários acessam arquivos do Office em dispositivos móveis** como **Ativada**. Você também pode acessar cada subconfiguração clicando nas divisas ao lado de cada configuração.
  
  Todos os arquivos de trabalho de seus usuários licenciados estão agora protegidos em dispositivos iOS e Android, assim que eles instalam os [aplicativos do Office](set-up-mobile-devices.md) (e autenticam com suas credenciais de negócios do Microsoft 365). 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. Na página **definir configuração de dispositivo do Windows 10** , defina a configuração **proteger dispositivos Windows 10** como **ativado**.
  
   Você também pode acessar cada subconfiguração clicando na divisa ao lado dela.
  
3. Defina a configuração **Instalar o Office em dispositivos Windows 10** como **Sim** se todos os seus usuários tiverem computadores Windows 10 e não houver instalações do Office ou do Office Clique para Executar. Se esse não for o caso, defina essa opção como **Não**. Você pode [instalar o Office automaticamente](auto-install-or-uninstall-office.md) no centro de administração após preparar os computadores dos usuários. Para obter instruções, consulte [preparar para a instalação do cliente do Office](prepare-for-office-client-deployment.md).
  
    Os arquivos de trabalho de usuários licenciados em dispositivos Windows 10 serão projetadas assim que eles [ingressarem em seu dispositivo Windows 10](set-up-windows-devices.md) para um domínio do Microsoft 365 Business Azure ad ou [instalar o Windows 10 em um novo computador](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) enquanto participam simultaneamente da Microsoft 365 Domínio comercial do Azure AD. 
  
4. Clique em **Avançar** e a instalação foi concluída. 
  
    Envie-nos comentários nesta etapa para nos ajudar a melhorar a experiência.
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>Configurações de segurança adicionais

Além da configuração de segurança e conformidade no assistente de instalação, você também pode definir as seguintes configurações adicionais:
  
- Configurar a proteção contra anexos não seguros. **Proteção avançada contra ameaças** (ATP) identifica conteúdo mal-intencionado e, em seguida, bloqueia a entrega de anexos não seguros, ajudando a protegê-lo contra esquemas de phishing e infecções de ransomware. Para ativar a proteção de anexos, confira [Configurar políticas de anexos seguros ATP do Office 365](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).
    
- Proteger seu ambiente quando os usuários clicarem em links mal-intencionados. A ATP examina os links em email no momento em que um usuário clica neles. Se um link não for seguro, o usuário será avisado para não visitar o site ou informando que o site foi bloqueado. Isso ajuda a proteger contra esquemas de phishing. [Configure as políticas de links seguros de ATP do office 365](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) ou [Configure as políticas de links seguros do Office 365 ATP](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
- Você pode preservar todo o conteúdo da caixa de correio, incluindo itens excluídos, colocando a caixa de correio de um usuário em **retenção de litígio**. Para obter instruções, consulte 
- [Configurar a retenção de email com o arquivamento do Exchange Online](security-features.md#set-up-email-retention-with-exchange-online-archiving).
    
- Configurar políticas de **retenção**personalizadas, por exemplo, para preservar um período específico de tempo ou excluir o conteúdo permanentemente no final do período de retenção. Você pode habilitar políticas de retenção personalizadas no centro de conformidade e títulos, acessar a **retenção**de **governança** \> de dados e seguir as etapas no assistente. Para saber mais, confira [visão geral das políticas de retenção](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
    
## <a name="next-steps"></a>Próximas etapas

Para os usuários que têm licenças, a próxima etapa será configurar dispositivos.<br/> Confira [Configurar dispositivos Windows para usuários do Microsoft 365 Business](set-up-windows-devices.md) e [Configurar dispositivos móveis para usuários do Microsoft 365 Business](set-up-mobile-devices.md). <br/>Confira [Gerenciar o Microsoft 365 Business](manage.md) para links de tópicos sobre como configurar políticas de proteção de dispositivos e aplicativos e como remover dados de dispositivos de usuários. 
  


