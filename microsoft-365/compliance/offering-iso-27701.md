---
title: ISO/IEC 27701 Sistema de Gerenciamento de Informações de Privacidade (PIMS)
description: O padrão ISO/IEC 27701 para oferecer suporte à responsabilidade da privacidade e à conformidade regulamentar entre os controladores e processadores na cadeia de fornecimento de processamento de dados globais.
keywords: Microsoft 365, conformidade, ofertas
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 8a4f59a817e8ddd38ee8132e7028a3357d15d578
ms.sourcegitcommit: daad5f2f1994a812c2b9c78e7dd148d10c51f61d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "44254164"
---
# <a name="isoiec-27701-privacy-information-management-system-pims"></a>PIMS (Sistema de Gerenciamento de Informações de Privacidade) do ISO/IEC 27701

## <a name="privacy-information-management-system-pims-overview"></a>Visão geral do Sistema de Gerenciamento de Informações de Privacidade (PIMS)

A Regulamentação Geral de Proteção de Dados da União Europeia (GDPR) trouxe uma nova era de conformidade e regulamentação global da privacidade. Mais regulamentações de privacidade, muitas inspiradas pela GDPR, foram aprovadas em diferentes jurisdições (seja no mercado/setor ou local físico). Como resultado, as organizações devem implementar políticas e procedimentos para garantir a conformidade com a lista crescente de regulamentações de privacidade. Além disso, estamos coletivamente no meio de uma transformação digital rápida onde a coleta de dados e o processamento estão aumentando drasticamente. O crescimento simultâneo no volume de dados e nos requisitos regulatórios referentes a esses dados torna a conformidade cada vez mais complexa para todos os tipos de organizações.

O novo padrão internacional [ISO/IEC 27701 Sistema de Gerenciamento de Informações de Privacidade (PIMS) ](https://www.iso.org/standard/71670.html) (conhecido anteriormente como ISO/IEC 27552 durante o período de rascunho), ajuda as organizações a reconciliar os requisitos regulatórios de privacidade. O padrão descreve um conjunto abrangente de controles operacionais que pode ser mapeado para vários regulamentos, incluindo a GDPR. Depois de mapeados, o controles operacionais PIMS são implementados por profissionais da privacidade e auditados por auditores internos ou de terceiros, resultando em uma certificação e em uma evidência abrangente de conformidade.

## <a name="compliance-challenges"></a>Desafios de conformidade

Esperar que os fornecedores certifiquem-se em relação ao PIMS será eficaz para estabelecer práticas de privacidade responsáveis por fornecedores e parceiros, independentemente do tamanho da sua organização. O ISO/IEC 27701 aborda os três principais desafios de conformidade:

- **Muitos requisitos regulamentares para manipular**: a reconciliação de vários requisitos regulamentares por meio do uso de um conjunto de controles operacionais universais permite uma implementação consistente e eficiente.
- **Caro demais para auditar cada regulamentação**: auditores, tanto internos quanto de terceiros, podem avaliar a conformidade usando um conjunto de controle universal dentro de um único ciclo de auditoria.
- **A promessa de conformidade sem evidência é potencialmente arriscada**: acordos comercias que envolvem a movimentação de informações pessoais podem garantir a certificação de conformidade.

## <a name="too-many-regulatory-requirements-to-juggle"></a>Muitos requisitos regulamentares para manipular

O ISO/IEC 27701 inclui um anexo que contém os controles operacionais do padrão que é mapeado em relação aos requisitos relevantes na GDPR para controladores e processadores. Esse mapeamento é apenas um exemplo de como as regulamentações de privacidade podem ser operacionalizadas na estrutura ISO. Conforme os mapeamentos adicionais com outras regulamentações tornarem-se disponíveis e forem validados, os controles operacionais do padrão poderão ser transferidos diretamente da análise regulatória para a implementação. Essa estrutura universal permite que as organizações operacionalizem de forma confiável os requisitos regulamentares relevantes sem ‘reinventar a roda’. Um projeto de software livre pendente está em andamento para permitir que a comunidade de privacidade mapeie outras regulamentações e valide os mapeamentos existentes. Fique atento aos comunicados.

## <a name="too-costly-to-audit-regulation-by-regulation"></a>Caro demais para auditar cada regulamentação

Vamos voltar para a nossa declaração inicial no cenário atual. Conforme mais regulamentações entram em vigor em várias jurisdições, a pressão para fornecer evidências de conformidade também aumentará. No entanto, os custos de certificações regulatórias distintas tornam-se inviáveis se cada regulamentação necessitar uma auditoria exclusiva. Ao descrever um conjunto de controles universais, o PIMS também descreve uma estrutura de conformidade universal para fazer a auditoria, e, potencialmente certificar para vários requisitos regulamentares.

É importante reconhecer que uma certificação oficial GDPR exige decisões pendentes para serem tomadas pelos reguladores europeus. Apesar do alinhamento entre PIMS e GDPR ser evidente, uma certificação PIMS deve ser usada como evidência de conformidade de GDPR, não como uma certificação oficial de GDPR até que as decisões regulamentares sejam finalizadas.

## <a name="promises-of-compliance-without-proof-is-potentially-risky"></a>As promessas de conformidade sem evidência são potencialmente arriscadas

As organizações modernas envolvem transferências completas de dados com uma ampla rede de parceiros de negócios, incluindo organizações de parceiros ou controladores conjuntos, processadores como provedores de nuvem e subprocessadores, como fornecedores que oferecem suporte a esses mesmos processadores. Se você não estiver em conformidade com as regulamentações em qualquer parte desta rede, isso pode gerar problemas de conformidade em cascata na cadeia de fornecimento. Esse é o local onde a verificação de conformidade pode ser valiosa além da garantia oferecida pelos termos contratuais entre essas organizações. Como a economia global determina que a maioria dessas organizações está espalhada pelo mundo, é prático usar um padrão internacional do ISO para gerenciar a conformidade em toda a rede.

Essa dependência na conformidade aumenta a importância da certificação para o padrão. Embora nem todas as empresas e organizações precisem obter essa certificação, a maioria se beneficiará de parceiros e fornecedores que o fazem, especialmente quando estão envolvidos volumes sensíveis ou altos de processamento de dados.

## <a name="building-blocks-of-the-standard"></a>Blocos de construção do padrão

O PMS foi criado a partir de um dos padrões internacionais mais adotados de gerenciamento de segurança de informações, [ISO/IEC 27001](offering-iso-27001.md). Se a sua organização já estiver familiarizada com o ISO/IEC 27001, será mais lógico e eficaz integrar os novos controles de privacidade do PIMS. Isso significa que a implementação e a auditoria de ambos será mais barata e mais fácil de obter.

Pontos principais no ISO/IEC 27001 e PIMS:

- O ISO/IEC 27001 é um dos padrões ISO mais usados do mundo.
- O PIMS inclui os novos controles de controlador e processador que ajudam a fechar a lacuna entre privacidade e segurança e oferece um ponto de integração entre o que pode ser duas funções separadas em organizações.
- Privacidade depende da segurança. Da mesma forma, PIMS depende do ISO/IEC 27001 para o gerenciamento da segurança. A certificação para PIMS deve ser obtida como uma extensão da certificação ISO/IEC 27001 e não pode ser obtida de forma independente.

## <a name="what-should-your-organization-do-with-pims"></a>O que a sua organização deve fazer com o PIMS?

Independentemente do tamanho da sua organização e se for uma controladora ou processadora, sua organização deve considerar a obtenção da certificação, seja para sua própria organização ou solicitando-a de fornecedores com base na suas necessidades de negócios. Isso se aplica principalmente a processadores, subprocessadores e controladores conjuntos que estejam processando dados pessoais confidenciais ou de grande quantidade. De qualquer forma, sua organização deve avaliar suas necessidades comerciais para determinar se a certificação para seus próprios produtos e serviços é adequada.

## <a name="microsoft-in-scope-cloud-services"></a>Serviços de nuvem no Escopo da Microsoft 

- Azure, Azure Government e Azure Alemanha
- Azure DevOps Services
- Microsoft Cloud App Security
- Dynamics 365, Dynamics 365 Government e Dynamics 365 Germany
- Microsoft Graph
- Bot do Microsoft Healthcare
- Intune
- Área de Trabalho Gerenciada da Microsoft
- Power Automate (anteriormente Microsoft Flow) 
- PowerApps
- Power BI
- Power BI incorporado
- Agentes virtuais do Power
- Microsoft Stream
- Especialistas em ameaças da Microsoft
- Proteção avançada contra ameaças do Windows Defender


## <a name="audits-reports-and-certificates"></a>Auditorias, relatórios e certificados

- [Azure, Dynamics 365 e Online Services: certificação ISO27701](https://aka.ms/azureiso27701cert)
- [Azure, Dynamics 365 e Online Services: relatório de avaliação ISO27701](https://aka.ms/azureiso27701report)

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>Use a Pontuação de Conformidade da Microsoft para avaliar seu risco

A [Pontuação de Conformidade da Microsoft](compliance-score.md) é um recurso de visualização no [Centro de conformidade do Microsoft 365](microsoft-365-compliance-center.md) para ajudá-lo a entender a postura de conformidade da sua organização e realizar ações para ajudar a reduzir os riscos. Depois de [configurar a Pontuação de Conformidade](compliance-score-setup.md), selecione o modelo pré-configurado [ISO 27701](https://go.microsoft.com/fwlink/?linkid=2117915) da lista suspensa **Template** para ajudar a sua organização a atender aos requisitos dessa regulamentação.

## <a name="resources"></a>Recursos

- [ISO/IEC 27701 (PIMS) para compra](https://www.iso.org/standard/71670.html)
- [White paper de BSI e conteúdo sobre PIMS](https://www.bsigroup.com/globalassets/localfiles/en-gb/data-protection/bsi_privacy_matters_white_paper-web.pdf)
- [Vídeo de introdução ao PIMS](https://www.microsoft.com/videoplayer/embed/RE3uaQJ)
- [Conformidade no Centro de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
