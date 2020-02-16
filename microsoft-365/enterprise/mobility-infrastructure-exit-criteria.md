---
title: Critérios de saída da infraestrutura de gerenciamento de dispositivo móvel
description: O Microsoft 365 Enterprise inclui gerenciamento de dispositivos móveis usando o Microsoft Intune. Revise os requisitos e pré-requisitos, configure o Intune usando seu recurso do Azure Active Directory, registre os dispositivos iOS, macOS, Android e Windows, implante aplicativos, crie um perfil de configuração, use uma política de conformidade e habilite o acesso condicional para dispositivos móveis gerenciamento de dispositivos com o Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentação do Microsoft 365, gerenciamento de dispositivos móveis, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: 3e8013426983584783488e6f937f8ba5b02d7a1a
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066778"
---
# <a name="mobile-device-management-infrastructure-exit-criteria"></a>Critérios de saída da infraestrutura de gerenciamento de dispositivo móvel

![Fase 5: gerenciamento de dispositivo móvel](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)

*Isso se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

Certifique-se de que a sua configuração atenda aos requisitos a seguir para a infraestrutura de gerenciamento de dispositivos móveis.

- O Intune é configurado, incluindo a criação de usuários e grupos do Azure Active Directory (Azure AD) para aplicar as regras da sua organização para dispositivos.
- Você registrou dispositivos no Intune para que eles possam receber as políticas que você criou.
- Os aplicativos são adicionados aos dispositivos para que os usuários tenham acesso a serviços de nuvem do Microsoft 365 da sua organização, como o Exchange Online e o SharePoint Online.
- As configurações e os recursos estão definidos e aplicados aos seus dispositivos usando os usuários e os grupos do Azure AD que você criar, o que pode incluir habilitar antivírus e restringir aplicativos específicos.
- As políticas de conformidade estão vigentes para exigir um firewall ou um comprimento de senha em um dispositivo. Se os dispositivos não forem compatíveis, o acesso condicional bloqueará o acesso aos dados da sua organização.

## <a name="results-and-next-steps"></a>Resultados e próximas etapas

Seus dispositivos estão registrados no Intune e configurados com as políticas apropriadas.

|||
|:-------|:-----|
|![Fase 6: proteção de informações](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)| Se você estiver seguindo as fases da implantação de ponta a ponta do Microsoft 365 Enterprise, sua próxima fase será a [proteção de informações](infoprotect-infrastructure.md). |
