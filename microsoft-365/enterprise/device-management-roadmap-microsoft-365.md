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
ms.openlocfilehash: 1a1bdb449aa1d1ba12cf1de422b3e279df6c1376
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315736"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Roteiro de gerenciamento de dispositivo para o Microsoft 365


O Microsoft 365 for Enterprise inclui recursos para ajudar a gerenciar dispositivos e seus aplicativos em sua organização. Gerenciar dispositivos móveis ajuda você a proteger e proteger os recursos da sua organização.

Há duas opções para o gerenciamento de dispositivos.

## <a name="microsoft-intune"></a>Microsoft Intune

O Intune oferece opções para gerenciar o acesso à sua organização usando o gerenciamento de dispositivo móvel (MDM) ou o gerenciamento de aplicativo móvel (MAM). O MDM é quando os usuários "registram" seus dispositivos no Intune. Após o registro, eles são dispositivos gerenciados e podem receber quaisquer políticas, regras e configurações usadas por sua organização. Por exemplo, você pode instalar aplicativos específicos, criar uma diretiva de senha, instalar uma conexão VPN e muito mais.

Os usuários com seus próprios dispositivos pessoais podem não querer registrar seus dispositivos ou ser gerenciados pelo Intune e suas políticas. Mas você ainda precisa proteger os recursos e os dados da sua organização. Neste cenário, você pode proteger seus aplicativos usando MAM. Por exemplo, você pode usar uma política MAM que exige que um usuário insira um PIN ao acessar o SharePoint no dispositivo.

Você também determinará como vai gerenciar dispositivos pessoais ou pertencentes à organização. Você pode querer tratar os dispositivos de forma diferente, dependendo do uso. 

Inicie [aqui](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).

## <a name="basic-mobility-and-security"></a>Mobilidade básica e segurança
 
Isso é feito no Microsoft 365 e ajuda você a proteger e gerenciar os dispositivos móveis dos seus usuários, como iPhones, iPads, Androids e Windows phones. Você pode criar e gerenciar políticas de segurança de dispositivo, apagar remotamente um dispositivo e exibir relatórios detalhados de dispositivos. 

Inicie [aqui](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).
 
## <a name="identity-and-device-access-recommendations"></a>Recomendações de acesso de dispositivo e identidade

A Microsoft fornece um conjunto de recomendações para [acesso de dispositivo e identidade](microsoft-365-policies-configurations.md) para garantir uma força de trabalho segura e produtiva. Para acesso ao dispositivo, use as recomendações e configurações nestes artigos:

- [Pré-requisitos](identity-access-prerequisites.md)
- [Identidade comum e políticas de acesso ao dispositivo](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Como a contoso fazia o gerenciamento de dispositivos para o Microsoft 365

Veja como a Contoso Corporation, uma empresa multinacional fictícia, mas representativa, [implantou sua infraestrutura de gerenciamento de dispositivo móvel com os](contoso-mdm.md) serviços de nuvem da Microsoft 365.
