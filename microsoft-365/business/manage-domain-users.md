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
description: Sincronizar usuários controlados por domínio com o Microsoft 365 para empresas.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841350"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Sincronizar os usuários do domínio com o Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Preparar-se para a sincronização de diretórios 

Antes de sincronizar seus usuários e computadores do Domínio do Active Directory local, revise Preparar-se para a sincronização de diretórios com [o Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization) Em particular:

   - Certifique-se de que não existam duplicatas em seu diretório para os seguintes atributos: **email,** **proxyAddresses** e **userPrincipalName**. Esses valores devem ser exclusivos e quaisquer duplicatas devem ser removidas.
   
   - Recomendamos que você configure o atributo **userPrincipalName** (UPN) para cada conta de usuário local para corresponder ao endereço de email principal que corresponde ao usuário licenciado do Microsoft 365. Por exemplo: *mary.shelley@contoso.com* em vez *de mary@contoso.local*
   
   - Se o domínio do Active Directory terminar em um sufixo não-rouável como *.local* ou *.lan*, em vez de um sufixo de internet routable, como *.com* ou *.org*, ajuste o sufixo UPN das contas de usuário local primeiro, conforme descrito em Preparar um domínio não-rouável para [sincronização](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)de diretório. 

O **IdFix de Executar** na etapa quatro (4) abaixo também garantirá que seu Active Directory local esteja pronto para a sincronização de diretórios.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Instalar e configurar o Azure AD Connect

Para sincronizar seus usuários, grupos e contatos do Active Directory local no Azure Active Directory, instale o Azure Active Directory Connect e configurar a sincronização de diretórios. 

 1. No centro [de administração,](https://go.microsoft.com/fwlink/p/?linkid=2024339)selecione **Instalação** na nav esquerda.

 2. Em **Entrar e segurança,** escolha **Exibir** em Sincronizar usuários no diretório da **sua organização.**

 3. Na página **Sincronizar usuários na página de diretório da sua** organização, escolha **Começar.**

 4. Na primeira etapa, execute a ferramenta IdFix para se preparar para a sincronização do Diretório.

 5. Siga as etapas do assistente para baixar o Azure AD Connect e usá-lo para sincronizar seus usuários controlados por domínio com o Microsoft 365.


Confira [Configurar a sincronização de diretórios do Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) para saber mais.

Conforme você configura suas opções para o Azure AD Connect, recomendamos que você habilita a Sincronização de **Senha,** Logon Único Contínuo e o recurso de **write-back** de senha, que também é suportado no Microsoft 365 para empresas. 

> [!NOTE]
> Há algumas etapas adicionais para write-back de senha além da caixa de seleção no Azure AD Connect. Para obter mais informações, [consulte Como: configurar o write-back de senha.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) 

Se você também quiser gerenciar dispositivos Windows 10 ingressados no domínio, confira Habilitar dispositivos Windows 10 ingressados no domínio a serem gerenciados pelo [Microsoft 365 Business Premium](manage-windows-devices.md) para configurar um ingresso híbrido no Azure AD. 