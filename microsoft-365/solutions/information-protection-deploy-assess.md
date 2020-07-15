---
title: Avaliar os riscos de privacidade de dados e identificar itens confidenciais com o Microsoft 365
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 07/13/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- M365solutions
ms.custom: ''
description: Determine as regulamentações de privacidade de dados, os cenários relevantes, a prontidão e os tipos de informações confidenciais que estão no seu ambiente Microsoft 365.
ms.openlocfilehash: 0cfa9f8a22810027e1a31ce2ace8b42f26ef9eb2
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126587"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Avaliar os riscos de privacidade de dados e identificar itens confidenciais com o Microsoft 365

Avaliar os regulamentos e os riscos de privacidade de dados em que sua organização está sujeita é uma primeira etapa principal antes de implementar qualquer ação de melhoria relacionada, incluindo as obtidas com os recursos e serviços do Microsoft 365. 

## <a name="potentially-applicable-data-privacy-regulations"></a>Regulamentações de privacidade de dados potencialmente aplicáveis

Para obter uma boa referência sobre a estrutura de regulamentações mais ampla para regulamentações de privacidade de dados, consulte o [portal de confiabilidade dos serviços da Microsoft](https://servicetrust.microsoft.com/) e a [série de artigos sobre a regulamentação geral de proteção de dados (rgpd)](../compliance/gdpr.md), além de outros materiais sobre as regulamentações que você pode estar sujeito em seu setor ou região.

### <a name="gdpr"></a>RGPD

O RGPD, mais conhecido e citado nas regulamentações de privacidade de dados, regula a coleta, o armazenamento, o processamento e o compartilhamento de qualquer dado pessoal que esteja relacionado a uma pessoa natural identificada ou identificável, que seja residente da União Européia (UE). 

De acordo com o artigo 4 do RGPD: 

- ' dados pessoais ' significa qualquer informação relacionada a uma pessoa física identificada ou identificável (' Subject de dados '); uma pessoa natural identificável é aquela que pode ser identificada, direta ou indiretamente, em particular por referência a um identificador como um nome, um número de identificação, dados de local, um identificador online ou para um ou mais fatores específicos da identidade física, physiological, genético, mental, econômica, cultural ou social da pessoa natural.

### <a name="iso-27001"></a>ISO 27001

A adesão a outros padrões como o ISO 27001 também foi reconhecida por várias autoridades de supervisão européias como um proxy válido de intenção no espectro de pessoas, processos e tecnologia. Os padrões que ele especifica sobrepõem e a adesão a mecanismos de proteção baseados em ISO-27001 podem ser considerados um proxy que atendem a algumas obrigações de privacidade em determinadas circunstâncias.

### <a name="other-data-privacy-regulations"></a>Outras regulamentações de privacidade de dados

Outras normas de privacidade de dados proeminentes também especificam os requisitos para o tratamento de dados pessoais.

Nos Estados Unidos, isso inclui o[CCPA](../compliance/ccpa-faq.md)(lei de proteção para consumidores da Califórnia), HIPAA-alta (lei de privacidade do atendimento de saúde dos EUA) e o Graham Normas adicionais específicas de estado também são in-loco ou em desenvolvimento. 

Em todo o mundo, exemplos adicionais incluem o BDSG (National RGPD Implementation Act) da Alemanha, a lei de proteção de dados do Brasil (LGPD) e muitas outras.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Mapeamento de regulamentação para categorias de controle técnico da Microsoft 365

Muitas das normas relacionadas à privacidade dos dados têm requisitos de sobreposição, portanto, você deve entender quais regulamentações estão sujeitas antes de desenvolver qualquer esquema de controle técnico. 

Para referência futura nos artigos desta solução geral, esta tabela fornece extratos de uma amostra de regulamentações de privacidade de dados. 

| Normas | Artigo/seção | Trecho | Categorias de controle técnico aplicáveis |
|:-------|:-----|:-------|:-------|
| RGPD | Artigo 5 (1) (f) | Os dados pessoais devem ser processados de forma a garantir a segurança adequada dos dados pessoais, incluindo proteção contra processamento não autorizado ou não ilegal e contra perda acidental, destruição ou danos, usando medidas técnicas ou organizacionais apropriadas ("integridade e confidencialidade".  |  Todos os <br> Identidade <br> Dispositivo <br> Proteção contra Ameaças <br> Proteger informações <br> Informações de controle <br> Descobrir e responder |
|  | Artigo (32) (1) (a) | Levando em consideração o estado da arte, os custos de implementação e a natureza, o escopo, o contexto e a finalidade do processamento, bem como o risco de variar a probabilidade e a gravidade dos direitos e das liberdades de pessoas naturais, o controlador e o processador devem implementar medidas técnicas e organizacionais apropriadas para garantir um nível de segurança apropriado para o risco , incluindo alia conforme apropriado: (a) o pseudônimos e a criptografia de dados pessoais. | Proteger informações |
|  | Artigo (13) (2) (a) | "... o controlador deve, no momento em que os dados pessoais são obtidos, fornecem os dados sujeitos às seguintes informações adicionais necessárias para garantir o processamento justo e transparente: (a) o período para o qual os dados pessoais serão armazenados ou, se isso não for possível, os critérios usados para determinar esse período. | Informações de controle |
|  | Artigo (15) (1) (e) | O assunto dos dados deverá ter o direito de obter da confirmação do controlador se os dados pessoais ou não estiverem sendo processados ou não. e onde esse é o caso, acesse os dados pessoais e as seguintes informações: (e) a existência do direito de solicitar a retificação do controlador ou o apagamento de dados pessoais ou a restrição de processamento de dados pessoais referentes ao assunto ou ao objeto de dados para esse processamento | Descobrir e responder |
| LGPD | Artigo 46 | Os agentes de processamento adotarão medidas de segurança, técnicas e administrativas capazes de proteger dados pessoais de acessos não autorizados e de situações acidentais ou ilegais de destruição, perda, alteração, comunicação ou qualquer tipo de processamento impróprio ou ilegal. | Proteger informações <br> Informações de controle <br> Descobrir e responder|
|  | Artigo 48 | O controlador deve se comunicar à autoridade nacional e ao titular dos dados a ocorrência de um incidente de segurança, que pode criar riscos ou danos relevantes aos titulares de dados. | Descobrir e responder |
| HIPPA-ALTA TECNOLOGIA | 45 CFR 164.312 (e) (1) | Implementar medidas técnicas de segurança para se proteger contra o acesso não autorizado às informações de saúde eletrônicas protegidas que estão sendo transmitidas por uma rede de comunicações eletrônicas. | Proteger informações |
|  | 45 C.F.R. 164.312(e)(2)(ii) | Implementar um mecanismo para criptografar as informações de saúde eletrônicas protegidas sempre que se julgar apropriado. | Proteger informações |
|  | 45 CFR 164.312(c)(2) | Implementar mecanismos eletrônicos para corroborar se as informações de saúde eletrônicas protegidas não foram alteradas nem destruídas de maneira não autorizada. | Informações de controle |
|  | 45 CFR 164.316(b)(1)(i) | Se uma ação, atividade ou avaliação for exigida por este subpart para ser documentada, mantenha um registro gravado (que pode ser eletrônico) da ação, atividade ou avaliação | Informações de controle |
|  | 45 CFR 164.316(b)(1)(ii) | Reter a documentação exigida pelo parágrafo (b)(1) desta seção por seis (6) anos a partir da data de criação ou da data em que esteve em vigor pela última vez, o que tiver ocorrido por último. | Informações de controle |
|  | 45 C.F.R. 164.308(a)(1)(ii)(D) | Implementar procedimentos para analisar regularmente registros de atividade do sistema de informações, como logs de auditoria, relatórios do Access e relatórios de acompanhamento de incidentes de segurança | Descobrir e responder |
|  | 45 C.F.R. 164.308(a)(6)(ii) | Identificar e responder a incidentes de segurança suspeitos ou conhecidos; atenuar, na medida do possível, os efeitos nocivos dos incidentes de segurança conhecidos pela entidade coberta ou parceiro comercial; e documentar incidentes de segurança e seus resultados. | Descobrir e responder |
|  | 45 C.F.R. 164.312(b) | Implemente mecanismos de hardware, software e de procedimentos que registrem e examinem a atividade em sistemas de informações que contenham ou usem informações de saúde protegidas eletrônicas. | Descobrir e responder |
| CCPA | 1798.105(c) | Uma empresa que recebe uma solicitação verificável de um consumidor para excluir as informações pessoais do consumidor de acordo com a subdivisão (a) desta seção deve excluir as informações pessoais do consumidor de seus registros e direcionar todos os provedores de serviços para excluir as informações pessoais do consumidor de seus registros | Descobrir e responder |
|  | 1798.105(d) | (exceções a 1798.105 (c) <br> Uma empresa ou um provedor de serviços não deverá ser compatível com a solicitação de um consumidor para excluir as informações pessoais do consumidor, se for necessário para que o provedor de negócios ou de serviços Mantenha as informações pessoais do consumidor para: (consulte a regulamentação atual para obter informações adicionais). | Descobrir e responder |
|||||

>[!Important]
>Isso não se destina a uma lista exaustiva. Consulte o [gerente de conformidade](../compliance/compliance-manager-overview.md) ou seu consultor jurídico ou de conformidade para obter mais informações sobre a aplicabilidade das seções citadas às categorias de controle técnico listadas.
>

## <a name="knowing-your-data"></a>Conhecendo seus dados

Independentemente das leis às quais você está sujeito, onde diferentes tipos de dados de usuário dentro e fora da sua organização interagem com seus sistemas são fatores importantes que podem afetar sua estratégia geral de proteção de dados pessoais, sujeito às normas do setor e do governo que se aplicam à sua organização. Isso inclui o local em que os dados pessoais são armazenados, qual é o tipo de e quanto ele tem e em que circunstâncias foram coletadas.
 
![Saber quais são os seus dados: Qual é o tipo de e quanto ele é e em que circunstâncias foram coletados](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Portabilidade de dados 

Os dados também são movidos ao longo do tempo enquanto são processados, refinados e outras versões são derivadas dele. Um instantâneo inicial nunca é suficiente. Precisa ser um processo contínuo para conhecer seus dados. Isso representa um dos maiores desafios para grandes organizações que lidam com volumes significativos de dados pessoais. As organizações que não solucionam o problema de "saber mais seus dados" podem acabar com um risco muito alto e possíveis multas de agências regulamentares.

![O ciclo de vida dos dados](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>Onde os dados pessoais são

Para lidar com as regulamentações de privacidade de dados, não é possível contar com noções gerais de onde você acha que os dados pessoais podem existir, agora ou no futuro. As leis de privacidade de dados exigem que as organizações comprovem que eles sabem onde os dados pessoais estão sempre em andamento. Isso torna importante obter um instantâneo inicial de todas as fontes de dados para possível armazenamento de informações pessoais, incluindo seu ambiente do Microsoft 365 e estabelecer mecanismos para monitoramento e detecção contínuas.

Se você ainda não tiver avaliado a preparação geral e o risco associados às normas de privacidade de dados, use a estrutura de 3 etapas a seguir para começar. 

![Etapas para avaliar a preparação e o risco gerais associados às normas de privacidade dos dados](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

>[!Note]
>Este artigo e seu conteúdo não são destinados ao local de serviços de consultoria jurídica. Ele apenas fornece algumas orientações básicas e links para ferramentas que podem ser de assistência nos estágios iniciais de sua avaliação.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Etapa 1: desenvolver uma compreensão básica dos cenários de dados pessoais da sua organização 

Você precisa avaliar a exposição ao risco de privacidade dos dados com base no tipo de dados pessoais que ele gerencia atualmente, onde ele está armazenado, quais controles de proteção são colocados nele, como o ciclo de vida é gerenciado e quem tem acesso a ele. 

Como ponto de partida, é importante inventariar quais tipos de dados pessoais existem no seu ambiente do Microsoft 365. Use estas categorias:

- Dados de funcionários necessários para realizar funções de negócios diárias
- Dados que a organização tem sobre seus clientes, parceiros e outros relacionamentos de negócios no cenário B2B (Business-to-Business)
- Dados a organização tem sobre os consumidores que fornecem informações aos serviços online que a organização gerencia no cenário empresa-para-cliente (B2C)

Veja um exemplo dos diferentes tipos de dados para os departamentos típicos de uma organização.

![Tipos de dados pessoais](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

Grande parte dos dados pessoais sujeitos à regulamentação de privacidade de dados é normalmente coletada e armazenada fora do Microsoft 365. Qualquer dado pessoal de aplicativos móveis ou Web voltados para o cliente precisaria ser exportado desses aplicativos para o Microsoft 365 para estar sujeito à investigação de privacidade de dados no Microsoft 365. 

Sua exposição de privacidade de dados no Microsoft 365 pode ser mais limitada em relação aos seus aplicativos Web e sistemas de CRM, que esta solução não aborda.

Também é importante considerar os seguintes desafios de conformidade de privacidade de dados comuns ao avaliar seu perfil de risco:

 - **Distribuição de dados pessoais.** Como as informações são dispersas sobre um determinado assunto? É conhecido o suficiente para convencer órgãos regulamentares de que os controles adequados estão em vigor? Eles podem ser investigados e corrigidos, se necessário?
- **Proteção contra o exfiltration.** Como você protege dados pessoais de um determinado tipo ou fonte de ser comprometido e como responder se foi?
- **Proteção versus risco.** Quais mecanismos de proteção de informações são apropriados em relação ao risco e como manter a continuidade e a produtividade dos negócios e minimizar o impacto do usuário final se a intervenção do usuário final for necessária? Por exemplo, a classificação manual ou a criptografia deve ser usada?
- **Retenção de dados pessoais.** Quanto tempo as informações que contêm dados pessoais precisam ser mantidas por motivos comerciais válidos e como evitar as práticas anteriores de manutenção de ti, equilibradas com necessidades de retenção para continuidade de negócios?
- **Tratamento de solicitações de entidades de dados.** Quais mecanismos serão necessários para lidar com as solicitações de entidades de dados (DSRs) e quaisquer ações corretivas, como anonimato, redação e exclusão?
- **Monitoramento e geração de relatórios contínuos.** Que espécie de técnicas cotidianas de monitoramento, investigação e relatórios estão disponíveis para os diferentes tipos de dados e fontes?
- **Limitações no processamento de dados.** Há limitações quanto ao uso de dados para informações coletadas ou armazenadas por esses métodos que a organização deve refletir nos controles de privacidade? Por exemplo, os compromissos que os dados pessoais não serão usados pelo pessoal de vendas podem exigir que sua organização Coloque mecanismos em vigor para impedir a transferência ou o armazenamento dessas informações em sistemas associados à organização de vendas.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Dados de funcionários necessários para realizar funções de negócios diárias

As organizações por natureza precisam coletar dados sobre funcionários para fins de identidade e RH eletrônicos, sujeitos ao que eles concordam em seus contratos de funcionário. Contanto que uma pessoa trabalhe para uma empresa, isso normalmente não é um problema. A organização pode querer colocar mecanismos in-loco para evitar que atores mal-intencionados exfiltration ou vazar dados pessoais de funcionários. 

Se uma pessoa deixa uma empresa, as organizações geralmente têm processos, procedimentos, e retenção e exclusão agendamentos para remover contas de usuário, encerrar caixas de correio e unidades pessoais e alterar o status do funcionário em itens como sistemas de recursos humanos. Para situações em que o litígio está envolvido, um funcionário ou outra parte de uma investigação legal pode ter razões válidas para obter informações sobre dados pessoais armazenados nos sistemas da organização. Em algumas ocasiões, essa parte pode solicitar que esses dados sejam removidos ou anônimos. 

Para atender a essas necessidades, as organizações devem ter processos e procedimentos que atendam às necessidades preventiva, de detecção e corretivas para facilitar essas solicitações, observando que algumas informações sobre um funcionário podem ser razoavelmente consideradas cruciais para continuidade de negócios. Por exemplo, informações que uma pessoa cria um arquivo ou executou uma função. 

>[!Note]
>Para obter técnicas investigativas e de correção para dados pessoais no Microsoft 365, consulte o [artigo monitorar e responder](information-protection-deploy-monitor-respond.md). Você também pode querer empregar esquemas de classificação e proteção automatizados para garantir que os dados pessoais sejam controlados enquanto estão dentro da organização, além de evitar que eles saiam da organização em situações mal-intencionadas de ator. Confira o [artigo proteger informações](information-protection-deploy-protect-information.md) para obter mais informações.
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Dados que a organização tem sobre seus clientes comerciais no cenário B2B

O conjunto de informações B2B também é um desafio, pois sua organização pode precisar manter registros de nomes de clientes e transações em seus vários sistemas para fins de continuidade de negócios e, ainda assim, proteger essas informações de exfiltration inadvertidas ou mal-intencionadas. Como os dados dos funcionários, as organizações devem ter políticas, procedimentos e controles técnicos em vigor para proteger esses dados, bem como a idade de acordo com os agendamentos de retenção e exclusão definidos. 

Normalmente, os contratos com clientes externos, parceiros e outras entidades com os quais a organização faz negócios têm um idioma que lida com o tratamento desses dados, incluindo proteção, retenção e exclusão durante e depois da entidade ter uma relação com a organização. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Dados a organização tem sobre os consumidores que fornecem informações aos serviços online que a organização gerencia no cenário B2C

Essa categoria é o que a maioria das pessoas pensa para a privacidade dos dados, devido a muitas instâncias públicas de vazamento de dados do cliente. Isso pode ser intencional, como um terceiro sob contrato para o provedor ou não intencional, como exfiltration por um ator mal-intencionado. A proteção de dados do cliente é uma das principais razões pelas quais a União Européia e outros agiram dessas regulamentações. Regulamentações de privacidade de dados como o RGPD e o CCPA exigem que você faça o planejamento de:

- Listas de verificação de [planos de ação](../compliance/gdpr-action-plan.md) e [preparação de responsabilidade](../compliance/gdpr-arc-office365.md)
- [Avaliações do impacto sobre a proteção dos dados](../compliance/gdpr-data-protection-impact-assessments.md)
- [Notificações de violação](../compliance/gdpr-breach-office365.md)
- [Solicitações de entidades de dados](../compliance/gdpr-dsr-office365.md)

Se sua organização não fizer muita parte da coleta de dados do Direct-from-Consumer, esta categoria pode ser menos um problema. No entanto, talvez ainda seja necessário passar pelos processos descritos nesses artigos para obter conformidade.

### <a name="step-1-summary"></a>Resumo da etapa 1

Entender sua exposição ao risco e à regulamentação de privacidade de dados é uma primeira etapa importante que se baseia em uma compreensão fundamental dos cenários de dados pessoais da sua organização.

Se você não tiver dados pessoais de consumidores no seu ambiente do Microsoft 365 ou se ele estiver confinado a determinadas partes do ambiente e a necessidade de um controle técnico estiver predicada sobre a exposição de dados de tipo de cliente, esse controle técnico só precisará ser empregado em partes de alto risco do ambiente, e não em qualquer lugar.

Embora uma organização externa ou uma recomendação de conjunto de controle padrão, como a pontuação de conformidade no Microsoft 365, possa ajudar a informar sua estratégia de controle, sua escolha de implementação deve ser orientada pelo reconhecimento de inventário de dados para quantificar sua exposição de risco real.

A maioria das organizações terá alguma exposição a um dos cenários acima. É importante fazer uma abordagem holística à avaliação.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Etapa 2: avaliar suas condições de conformidade com as regulamentações de privacidade de dados

Embora específico do RGPD, as perguntas que são oferecidas na ferramenta gratuita de [avaliação do Microsoft rgpd](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) fornecem uma boa introdução para entender a preparação geral da privacidade dos dados. 

As organizações que estão sujeitas a outras regulamentações de privacidade de dados, como o CCPA no LGPD dos Estados Unidos ou Brasil, também podem se beneficiar do inventário de preparação desta ferramenta devido à sobreposição de disposições com o RGPD.

A avaliação do RGPD consiste em estas seções:

| Seção | Descrição |
|:-------|:-----|
| Gestão | <ol><li>A política de privacidade afirma explicitamente quais informações de dados estão sendo processadas? </li><li>Você executa regularmente as avaliações de impacto de privacidade (PIAs)? </li><li> Você usa uma ferramenta para gerenciar informações pessoais (PI)? </li><li> Você tem autoridade legal para realizar negócios usando dados de PI em qualquer indivíduo específico? Você controla o consentimento dos dados? </li><li> Você controla, implementa e gerencia os controles de auditoria? Você monitora os vazamentos de dados? </li></ol>|
| Exclusão e notificação | <ol><li>Você fornece instruções explícitas sobre como os dados dos usuários podem ser acessados? </li><li> Você tem processos documentados em vigor para lidar com o consentimento de recusa? </li><li> Você tem um processo de exclusão automatizada para dados? </li><li>   Você tem um processo para validar a identidade ao participar de um cliente? </li></ol>|
| Mitigação de risco e segurança de informações | <ol><li>Você usa ferramentas para verificar dados não estruturados? </li><li>Todos os servidores estão atualizados e você utiliza firewalls para protegê-los? </li><li>Você executa backups regulares de seus servidores? </li><li>Você monitora ativamente os vazamentos de dados? </li><li>Você criptografa seus dados em repouso e em transmissão? </li></ol>|
| Gerenciamento de políticas | <ol><li>Como gerenciar suas regras corporativas de associação (BCRs)? </li><li>Você controla o consentimento dos dados? </li><li> Em uma escala de 1 a 5, 5 sendo completamente cobertas, seus contratos cobrem as classificações de dados e os requisitos de manuseio? </li><li>Você tem e testa regularmente um plano de resposta a incidentes? </li><li>Qual política você usa para gerenciar o acesso? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Etapa 3: identificar tipos de informações confidenciais que ocorrem no seu ambiente do Microsoft 365. 

Esta etapa envolve a identificação de determinados tipos de informações confidenciais que estão sujeitos a controles normativos específicos, bem como a ocorrência deles no seu ambiente do Microsoft 365. 

Localizar conteúdo em seu ambiente contendo pessoal pode ser uma tarefa formidável, anteriormente envolvendo uma combinação de usar a pesquisa de conformidade, eDiscovery, descoberta eletrônica avançada, DLP e auditoria. 

Com a nova solução de **classificação de dados** no centro de administração de conformidade da Microsoft, isso ficou muito mais fácil com o recurso de [Gerenciador de conteúdo](../compliance/data-classification-content-explorer.md) , que funciona com tipos de informações confidenciais internas ou personalizadas, incluindo aqueles relacionados a dados pessoais.
 
### <a name="sensitive-information-types"></a>Tipos de informações confidenciais

O centro de administração de conformidade da Microsoft vem previamente carregado com mais de 100 tipos de informações confidenciais, a maioria deles está relacionada à identificação e à localização de dados pessoais. Esses tipos de informações confidenciais internas podem ajudar a identificar e proteger números de cartão de crédito, números de contas bancárias, números de passaportes e muito mais, com base em padrões definidos por uma expressão regular (Regex) ou uma função. Para saber mais, consulte [O que os tipos de informações confidenciais procuram](../compliance/what-the-sensitive-information-types-look-for.md).

Se você precisar identificar e proteger um tipo de item confidencial ou específico da organização, como um formato personalizado para IDs de funcionários, ou outras informações pessoais ainda não cobertas por um tipo de informação confidencial interno, você pode criar um tipo de informação confidencial personalizado com estes métodos: 

- PowerShell
- Regras personalizadas com o EDM (correspondência exata de dados)
- Por meio da IU de administração do centro de conformidade, conforme realçado no [artigo usar o placar de conformidade e o Gerenciador de conformidade](information-protection-deploy-compliance.md)

Você também pode personalizar um tipo de informação confidencial interno existente.

Consulte estes artigos para obter mais informações:

- [Personalizar um tipo de informação confidencial interno](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Personalizar tipos de informações confidenciais](../compliance/custom-sensitive-info-types.md)
- [Criar um tipo personalizado de informação confidencial no Centro de Conformidade e Segurança](../compliance/create-a-custom-sensitive-information-type.md)
- [Crie um tipo personalizado de informação confidencial no PowerShell do Centro de Conformidade e Segurança](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Criar tipos de informações confidenciais personalizados com classificação com base na correspondência exata de dados](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Gerenciador de conteúdo

Uma ferramenta importante que determina a ocorrência de itens confidenciais no seu ambiente é o novo [Gerenciador de conteúdo](../compliance/data-classification-content-explorer.md) no centro de administração de conformidade da Microsoft 365. É uma ferramenta automatizada para a verificação inicial e contínua de toda a sua assinatura do Microsoft 365 para a ocorrência de tipos de informações confidenciais e exibição dos resultados.
 
A nova ferramenta de navegador de conteúdo permite que você identifique rapidamente os locais de itens confidenciais em seu ambiente, usando tipos de informações confidenciais internos ou personalizados. Isso pode envolver o estabelecimento de um processo e a responsabilidade atribuída para investigar regularmente a presença e o local de itens confidenciais.

Juntamente com as outras etapas realçadas neste artigo, isso fornece um ponto de partida para identificar a exposição, a preparação e a localização de itens confidenciais em geral para proteger através da configuração e do monitoramento do Microsoft 365 planejado. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Outros métodos para identificar dados pessoais em seu ambiente

Além do Gerenciador de conteúdo, as organizações têm acesso ao recurso de pesquisa de conteúdo para produzir pesquisas personalizadas para localizar dados pessoais em seu ambiente, usando critérios de pesquisa avançados e filtros personalizados.

Orientações detalhadas sobre o uso da pesquisa de conteúdo para descoberta de dados pessoais são fornecidas neste [artigo](../compliance/search-for-and-find-personal-data.md). A pesquisa de conteúdo e outras técnicas de descoberta também são exploradas no [DSRs para o rgpd e o CCPA](../compliance/gdpr-dsr-office365.md#introduction-to-dsrs).

Informações adicionais sobre técnicas investigativas e de correção para dados pessoais no Microsoft 365 são fornecidas no [artigo monitorar e responder](information-protection-deploy-monitor-respond.md).
