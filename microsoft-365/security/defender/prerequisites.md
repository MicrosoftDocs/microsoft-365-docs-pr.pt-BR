---
title: Microsoft 365 Pré-requisitos do Defender
description: Saiba mais sobre os requisitos de licenciamento, hardware e software e outras configurações do Microsoft 365 Defender
keywords: requisitos, pré-requisitos, hardware, software, navegador, Microsoft 365 Defender, M365, licença, E5, A5, EMS, compra
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 69345a0db42ec838dc0758cdb0e93a49a8ba6cfd
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259398"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Pré-requisitos do Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Saiba mais sobre licenciamento e outros requisitos para provisionamento e uso [Microsoft 365 Defender](microsoft-365-defender.md).

## <a name="licensing-requirements"></a>Requisitos de licença
Qualquer uma dessas licenças oferece acesso aos recursos Microsoft 365 Defender no centro de segurança Microsoft 365 sem custo adicional:

- Microsoft 365 E5 ou A5
- Microsoft 365 E3 com o Microsoft 365 E5 Security complemento
- Microsoft 365 A3 com o complemento Microsoft 365 A5 Security
- Windows 10 Enterprise E5 ou A5
- Enterprise Mobility + Security (EMS) E5 ou A5 
- Office 365 E5 ou A5
- Microsoft Defender para Ponto de Extremidade
- Microsoft Defender para Identidade? 
- Microsoft Cloud App Security
- Microsoft Defender para Office 365 (Plano 2)

Para obter mais informações, [consulte o Microsoft 365 Enterprise de serviço](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Ainda não tem licença? [Experimentar ou comprar uma assinatura do Microsoft 365](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>Verificar suas licenças existentes
Vá para Microsoft 365 centro de administração ([admin.microsoft.com](https://admin.microsoft.com/)) para exibir suas licenças existentes. No Centro de administração, acesse **Cobrança** > **Licenças**.

>[!NOTE]
> Você precisa ser atribuído ao administrador de **Cobrança** ou à função de leitor **global** no [Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver as informações de licença. Se tiver problemas de acesso, entre em contato com um administrador global.

## <a name="required-permissions"></a>Permissões obrigatórias
Você deve ser um **administrador global ou** um administrador **de** segurança Azure Active Directory ativar o Microsoft 365 Defender. Para obter a lista de funções necessárias para usar o Microsoft 365 Defender e informações sobre como o acesso aos dados é regulado, leia sobre como gerenciar o acesso ao [Microsoft 365 Defender](m365d-permissions.md).

## <a name="browser-requirements"></a>Requisitos de navegador
Acesse Microsoft 365 Defender no centro de segurança Microsoft 365 usando Microsoft Edge, Internet Explorer 11 ou qualquer navegador da Web compatível com HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilidade para GCC, GCC Alta e outras instituições governamentais dos EUA
Atualmente, o Microsoft 365 Defender *não* está disponível para:
- US Nuvem da Comunidade Governamental (GCC)
- Us Nuvem da Comunidade Governamental Alta (GCC Alta)
- Departamento de Defesa dos EUA
- Todas as instituições governamentais dos EUA com licenças comerciais

## <a name="related-topics"></a>Tópicos relacionados
- [Microsoft 365 Visão geral do Defender](microsoft-365-defender.md)
- [Ativar o Microsoft 365 Defender](m365d-enable.md)
- [Gerenciar acesso e permissões](m365d-permissions.md)
