---
title: Visão geral da configuração
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Saiba as etapas de instalação do Microsoft 365 Business Premium, desde a assinatura, a adição de um domínio e usuários, a configuração de políticas de segurança e muito mais.
ms.openlocfilehash: 749acbfdbde92ad97b09dc720c85dd850b76c9cf
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579925"
---
# <a name="overview-of-setup"></a>Visão geral da configuração

Assista a um breve vídeo sobre a instalação do Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Se você achou este vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades para o Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

A maioria das etapas de instalação pode ser feita na configuração guiada, mas as outras opções também estão listadas.

## <a name="step-1-add-your-domain-and-users"></a>Etapa 1: Adicionar seu domínio e usuários

   - **[Adicione seu domínio](set-up.md#add-your-domain-to-personalize-sign-in)** (se você comprou seu domínio [durante a assinatura,](sign-up.md)esta etapa já foi feita.)

   - **Adicionar usuários**. Você pode adicionar usuários de qualquer uma das três maneiras:
        - Na [configuração guiada](set-up.md#add-users-in-the-wizard).
        - Use a sincronização de diretórios para [adicionar usuários usando o Azure AD Connect](../enterprise/set-up-directory-synchronization.md) se você tiver um Active directory local.
        - Você também pode [adicionar usuários posteriormente](../admin/add-users/add-users.md) no centro de administração.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Etapa 2: Configurar políticas de segurança e configurar dispositivos 

  - Use a [configuração guiada](set-up.md#protect-your-organization) para configurar políticas de dispositivo. 
  - Você também pode adicionar mais ou editá-los posteriormente no centro [de administração](view-policies-and-devices.md) e no portal [do Intune.](/intune/tutorial-walkthrough-intune-portal)
  - O assistente de instalação também configurará configurações básicas de proteção contra ameaças e prevenção contra perda de dados.
  
  Além das configurações de segurança no assistente de instalação, você pode aumentar sua segurança adicionando as seguintes configurações:

- **Proteção contra malware de email**
- **Anti-phishing no Defender para Office 365**
- **Arquivamento do Exchange Online**
- **Proteção de Informações do Azure (Plan1**)

Para começar, confira [aumentar a proteção contra ameaças](increase-threat-protection.md) e configurar recursos de [conformidade.](set-up-compliance.md)

Confira também as 10 principais maneiras de [proteger seu Microsoft 365 Business Premium](/office365/admin/security-and-compliance/secure-your-business-data) para obter um roteiro das melhores práticas de segurança.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Etapa 3: Configurar e gerenciar dispositivos Windows 10

Depois de concluir a configuração guiada, você vai querer proteger todos os computadores Windows 10 em sua organização.
  
- O Windows 10 Pro é um [pré-requisito](pre-requisites-for-data-protection.md) para o Microsoft 365 Business Premium, mas se você tiver Windows 7 Pro, Windows 8 Pro ou Windows 8.1 Pro, sua assinatura terá direito a uma atualização para [o Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md).
- Siga as etapas em [computadores windows 10 seguros](secure-win-10-pcs.md) para configurar políticas para dispositivos Windows 10.

Ao ingressar um dispositivo Windows 10 no Azure AD, as políticas definidas para computadores Windows 10 serão aplicadas a ele. Para obter mais informações, consulte Configurar dispositivos Windows para usuários do [Microsoft 365.](set-up-windows-devices.md)

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Etapa 4: Instalar o Microsoft 365 Apps para empresas
- Você pode instalar o Office automaticamente nos dispositivos Windows usando o [assistente de instalação](set-up.md#deploy-office-365-client-apps).
- Permitir que [os usuários instalem aplicativos do Office](/office365/admin/setup/install-applications) para Windows e dispositivos.
     
## <a name="advanced"></a>Advanced
- **Usar o Autopilot para configurar novos dispositivos**
            
     Você pode usar o [Windows Autopilot](add-autopilot-devices-and-profile.md) para pré-configurar automaticamente novos dispositivos **Windows** [](https://www.microsoft.com/solution-providers/search) 10 para um usuário, mas pode ser mais fácil obter um parceiro que possa fazer isso por você. Você também pode ir à [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)e pedir a um especialista em tecnologia de nuvem para configurar novos dispositivos que você compra.

- **Acesse recursos locais**

     - Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business Premium para proteger seus dispositivos Windows 10 e, ao mesmo tempo, manter o acesso a recursos locais que exigem autenticação local. Siga as etapas em Habilitar dispositivos Windows 10 ingressados no domínio a serem gerenciados pelo [Microsoft 365 Business Premium](manage-windows-devices.md) para configurar isso. Esse é o método preferencial, e os dispositivos nesse estado são chamados de dispositivos ingressados no Azure AD híbridos.

    - Se sua empresa tiver um Active Directory local que contenha alguns recursos locais (como compartilhamentos de arquivos e impressoras), você poderá dar aos dispositivos ingressados no Azure AD acesso a esses recursos seguindo as etapas aqui: Acessar recursos locais de um dispositivo ingressado no [Azure AD no Microsoft 365 Business Premium](access-resources.md).

## <a name="see-also"></a>Confira também

[Vídeos de treinamento do Microsoft 365 Business ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)