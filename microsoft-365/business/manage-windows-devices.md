---
title: Habilitar os dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: 661e5bf8205a661eb4382b4bdd8fcf3a54ecc12f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660283"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Habilitar os dispositivos Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business

Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10 e ainda manter o acesso a recursos locais que exigem autenticação local. Você pode configurar isso primeiro sincronizando o Active Directory com o Azure Active Directory, seguido ao registrar os dispositivos Windows 10 com o Azure AD e registrá-los para gerenciamento de dispositivos móveis pelo Microsoft 365 Business.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Configurar dispositivos associados ao domínio para serem gerenciados pelo Microsoft 365 Business

Para configurar os dispositivos que ingressaram no domínio da sua organização para se beneficiar dos recursos fornecidos pelo Azure Active Directory, além do Active Directory local, é possível implementar **dispositivos do Azure ad associados híbridos**. Estes são os dispositivos que ingressaram no seu Active Directory local e no Azure Active Directory. Dispositivos híbridos associados do Azure AD podem ser protegidos e gerenciados pelo Microsoft 365 Business. 
  
Conclua as etapas abaixo para tornar seus dispositivos Windows 10 híbridos do Azure AD associados e gerenciados pelo Microsoft 365 Business.
  
1. Para sincronizar seus usuários, grupos e contatos do Active Directory local para o Active Directory do Azure, execute o assistente de sincronização de diretórios e o Azure Active Directory Connect conforme descrito em [Configurar a sincronização de diretórios para o Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > As etapas são exatamente as mesmas para o Microsoft 365 Business. 
  
2. Antes de concluir a etapa 3 para permitir que os dispositivos Windows 10 sejam associados ao Azure AD híbrido, você precisa certificar-se de que atende aos seguintes pré-requisitos:

   - Você está executando a versão mais recente do Azure AD Connect.

   - O Azure AD Connect sincronizou todos os objetos de computador dos dispositivos que você deseja que sejam associados ao Azure AD híbrido. Se os objetos de computador pertencem a unidades organizacionais (OU) específicas, verifique se essas UOs estão definidas para sincronização no Azure AD Connect também.
    
3. Registre os dispositivos Windows 10 associados ao domínio existente para que o Azure AD híbrido seja Unido e registre-os para gerenciamento de dispositivos móveis pelo Intune (Microsoft 365 Business):
    
4. Siga as instruções passo a passo sobre [como configurar dispositivos híbridos associados do Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=872870). Isso permitirá que a sincronização de seu Active Directory local seja associada aos computadores Windows 10 e tornará-os prontos para a nuvem.
    
5. Para registrar um dispositivo Windows 10 para gerenciamento de dispositivos móveis, confira [registrar um dispositivo Windows 10 com o Intune usando uma política de grupo](https://go.microsoft.com/fwlink/p/?linkid=872871) para obter instruções. Você pode definir a política de grupo em um nível de computador local ou para operações em massa, você pode criar essa configuração de política de grupo no servidor de controlador de domínio.