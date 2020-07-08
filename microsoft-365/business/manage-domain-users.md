---
title: Sincronizar os usuários do domínio com o Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Sincronizar usuários controlados pelo domínio com o Microsoft 365 for Business.
ms.openlocfilehash: af9cb7c9b2b639edc2375679a73ab41c4cf6de71
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080054"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizar os usuários do domínio com o Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. preparar para a sincronização de diretório 

Antes de sincronizar os usuários e computadores do domínio do Active Directory local, revise [preparar para a sincronização de diretório para o Microsoft 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). Em particular:

   - Verifique se não há duplicatas no diretório para os seguintes atributos: **mail**, **proxyAddresses**e **userPrincipalName**. Esses valores devem ser exclusivos e qualquer duplicatas deve ser removida.
   
   - Recomendamos que você configure o atributo **userPrincipalName** (UPN) para cada conta de usuário local para corresponder ao endereço de email principal que corresponde ao usuário licenciado 365 da Microsoft. Por exemplo: *Mary.Shelley@contoso.com* em vez de *Mary@contoso. local*
   
   - Se o domínio do Active Directory terminar em um sufixo não roteável, como. *local* ou *. LAN*, em vez de um sufixo roteável na Internet, como *. com* ou *. org*, ajuste o sufixo UPN das contas de usuário local primeiro, conforme descrito em [preparar um domínio não roteável para a sincronização de diretórios](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

A **execução IdFix** na etapa quatro (4) abaixo também garantirá que o Active Directory local está pronto para a sincronização de dir.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. instalar e configurar o Azure AD Connect

Para sincronizar os usuários, grupos e contatos do Active Directory local para o Active Directory do Azure, instale o Azure Active Directory Connect e configure a sincronização de diretórios. 

 1. No centro de administração, em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> selecionar **configuração** no painel de navegação esquerdo.

 2. Em **entrada e segurança**, escolha **Exibir** em **sincronizar usuários do diretório da sua organização**.

 3. Na página **sincronizar usuários do diretório da organização** , escolha **introdução**.

 4. Na primeira etapa, execute IdFix Tool para preparar a sincronização de diretórios.

 5. Siga as etapas do assistente para baixar o Azure AD Connect e usá-lo para sincronizar seus usuários de domínio controlado com o Microsoft 365.


Confira [Configurar a sincronização de diretórios para o Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) para saber mais.

Ao configurar suas opções para o Azure AD Connect, recomendamos que você habilite a **sincronização de senha**, o **logon único contínuo**e o recurso **write-back de senha** , que também é suportado no Microsoft 365 for Business.

> [!NOTE]
> Há algumas etapas adicionais para o Write-back de senha além da caixa de seleção no Azure AD Connect. Para obter mais informações, consulte [como fazer: configurar o Write-back de senha](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

Se você quiser gerenciar dispositivos Windows 10 associados ao domínio também, confira [habilitar dispositivos Windows 10 associados ao domínio para que sejam gerenciados pelo Microsoft 365 Business Premium](manage-windows-devices.md) para configurar uma associação híbrida do Azure AD. 