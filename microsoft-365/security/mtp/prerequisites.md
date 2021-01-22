---
title: Pré-requisitos do Microsoft 365 Defender
description: Saiba mais sobre os requisitos de licenciamento, hardware e software e outras configurações do Microsoft 365 Defender
keywords: requisitos, pré-requisitos, hardware, software, navegador, MTP, M365, licença, E5, A5, EMS, compra
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ee1777debdb91a6ac73737db2db48e434ed3e2e2
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930085"
---
# <a name="microsoft-365-defender-prerequisites"></a>Pré-requisitos do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Saiba mais sobre licenciamento e outros requisitos para provisionamento e uso [do Microsoft 365 Defender.](microsoft-threat-protection.md)

## <a name="licensing-requirements"></a>Requisitos de licença
Qualquer uma dessas licenças oferece acesso aos recursos do Microsoft 365 Defender na central de segurança do Microsoft 365 sem custo adicional:

- Microsoft 365 E5 ou A5
- Segurança do Microsoft 365 E5 ou A5 Security
- Windows 10 Enterprise E5 ou A5
- Enterprise Mobility + Security (EMS) E5 ou A5 
- Office 365 E5 ou A5
- Microsoft Defender para Ponto de Extremidade
- Microsoft Defender para Identidade? 
- Microsoft Cloud App Security
- Defender para Office 365 (Plano 2)

> [!NOTE]
> As licenças de avaliação do Office 365 atualmente não fornecem acesso ao Microsoft 365 Defender.

Para obter mais informações, [veja os planos de serviço do Microsoft 365 Enterprise.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> Ainda não tem licença? [Experimentar ou comprar uma assinatura do Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Verificar suas licenças existentes
Vá para o Centro de administração do Microsoft 365[(admin.microsoft.com)](https://admin.microsoft.com/)para exibir suas licenças existentes. No Centro de administração, acesse **Cobrança** > **Licenças**.

>[!NOTE]
> Você precisa ter a  função de administrador de cobrança ou leitor **global** no [Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver as informações de licença. Se tiver problemas de acesso, entre em contato com um administrador global.

## <a name="required-permissions"></a>Permissões obrigatórias
Você deve ser um **administrador global** ou um administrador **de** segurança no Azure Active Directory para ativar o Microsoft 365 Defender. Para obter a lista de funções necessárias para usar o Microsoft 365 Defender e informações sobre como o acesso aos dados é regulamentado, leia sobre como gerenciar o acesso ao [Microsoft 365 Defender.](mtp-permissions.md)

## <a name="browser-requirements"></a>Requisitos de navegador
Acesse o Microsoft 365 Defender no centro de segurança do Microsoft 365 usando o Microsoft Edge, o Internet Explorer 11 ou qualquer navegador da Web compatível com HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilidade para GCC dos EUA, GCC High e outras instituições governamentais dos EUA
Atualmente, o Microsoft 365 Defender *não está* disponível para:
- Nuvem da Comunidade Governamental dos EUA (GCC)
- Nuvem Alta da Comunidade Governamental dos EUA (GCC High)
- Departamento de Defesa dos EUA
- Todas as instituições governamentais dos EUA com licenças comerciais

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral do Microsoft 365 Defender](microsoft-threat-protection.md)
- [Ativar o Microsoft 365 Defender](mtp-enable.md)
- [Gerenciar acesso e permissões](mtp-permissions.md)
