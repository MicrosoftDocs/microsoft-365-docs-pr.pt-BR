---
title: 'Etapa 2: Configurar classificações de ambiente'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar várias maneiras para classificar os dados em sua organização.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864877"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Etapa 2: Configurar classificações de ambiente

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Nesta etapa, você trabalha com as equipes de conformidade e jurídica para definir um esquema de classificação dos dados da sua organização.

## <a name="microsoft-classifications"></a>Classificações da Microsoft

O Microsoft 365 inclui três tipos de classificação:

- Tipos de informações confidenciais no Office 365
- Rótulos do Office 365
- Proteção e rótulos de Proteção de Informações do Azure

### <a name="sensitive-information-types-for-office-365"></a>Tipos de informações confidenciais no Office 365

Os tipos de informações confidenciais do Office 365 definem como os processos automatizados, como a pesquisa, reconhecem os tipos específicos de informações, como os números da segurança social e de cartões de crédito. Usamos os tipos de informações confidenciais para localizar os dados confidenciais e aplicar regras e políticas de prevenção contra perda de dados para proteger esses dados. Saiba mais em [Visão geral das políticas de prevenção contra perda de dados](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). Por exemplo, os tipos de informações confidenciais são especialmente úteis para atender aos requisitos de regulamentação e conformidade, como o GDPR (Regulamento Geral sobre a Proteção de Dados).

### <a name="office-365-labels"></a>Rótulos do Office 365
É possível usar os rótulos do Office 365 para dados pessoais e para arquivos secretos comerciais e altamente controlados armazenados no SharePoint Online e no OneDrive for Business. Para saber mais, inclusive como criá-los, confira [Visão geral de rótulos](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).

Se decidir usar rótulos do Office 365, configure pelo menos um rótulo para cada nível de proteção. Por exemplo, crie três rótulos para:

- Linha de base
- Confidencial
- Altamente controlado

### <a name="azure-information-protection-labels-and-protection"></a>Proteção e rótulos de Proteção de Informações do Azure

É possível usar rótulos de Proteção de Informações do Azure para classificar e, opcionalmente, proteger documentos e emails da organização. Eles podem ser aplicados aos documentos que estão armazenados fora do Office 365 e também podem ser aplicados automaticamente pelos administradores que definem as regras e as condições, manualmente por usuários ou uma combinação onde os usuários recebem recomendações.

Para planejar e implantar a proteção e os rótulos de Proteção de Informações do Azure, faça o seguinte:

1. Revise os [Requisitos de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Siga o [Roteiro de implantação para classificação, rotulamento e proteção](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Veja mais informações na [Biblioteca de documentação de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/).

## <a name="classification-for-gdpr"></a>Classificação para GDPR

Confira um exemplo de esquema de classificação que inclui os dados pessoais para GDPR em [Desenvolver um esquema de classificação para dados pessoais](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).

|||
|:-------|:-----|
|![Guias do Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: Classificação de dados](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step3) correspondente desta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Configurar mais segurança no Office 365](infoprotect-configure-increased-security-office-365.md)|

