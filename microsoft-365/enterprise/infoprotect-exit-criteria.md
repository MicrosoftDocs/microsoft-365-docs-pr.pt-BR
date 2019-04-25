---
title: Critérios de saída da infraestrutura de proteção de informações
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Examinar os critérios da infraestrutura e dos serviços com base na proteção de informações a fim de garantir que sua configuração atenda aos requisitos do Microsoft 365 Enterprise.
ms.openlocfilehash: 681b3bb2500680b4f5d5801486347aec1b801714
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283688"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Critérios de saída da infraestrutura de proteção de informações

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Verifique se a sua infraestrutura de proteção de informações atende aos seguintes critérios necessários e que você considerou aqueles que são opcionais.

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Obrigatório: os níveis de segurança e proteção de informações foram definidos em para a sua organização

Você planejou e determinou os níveis de segurança necessários para a sua organização. Esses níveis definem o patamar mínimo de segurança e outros níveis para informações cuja confidencialidade aumenta gradualmente, assim como a segurança de dados exigida para cada uma delas.

No mínimo, você está usando três níveis de segurança:

- Linha de base
- Confidencial
- Altamente controlada

Se necessário, a [Etapa 1](infoprotect-define-sec-infoprotect-levels.md) pode ajudá-lo a atender a esse requisito. 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>Obrigatório: configuração de segurança aprimorada para Microsoft 365 

As seguintes configurações foram habilitadas para a [segurança aprimorada do Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Políticas de gerenciamento de ameaças na Central de segurança do Microsoft 365
- Configurações adicionais para todos os locatários do Exchange Online
- Políticas de compartilhamento de todos os locatários no SharePoint Admin Center
- Configurações do Azure Active Directory (Azure AD)

Você também [habilitou a Proteção Avançada contra Ameaças (ATP) do Office 365 para SharePoint, OneDrive e Microsoft Teams](https://docs.microsoft.com/pt-BR/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Se necessário, a [Etapa 3](infoprotect-configure-increased-security-office-365.md) pode ajudá-lo a atender a esse requisito. 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Opcional: a classificação está configurada em seu ambiente

Você trabalhou com o seu departamento jurídico e de conformidade para desenvolver uma classificação apropriada e um esquema de identificação de governança de dados e políticas de segurança para a sua organização. 

Essa políticas correspondem a configuração e implantação de:

- Tipos de dados confidenciais
- Rótulos de retenção
- Rótulos de confidencialidade
- Rótulos da Proteção de Informações do Azure

Se necessário, a [Etapa 2](infoprotect-configure-classification.md) pode ajudá-lo a atender a esse requisito. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Opcional: configurar o gerenciamento de acesso privilegiado no Office 365

Você usou as informações do tópico [Configurar gerenciamento de acesso privilegiado do Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar uma ou mais políticas de acesso privilegiado em sua organização. Você configurou essas políticas e o acesso just-in-time está habilitado para acessar dados confidenciais ou configurações críticas.

Se necessário, a [Etapa 4](infoprotect-configure-privileged-access-management.md) pode ajudá-lo a atender a esse requisito. 

## <a name="results-and-next-steps"></a>Resultados e próximas etapas

Sua infraestrutura de proteção de informações para o Microsoft 365 Enterprise usa níveis de segurança definidos, segurança aprimorada para o Office 365, classificação usando tipos de dados e rótulos confidenciais e gerenciamento de acesso privilegiado.

Se você está seguindo a implantação de ponta a ponta do Microsoft 365 Enterprise, você está pronto para fazer suas [cargas de trabalho e seus cenários](deploy-workloads.md) aproveitarem todos os recursos e configurações de sua infraestrutura de base.
