---
title: 'Etapa 5: Configurar a Prevenção de Perda de Dados do Office 365'
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
description: Compreender e implantar a Prevenção de Perda de Dados do Office 365 no Microsoft 365.
ms.openlocfilehash: f6b9291a2965552837f989c98b32674f6093b383
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073551"
---
# <a name="step-5-configure-office-365-data-loss-prevention"></a>Etapa 5: Configurar a Prevenção de Perda de Dados do Office 365

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Com políticas de prevenção de perda de dados (DLP) na Central de Conformidade e Segurança do Office 365, você pode identificar, monitorar e proteger automaticamente informações confidenciais no Microsoft 365. Com políticas de DLP, você pode:

- Identificar informações confidenciais em vários locais, como no Exchange Online, SharePoint Online, OneDrive for Business e Microsoft Teams.
- Evitar o compartilhamento acidental de informações confidenciais, bloqueando o acesso a um documento ou bloqueando o email que o contém.
- Monitorar e proteger informações confidenciais nas versões para área de trabalho do Excel, PowerPoint e Word.
- Ajudar os usuários a aprender como permanecer em conformidade sem interromper o fluxo de trabalho com notificações de emails e dicas de políticas. 
- Visualizar relatórios de DLP que mostrem conteúdo que corresponda às políticas de DLP da sua organização.

Uma política de DLP especifica:

- **Onde:** Locais como os sites do Exchange Online, SharePoint Online e OneDrive for Business, bem como bate-papos e canais do Microsoft Teams.
- **Quando:** Condições que o conteúdo deve cumprir em uma regra de política específica.
- **Como:** Ações dentro dessa regra de política de correspondência a serem aplicadas automaticamente às condições correspondentes.

Em outras palavras:

- Para um documento neste local (onde), se o conteúdo corresponder às condições de uma regra (quando), então executar automaticamente as ações especificadas na regra (como).

Para determinar o conjunto de políticas de DLP que você precisa, você deve analisar seus documentos e os tipos de dados dentro deles que precisam de proteção contra perda de dados. Por exemplo, se você é uma organização financeira nos Estados Unidos da América, deve criar uma política de DLP que evite que documentos com números de seguridade social sejam compartilhados fora da organização ou enviados por email para locais fora da organização.

Em seguida, você configura e testa as políticas com os locais de teste para garantir o comportamento correto da DLP e minimizar falsos positivos.

Por fim, você o apresenta à sua organização, informando os funcionários sobre as novas políticas e o comportamento desejado e ampliando o escopo dos locais.

Para mais informações, confira [Introdução às recomendações de política de DLP](https://docs.microsoft.com/office365/securitycompliance/get-started-with-dlp-policy-recommendations).

Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step5) correspondente desta etapa.

## <a name="next-step"></a>Próxima etapa


|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)|[Configurar o gerenciamento de acesso privilegiado do Office 365](infoprotect-configure-privileged-access-management.md)|


