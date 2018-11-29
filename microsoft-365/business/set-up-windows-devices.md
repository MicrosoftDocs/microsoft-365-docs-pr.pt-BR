---
title: Configurar dispositivos Windows para usuários do Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: 'Saiba como configurar os dispositivos do Windows executando Windows 10 Pro para usuários do Microsoft 365 Business. '
ms.openlocfilehash: 482199b175c568bfae420619aa02024303894789
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864892"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-users"></a>Configurar dispositivos Windows para usuários do Microsoft 365 Business

## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar dispositivos Windows para usuários do Microsoft 365 Business, verifique se todos os dispositivos Windows estão executando o Windows 10 Pro, versão 1703 (Atualização para Criadores). O Windows 10 Pro é um pré-requisito para a implantação do Windows 10 Business, que é um conjunto de serviços de nuvem e recursos de gerenciamento de dispositivos que complementam o Windows 10 Pro e permitem o gerenciamento centralizado e os controles de segurança do Microsoft 365 Business.
  
Se você tiver dispositivos Windows executando o Windows 7 Pro, Windows 8 Pro ou Windows 8.1 Pro, sua assinatura do Microsoft Business 365 dará direito a uma atualização do Windows 10.
  
Para obter mais informações sobre como atualizar dispositivos Windows para a Atualização do Windows 10 Pro para Criadores, siga as etapas deste tópico: [Atualize dispositivos Windows para a Atualização do Windows Pro para Criadores](upgrade-to-windows-pro-creators-update.md).
  
Confira [Verifique se o dispositivo está atualizado para o Windows 10 Business](set-up-windows-devices.md#bkmk_verifywin10) para verificar se você tem a atualização ou para garantir que a atualização funcionou. 
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Ingressar dispositivos Windows 10 ao Azure AD de sua organização

Depois que todos os dispositivos Windows de sua organização terem sido atualizados para a Atualização do Windows 10 Pro para Criadores ou já estiverem executando a Atualização do Windows 10 Pro para Criadores, você poderá ingressar esses dispositivos em sua organização do Azure Active Directory. Depois que os dispositivos são ingressados, eles serão automaticamente atualizados para o Windows 10 Business, que faz parte de sua assinatura do Microsoft 365 Business.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>No caso de um dispositivo Windows 10 Pro novo ou atualizado recentemente

No caso de um novo dispositivo que executa a Atualização do Windows 10 Pro para Criadores ou um dispositivo que foi atualizado para a Atualização do Windows 10 Pro para Criadores, mas não passou pela configuração do dispositivo Windows 10, siga estas etapas.
  
1. Execute a configuração do dispositivo Windows 10 até chegar à página **Como você deseja configurar?**. 
    
    ![On the How would you like to set up page, choose Set up for an organization](media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Aqui, escolha **Configuração para uma organização** e, em seguida, insira seu nome de usuário e senha do Microsoft 365 Business. 
    
3. Conclua a configuração do dispositivo Windows 10.
    
   Quando terminar, o usuário será conectado ao Azure AD de sua organização. Para garantir a conexão, confira [Verifique se o dispositivo está conectado ao Azure AD](set-up-windows-devices.md#bkmk_verifyaad). 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>Para um dispositivo já configurado executando o Windows 10 Pro

 **Conecte os usuários ao Azure AD:**
  
1. No PC Windows do usuário, que esteja executando o Windows 10 Pro, versão 1703 (Atualização do Criador) (veja os [pré-requisitos](pre-requisites-for-data-protection.md)), clique no logotipo do Windows e, em seguida, no ícone de Configurações.
  
   ![In the Start menu, click Windows Settings icon](media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. Em **Configurações**, vá para **Contas**.
  
   ![In Windows Settings, go to Accounts](media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. Na página **Suas informações**, clique em **Acessar trabalho ou escola** \> **Conectar**.
  
   ![Choose Connect under Access work or school](media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. Na caixa de diálogo **Configurar uma conta corporativa ou de estudante**, em **Ações alternativas**, escolha **Ingressar este dispositivo no Azure Active Directory**.
  
   ![Click Join this device to Azure Active Directory](media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. Na página de **login**, insira sua conta corporativa ou de estudante \> **Avançar**.
  
   Na página **Insira sua senha**, insira a senha \> **Entrar**.
  
   ![Enter your work or school email on the Let's get you signed in page](media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. Sobre o * * certificar-se de que sua organização se trata * * página, verifique se as informações estão corretas e clique em **ingressar**.
  
   Na página **Tudo pronto!**, clique em **Concluído**.
  
   ![On the Make sure this is your organization screen, click Join](media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Se você carregou arquivos no OneDrive for Business, sincronize-os novamente. Se você usou uma ferramenta de terceiros para migrar o perfil e arquivos, sincronize-os também com o novo perfil.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Verifique se o dispositivo está conectado ao Azure AD

Para verificar seu status de sincronização, na página **Acessar trabalho ou escola**, em **Configurações**, clique na área **Conectado a** _ \<organization name\> _ para expor os botões **Informações** e **Desconectar**. Clique em **Informações** para obter o status da sincronização. 
  
Na página de status de sincronização, clique em Sincronização para obter as últimas políticas de gerenciamento de dispositivo móvel no PC.
  
Para começar a usar a conta do Microsoft 365 Business, vá para o botão **Iniciar** do Windows, clique com botão direito na imagem da conta atual e, em seguida, clique em **Trocar conta**. Entre com o email e a senha da sua organização.
  
![Click Info button to view synchronization status](media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-device-is-upgraded-to-windows-10-business"></a>Verifique se o dispositivo está atualizado para o Windows 10 Business

Verifique se seu Azure AD ingressado em dispositivos Windows 10 foram atualizados para o Windows 10 Business como parte de sua assinatura do Microsoft 365 Business.
  
1. Vá para **Configurações** \> **Sistema** \> **Sobre**.
    
2. Confirme se a opção **Edição** exibe **Windows 10 Business**.
    
    ![Verify that Windows edition is Windows 10 Business.](media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Próximas etapas

Para configurar seus dispositivos móveis, confira [Configurar dispositivos móveis para usuários do Microsoft 365 Business](set-up-mobile-devices.md). Para definir políticas de proteção de dispositivos ou proteção de aplicativos, confira [Gerenciar o Microsoft 365 Business](manage.md).
  
