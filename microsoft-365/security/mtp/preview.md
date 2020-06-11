---
title: Recursos de visualização no Microsoft Threat Protection
description: Saiba mais sobre os novos recursos no Microsoft 365 Security
keywords: visualização, nova, M365 Security, Security, 365, Capabilities
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
ms.openlocfilehash: 8a3e4b8979a346266336e2729d18465d391c28f9
ms.sourcegitcommit: efd4dd29af0ea2b71b674534de3b2dcbfd7482db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689261"
---
# <a name="microsoft-threat-protection-preview-features"></a>Recursos de prévia da proteção contra ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft


O serviço de proteção contra ameaças da Microsoft é atualizado constantemente para incluir novos recursos e aprimoramentos de recursos.

Saiba mais sobre os novos recursos da versão prévia da proteção contra ameaças da Microsoft e esteja entre os primeiros a experimentar os recursos futuros, ativando a experiência de visualização.

Para saber mais sobre os novos recursos que estão disponíveis ao público em geral, confira [novidades da Proteção contra Ameaças da Microsoft](whats-new.md).

## <a name="turn-on-preview-features"></a>Ativar recursos de visualização
Você terá acesso aos próximos recursos nos quais pode fornecer comentários para ajudar a melhorar a experiência geral antes que os recursos estejam disponíveis.

Ative a configuração de experiência de visualização para estar entre o primeiro a experimentar os recursos futuros.

1. No painel de navegação, selecione **configurações**.

2. Selecione **proteção contra ameaças da Microsoft**.


3. Selecionar **recursos**  >  **de visualização ative os recursos de visualização**. 

3. Selecione **Salvar**.

Você saberá que os recursos de visualização estão ativados ao ver que a caixa de seleção **ativar recursos de visualização** está marcada. 

## <a name="preview-features"></a>Visualização prévia de recursos
Os seguintes recursos e aprimoramentos estão disponíveis atualmente na visualização:

- **[Tabelas de identidade e aplicativo](advanced-hunting-schema-tables.md)** — obtenha visibilidade em eventos de autenticação, consultas do Active Directory e atividades relacionadas a aplicativos com as tabelas [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)e [AppFileEvents](advanced-hunting-appfileevents-table.md) no esquema de caça avançada.

- **[Ir](advanced-hunting-go-hunt.md)** para a busca, dinamizar rapidamente da investigação de um incidente para inspecionar um evento específico, um usuário, um dispositivo ou outros tipos de entidade usando recursos de [busca avançada](advanced-hunting-overview.md) baseados em consulta.

- **[Tabela EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** — Use esta tabela para criar consultas de [busca avançada](advanced-hunting-overview.md) que verificam ações executadas nos emails depois de serem entregues às caixas de correio de destinatários.

- **[Função fileprofile ()](advanced-hunting-fileprofile-function.md)** — use em suas consultas de [busca avançada](advanced-hunting-overview.md) para incorporar informações de arquivo abrangentes.
