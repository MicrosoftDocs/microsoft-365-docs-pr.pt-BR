---
title: Validar as configurações de proteção de aplicativo em computadores Windows 10
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Saiba como validar configurações de proteção do aplicativo Microsoft 365 Business em dispositivos Windows 10.
ms.openlocfilehash: f00dd380103ad9498d77b0e8814bace3de168df4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865086"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Validar as configurações de proteção de aplicativo em computadores Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Verifique se os usuários não podem copiar dados da empresa para arquivos pessoais em dispositivos corporativos

Depois de [configurar políticas de proteção do aplicativo](protection-settings-for-windows-10-devices.md), pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários. Se você **ativou** a configuração **Impedir os usuários de copiar dados da empresa para arquivos pessoais e forçá-los a salvar arquivos de trabalho no OneDrive for Business** para dispositivos de propriedade da empresa, poderá verificar isso nos dispositivos dos usuários quando eles se conectarem e entrarem no Microsoft Azure AD. 
  
 **Verificar configurações de conexão**
  
1. Depois que você entrar com credenciais do Microsoft 365 Business e se conectar ao AD do Windows Azure, conforme descrito em [Configurar os dispositivos do Windows para usuários comerciais de 365 da Microsoft](set-up-windows-devices.md), vá para **Configurações do Windows** \> **contas** \> **acesso trabalho ou escola **. Escolha **conectado à \<nome do locatário\> Azure AD**e escolha **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Na página **Gerenciado por** \<nome do locatário\>, você pode ver as **Informações de conexão**, que incluem um **Endereço de Servidor de Gerenciamento**, como mostrado na figura a seguir. 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Verifique se você não pode colar dados da empresa em um aplicativo não gerenciado**
  
1. Abra o Outlook 2016 que foi instalado por Microsoft 365 Business.
    
2. Abra um email e copie algum conteúdo dele.
    
    Abra o Bloco de Notas e tente colar conteúdo.
    
    Você receberá um erro indicando que o aplicativo não pode acessar conteúdo.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    No entanto, você pode colar o mesmo conteúdo no Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Verifique se os usuários não podem copiar dados da empresa para arquivos pessoais em dispositivos pessoais

 **Verificar configurações de conexão**
  
1. Em seu dispositivo Windows 10 pessoal em que você está conectado como um usuário local, acesse **Configurações do Windows** e clique ou toque em **Contas** \> **Acessar trabalho ou escola**.
    
2. Em **Acessar trabalho ou escola**, escolha **Conectar**.
    
3. Insira sua credencial do Microsoft 365 Business na **caixa de diálogo Configurar uma conta corporativa ou de estudante** \> **Entrar**.
    
4. Na página **Acessar trabalho ou escola**, escolha a **Conta corporativa ou de estudante** e escolha **Informações**.
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Na página **Acessar trabalho ou escola**, você pode ver as **Informações de Conexão**, que incluem um **Endereço de Servidor de Gerenciamento** igual ao mostrado na figura a seguir e incluem as palavras  *wip*  e  *mam*  . 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Verifique se você não pode colar dados da empresa em um aplicativo não gerenciado**
  
1. Abra o Outlook 2016, adicione sua conta do Microsoft 365 Business, se necessário, e entre com suas credenciais do Microsoft 365 Business.
    
2. Abra um email e copie algum conteúdo dele.
    
    Abra o Bloco de Notas e tente colar conteúdo.
    
    Você receberá um erro indicando que o aplicativo não pode acessar conteúdo.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    No entanto, você pode colar o mesmo conteúdo no Word 2016.
    

