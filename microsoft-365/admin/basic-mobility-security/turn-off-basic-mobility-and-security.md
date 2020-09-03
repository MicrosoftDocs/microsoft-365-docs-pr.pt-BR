---
title: Desativar a mobilidade básica e segurança
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
description: Remover grupos ou políticas para desativar a mobilidade básica e a segurança.
ms.openlocfilehash: 54f78cc30e5259ad5244ce3a8fc6d0f46a395d7c
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336696"
---
# <a name="turn-off-basic-mobility-and-security"></a>Desativar a mobilidade básica e segurança

Para desativar efetivamente a mobilidade e a segurança básica, remova grupos de pessoas definidos por grupos de segurança das políticas de gerenciamento de dispositivos ou remova as próprias políticas.

- Remover grupos de usuários, removendo grupos de segurança do usuário das políticas de dispositivos que você criou.
    
- Desabilite a mobilidade básica e a segurança para todos removendo todas as políticas básicas de mobilidade e dispositivo de segurança.
    
Essas opções removem a mobilidade básica e a imposição de segurança para dispositivos em sua organização. Infelizmente, não é possível simplesmente "desconfigurar" a mobilidade básica e a segurança após configurá-la. 

>[!IMPORTANT]
>Lembre-se do impacto nos dispositivos dos usuários ao remover grupos de segurança do usuário das políticas ou remover as próprias diretivas. Por exemplo, perfis de email e emails em cache podem ser removidos, dependendo do dispositivo. Para obter mais informações, consulte  [o que acontece quando você exclui uma política ou remove um usuário da política?](https://support.microsoft.com/office/create-device-security-policies-in-basic-mobility-and-security-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6#bkmk_changeimpact)

## <a name="remove-user-security-groups-from-basic-mobility-and-security-device-policies"></a>Remover grupos de segurança de usuário das políticas de mobilidade básica e dispositivo de segurança

1. No seu navegador, digite:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecione uma política de dispositivo e selecione **Editar política**. 

3. Na página  **implantação**   , selecione **remover**.
    
4. Em  **grupos**, selecione um grupo de segurança.

5. Selecione  **remover**e selecione **salvar**.
    

## <a name="remove-basic-mobility-and-security-device-policies"></a>Remover as políticas de mobilidade básica e dispositivo de segurança

1.  No seu navegador, digite:  [https://protection.office.com/devicev2](https://protection.office.com/devicev2) . 

2.  Selecione uma política de dispositivo e, em seguida, selecione  **excluir política**.
    
3.  Na caixa de diálogo de aviso, selecione **Sim**.

>[!NOTE] 
>Para obter mais etapas para desbloquear dispositivos se os dispositivos de sua organização ainda estiverem em um estado bloqueado, consulte o blog post [removendo o controle de acesso do gerenciamento de dispositivos móveis para o Office 365](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Removing-Access-Control-from-Mobile-Device-Management-for-Office/ba-p/279934).
