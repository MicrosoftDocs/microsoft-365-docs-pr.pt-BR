---
title: Pré-requisitos do Microsoft 365 defender
description: Saiba mais sobre os requisitos de licenciamento, hardware e software e outras definições de configuração para o Microsoft 365 defender
keywords: requisitos, pré-requisitos, hardware, software, navegador, MTP, M365, licença, e5, a5, EMS, compra
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 415cdb79a6aa9371ee2f07de579cfb2f873f1acb
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844771"
---
# <a name="microsoft-365-defender-prerequisites"></a>Pré-requisitos do Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

Saiba mais sobre licenciamento e outros requisitos para provisionamento e uso [do Microsoft 365 defender](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Requisitos de licença
Qualquer uma dessas licenças oferece acesso aos recursos do Microsoft 365 defender no centro de segurança da Microsoft 365 sem custo adicional:

- Microsoft 365 E5 ou a5
- Segurança da Microsoft 365 E5 Security ou a5
- Windows 10 Enterprise E5 ou a5
- Enterprise Mobility + Security (EMS) E5 ou a5 
- Office 365 E5 ou a5
- Microsoft Defender para Ponto de Extremidade
- Microsoft Defender para Identidade 
- Segurança no aplicativo na nuvem da Microsoft
- Defender para Office 365 (plano 2)

> [!NOTE]
> As licenças de avaliação do Office 365 atualmente não oferecem acesso ao Microsoft 365 defender.

Para obter mais informações, [consulte o Microsoft 365 Enterprise Service Plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Ainda não tem licença? [Experimentar ou comprar uma assinatura do Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Verificar suas licenças existentes
Vá para o centro de administração do Microsoft 365 ([admin.Microsoft.com](https://admin.microsoft.com/)) para exibir suas licenças existentes. No Centro de administração, acesse **Cobrança** > **Licenças**.

>[!NOTE]
> Você precisa ser atribuído à função de **administrador de cobrança** ou **leitor global** [no Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver as informações de licença. Se tiver problemas de acesso, entre em contato com um administrador global.

## <a name="required-permissions"></a>Permissões obrigatórias
Você deve ser um **administrador global** ou um **administrador de segurança** no Azure Active Directory para ativar o Microsoft 365 defender. Para obter a lista de funções necessárias para usar o Microsoft 365 defender e informações sobre como o acesso a dados é regulamentado, leia sobre como [gerenciar o acesso ao Microsoft 365 defender](mtp-permissions.md).

## <a name="browser-requirements"></a>Requisitos de navegador
Acesse o Microsoft 365 defender na central de segurança do Microsoft 365 usando o Microsoft Edge, o Internet Explorer 11 ou qualquer navegador da Web compatível com HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilidade para nós GCC, GCC alta e outras instituições governamentais americanas
No momento, o Microsoft 365 defender *não* está disponível para:
- GCC (nuvem da Comunidade do governo dos EUA)
- Nuvem de comunidade do governo dos EUA (GCC alta)
- Departamento de defesa dos EUA
- Todas as instituições governamentais dos EUA com licenças comerciais

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral do Microsoft 365 defender](microsoft-threat-protection.md)
- [Ativar o Microsoft 365 defender](mtp-enable.md)
- [Gerenciar acesso e permissões](mtp-permissions.md)
