---
title: Desativar a Mobilidade e Segurança Básica
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Remova grupos ou políticas para desativar a Mobilidade Básica e Segurança.
ms.openlocfilehash: 0786ac8ebd190b9af3211c211cc6db2ea9e0ea48
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876835"
---
# <a name="turn-off-basic-mobility-and-security"></a>Desativar a Mobilidade e Segurança Básica

Para desativar efetivamente a Mobilidade Básica e a Segurança, remova grupos de pessoas definidos por grupos de segurança das políticas de gerenciamento de dispositivos ou remova as próprias políticas.

- Remova grupos de usuários removendo grupos de segurança de usuários das políticas de dispositivo que você criou.

- Desabilite a Mobilidade Básica e a Segurança para todos removendo todas as políticas básicas de dispositivos de Mobilidade e Segurança.

Essas opções removem a imposição básica de mobilidade e segurança para dispositivos em sua organização. Infelizmente, você não pode simplesmente "desprovisionar" a Mobilidade e a Segurança Básica após a configuração. 

>[!IMPORTANT]
>Esteja ciente do impacto nos dispositivos dos usuários ao remover grupos de segurança de usuários das políticas ou remover as próprias políticas. Por exemplo, perfis de email e emails armazenados em cache podem ser removidos, dependendo do dispositivo. Para obter mais informações,  [consulte O que acontece quando você exclui uma política ou remove um usuário da política?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Remover grupos de segurança do usuário das políticas básicas de dispositivos de mobilidade e segurança

1. No seu tipo de navegador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecione uma política de dispositivo e selecione **Editar política.** 

3. Na  **** página   Implantação, selecione **Remover**.

4. Em  **Grupos,** selecione um grupo de segurança.

5. Selecione  **Remover** e **Salvar.**

## <a name="remove-basic-mobility-and-security-device-policies"></a>Remover políticas básicas de dispositivos de mobilidade e segurança

1.  No seu tipo de navegador:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Selecione uma política de dispositivo e, em seguida,  **selecione Excluir política.**
    
3.  Na caixa de diálogo Aviso, selecione **Sim**.

>[!NOTE]
>Para obter mais etapas para desbloquear dispositivos se os dispositivos da sua organização ainda estão em um estado bloqueado, consulte a postagem do blog Removendo o Controle de Acesso do Gerenciamento de Dispositivo Móvel para [o Office 365.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934)
