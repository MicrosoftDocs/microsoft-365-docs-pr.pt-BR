---
title: 'Etapa 2: Configurar classificações de ambiente'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Entender e configurar várias maneiras para classificar os dados em sua organização.
ms.openlocfilehash: 5323e4f682e8a530601308877423502f64878a4c
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400085"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Etapa 2: Configurar classificações de ambiente

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Nesta etapa, você trabalha com as equipes de conformidade e jurídica para definir um esquema de classificação dos dados da sua organização.

## <a name="microsoft-365-classification-types"></a>Tipos de classificação do Microsoft 365

O Microsoft 365 inclui quatro tipos de classificação:

- Tipos de informações confidenciais
- Rótulos de retenção
- Rótulos de confidencialidade
- Proteção e rótulos de Proteção de Informações do Azure

### <a name="sensitive-information-types"></a>Tipos de informações confidenciais

Tipos de informações confidenciais para o Microsoft 365 definem como processos automatizados como pesquisar e reconhecer tipos específicos de informações. Isso inclui informações confidenciais de funcionários ou dados de clientes como números do serviço de saúde e números de cartão de crédito. Você usa tipos de informações confidenciais para encontrar dados confidenciais e aplica as regras e políticas da prevenção contra perda de dados (DLP) para protegê-los. Para saber mais, confira [o que uma política de DLP contém](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains). 

Tipos de informações confidenciais são especialmente úteis para cumprir exigências de conformidade e regulatórias, como para o Regulamento Geral de Proteção de Dados (GDPR).

### <a name="retention-labels"></a>Rótulos de retenção

Parte de definir uma estratégia de governança de dados é decidir por quanto tempo tipos específicos de documentos ou documentos com conteúdos específicos devem ser retidos em conformidade com políticas de organização e regulamentos regionais. Por exemplo, alguns tipos de documentos devem ser retidos por um período específico de tempo e depois apagados e outros devem ser retidos por tempo indeterminado.

Para documentos armazenados no Microsoft 365, você define e aplica rótulos de retenção a documentos e dados armazenados no email do Exchange, SharePoint, OneDrive for Business e mensagens de canal e chat do Teams. 

Se você usar rótulos de retenção, deve configurar um rótulo para cada categoria de arquivo que precisa de uma política de retenção aplicada. No rótulo de retenção, você pode especificar:

- Um conjunto de descritores para os arquivos (por exemplo, por departamento empresarial, categoria de arquivo ou regulamento).
- As configurações de retenção para os arquivos que possuem um rótulo de retenção anexado, como horários e comportamentos de retenção depois que atingirem o tempo de retenção.

Você também pode aplicar automaticamente um rótulo de retenção aos arquivos configurando um site do SharePoint online para aplicar um rótulo de retenção padrão para todos os novos documentos no site. 

Para mais informações, confira a [visão geral dos rótulos de retenção](https://docs.microsoft.com/office365/securitycompliance/labels).

### <a name="sensitivity-labels"></a>Rótulos de confidencialidade

Parte de proteger e implementar a segurança para tipos específicos de documentos ou documentos com conteúdos específicos é marcá-los com um rótulo para que a segurança adicional possa ser aplicada. Com rótulos de confidencialidade no Microsoft 365, você pode:

- Impor configurações de proteção como criptografia, permissões ou adicionar uma marca d´água.
- Evitar que conteúdo confidencial saia de sua organização em dispositivos executando o Windows, usando a proteção de pontos de extremidade no Microsoft Intune. 
- Usar a proteção de pontos de extremidade da Proteção de Informações do Windows (WIP) para evitar que um conteúdo seja copiado para um aplicativo de terceiros, como Twitter ou Gmail, ou que seja copiado para armazenamento removível, como uma unidade USB. 
- Usar Segurança no Aplicativo de Nuvem da Microsoft para proteger conteúdo em aplicativos e serviços de terceiros. 
- Classificar conteúdo sem usar nenhuma configuração de proteção.

Se você usar rótulos de confidencialidade, você deve configurar um rótulo para cada nível de segurança e proteção de informações. Por exemplo, crie três rótulos de confidencialidade para:

- Linha de base
- Confidencial
- Altamente controlado

Para saber mais, confira a [visão geral de rótulos de confidencialidade](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).

### <a name="azure-information-protection-labels-and-protection"></a>Proteção e rótulos de Proteção de Informações do Azure

Você pode usar os rótulos de Proteção de Informações do Azure para classificar e, opcionalmente, proteger os documentos e emails da sua organização. Esses rótulos podem se aplicar a documentos que são armazenados fora do Microsoft 365. Esses rótulos podem ser aplicados automaticamente por administradores que definem regras e condições manualmente por usuários, ou uma combinação onde usuários recebem recomendações.

Para planejar e implantar a proteção e os rótulos de Proteção de Informações do Azure, faça o seguinte:

1. Revise os [Requisitos de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Siga o [Roteiro de implantação para classificação, rotulamento e proteção](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Veja mais informações na [Biblioteca de documentação de Proteção de Informações do Azure](https://docs.microsoft.com/information-protection/).

Rótulos existentes de Proteção de Informações do Azure funcionam perfeitamente com rótulos de confidencialidade. Por exemplo, você pode manter seus rótulos existentes de Proteção de Informações do Azure e os rótulos que são aplicados aos documentos e email.

Se você tem tanto os rótulos de confidencialidade como os rótulos de Proteção de Informações do Azure, você deve [migrar seus rótulos de Proteção de Informações do Azure para rótulos de confidencialidade](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).

## <a name="example-classification-for-gdpr"></a>Exemplo: Classificação para GDPR

Confira um exemplo de esquema de classificação que inclui os dados pessoais para GDPR em [Desenvolver um esquema de classificação para dados pessoais](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).

## <a name="take-it-for-a-test-drive"></a>Levar para um test drive

|||
|:-------|:-----|
|![Guias de laboratório de teste da Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guia do Laboratório de Teste: Classificação de dados](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step2) correspondente desta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Configurar mais segurança no Office 365](infoprotect-configure-increased-security-office-365.md)|

