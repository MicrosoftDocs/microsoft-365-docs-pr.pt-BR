---
title: Sincronizar os usuários do domínio com o Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Sincronizar usuários controlados por domínio com o Microsoft 365 para empresas.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578398"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizar os usuários do domínio com o Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Preparar-se para Sincronização de Diretórios 

Antes de sincronizar seus usuários e computadores do Domínio Local do Active Directory, revise [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md). Em particular:

   - Certifique-se de que não existam duplicatas no diretório para os seguintes atributos: **email,** **proxyAddresses** e **userPrincipalName**. Esses valores devem ser exclusivos e quaisquer duplicatas devem ser removidas.
   
   - Recomendamos que você configure o **atributo userPrincipalName** (UPN) para cada conta de usuário local para corresponder ao endereço de email principal que corresponde ao usuário licenciado do Microsoft 365. Por exemplo: *mary.shelley@contoso.com* em vez *de mary@contoso.local*
   
   - Se o domínio do Active Directory terminar em um sufixo não rouável como *.local* ou *.lan*, em vez de um sufixo de tabela de internet como *.com* ou *.org*, ajuste o sufixo UPN das contas de usuário locais primeiro, conforme descrito em [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md). 

O **IdFix** de Executar na etapa quatro (4) abaixo também garantirá que o Active Directory local esteja pronto para sincronização de diretórios.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Instalar e configurar o Azure AD Connect

Para sincronizar seus usuários, grupos e contatos do Active Directory local no Azure Active Directory, instale o Azure Active Directory Connect e configurar a sincronização de diretórios. 

 1. No centro [de administração,](https://go.microsoft.com/fwlink/p/?linkid=2024339)selecione **Instalação** na nav esquerda.

 2. Em **Entrar e segurança,** escolha **Exibir** em **Sincronizar usuários no diretório da sua organização.**

 3. Na página **Sincronizar usuários na página de** diretório da sua organização, escolha **Iniciar**.

 4. Na primeira etapa, execute a ferramenta IdFix para se preparar para a sincronização de diretórios.

 5. Siga as etapas do assistente para baixar o Azure AD Connect e usá-lo para sincronizar seus usuários controlados pelo domínio com o Microsoft 365.


Consulte [Configurar a sincronização de diretórios do Microsoft 365](../enterprise/set-up-directory-synchronization.md) para saber mais.

Ao configurar suas opções para o Azure AD Connect, recomendamos que você habilita a Sincronização de **Senha,** o Logon Único Contínuo e o recurso de **writeback** de senha, que também é suportado no Microsoft 365 para empresas.

> [!NOTE]
> Há algumas etapas adicionais para write-back de senha além da caixa de seleção no Azure AD Connect. Para obter mais informações, consulte [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback). 

Se você também deseja gerenciar dispositivos Windows 10 ingressados no domínio, consulte [Enable domain-joined Windows 10 devices](manage-windows-devices.md) to be managed by Microsoft 365 Business Premium to set up a hybrid Azure AD Join.