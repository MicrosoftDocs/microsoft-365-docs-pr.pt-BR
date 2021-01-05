---
title: Roteiro de gerenciamento de dispositivo para o Microsoft 365
keywords: Microsoft 365, Microsoft 365 para empresas, documentação do Microsoft 365, gerenciamento de dispositivos móveis, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: O roteiro para configurar o gerenciamento de dispositivos para o Microsoft 365.
ms.openlocfilehash: 79be47d6bc83c124f2203866986e06181a1f7f3d
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749534"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Roteiro de gerenciamento de dispositivo para o Microsoft 365

O Microsoft 365 for Enterprise inclui recursos para ajudar a gerenciar dispositivos e seus aplicativos em sua organização. Gerenciar dispositivos móveis ajuda você a proteger e proteger os recursos da sua organização.

Há duas opções para o gerenciamento de dispositivos:

- [Microsoft Intune](#microsoft-intune)
- [Mobilidade e Segurança Básica](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

Você pode usar o Microsoft Intune para gerenciar o acesso à sua organização usando o gerenciamento de dispositivos móveis ou o gerenciamento de aplicativos móveis. O gerenciamento de dispositivos móveis é quando os usuários "registram" seus dispositivos no Intune. Após um dispositivo ser inscrito, é um dispositivo gerenciado; Portanto, ele pode receber as políticas, as regras e as configurações da sua organização. Por exemplo, você pode instalar aplicativos específicos, criar uma política de senha, instalar uma conexão VPN e muito mais.

Os usuários com seus próprios dispositivos pessoais podem não querer registrar seus dispositivos ou ser gerenciados pelo Intune e pelas políticas da sua organização. Mas você ainda precisa proteger os recursos e os dados da sua organização. Neste cenário, você pode proteger seus aplicativos usando o gerenciamento de aplicativo móvel. Por exemplo, você pode usar uma política de gerenciamento de aplicativo móvel que exige que um usuário insira um PIN ao acessar o SharePoint Online no dispositivo.

Você também determinará como você vai gerenciar dispositivos pessoais e dispositivos de propriedade da organização. Você pode querer tratar os dispositivos de forma diferente, dependendo de seus usos.

## <a name="basic-mobility-and-security"></a>Mobilidade e Segurança Básica

Isso é feito no Microsoft 365 e ajuda você a proteger e gerenciar os dispositivos móveis dos seus usuários, como iPhones, iPads, Androids e Windows phones. Você pode criar e gerenciar políticas de segurança de dispositivo, apagar remotamente um dispositivo e exibir relatórios detalhados de dispositivos.

## <a name="choose-between-the-two-options"></a>Escolha entre as duas opções

Para ajudá-lo a avaliar melhor qual opção de gerenciamento de dispositivos é melhor para você, consulte [escolher entre a segurança de mobilidade básica e o Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).

Com base em sua avaliação, comece a gerenciar seus dispositivos com:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [Mobilidade e Segurança Básica](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>Recomendações de acesso de dispositivo e identidade

A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](../security/office-365-security/microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. Para acesso ao dispositivo, use as recomendações e configurações nestes artigos:

- [Pré-requisitos](../security/office-365-security/identity-access-prerequisites.md)
- [Identidade comum e políticas de acesso ao dispositivo](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Como a contoso fazia o gerenciamento de dispositivos para o Microsoft 365

Para obter informações sobre como uma empresa multinacional fictícia, mas representativa, implantou sua infraestrutura de gerenciamento de dispositivo móvel com os serviços de nuvem da Microsoft 365, consulte [Mobile Device Management for contoso](contoso-mdm.md).
