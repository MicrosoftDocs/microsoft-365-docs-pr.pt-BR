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
description: Saiba mais sobre as etapas de configuração para o Microsoft 365 Business Premium, em assinatura, para adicionar um domínio e usuários, para configurar as políticas de segurança e muito mais.
ms.openlocfilehash: 80243fac6ca2efcfca030b6ee1c1113c026a80ce
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402969"
---
# <a name="overview-of-setup"></a>Visão geral da configuração

Assista a um pequeno vídeo sobre a configuração do Microsoft 365 Business Premium.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

A maioria das etapas de configuração pode ser feita no assistente de configuração, mas as outras opções também são listadas.

## <a name="step-1-add-your-domain-and-users"></a>Etapa 1: adicionar seu domínio e seus usuários

   - **[Adicione seu domínio](set-up.md#add-your-domain-to-personalize-sign-in)** (se você comprou seu domínio durante a [inscrição](sign-up.md), esta etapa já foi feita.)

    - **Adicionar usuários**. Você pode adicionar usuários de uma das três maneiras:
        - No [Assistente](set-up.md#add-users-in-the-wizard).
        - Use a sincronização de diretórios para [Adicionar usuários usando o Azure ad Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) se você tiver um Active Directory local.
        - Você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Etapa 2: configurar políticas de segurança e configurar dispositivos 

  - Use o [Assistente de configuração](set-up.md#protect-your-organization) para configurar as políticas de dispositivos. 
  - Você também pode adicionar mais ou editá-los mais tarde no [centro de administração](view-policies-and-devices.md) e no [portal do Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - O assistente de configuração também definirá as configurações básicas de proteção contra ameaças e prevenção contra perda de dados.
  
  Além das configurações de segurança no assistente de instalação, você pode aumentar a segurança adicionando as seguintes configurações:

- **Proteção contra malware de email**
- **Anti-phishing ATP**
- **Arquivamento do Exchange Online**
- **Proteção de informações do Azure (Plan1**)

Para começar, consulte [aumentar a proteção contra ameaças](increase-threat-protection.md) e [configurar recursos de conformidade](set-up-compliance.md).

Confira também [as 10 maneiras principais de proteger o Microsoft 365 Business Premium](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para um roteiro de práticas recomendadas de segurança.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Etapa 3: configurar e gerenciar dispositivos Windows 10

Depois de executar o assistente de configuração, você desejará proctectr todos os computadores windwos 10 em sua organização.
  
- O Windows 10 pro é um [pré-requisito](pre-requisites-for-data-protection.md) para o Microsoft 365 Business Premium, mas se você tiver o Windows 7 Pro, Windows 8 Pro ou Windows 8,1 Pro, sua assinatura lhe contitulará uma [atualização para o Windows 10 pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
- Siga as etapas em [proteger PCs Windows 10](secure-win-10-pcs.md) para configurar políticas para dispositivos Windows 10.

Ao ingressar em um dispositivo Windows 10 no Azure AD, as políticas definidas para computadores com Windows 10 são aplicadas a ela. Para obter mais informações, consulte [configurar dispositivos Windows para usuários do Microsoft 365](set-up-windows-devices.md).

## <a name="step-4-install-microsoft-365-apps-for-business"></a>Etapa 4: instalar o Microsoft 365 aplicativos para empresas
- Você pode instalar automaticamente o Office nos dispositivos Windows usando o [Assistente de configuração](set-up.md#deploy-office-365-client-apps).
- Permitir que os usuários [instalem aplicativos do Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows e dispositivos.
     
## <a name="advanced"></a>Avançado
- **Usar o piloto automático para configurar novos dispositivos**
            
     Você pode usar o [Windows AutoPilot](add-autopilot-devices-and-profile.md) para configurar automaticamente **novos** dispositivos Windows 10 para um usuário, mas pode ser mais fácil obter um [parceiro](https://www.microsoft.com/solution-providers/search) que pode fazer isso para você. Você também pode ir para a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)e solicitar que um especialista em tecnologia de nuvem configure novos dispositivos que você comprou.

- **Acesse recursos locais**

     - Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business Premium para proteger seus dispositivos Windows 10, mantendo ainda a manutenção do acesso a recursos locais que exigem autenticação local. Siga as etapas em [habilitar dispositivos do Windows 10 associados ao domínio para serem gerenciados pelo Microsoft 365 Business Premium](manage-windows-devices.md) para configurar isso. Este é o método preferencial, e os dispositivos nesse estado são chamados de dispositivos do Azure AD associados híbridos.

    - Se sua empresa tiver um Active Directory local que contenha alguns recursos locais (como compartilhamentos de arquivos e impressoras), você poderá permitir que seus dispositivos associados ao AD do Azure acessem esses recursos seguindo as etapas aqui: [acessar recursos locais de um dispositivo associado ao AD do Azure no Microsoft 365 Business Premium](access-resources.md).

## <a name="see-also"></a>Confira também

[Vídeos de treinamento do Microsoft 365 Business ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
