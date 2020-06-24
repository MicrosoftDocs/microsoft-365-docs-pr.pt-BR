---
title: Pré-requisitos da proteção contra ameaças da Microsoft
description: Saiba mais sobre os requisitos de licenciamento, hardware e software, além de outras configurações para proteção contra ameaças da Microsoft
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
ms.openlocfilehash: c64adf870d3669b983e11093196f59c82b1f59e0
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844901"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Pré-requisitos da proteção contra ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Saiba mais sobre licenciamento e outros requisitos para provisionamento e uso da [proteção contra ameaças da Microsoft](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Requisitos de licença
Qualquer uma dessas licenças oferece acesso aos recursos de proteção contra ameaças da Microsoft no centro de segurança do Microsoft 365 sem custo adicional:

- Microsoft 365 E5 ou a5
- Segurança da Microsoft 365 E5 Security ou a5
- Windows 10 Enterprise E5 ou a5
- Enterprise Mobility + Security (EMS) E5 ou a5 
- Office 365 E5 ou a5
- Proteção avançada contra ameaças do Microsoft Defender
- Proteção Avançada contra Ameaças do Azure 
- Segurança no aplicativo na nuvem da Microsoft
- Proteção contra Ameaças do Office 365 Advanced (Plano 2)

> [!NOTE]
> As licenças de avaliação do Office 365 atualmente não oferecem acesso à proteção contra ameaças da Microsoft.

Para obter mais informações, [consulte o Microsoft 365 Enterprise Service Plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Ainda não tem licença? [Experimentar ou comprar uma assinatura do Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Verificar suas licenças existentes
Vá para o centro de administração do Microsoft 365 ([admin.Microsoft.com](https://admin.microsoft.com/)) para exibir suas licenças existentes. No Centro de administração, acesse **Cobrança** > **Licenças**.

>[!NOTE]
> Você precisa ser atribuído à função de **administrador de cobrança** ou **leitor global** [no Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) para poder ver as informações de licença. Se tiver problemas de acesso, entre em contato com um administrador global.

## <a name="required-permissions"></a>Permissões obrigatórias
Você deve ser um **administrador global** ou um **administrador de segurança** no Azure Active Directory para ativar a proteção contra ameaças da Microsoft. Para obter a lista de funções necessárias para usar a proteção contra ameaças da Microsoft e informações sobre como o acesso a dados é regulamentado, leia sobre o [Gerenciamento de acesso à proteção contra ameaças da Microsoft](mtp-permissions.md).

## <a name="browser-requirements"></a>Requisitos de navegador
Acessar a proteção contra ameaças da Microsoft na central de segurança do Microsoft 365 usando o Microsoft Edge, o Internet Explorer 11 ou qualquer navegador da Web compatível com HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilidade para nós GCC, GCC alta e outras instituições governamentais americanas
No momento, a proteção contra ameaças da Microsoft *não* está disponível para:
- GCC (nuvem da Comunidade do governo dos EUA)
- Nuvem de comunidade do governo dos EUA (GCC alta)
- Departamento de defesa dos EUA
- Todas as instituições governamentais dos EUA com licenças comerciais

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da Proteção contra Ameaças da Microsoft](microsoft-threat-protection.md)
- [Habilitar a Proteção contra Ameaças da Microsoft](mtp-enable.md)
- [Gerenciar acesso e permissões](mtp-permissions.md)
