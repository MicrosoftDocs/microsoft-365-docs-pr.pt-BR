---
title: Habilitar os dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business
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
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Saiba como habilitar o Microsoft 365 para proteger dispositivos do Windows 10 associados ao AD local.
ms.openlocfilehash: 15804a0bd6cf9d013c5138470aa4a4a7acec57e1
ms.sourcegitcommit: 08c334b754bd6d64375b33d91a972a31f2f309cb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2019
ms.locfileid: "37100432"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Habilitar os dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business

Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10 e ainda manter o acesso a recursos locais que exigem autenticação local.
Para configurar isso, você pode implementar **dispositivos híbridos associados do Azure ad**. Estes são os dispositivos que ingressaram no seu Active Directory local e no Azure Active Directory.

O vídeo a seguir detalha as etapas de como configurar isso para o cenário mais comum que também é detalhado nas etapas a seguir.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. preparar para a sincronização de diretório 

Antes de sincronizar os usuários e computadores do domínio do Active Directory local, examine [preparar a sincronização de diretório para o Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). Em particular:

   - Certifique-se de que não exista duplicatas no diretório para os seguintes atributos: **mail**, **proxyAddresses**e **userPrincipalName**. Esses valores devem ser exclusivos e qualquer duplicatas deve ser removida..
   
   - Recomendamos que o atributo **userPrincipalName** (UPN) para cada conta de usuário local seja configurado para corresponder ao endereço de email principal que corresponde ao usuário licenciado 365 da Microsoft. Por exemplo, *Mary. Shelley<span>@ Contoso<span> . com* , em vez de *Mary @ contoso. local*
   
   - Se o domínio do Active Directory terminar em um sufixo não roteável, como. *local* ou *. LAN*, em vez de um sufixo roteável na Internet, como *. com* ou *. org*, você precisará ajustar o sufixo UPN das contas de usuário local primeiro, conforme descrito em [Prepare um domínio não roteável para a sincronização de diretórios](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. instalar e configurar o Azure AD Connect

Para sincronizar os usuários, grupos e contatos do Active Directory local para o Active Directory do Azure, instale o Azure Active Directory Connect e configure a sincronização de diretórios. Confira [Configurar a sincronização de diretórios para o Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) para saber mais.

> [!NOTE]
> As etapas são exatamente as mesmas para o Microsoft 365 Business. 

À medida que você configura suas opções para o Azure AD Connect, recomendamos habilitar a **sincronização de senha** e o **logon único contínuo**, bem como o recurso de **write-back de senha** , que também é suportado no Microsoft 365 Business.

> [!NOTE]
> Há algumas etapas adicionais para o Write-back de senha além da caixa de seleção no Azure AD Connect. Para obter mais informações, consulte [como fazer: configurar o Write-back de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. configurar a União híbrida do Azure AD

Antes de habilitar os dispositivos Windows 10 para que o Azure AD híbrido seja Unido, você deve se certificar de que atende aos seguintes pré-requisitos:

   - Você está executando a versão mais recente do Azure AD Connect.

   - O Azure AD Connect sincronizou todos os objetos de computador dos dispositivos que você deseja que sejam associados ao Azure AD híbrido. Se os objetos de computador pertencem a unidades organizacionais (OU) específicas, verifique se essas UOs estão definidas para sincronização no Azure AD Connect também.

Para registrar dispositivos do Windows 10 associados a um domínio existente como ingressado no Azure AD, siga as etapas no [tutorial: configurar o Azure Active Directory híbrido ingressar em domínios gerenciados](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Isso permitirá que o Active Directory local existente ingresse em computadores com Windows 10 e os torne prontos para a nuvem.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. habilitar o registro automático para o Windows 10

 Para registrar automaticamente dispositivos Windows 10 para gerenciamento de dispositivos móveis no Intune, confira [registrar um dispositivo Windows 10 automaticamente usando a política de grupo](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). Você pode definir a política de grupo em um nível de computador local ou para operações em massa, você pode criar essa configuração de política de grupo no controlador de domínio usando o console de gerenciamento de política de grupo e modelos ADMX.

## <a name="5-configure-seamless-single-sign-on"></a>5. configurar o logon único contínuo

  O SSO direto assinará automaticamente os usuários em seus recursos de nuvem do Microsoft 365 quando eles usarem computadores corporativos. Basta implantar uma das duas opções de política de grupo descritas no [logon único contínuo do Azure Active Directory: início rápido](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). A opção de **política de grupo** não permite que os usuários alterem suas configurações, enquanto a opção de **preferência política de grupo** define os valores, mas também os deixa configuráveis pelo usuário.

## <a name="6-set-up-windows-hello-for-business"></a>6. configurar o Windows Hello para empresas

 O Windows Hello para empresas substitui senhas com autenticação de dois fatores (2FA) para entrar em um computador local. Um fator é um par de chaves assimétricas e o outro é um PIN ou outro gesto local, como impressão digital ou reconhecimento facial se o seu dispositivo suportar. Recomendamos que você substitua senhas com o 2FA e o Windows Hello para empresas, onde for possível.

Para configurar o Windows Hello para empresas híbridos, revise os [pré-requisitos de confiança da chave híbrida do Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Siga as instruções em [configurar as configurações de confiança de chave híbrida do Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
