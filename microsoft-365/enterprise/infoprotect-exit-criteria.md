---
title: Critérios de saída da infraestrutura de proteção de informações
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Examinar os critérios da infraestrutura e dos serviços com base na proteção de informações a fim de garantir que sua configuração atenda aos requisitos do Microsoft 365 Enterprise.
ms.openlocfilehash: 10d7b3b888999b65e5faff81e9a2d32e595294cf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865207"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Critérios de saída da infraestrutura de proteção de informações

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Antes de concluir a infraestrutura de base, verifique se a infraestrutura de proteção de informações atende a estes requisitos. 

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Obrigatório: os níveis de segurança e proteção de informações foram definidos em para a sua organização

Você planejou e determinou os níveis de segurança necessários para a sua organização. Esses níveis definem o patamar mínimo de segurança e outros níveis para informações cuja confidencialidade aumenta gradualmente, assim como a segurança de dados exigida para cada uma delas.

No mínimo, você está usando três níveis de segurança:

- Linha de base
- Confidencial
- Altamente controlada

Se necessário, a [Etapa 1](infoprotect-define-sec-infoprotect-levels.md) pode ajudá-lo a atender a esse requisito. 

<a name="crit-infoprotect-step4"></a>
## <a name="required-increased-security-for-office-365-is-configured"></a>Obrigatório: a segurança elevada está configurada no Office 365

Você definiu as seguintes configurações para obter uma segurança elevada, com base nas informações sobre como [configurar seu locatário do Office 365 para aumentar a segurança](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):

- Políticas de gerenciamento de ameaças no Centro de Conformidade e Segurança do Office 365
- Configurações adicionais para todos os locatários do Exchange Online
- Políticas de compartilhamento de todos os locatários no SharePoint Admin Center
- Configurações no Azure Active Directory

Você também [habilitou a Proteção Avançada contra Ameaças (ATP) do Office 365](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).

Se necessário, a [Etapa 3](infoprotect-configure-increased-security-office-365.md) pode ajudá-lo a atender a esse requisito. 

<a name="crit-infoprotect-step3"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Opcional: a classificação está configurada em seu ambiente

Você e o departamento jurídico e de conformidade trabalharam em conjunto para desenvolver uma classificação apropriada e um esquema de identificação de dados em sua organização, que incluem o seguinte:

- tipos de dados confidenciais;
- Rótulos do Office 365
- Rótulos da Proteção de Informações do Azure

Se necessário, a [Etapa 2](infoprotect-configure-classification.md) pode ajudá-lo a atender a esse requisito. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Opcional: configurar o gerenciamento de acesso privilegiado no Office 365

Você usou as informações ano tópico [Configurar o gerenciamento de acesso privilegiado no Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) para habilitar o acesso privilegiado e criar uma ou mais políticas de acesso privilegiado na sua organização do Office 365. Você configurou essas políticas e o acesso Just-In-Time está habilitado para acesso a dados confidenciais ou acesso a definições de configuração crítica.

Se necessário, a [Etapa 4](infoprotect-configure-privileged-access-management.md) pode ajudá-lo a atender a esse requisito. 

## <a name="next-step"></a>Próxima etapa

Agora já está tudo pronto para a implantação das [cargas de trabalho e cenários](deploy-workloads.md), como o Microsoft Teams e o Exchange Online, que são executadas acima da infraestrutura de base do Microsoft 365 Enterprise.
