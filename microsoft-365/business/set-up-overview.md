---
title: Visão geral da configuração
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Conheça as etapas de configuração do Microsoft 365 Business Premium, desde a assinatura, adicione um domínio e usuários, configure políticas de segurança e muito mais.
ms.openlocfilehash: 46370166a9d5e8c9308b8947513e631c159f0b86
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842121"
---
# <a name="overview-of-setup"></a>Visão geral da configuração

Assista a um vídeo curto sobre a configuração do Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

A maioria das etapas de configuração pode ser feita na configuração orientada, mas as outras opções também estão listadas.

## <a name="step-1-add-your-domain-and-users"></a>Etapa 1: Adicionar seu domínio e usuários

   - **[Adicione seu domínio](set-up.md#add-your-domain-to-personalize-sign-in)** (se você comprou seu domínio durante [a assinatura,](sign-up.md)esta etapa já está feita.)

   - **Adicionar usuários**. Você pode adicionar usuários de qualquer uma das três maneiras:
        - Na [configuração guiada.](set-up.md#add-users-in-the-wizard)
        - Use a sincronização de diretórios para adicionar usuários usando o [Azure AD Connect](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) se você tiver um Active Directory local.
        - Você também pode [adicionar usuários posteriormente](add-users-m365b.md) no centro de administração.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Etapa 2: Configurar políticas de segurança e configurar dispositivos 

  - Use a [configuração orientada para](set-up.md#protect-your-organization) configurar políticas de dispositivo. 
  - Você também pode adicionar mais ou editá-los posteriormente no centro [de administração](view-policies-and-devices.md) e no portal [do Intune.](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)
  - O assistente de configuração também definirá configurações básicas de prevenção contra perda de dados e proteção contra ameaças.
  
  Além das configurações de segurança no assistente de configuração, você pode aumentar a segurança adicionando as seguintes configurações:

- **Proteção contra malware de email**
- **Anti-phishing no Defender para Office 365**
- **Arquivamento do Exchange Online**
- **Proteção de Informações do Azure (Plano1)**

Para começar, veja aumentar a [proteção contra ameaças](increase-threat-protection.md) e configurar recursos de [conformidade.](set-up-compliance.md)

Confira também as 10 principais maneiras de proteger [o Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para obter um roteiro das práticas recomendadas de segurança.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Etapa 3: Configurar e gerenciar dispositivos Windows 10

Depois de concluir a configuração guiada, você vai querer proteger todos os computadores Windows 10 em sua organização.
  
- O Windows 10 Pro é um pré-requisito do Microsoft 365 Business Premium, mas se você tiver o Windows 7 Pro, o Windows 8 Pro ou o Windows 8.1 Pro, sua assinatura lhe dará direito [a](pre-requisites-for-data-protection.md) uma atualização para o [Windows 10 Pro.](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)
- Siga as etapas em [computadores Windows 10](secure-win-10-pcs.md) seguros para configurar políticas para dispositivos Windows 10.

Ao ingressar um dispositivo Windows 10 no Azure AD, as políticas definidas para computadores Com Windows 10 são aplicadas a ele. Para obter mais informações, consulte [Configurar dispositivos Windows para usuários do Microsoft 365.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Etapa 4: Instalar o Microsoft 365 Apps para Empresas
- Você pode instalar o Office automaticamente nos dispositivos Windows usando o assistente [de configuração.](set-up.md#deploy-office-365-client-apps)
- Permitir que os [usuários instalem aplicativos do Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows e dispositivos.
     
## <a name="advanced"></a>Advanced
- **Usar o Autopilot para configurar novos dispositivos**
            
     Você pode usar o [Windows Autopilot](add-autopilot-devices-and-profile.md) para pré-configurar automaticamente novos dispositivos **Windows** [](https://www.microsoft.com/solution-providers/search) 10 para um usuário, mas pode ser mais fácil obter um parceiro que possa fazer isso por você. Você também pode ir para a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)e pedir a um especialista em tecnologia de nuvem para configurar novos dispositivos que você comprar.

- **Acesse recursos locais**

     - Se sua organização usa o Windows Server Active Directory local, você pode configurar o Microsoft 365 Business Premium para proteger seus dispositivos Windows 10, enquanto ainda mantém o acesso a recursos locais que exigem autenticação local. Siga as etapas em Habilitar dispositivos Windows 10 ingressados no domínio a serem gerenciados pelo [Microsoft 365 Business Premium](manage-windows-devices.md) para configurar isso. Esse é o método preferencial, e os dispositivos nesse estado são chamados de dispositivos híbridos ingressados no Azure AD.

    - Se sua empresa tiver um Active Directory local que contenha alguns recursos locais (como compartilhamentos de arquivos e impressoras), você poderá dar aos dispositivos ingressados no Azure AD acesso a esses recursos seguindo as etapas aqui: acessar recursos locais de um dispositivo [ingressado no Azure AD no Microsoft 365 Business Premium.](access-resources.md)

## <a name="see-also"></a>Confira também

[Vídeos de treinamento do Microsoft 365 Business ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
