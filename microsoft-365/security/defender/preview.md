---
title: Recursos de visualização no Microsoft 365 Defender
description: Saiba mais sobre os novos recursos de segurança do Microsoft 365
keywords: prévia, novo, segurança do m365, segurança, 365, recursos
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
ms.openlocfilehash: b852071c3fbfe12aac62e1d309fa130a4cd81e9c
ms.sourcegitcommit: b42dd3e706ebf9638cd893b35f75eaa56dd8fd7e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53125393"
---
# <a name="microsoft-365-defender-preview-features"></a>Microsoft 365 Defender recursos de visualização

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> As versões de visualização são fornecidas sem um contrato de nível de serviço e não são recomendadas para cargas de trabalho de produção. Determinados recursos podem não ser suportados ou podem ter recursos restritos.

**Aplica-se a:**
- Microsoft 365 Defender

O Microsoft 365 Defender serviço está sendo atualizado constantemente para incluir novos aprimoramentos e recursos de recursos.

Saiba mais sobre os novos recursos na versão Microsoft 365 Defender versão de visualização e entre os primeiros a experimentar os recursos futuros, a ligar a experiência de visualização.

Para obter mais informações sobre novos recursos que geralmente estão disponíveis, consulte [Novidades no](whats-new.md)Microsoft 365 Defender .

## <a name="required-permissions"></a>Permissões obrigatórias

As contas atribuídas às seguintes funções Azure Active Directory (Azure AD) podem ativar Microsoft 365 Defender recursos de visualização:

- Administrador global
- Administrador de segurança
- Operador de segurança

## <a name="turn-on-preview-features"></a>Habilitar recursos de prévia

Você terá acesso aos recursos futuros que você pode fornecer comentários para ajudar a melhorar a experiência geral antes que os recursos geralmente estão disponíveis.

Ative a configuração de experiência de visualização para ser uma das primeiras pessoas a experimentar os recursos futuros.

1. No painel de navegação, selecione **Configurações**.
2. Selecione **Microsoft 365 Defender**.
3. Selecione **Prévia dos recursos** > **Ativar prévia dos recursos**. 
4. Selecione **Salvar**.

Você saberá que tem prévia dos recursos ativados quando vir que a caixa de seleção **Ativar prévia dos recursos** está marcada. 

## <a name="preview-features"></a>Recursos em versão prévia

Os recursos e aprimoramentos a seguir estão disponíveis em prévia:

- **[Exibir relatórios por marcas de ameaça](threat-analytics.md#view-reports-per-threat-tags)** - Marcas de ameaça ajudam você a se concentrar em categorias de ameaça específicas e revisar os relatórios mais relevantes.
- **[API de streaming](../defender-endpoint/raw-data-export.md)** - Microsoft 365 Defender suporta streaming de todos os eventos disponíveis por meio da Busca Avançada para uma conta de armazenamento do Azure e/ou Hubs de Eventos.
- **[Microsoft 365 Defender APIs](api-overview.md)** - As APIs de nível superior Microsoft 365 Defender permitirão automatizar fluxos de trabalho com base no incidente compartilhado e em tabelas avançadas de busca. 
- **[Tomar medidas na busca avançada](advanced-hunting-take-action.md)** - Conter rapidamente ameaças ou resolver ativos comprometidos que você encontra na busca [avançada](advanced-hunting-overview.md).
- **[Referência de esquema no portal](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** - Obter informações sobre tabelas avançadas de esquema de busca diretamente no centro de segurança. Além das descrições de tabela e coluna, essa referência inclui tipos de eventos com suporte `ActionType` (valores) e consultas de exemplo.
- **[Função DeviceFromIP()](advanced-hunting-devicefromip-function.md)** - Obter informações sobre quais dispositivos receberam um endereço IP específico ou endereços em um determinado intervalo de tempo.
