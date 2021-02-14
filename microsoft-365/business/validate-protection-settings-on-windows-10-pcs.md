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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Valide as configurações de proteção de aplicativo do Microsoft 365 Business Premium em dispositivos Windows 10 e verifique se os usuários não podem copiar dados da empresa para arquivos pessoais ou aplicativos não gerenciados.
ms.openlocfilehash: 589d2fc25cc1425a775523595881660cc03e152e
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403381"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Validar as configurações de proteção de aplicativo em computadores Windows 10

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Verifique se os usuários não podem copiar dados da empresa para arquivos pessoais em dispositivos corporativos

Depois de [configurar políticas de proteção do aplicativo](protection-settings-for-windows-10-devices.md), pode levar algumas horas para que a política entre em vigor nos dispositivos dos usuários. Se você  tiver a opção Impedir que os usuários copiem dados da empresa para arquivos pessoais e forçar-os a salvar arquivos de trabalho na configuração do **OneDrive for Business** para dispositivos de propriedade da empresa, você poderá verificar isso no dispositivo do usuário depois que eles se conectarem ao Azure AD e se conectarem. 
  
 **Verificar configurações de conexão**
  
1. Depois de entrar com as credenciais do Microsoft 365 Business Premium e conectar-se ao Azure AD conforme descrito em Configurar dispositivos Windows para usuários do [Microsoft 365 Business Premium,](set-up-windows-devices.md)vá para o Windows **Settings** Accounts Access no trabalho ou \>  \> **na escola.** Escolha **Conectado ao \<tenant name\> Azure AD** e, em seguida, escolha **Informações.**
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Na página **Gerenciado por,** você pode ver as informações de conexão que incluem um endereço de servidor de gerenciamento como o \<tenant name\> mostrado na figura a  seguir.  
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Verifique se você não pode colar dados da empresa em um aplicativo não gerenciado**
  
1. Abra o Outlook 2016 que foi instalado pelo Microsoft 365 Business Premium.
    
2. Abra um email e copie algum conteúdo dele.
    
    Abra o Bloco de Notas e tente colar conteúdo.
    
    Você receberá um erro informando que o aplicativo não pode acessar o conteúdo.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    No entanto, você pode colar o mesmo conteúdo no Word 2016.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Verifique se os usuários não podem copiar dados da empresa para arquivos pessoais em dispositivos pessoais

 **Verificar configurações de conexão**
  
1. Em seu dispositivo pessoal do Windows 10 em que você está conectado como um usuário local, vá para Configurações do **Windows** e clique ou toque em **Contas** do Access no trabalho \> **ou na escola.**
    
2. Em **Acessar trabalho ou escola**, escolha **Conectar**.
    
3. Insira sua credencial do Microsoft 365 Business Premium na caixa de diálogo Configurar uma conta comercial ou **de** \> **estudante.**
    
4. Na página **Acessar trabalho ou escola**, escolha a **Conta corporativa ou de estudante** e escolha **Informações**.
    
    ![Clique ou toque em Informações na caixa de diálogo Conta de trabalho ou de estudante.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Na página de trabalho ou escola  do **Access,** você pode ver as informações de conexão que incluem um endereço de servidor de gerenciamento como o mostrado na figura **a** seguir e inclui as palavras *wip* e *mam* dentro. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Verifique se você não pode colar dados da empresa em um aplicativo não gerenciado**
  
1. Abra o Outlook 2016 e adicione sua conta do Microsoft 365 Business Premium, se necessário, e entre com suas credenciais do Microsoft 365 Business Premium.
    
2. Abra um email e copie algum conteúdo dele.
    
    Abra o Bloco de Notas e tente colar conteúdo.
    
    Você receberá um erro informando que o aplicativo não pode acessar o conteúdo.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    No entanto, você pode colar o mesmo conteúdo no Word 2016.
    

