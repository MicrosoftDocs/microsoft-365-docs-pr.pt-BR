---
title: Avaliações do Impacto sobre a Proteção dos Dados
description: Estes documentos fornecem informações aos controladores de dados, para lhes ajudar a determinar se a AIPD é necessária e, se esse for o caso, a saber que detalhes devem ser incluídos.
keywords: Avaliação do impacto sobre a proteção de dados, AIPD, Dynamics 365, Serviços Profissionais Microsoft, Microsoft 365, documentação da Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 21bda86075b2ab1e542e482e8c0a1edee640035e
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558071"
---
# <a name="data-protection-impact-assessment-for-the-gdpr"></a>Avaliação de impacto de proteção de dados do GDPR

O RGPD introduz novas regras a empresas, agências governamentais, organizações sem fins lucrativos e outras organizações que ofereçam bens e serviços a pessoas na União Europeia (UE) ou que coletam e analisam dados vinculados a residentes na UE. O RGPD se aplica onde quer que você e sua empresa estejam localizados. É possível encontrar mais informações no [tópico Resumo RGDP](gdpr.md). Este documento orienta você a informações relacionadas a Avaliações do Impacto sobre a Proteção de Dados (DPIAs) no GDPR, usando produtos e serviços da Microsoft.

## <a name="terminology"></a>Terminologia

Definições úteis para os termos do RGPD usados neste documento:

- *Controlador de Dados (Controlador*): uma pessoa jurídica, uma autoridade pública, uma agência ou outro corpo que, isoladamente ou em conjunto com outras pessoas, determina a finalidade e o meio de processamento de dados pessoais.  
- *Dados pessoais* e *entidade de dados*: qualquer informação relacionada a uma pessoa natural identificada ou identificável (entidade de dados); uma pessoa natural identificável é uma que pode ser identificada, direta ou indiretamente.  
- *Processador:* uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.  
- *Dados do cliente*: dados produzidos e armazenados nas operações do dia a dia para o trabalho em andamento.

## <a name="what-is-a-dpia"></a>O que é o DPIA?

O GDPR exige que os controladores preparem uma avaliação de impacto de proteção de dados (DPIA) para operações que são "prováveis em resultar em alto risco para os direitos e a liberdade de pessoas naturais". Não há nada inerente aos produtos e serviços da Microsoft que precisem da criação de um DPIA. No entanto, como produtos e serviços da Microsoft são altamente personalizáveis, pode ser necessário um DPIA dependendo dos detalhes da sua configuração da Microsoft. A Microsoft não tem controle e pouca ou nenhuma percepção dessas informações. Você, como um controlador de dados deve determinar os usos apropriados dos seus dados.

## <a name="dpia-in-action"></a>DPIA em ação

As diretrizes DPIA se aplicam ao Office 365, ao Azure, ao Dynamics 365 e a suporte da Microsoft e a serviços profissionais. Essas diretrizes incluem considerações sobre:

**Quando um DPIA é necessário?**

Os fatores de risco listados abaixo devem ser resolvidos quando se avaliam se deseja concluir um DPIA. Outros fatores possíveis e detalhes são encontrados na parte 1 de cada uma das diretrizes.  

- Uma avaliação sistemática e abrangente dos dados com base no processamento automático.  
- Processamento em grande escala de categorias especiais de dados pessoais (os dados revelam informações de forma exclusiva, identificando uma pessoa natural) ou de dados relacionados a condenações e delitos penais.
- Monitoramento sistemático de uma área de acesso público em grande escala.

O GDPR esclarece que: “O processamento de dados pessoais não deve ser considerado em grande escala se o processamento se referir a dados pessoais de pacientes ou clientes por um médico individual, outro profissional da saúde ou advogado. Nesses casos, a avaliação de impacto sobre a proteção dos dados não deve ser obrigatória.”

**O que é necessário para concluir um DPIA?**

Um DPIA deve fornecer informações específicas sobre o processamento desejado, que é detalhado na parte 2 das instruções. Essas informações incluem:

- Avaliação da necessidade e da proporcionalidade das operações de processamento em relação aos propósitos.  
- Uma avaliação dos riscos aos direitos e às liberdades dos indivíduos.
- As medidas desejadas para lidar com os riscos, incluindo proteções, medidas de segurança e mecanismos, para garantir a proteção de dados pessoais e demonstrar a conformidade com a RGDP.
- Propósito de processar  
- Categorias de dados pessoais processados  
- Retenção de dados  
- Localização e transferências de dados pessoais  
- Compartilhamento de dados com subprocessadores de terceiros  
- Compartilhamento de dados com terceiros independentes  
- Direitos das entidades de dados

## <a name="additional-considerations"></a>Considerações adicionais

Abaixo, detalhes específicos que podem ser relevantes para a implementação da Microsoft.

- [Office 365](gdpr-dpia-office365.md): Este documento se aplica aos aplicativos e serviços do Office 365, incluindo o, mas não se limitando ao Exchange Online, SharePoint Online, Yammer, Skype for Business e Power BI. Confira as tabelas[1](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed) e [2](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia) para obter mais detalhes.  
- [Azure](gdpr-dpia-azure.md): Aconselhamos os clientes a trabalhar com os agentes de privacidade e de aconselhamento jurídico para determinar a necessidade e conteúdo de qualquer DPIAs relacionada ao uso do Microsoft Azure.  
- [Dynamics 365](gdpr-dpia-dynamics.md): o conteúdo de um DPIA pode variar de acordo com as ferramentas Dynamics 365 que você está utilizando. Para obter detalhes específicos, consulte [Parte 2 do conteúdo de um DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-dynamics#part-2--contents-of-a-dpia).
- [Suporte da Microsoft e serviços profissionais](gdpr-dpia-prof-services.md)os serviços profissionais não realizam determinadas rotinas ou o processamento de dados automático, nem se destina a processar categorias especiais ou executar tarefas que facilitem ou exijam o monitoramento de dados acessíveis publicamente. Para mais informações, confira [Parte 1 — Determinar se a DPIA é necessária](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-1--determining-whether-a-dpia-is-needed). Os controladores devem considerar os elementos do DPIA descritos acima, juntamente com outros fatores relevantes, no contexto das implementações específicas do controlador e do uso de serviços profissionais. Para obter informações sobre serviços profissionais, consulte[Part 2 — conteúdo de um DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-prof-services#part-2--contents-of-a-dpia).

## <a name="learn-more"></a>Saiba mais

- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
