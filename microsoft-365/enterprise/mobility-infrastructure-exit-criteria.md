---
title: Critérios de saída de infraestrutura de gerenciamento de dispositivo móvel
description: Microsoft 365 Enterprise inclui o gerenciamento de dispositivos móveis usando o Microsoft Intune. Examine os requisitos e pré-requisitos, configurar Intune usando seu recurso do Active Directory do Azure, registrar iOS, macOS, Android e Windows dispositivos, implantar apps, crie um perfil de configurar, usar uma política de conformidade e habilitar o acesso condicional para dispositivos móveis gerenciamento de dispositivo com Microsoft 365 Enterprise.
keywords: 365 da Microsoft, Microsoft 365 Enterprise, Microsoft 365 documentação, gerenciamento de dispositivos móveis, Intune
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/10/2018
ms.topic: article
audience: ITPro
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
ms.custom: microsoft-intune
ms.openlocfilehash: b511052698f42a07df5fc25aeaad7fc7f00c2a6e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864850"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Critérios de saída de infraestrutura de gerenciamento de dispositivo móvel

![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Isso se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Antes de passar para a próxima fase no processo de implantação, certifique-se de que sua configuração atende aos seguintes requisitos de infraestrutura de gerenciamento de dispositivo móvel.

- O Intune está configurado, incluindo a criação de grupos e usuários do Azure AD para aplicar as regras da sua organização para dispositivos.
- Você registrou dispositivos no Intune para que eles possam receber as políticas que você criou.
- Os aplicativos são adicionados aos dispositivos para que os usuários tenham acesso a serviços de nuvem do Microsoft 365 da sua organização, como o Exchange Online e o SharePoint Online.
- As configurações e os recursos estão definidos e aplicados aos seus dispositivos usando os usuários e os grupos do Azure AD que você criar, o que pode incluir habilitar antivírus e restringir aplicativos específicos.
- As políticas de conformidade estão prontas para exigir um firewall ou tamanho de senha em um dispositivo. Se os dispositivos não estiverem em conformidade, o acesso condicional bloqueará o acesso aos dados da organização.

## <a name="next-phase"></a>Próxima fase

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| A próxima fase no processo de implantação de ponta a ponta para Microsoft 365 Enterprise é a [proteção de informações](infoprotect-infrastructure.md). |
