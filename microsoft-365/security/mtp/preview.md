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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 1636b1deb5f35d8286b33238a8f4bbfff0b33521
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288120"
---
# <a name="microsoft-365-defender-preview-features"></a>Recursos de visualização do Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

> [!IMPORTANT]
> As versões de visualização são fornecidas sem um contrato de nível de serviço e não são recomendadas para cargas de trabalho de produção. Certos recursos podem não ter suporte ou podem ter funcionalidades restritas.

**Aplica-se a:**
- Microsoft 365 Defender

O serviço Do Microsoft 365 Defender está sendo constantemente atualizado para incluir novos recursos e melhorias.

Saiba mais sobre os novos recursos na versão de visualização do Microsoft 365 Defender e seja um dos primeiros a experimentar os recursos futuros, a ligar a experiência de visualização.

Para obter mais informações sobre os novos recursos que estão geralmente disponíveis, consulte [Novidades no Microsoft 365 Defender.](whats-new.md)

## <a name="required-permissions"></a>Permissões obrigatórias

As contas atribuídas às seguintes funções do Azure Active Directory (Azure AD) podem ativar os recursos do Microsoft 365 Defender Preview:

- Administrador global
- Administrador de segurança
- Operador de segurança

## <a name="turn-on-preview-features"></a>Habilitar recursos de prévia

Você terá acesso aos recursos futuros sobre os que poderá fornecer comentários para ajudar a melhorar a experiência geral antes que os recursos sejam disponibilizados em geral.

Ative a configuração de experiência de visualização para ser uma das primeiras pessoas a experimentar os recursos futuros.

1. No painel de navegação, selecione **Configurações**.
2. Selecione **o Microsoft 365 Defender.**
3. Selecione **Prévia dos recursos** > **Ativar prévia dos recursos**. 
4. Selecione **Salvar**.

Você saberá que tem prévia dos recursos ativados quando vir que a caixa de seleção **Ativar prévia dos recursos** está marcada. 

## <a name="preview-features"></a>Recursos em versão prévia

Os recursos e aprimoramentos a seguir estão disponíveis em prévia:

### <a name="improved-microsoft-365-security-center"></a>Centro de segurança aprimorado do Microsoft 365
O aperfeiçoado[Centro de segurança do Microsoft 365](https://security.microsoft.com) está agora disponível em pré-visualização pública. Essa nova experiência traz o Defender para o Ponto de Extremidade, o Defender para Office 365, o Microsoft 365 Defender e muito mais para a central de segurança do Microsoft 365. Esta é a nova página de gerenciamento dos controles de segurança. [Conheça as novidades](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center).

- Relatório de análise de ameaças do **[Microsoft 365 Defender](threat-analytics.md)** - A Análise de ameaças ajuda você a responder e minimizar o impacto de ataques ativos. Você também pode aprender sobre tentativas de ataque bloqueadas pelas soluções do Microsoft 365 Defender e tomar ações preventivas que reduzam o risco de mais exposição e aumentam a resiliência. Como parte da experiência de segurança unificada, a análise de ameaças agora está disponível para os titulares de licença do Microsoft Defender para Ponto de Extremidade e do Microsoft Defender para Office E5.
- **[APIs do Microsoft 365 Defender](api-overview.md)** – as APIs de nível superior do Microsoft 365 Defender permitirão automatizar fluxos de trabalho com base no incidente compartilhado e tabelas de busca avançada. 
- **[Tome medidas na busca avançada](advanced-hunting-take-action.md)**— contenha rapidamente ameaças ou soluções de ativos comprometidos que você encontra na busca [avançada.](advanced-hunting-overview.md)
- **[Referência de esquema no portal :](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** obter informações sobre tabelas de esquema de busca avançada diretamente no centro de segurança. Além das descrições de tabelas e colunas, esta referência inclui tipos de eventos com suporte `ActionType` (valores) e consultas de exemplo.
- **[Função DeviceFromIP()](advanced-hunting-devicefromip-function.md)**— Obter informações sobre quais dispositivos receberam um endereço IP ou endereços específicos em um determinado intervalo de tempo.
