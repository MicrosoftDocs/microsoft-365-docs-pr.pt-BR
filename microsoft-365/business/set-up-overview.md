---
title: Visão geral da configuração
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Visão geral das etapas de configuração para o Microsoft 365 Business.
ms.openlocfilehash: 4be0a8aa1b050ee3e20a045eb2c07666765118ed
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37440528"
---
# <a name="overview-of-setup"></a>Visão geral da configuração

A maioria das etapas de configuração pode ser feita no assistente de configuração, mas as outras opções também são listadas.


## <a name="step-1-add-your-domain-and-users"></a>Etapa 1: adicionar seu domínio e seus usuários

   - **[Adicione seu domínio](set-up.md#add-your-domain-to-personalize-sign-in)** (se você comprou seu domínio durante a [inscrição](sign-up.md), esta etapa já foi feita.)

    - **Adicionar usuários**. Você pode fazer isso de uma das três maneiras:
        - No [Assistente](set-up.md#add-users-in-the-wizard).
        - Use a sincronização de diretórios para [Adicionar usuários usando o Azure ad Connect](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) se você tiver um Active Directory local.
        - Você também pode [Adicionar usuários posteriormente](add-users-m365b.md) no centro de administração.
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>Etapa 2: configurar políticas de segurança e configurar dispositivos 

  - Use o [Assistente de configuração](set-up.md#protect-data-and-devices) para configurar as políticas de dispositivo e segurança. 
  - Você também pode adicionar mais ou editá-los mais tarde no [centro de administração](view-policies-and-devices.md) e no [portal do Intune](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal).
  - Além das configurações de segurança no assistente de instalação, você pode aumentar a segurança adicionando as seguintes configurações:

      - **Proteção contra malware de email**
      - **Links seguros de proteção avançada contra ameaças (ATP)**
      - **Anexos Seguros da ATP**
      - **Anti-phishing ATP**
      - **Arquivamento do Exchange Online**
      - **Data Loss Prevention (DLP)**
      - **Proteção de informações do Azure (Plan1**)

          Para começar, veja [Configurar políticas avançadas de segurança](set-up-advanced-security.md).

        Confira também [as 10 maneiras principais de proteger o Microsoft 365 Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) para um mapa de práticas recomendadas de segurança.

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>Etapa 3: configurar e gerenciar dispositivos Windows 10

   Ao ingressar em um dispositivo Windows 10 no Azure AD, as políticas que você configurou na [etapa 2](#step-2-set-up-security-policies-and-configure-devices) são aplicadas a ela.

   - O Windows 10 pro é um [pré-requisito](pre-requisites-for-data-protection.md) para o Microsoft 365 Business, mas se você tem o Windows 7 Pro, Windows 8 Pro ou Windows 8,1 Pro, sua assinatura lhe concede uma [atualização para o Windows 10 pro](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update).
    - Use o [Assistente de configuração](set-up.md#protect-data-and-devices) para configurar políticas para dispositivos Windows 10.

## <a name="stes-4-install-office-365-business"></a>Stes 4: instalar o Office 365 Business
- Você pode instalar automaticamente o Office nos dispositivos Windows usando o [Assistente de configuração](set-up.md#deploy-office-365-client-apps).
- Instale automaticamente o [Office](auto-install-or-uninstall-office.md) a partir do centro de administração.
- Permitir que os usuários [instalem aplicativos do Office](https://docs.microsoft.com/office365/admin/setup/install-applications) para Windows e dispositivos.
     
## <a name="advanced"></a>Advanced
- **Usar o piloto automático para configurar novos dispositivos**
            
     Você pode usar o [Windows AutoPilot](add-autopilot-devices-and-profile.md) para configurar automaticamente **novos** dispositivos Windows 10 para um usuário, mas pode ser mais fácil obter um [parceiro](https://www.microsoft.com/solution-providers/search) que pode fazer isso para você. Você também pode ir para a [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598) e solicitar que um especialista em tecnologia de nuvem configure novos dispositivos que você comprou para você.

- **Acesse recursos locais**

     - Se sua organização usa o Windows Server Active Directory no local, você pode configurar o Microsoft 365 Business para proteger seus dispositivos Windows 10 e ainda manter o acesso a recursos locais que exigem autenticação local. Siga as etapas em [habilitar dispositivos do Windows 10 associados ao domínio para serem gerenciados pela Microsoft 365 Business](manage-windows-devices.md) para configurar isso. Este é o método preferencial e os dispositivos nesse estado são chamados de dispositivos do Azure AD associados híbridos.

    - Se sua empresa tiver um Active Directory local que contenha alguns recursos locais (como compartilhamento de arquivos e impressoras), você poderá dar aos seus dispositivos associados ao AD do Azure acesso a esses recursos seguindo as etapas aqui: [acessar recursos locais de um Dispositivo ingressado no AD do Azure no Microsoft 365 Business](access-resources.md).

  