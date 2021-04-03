---
title: Configurar dispositivos Windows para usuários do Microsoft 365 Business Premium
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Saiba como configurar dispositivos Windows executando o Windows 10 Pro para usuários do Microsoft 365 Business Premium, habilitando controles de segurança e gerenciamento centralizados.
ms.openlocfilehash: 9c9ffe5bd74d9e9877a87309757c481576ee89d2
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578118"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Configurar dispositivos Windows para usuários do Microsoft 365 Business Premium

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Pré-requisitos para configurar dispositivos Windows para usuários do Microsoft 365 Business Premium

Antes de configurar dispositivos Windows para usuários do Microsoft 365 Business Premium, certifique-se de que todos os dispositivos Windows estão executando o Windows 10 Pro, versão 1703 (Atualização de Criadores). O Windows 10 Pro é um pré-requisito para implantar o Windows 10 Business, que é um conjunto de serviços de nuvem e recursos de gerenciamento de dispositivos que complementam o Windows 10 Pro e permitem o gerenciamento centralizado e os controles de segurança do Microsoft 365 Business Premium.
  
Se você tiver dispositivos Windows executando o Windows 7 Pro, Windows 8 Pro ou Windows 8.1 Pro, sua assinatura do Microsoft 365 Business Premium lhe dará direito a uma atualização do Windows 10.
  
Para obter mais informações sobre como atualizar dispositivos Windows para a Atualização do Windows 10 Pro para Criadores, siga as etapas deste tópico: [Atualize dispositivos Windows para a Atualização do Windows Pro para Criadores](upgrade-to-windows-pro-creators-update.md).
  
Consulte [Verify the device is connected to Azure AD](#verify-the-device-is-connected-to-azure-ad) to verify you have the upgrade, or to make sure the upgrade worked.

Assista a um breve vídeo sobre como conectar o Windows ao Microsoft 365.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Se você achou este vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades para o Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Ingressar dispositivos Windows 10 ao Azure AD de sua organização

Quando todos os dispositivos Windows em sua organização foram atualizados para o Windows 10 Pro Creators Update ou já estão executando o Windows 10 Pro Creators Update, você pode ingressar esses dispositivos no Azure Active Directory da sua organização. Depois que os dispositivos são ingressados, eles serão atualizados automaticamente para o Windows 10 Business, que faz parte da sua assinatura do Microsoft 365 Business Premium.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>No caso de um dispositivo Windows 10 Pro novo ou atualizado recentemente

No caso de um novo dispositivo que executa a Atualização do Windows 10 Pro para Criadores ou um dispositivo que foi atualizado para a Atualização do Windows 10 Pro para Criadores, mas não passou pela configuração do dispositivo Windows 10, siga estas etapas.
  
1. Execute a configuração do dispositivo Windows 10 até chegar à página **Como você deseja configurar?**. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Aqui, escolha **Configurar para uma organização** e insira seu nome de usuário e senha para o Microsoft 365 Business Premium. 
    
3. Conclua a configuração do dispositivo Windows 10.
    
   Quando terminar, o usuário será conectado ao Azure AD de sua organização. Para garantir a conexão, confira [Verifique se o dispositivo está conectado ao Azure AD](#verify-the-device-is-connected-to-azure-ad). 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>Para um dispositivo já configurado executando o Windows 10 Pro

 **Conecte os usuários ao Azure AD:**
  
1. No PC Windows do usuário, que esteja executando o Windows 10 Pro, versão 1703 (Atualização do Criador) (veja os [pré-requisitos](pre-requisites-for-data-protection.md)), clique no logotipo do Windows e, em seguida, no ícone de Configurações.
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. Em **Configurações**, vá para **Contas**.
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. Na página **Suas informações**, clique em **Acessar trabalho ou escola** \> **Conectar**.
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. Na caixa de diálogo **Configurar uma conta corporativa ou de estudante**, em **Ações alternativas**, escolha **Ingressar este dispositivo no Azure Active Directory**.
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. Na página de **login**, insira sua conta corporativa ou de estudante \> **Avançar**.
  
   Na página **Insira sua senha**, insira a senha \> **Entrar**.
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. Na página **Certifique-se de que essa é a sua organização,** verifique se as informações estão corretas e escolha **Ingressar**.
  
   No **you're all set!** page, chosse **Done**.
  
   ![Na tela Certifique-se de que essa é a sua organização, escolha Ingressar](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Se você carregou arquivos no OneDrive for Business, sincronize-os novamente. Se você usou uma ferramenta de terceiros para migrar perfis e arquivos, sincronize-os também com o novo perfil.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Verifique se o dispositivo está conectado ao Azure AD

Para verificar seu status de sincronização, na página Trabalho ou Escola do **Access** em Configurações, selecione a área Conectado a **_** _ para expor os botões \<organization name\> **Informações** e **Desconectar.** Escolha **Informações** para obter seu status de sincronização. 
  
Na página **Status da sincronização,** escolha **Sincronizar** para obter as políticas de gerenciamento de dispositivos móveis mais recentes no computador.
  
Para começar a usar a conta do Microsoft 365 Business Premium, vá para o botão **Iniciar** do Windows, clique com o botão direito do mouse na imagem da sua conta atual e alternar **conta**. Entre com o email e a senha da sua organização.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>Verifique se o computador foi atualizado para o Windows 10 Business

Verifique se seus dispositivos do Azure AD ingressados no Windows 10 são atualizados para o Windows 10 Business como parte da sua assinatura do Microsoft 365 Business Premium.
  
1. Vá para **Configurações** \> **Sistema** \> **Sobre**.
    
2. Confirme se a opção **Edição** exibe **Windows 10 Business**.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Próximas etapas

Para configurar seus dispositivos móveis, consulte Configurar dispositivos móveis para usuários do [Microsoft 365 Business Premium](set-up-mobile-devices.md), Para definir políticas de proteção de dispositivos ou proteção de aplicativos, consulte Manage Microsoft [365 for business](manage.md).
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Para obter mais informações sobre como configurar e usar o Microsoft 365 Business Premium

[Vídeos de treinamento do Microsoft 365 Business ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
