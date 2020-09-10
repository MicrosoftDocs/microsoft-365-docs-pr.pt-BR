---
title: North American Electric Reliability Corporation (NERC)
description: O Azure e o Azure Governamental são indicados para entidades registradas que implantam determinadas cargas de trabalho na nuvem sujeitas aos padrões NERC CIP.
keywords: Microsoft 365, conformidade, ofertas
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 7001a17af7932a7aafa7cceac207b772b42b55d9
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417159"
---
# <a name="north-american-electric-reliability-corporation-nerc"></a>North American Electric Reliability Corporation (NERC)

## <a name="about-the-nerc"></a>Sobre a NERC

A [North American Electric Reliability Corporation](https://www.nerc.com/) (NERC) é uma autoridade reguladora sem fins lucrativos cuja missão é garantir a confiabilidade do sistema elétrico de distribuição em massa na América do Norte. A NERC está sujeita à supervisão da Comissão Federal de Regulação Energética dos EUA (FERC) e das autoridades governamentais do Canadá. Em 2006, a FERC concedeu à NERC a designação de Organização de Confiabilidade Elétrica (ERO) consoante a Lei de Política Energética de 2005 (Lei Pública dos EUA 109-58). A NERC desenvolve e aplica padrões de confiabilidade conhecidos como padrões NERC [CIP (Critical Infrastructure Protection)](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx).

## <a name="microsoft-and-the-nerc-cip-standard"></a>Microsoft e o padrão NERC CIP

A North American Electric Reliability Corporation (NERC) é uma autoridade reguladora sem fins lucrativos cuja missão é garantir a confiabilidade do sistema elétrico de distribuição em massa na América do Norte. A NERC está sujeita à supervisão da Comissão Federal de Regulação Energética dos EUA (FERC) e das autoridades governamentais do Canadá. Em 2006, a FERC concedeu à NERC a designação de Organização de Confiabilidade Elétrica (ERO) consoante a Lei de Política Energética de 2005 (Lei Pública dos EUA 109-58). A NERC desenvolve e aplica padrões de confiabilidade conhecidos como padrões NERC [CIP (Critical Infrastructure Protection)](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx).

Todos os proprietários, operadores e usuários de sistemas de energia em massa devem [obedecer os padrões NERC CIP](https://www.nerc.com/pa/comp/Pages/default.aspx). É exigido que essas entidades se registrem na NERC. Os provedores de serviços de nuvem e terceiros não estão sujeitos aos padrões NERC CIP. No entanto, os padrões CIP incluem metas que devem ser consideradas quando [Entidades registradas](https://www.nerc.com/pa/comp/Pages/Registration.aspx) usam fornecedores na operação do BES (Sistema elétrico de distribuição em massa). Os clientes da Microsoft que operam o BES são totalmente responsáveis por garantir sua própria conformidade com os padrões NERC CIP. Nem o Microsoft Azure nem o Microsoft Azure Governamental constituem um BES ou Ativo Cibernético do BES.

Conforme declarado pela NERC no atual conjunto de [Padrões CIP](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf) e no [Glossário de Termos](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf) da NERC, os Ativos Cibernéticos do BES desempenham funções em tempo real de monitoramento ou controle do BES e afetariam a operação confiável do BES 15 minutos após seu comprometimento. Para acomodar adequadamente os Ativos Cibernéticos do BES e os Ativos Cibernéticos Protegidos na computação em nuvem, as definições existentes nos padrões NERC CIP [precisariam ser revisadas](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx). No entanto, existem muitas cargas de trabalho que lidam com dados confidenciais do CIP e não se enquadram na regra dos 15 minutos, incluindo a ampla categoria do BCES (BES Cyber System Information).

O Azure e o Azure Governamental são indicados para Entidades registradas que implantam determinadas cargas de trabalho sujeitas aos padrões NERC CIP, incluindo cargas de trabalho do BCSI. A Microsoft disponibiliza os seguintes documentos para Entidades registradas interessadas em implantar dados e cargas de trabalho sujeitas às obrigações de conformidade com os padrões NERC CIP no Azure ou no Azure Governamental:

- O white paper [Padrões NERC CIP e computação em nuvem](https://aka.ms/AzureNERC) discute considerações de conformidade dos requisitos dos padrões NERC CIP com base em auditorias de terceiros aplicáveis a provedores de serviços de nuvem, como o FedRAMP. Ele aborda a triagem em segundo plano da equipe de operações da nuvem e responde a perguntas comuns sobre isolamento lógico e multilocação que são questões de interesse para as Entidades registradas. Ele também trata de considerações de segurança da implantação local versus implantação na nuvem.
- O [Guia de implementação da nuvem para Auditorias da NERC](https://aka.ms/AzureNERCGuide) é um documento de orientação que oferece o mapeamento dos controles entre o atual conjunto de requisitos dos padrões NERC CIP e o conjunto de controles [NIST SP 800-53 Rev 4](https://nvd.nist.gov/800-53/Rev4), a base do FedRAMP. Ele foi desenvolvido em forma de uma orientação técnica para ajudar as Entidades registradas a tratar dos requisitos de conformidade dos padrões NERC CIP de ativos implantados na nuvem. O documento contém narrativas previamente preenchidas das [Reliability Standard Audit Worksheets (RSAWs)](https://www.nerc.com/pa/comp/Pages/Reliability-Standard-Audit-Worksheets-\(RSAWs\).aspx) que ajudam a explicar como os controles do Azure satisfazem os requisitos dos padrões NERC CIP e orientações para Entidades registradas sobre como usar os serviços do Azure para implementar controles próprios.

A ERO Enterprise da NERC [lançou](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx) um [guia prático](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf) do CMEP (Compliance Monitoring and Enforcement Program) para oferecer orientação à equipe do CMEP da ERO Enterprise durante a avaliação do processo de uma Entidade registrada para autorizar o acesso a locais designados de armazenamento do BCSI e todos os controles de acesso que a Entidade registrada implementou. Além disso, a NERC revisou os detalhes da implementação de controles do Azure e as evidências de auditoria do FedRAMP relacionadas aos padrões NERC CIP-004-6 e CIP-011-2 aplicáveis ao BCSI. Com base no guia prático emitido pela ERO e nos controles revisados do FedRAMP para garantir que as Entidades registradas criptografem seus dados, nenhuma orientação ou esclarecimento adicional é necessário para que as Entidades registradas implementem o BCSI e cargas de trabalho associadas na nuvem. No entanto, as Entidades registradas são responsáveis pelo cumprimento dos padrões NERC CIP de acordo com seus próprios fatos e circunstâncias. As Entidades registradas devem revisar o [Guia de implementação da nuvem para Auditorias da NERC](https://aka.ms/AzureNERCGuide) para ter acesso à ajuda na documentação dos processos e evidências usadas para autorizar o acesso eletrônico aos locais de armazenamento do BCSI, incluindo o gerenciamento de chaves de criptografia usadas na criptografia do BCSI no Azure e Azure Governamental.

## <a name="microsoft-in-scope-cloud-services"></a>Serviços de nuvem no escopo da Microsoft

- [Azure e Azure Governamental](https://aka.ms/AzureCompliance)

## <a name="audits-reports-and-certificates"></a>Auditorias, relatórios e certificados

A Microsoft tem a obrigação de certificar novamente seus serviços de nuvem todos os anos para manter os P-ATOs e ATOs. Para isso, a Microsoft tem de monitorar e avaliar continuamente seus controles de segurança e demonstrar que a conformidade se mantém.

- [Autorizações dos serviços de nuvem da Microsoft](https://marketplace.fedramp.gov/?sort=productName&productNameSearch=azure#/product/azure-government)
- [Relatórios de auditoria do Microsoft FedRAMP](https://aka.ms/MicrosoftFedRAMPAuditDocuments)

## <a name="how-to-implement"></a>Como implementar

### <a name="nerc-cip-standards-and-cloud-computing"></a>Padrões NERC CIP e computação em nuvem

Aborda a conformidade para Entidades registradas levando em conta a adoção da nuvem para cargas de trabalho sujeitas aos padrões NERC CIP.

[Saiba mais](https://aka.ms/AzureNERC)

### <a name="cloud-implementation-guide-for-nerc-audits"></a>Guia de implementação da nuvem para Auditorias da NERC

As diretrizes técnicas ajudam as Entidades registradas com Auditorias da NERC de ativos implantados no Azure ou Azure Governamental. 

[Saiba mais](https://aka.ms/AzureNERCGuide)

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Quem é responsável pela conformidade com os padrões NERC CIP?**

Todos os proprietários, operadores e usuários de sistemas de energia em massa devem [obedecer os padrões NERC CIP](https://www.nerc.com/pa/comp/Pages/default.aspx). É exigido que essas entidades se registrem na NERC. Os provedores de serviços de nuvem e terceiros não estão sujeitos aos padrões NERC CIP. No entanto, os padrões CIP incluem metas que devem ser consideradas quando [Entidades registradas](https://www.nerc.com/pa/comp/Pages/Registration.aspx) usam fornecedores na operação do BES (Sistema elétrico de distribuição em massa). Os clientes da Microsoft que operam o BES são totalmente responsáveis por garantir sua própria conformidade com os padrões NERC CIP. Nem o Azure nem o Azure Governamental constituem um BES ou Ativo Cibernético do BES.

Para avaliar a adequação do Azure e do Azure Governamental aos dados e cargas de trabalho sujeitos aos padrões NERC CIP, as Entidades registradas devem consultar seus próprios responsáveis pela conformidade e auditores da NERC. Elas devem revisar o [Guia de implementação da nuvem para Auditorias da NERC](https://aka.ms/AzureNERCGuide) para obter ajuda na documentação de seus processos e evidências de ativos implantados na nuvem.

**Quais cargas de trabalho podem ser implantadas em Entidades registradas no Azure e no Azure Governamental?**

Os [Padrões CIP](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf) e o [Glossário de Termos](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf) da NERC declaram que os Ativos Cibernéticos do BES desempenham funções em tempo real de monitoramento ou controle do BES e, caso fossem comprometidos, em 15 minutos, afetariam a operação confiável do BES. Para acomodar adequadamente os Ativos Cibernéticos do BES e os Ativos Cibernéticos Protegidos na computação em nuvem, as definições existentes nos padrões NERC CIP [precisariam ser revisadas](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx). No entanto, existem muitas cargas de trabalho que lidam com dados confidenciais do CIP e não se enquadram na regra dos 15 minutos, incluindo a ampla categoria do BCES (BES Cyber System Information).

A ERO Enterprise da NERC [lançou](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx) um [guia prático](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf) do CMEP (Compliance Monitoring and Enforcement Program) para oferecer orientação à equipe do CMEP da ERO Enterprise durante a avaliação do processo de uma Entidade registrada para autorizar o acesso a locais designados de armazenamento do BCSI e todos os controles de acesso que a Entidade registrada implementou. Além disso, a NERC revisou os detalhes da implementação de controles do Azure e as evidências de auditoria do FedRAMP relacionadas aos padrões NERC CIP-004-6 e CIP-011-2 aplicáveis ao BCSI. Com base no guia prático emitido pela ERO e nos controles revisados do FedRAMP para garantir que as Entidades registradas criptografem seus dados, nenhuma orientação ou esclarecimento adicional é necessário para que as Entidades registradas implementem o BCSI e cargas de trabalho associadas na nuvem. No entanto, as Entidades registradas são responsáveis pelo cumprimento dos padrões NERC CIP de acordo com seus próprios fatos e circunstâncias.

## <a name="resources"></a>Recursos

- [Diretriz de conformidade da NERC](https://www.nerc.com/pa/comp/guidance/)
- [Aplicação e conformidade da NERC](https://www.nerc.com/pa/comp/Pages/default.aspx)
- [Organização e certificação da NERC](https://www.nerc.com/pa/comp/Pages/Registration.aspx)
- [Microsoft e FedRAMP](offering-fedramp.md)
- [Atestado](offering-csa-star-attestation.md) e [Certificação](offering-csa-star-certification.md) STAR do CSA e Microsoft
- [Relatórios da Microsoft e do SOC 2](offering-soc.md)
- [Conformidade na Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/compliance/compliance-overview)
