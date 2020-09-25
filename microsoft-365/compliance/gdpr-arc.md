---
title: Listas de verificação de preparação de responsabilidade para o RGPD
description: Neste artigo, você aprenderá sobre as listas de Responsabilidade de preparação para acessar informações para oferecer suporte ao GDPR ao usar produtos e serviços da Microsoft.
keywords: Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
localization_priority: Priority
ms.prod: microsoft-365-enterprise
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
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 6952545060a524ef92af6e1e7a063da7091b0860
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214806"
---
# <a name="support-your-gdpr-program-with-accountability-readiness-checklists"></a>Suporte ao seu programa RGPD com listas de verificação de preparação para responsabilidade

O RGPD introduz novas regras a empresas, agências governamentais, organizações sem fins lucrativos e outras organizações que ofereçam bens e serviços a pessoas na União Europeia (UE) ou que coletam e analisam dados vinculados a residentes na UE. O RGPD se aplica onde quer que você e sua empresa estejam localizados. É possível encontrar mais informações no [tópico Resumo RGPD](gdpr.md).

## <a name="accountability-readiness-checklists"></a>Listas de verificação de preparação de responsabilidade

Esta lista de verificação de preparação de responsabilidade fornece uma maneira conveniente para acessar informações que podem ser necessárias para dar suporte ao RGPD ao usar os produtos e serviços da Microsoft. A lista de verificação lista as possíveis obrigações que você pode ter no RGPD e direciona você para as informações que você pode usar para dar suporte à conformidade da sua organização.

Há um guia específico para quatro famílias de produtos e serviços da Microsoft:

- [Office 365](gdpr-arc-Office365.md)
- [Dynamics 365](gdpr-arc-Dynamics365.md)
- [Azure](gdpr-arc-Azure.md)
- [Suporte e Serviços Profissionais da Microsoft](gdpr-arc-prof-services.md)

Você pode gerenciar os itens nesta lista de verificação com o [Gerente de Conformidade](compliance-manager.md) fazendo referência à ID de controle e ao Título do controle em Controles gerenciados do cliente no bloco RGPD.

As listas de verificação incluem as quatro categorias básicas de considerações para um programa de privacidade compatível com RGPD listados abaixo, juntamente com os requisitos de exemplo.

1. Condições de coleta e processamento de dados:

    - Quando o consentimento é obtido?  
    - Identificar e documentar a finalidade  
    - Avaliação de impacto de privacidade

2. Direitos das entidades dos dados  

    - Determinação de informações para entidades de segurança de PII (entidades de dados)   
    - Fornecer mecanismo para modificar ou retirar o consentimento 

3. Privacidade por padrão e design  

    - Limitar coleta  
    - Conformidade com níveis de identificação  
    - Arquivos temporários

4. Segurança e proteção de dados  

    - Noções básicas sobre a organização e o contexto  
    - Planejamento  
    - Políticas de segurança da informação

## <a name="customer-agreements"></a>Contratos com os clientes

- **Termos de Serviços Online**: você pode encontrar os compromissos contratuais da Microsoft com relação ao GDPR nos [Termos dos Serviços Online](https://go.microsoft.com/fwlink/p/?linkid=2052208).
- **Termos do produto da Microsoft**: a Microsoft estende os [compromissos dos Termos do GDPR](https://go.microsoft.com/fwlink/p/?linkid=2052213) a todos os clientes de licenciamento por volume.
- **Adendo de proteção de dados**: os serviços da Microsoft [estendem os compromissos](https://go.microsoft.com/fwlink/p/?linkid=2052215) aos clientes dos Serviços de Consultoria da Microsoft e outras pessoas.

## <a name="gdpr-compliance-controls"></a>Controles de conformidade com o GDPR

- **Usar o Gerenciador de Conformidade**: analise e integre os controles que a Microsoft usa para dar suporte às obrigações no GDPR com o [Gerenciador de Conformidade](compliance-manager.md).
- **Mapeamento de controle do GDPR**: acesse um [mapeamento abrangente](https://go.microsoft.com/fwlink/p/?linkid=2052220) dos controles da Microsoft para as obrigações do GDPR.

## <a name="records-of-processing-for-processors"></a>Registros do processamento para processadores

Devido à escala e à amplitude dos serviços online que fornecemos como processadores aos nossos clientes controladores, esperamos que os clientes identifiquem os serviços que eles procuram para os registros de processamento e recuperem os logs relevantes nas ferramentas online fornecidas por nós. Um exemplo é para os registros de processamento do Azure nos quais os clientes seriam solicitados a identificar para quais tipos de atividade de processamento eles procuram os registros.

### <a name="azure-logs"></a>Logs do Azure

Geralmente, os clientes se interessariam nos registros de atividade e, potencialmente, nos logs de diagnóstico:

- **Registros de atividade**: [Logs de atividades](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) fornecem informações sobre as operações executadas nos recursos em uma assinatura. Os logs de atividades podem ajudar a determinar o iniciador de uma operação, a hora da ocorrência e o status.
- **Logs de diagnóstico**: [Logs de diagnóstico](https://docs.microsoft.com/azure/azure-monitor/platform/platform-logs-overview) são todos os logs emitidos por todos os recursos. Esses logs incluem registros do sistema de eventos do Windows, registros de armazenamento do Azure, registros de auditoria do Key Vault, além de acesso ao gateway do aplicativo e registros de firewall.
- **Arquivamento de log**: todos os logs de diagnóstico gravam em uma conta de armazenamento do Azure centralizada e criptografada para arquivamento. A retenção é configurável pelo usuário, até 730 dias, para atender aos requisitos de retenção específicos da organização. Esses registros se conectam aos logs do Azure Monitor para processamento, armazenamento e relatórios de painéis.

### <a name="other-logs"></a>Outros logs

Além disso, as seguintes soluções de monitoramento são instaladas como parte dessa arquitetura. É responsabilidade do cliente configurar essas soluções para se alinharem com os controles de segurança do FedRAMP:

- [Avaliação do AD](https://docs.microsoft.com/azure/azure-monitor/insights/ad-assessment): a solução de verificação da integridade do Active Directory avalia o risco e a integridade dos ambientes do servidor em um intervalo regular, além de fornecer uma lista priorizada de recomendações específicas para a infraestrutura de servidor implantada.
- [Avaliação anti-malware](https://docs.microsoft.com/azure/security-center/security-center-services?tabs=features-windows#supported-endpoint-protection-solutions-): a solução anti-malware relata sobre malware, ameaças e status de proteção.
- [Automação do Azure](https://docs.microsoft.com/azure/automation/automation-hybrid-runbook-worker): a solução de Automação do Azure armazena, executa e gerencia runbooks.
- [Segurança e auditoria](https://docs.microsoft.com/azure/security-center/security-center-introduction): o painel de segurança e auditoria fornece uma visão geral de alto nível sobre o estado de segurança dos recursos fornecendo métricas sobre domínios de segurança, problemas notáveis, detecções, inteligência de ameaças e consultas de segurança comuns.
- [Avaliação do SQL](https://docs.microsoft.com/azure/azure-monitor/insights/sql-assessment): a solução de verificação da integridade do SQL avalia o risco e a integridade dos ambientes do servidor em um intervalo regular, além de fornecer aos clientes uma lista priorizada de recomendações específicas para a infraestrutura de servidor implantada.
- [Gerenciamento de atualizações](https://docs.microsoft.com/azure/automation/update-management/update-mgmt-overview): a solução de gerenciamento de atualizações permite o gerenciamento de clientes das atualizações de segurança do sistema operacional, incluindo um status de atualizações disponíveis e o processo de instalação das atualizações necessárias.
- [Integridade do agente](https://docs.microsoft.com/azure/azure-monitor/insights/solution-agenthealth): a solução de integridade do agente relata quantos agentes são implantados e sua distribuição geográfica, bem como os agentes que não respondem e o número de agentes que estão enviando dados operacionais.
- [Logs de atividades do Azure](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log): a solução de análise de logs de atividades auxilia na análise dos logs de atividades do Azure em todas as assinaturas do Azure de um cliente.
- [Controle de alterações](https://docs.microsoft.com/azure/azure-monitor/platform/activity-log): a solução de controle de alterações permite aos clientes identificar facilmente as alterações no ambiente.

Para saber mais sobre as medidas de segurança e técnicas para o Azure, os clientes do controlador devem visitar a [Documentação da segurança do Azure](https://docs.microsoft.com/azure/security/). Como a Microsoft não sabe se os dados dos clientes são dados pessoais ou não, o Azure processa todos os dados dos clientes como se fossem dados pessoais, para que um cliente provavelmente considere todo o material relevante.

### <a name="processor-information"></a>Informações do processador

Outro produto que nosso cliente talvez precise dos registros de informações de processamento de processadores é Office 365. Para exibir informações relacionadas ao Office 365, confira o artigo [Pesquisar o log de auditoria no Centro de Conformidade e Segurança](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

Você também pode exibir as informações do Dynamics 365 usando o Centro de Conformidade e Segurança.  Para exibir a página do Centro de Conformidade e Segurança, certifique-se de que você tenha a licença correta. Saiba mais sobre o licenciamento com o artigo [Descrição do serviço do Centro de Conformidade e Segurança](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Para pesquisar eventos do Dynamics 365, visite o log de auditoria unificado no [Centro de Conformidade e Segurança](https://protection.office.com/unifiedauditlog).

### <a name="professional-services-information"></a>Informações dos Serviços Profissionais

Quanto aos Serviços Profissionais, os dados de suporte dos Serviços Profissionais são fornecidos ao engenheiro de suporte pelo representante do cliente.  Isso poderá ocorrer quando um cliente enviar uma solicitação de serviço por meio do portal do produto online, do hub de serviços ou por telefone.

As informações são armazenadas em nossos sistemas do CRM e são usadas apenas para os seguintes objetivos:

- Oferecer Serviços Profissionais, incluindo fornecer suporte técnico, planejamento profissional, conselhos, diretrizes, migração de dados, implantação e serviços de desenvolvimento de software/soluções.  
- Solução de problemas (prevenção, investigação, mitigação e reparo de problemas, incluindo incidentes de segurança); e 
- Melhoramentos contínuos (manter os Serviços Profissionais, incluindo a instalação das últimas atualizações e a realização de melhorias na confiabilidade, eficácia, qualidade e segurança). 

Devido à escala das nossas operações de suporte, a Microsoft opera o sistema CRM baseado no grupo de produtos da Microsoft. Os registros de processamento estarão contidos nesses sistemas.
Um histórico de processamento é refletido nos registros mantidos nos sistemas do CRM.  Na maioria dos casos, o histórico da solicitação de serviço está disponível nos portais ou no hub de serviços.
Para ver detalhes específicos que não estão disponíveis nos portais ou para outras consultas sobre o processamento dos seus dados, contate o seu gerente de conta técnica ou o [suporte técnico da Microsoft](https://support.microsoft.com/contactus/).

## <a name="learn-more"></a>Saiba mais

- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
