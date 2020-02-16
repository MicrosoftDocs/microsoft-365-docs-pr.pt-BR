---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como validar as configurações de proteção do Microsoft 365 Business app em dispositivos Windows 10.
ms.openlocfilehash: 577921f7f33eafbbe652dcf825a145d89f1ff556
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42057154"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Validar as configurações de proteção de aplicativo em computadores Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Verifique se os usuários não podem copiar dados da empresa para arquivos pessoais em dispositivos corporativos

Depois de [configurar políticas de proteção do aplicativo](protection-settings-for-windows-10-devices.md), pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários. Se **você ativou a** opção **impedir que os usuários copiem dados da empresa para arquivos pessoais e forçá-los a salvar arquivos de trabalho na configuração do onedrive for Business** para dispositivos pertencentes à empresa, você pode verificar isso no dispositivo do usuário depois que ele se conectou ao Azure AD e entrar. 
  
 **Verificar configurações de conexão**
  
1. After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Na página **gerenciado pelo** \<nome\> do locatário, você pode ver as **informações de conexão** que incluem um **endereço de servidor de gerenciamento** como aquele mostrado na figura a seguir. 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Verificar se você não pode colar dados da empresa em um aplicativo não gerenciado**
  
1. Abra o Outlook 2016 que foi instalado por Microsoft 365 Business.
    
2. Abra um email e copie algum conteúdo dele.
    
    Abra o Bloco de Notas e tente colar conteúdo.
    
    Você receberá um erro afirmando que o aplicativo não pode acessar o conteúdo.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    No entanto, você pode colar o mesmo conteúdo no Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Verifique se os usuários não podem copiar dados da empresa para arquivos pessoais em dispositivos pessoais

 **Verificar configurações de conexão**
  
1. Em seu dispositivo pessoal do Windows 10 no qual você está conectado como um usuário local, vá **até configurações do Windows**e clique ou toque em **contas** \> de **trabalho ou escola do Access**.
    
2. Em **Acessar trabalho ou escola**, escolha **Conectar**.
    
3. Insira sua credencial do Microsoft 365 Business na **caixa de diálogo Configurar uma conta corporativa ou de estudante** \> **Entrar**.
    
4. Na página **Acessar trabalho ou escola**, escolha a **Conta corporativa ou de estudante** e escolha **Informações**.
    
    ![Clique ou toque em informações na caixa de diálogo de conta corporativa ou de estudante.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Na página **trabalho ou escola do Access** , você pode ver as **informações de conexão** que incluem um **endereço de servidor de gerenciamento** como aquele mostrado na figura a seguir e inclui as palavras *WIP* e *Mam* no. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Verificar se você não pode colar dados da empresa em um aplicativo não gerenciado**
  
1. Abra o Outlook 2016, adicione sua conta do Microsoft 365 Business, se necessário, e entre com suas credenciais do Microsoft 365 Business.
    
2. Abra um email e copie algum conteúdo dele.
    
    Abra o Bloco de Notas e tente colar conteúdo.
    
    Você receberá um erro informando que o aplicativo não pode acessar o conteúdo.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    No entanto, você pode colar o mesmo conteúdo no Word 2016.
    

