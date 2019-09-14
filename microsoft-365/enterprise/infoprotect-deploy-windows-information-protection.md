---
title: 'Etapa 4: configurar a Proteção de Informações do Windows'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Compreender e implantar a Proteção de Informações do Windows no Microsoft 365.
ms.openlocfilehash: a89d61367d3e07cabff0576f16fa359a06dc1ecc
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981812"
---
# <a name="step-4-configure-windows-information-protection"></a>Etapa 4: configurar a Proteção de Informações do Windows

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Com mais dispositivos pessoais sendo usados para o trabalho, há um risco maior de aplicativos e dispositivos vazarem dados da organização privada. Por exemplo, um funcionário inadvertidamente envia uma imagem de um plano de marketing para um produto futuro para um site de mídia social ou salva um arquivo contendo informações altamente confidenciais em seu armazenamento em nuvem pública. 

A Proteção de Informações do Windows (WIP) ajuda a proteger contra esses tipos de vazamento de dados em dispositivos Windows 10. Para obter mais informações, confira [Proteger seus dados corporativos usando o WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

No Microsoft 365 Enterprise, o WIP é uma combinação do Windows 10 Enterprise e do Microsoft Intune, incluído na sua assinatura. 

Para implantar o WIP na sua organização com o Microsoft 365 Enterprise:

1. Inscreva seus dispositivos do Windows no Intune. Você deveria ter feito isso na [Fase 5: Gerenciamento de Dispositivos Móveis](mobility-infrastructure.md).
2. Crie uma [política do Intune para WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).
  - Certifique-se de que você tenha preenchido sua lista de aplicativos protegidos.
  - Escolha o seu nível de proteção WIP.

Você também pode usar o WIP com o [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm). 

Veja [Práticas recomendadas de WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip) para mais informações.

Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step4) correspondente desta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Configurar a Prevenção de Perda de Dados do Office 365](infoprotect-data-loss-prevention.md)|


