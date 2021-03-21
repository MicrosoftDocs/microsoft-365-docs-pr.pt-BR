---
title: Avaliar riscos de privacidade de dados e identificar itens confidenciais com o Microsoft 365
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
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: Determine os regulamentos de privacidade de dados, os cenários relevantes, sua prontidão e os tipos de informações confidenciais que estão em seu ambiente do Microsoft 365.
ms.openlocfilehash: 6801f0af70e08d2b4efdc9e27f1cb1f1d636b821
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929163"
---
# <a name="assess-data-privacy-risks-and-identify-sensitive-items-with-microsoft-365"></a>Avaliar riscos de privacidade de dados e identificar itens confidenciais com o Microsoft 365

Avaliar os regulamentos e os riscos de privacidade de dados aos quais sua organização está sujeita é um primeiro passo importante antes de implementar quaisquer ações de melhoria relacionadas, incluindo as que podem ser alcançadas com recursos e serviços do Microsoft 365. 

## <a name="potentially-applicable-data-privacy-regulations"></a>Regulamentos de privacidade de dados potencialmente aplicáveis

Para uma boa referência sobre a estrutura regulatória mais ampla para regulamentos de privacidade de dados, consulte o Portal de Confiança dos Serviços microsoft [e](https://servicetrust.microsoft.com/) a série de artigos sobre a regulamentação [RGPD (Regulamento](/compliance/regulatory/gdpr)Geral de Proteção de Dados), bem como outros materiais sobre os regulamentos aos quais você pode estar sujeito em sua indústria ou região.

### <a name="gdpr"></a>RGPD

O RGPD, o mais conhecido e citado dos regulamentos de privacidade de dados, regula a coleta, armazenamento, processamento e compartilhamento de todos os dados pessoais relacionados a uma pessoa natural identificada ou identificável que é residente da União Europeia (UE). 

De acordo com o artigo 4 do RGPD: 

- 'dados pessoais' significa qualquer informação relacionada a uma pessoa natural identificada ou identificável ('assunto de dados'); uma pessoa natural identificável é aquela que pode ser identificada, direta ou indiretamente, em particular por referência a um identificador, como um nome, um número de identificação, dados de localização, um identificador online ou para um ou mais fatores específicos da identidade física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa natural.

### <a name="iso-27001"></a>ISO 27001

A adesão a outros padrões, como a ISO 27001, também foi reconhecida por várias autoridades de supervisão europeias como um proxy válido de intenção em todo o espectro de pessoas, processos e tecnologias. Os padrões que especifica a sobreposição e a adesão aos mecanismos de proteção orientados pela ISO-27001 podem ser considerados um proxy que cumpre algumas obrigações de privacidade em determinadas circunstâncias.

### <a name="other-data-privacy-regulations"></a>Outros regulamentos de privacidade de dados

Outras regulamentações de privacidade de dados proeminentes também especificam requisitos para o tratamento de dados pessoais.

Nos Estados Unidos, eles incluem a Lei de Proteção do Consumidor da Califórnia ([CCPA](/compliance/regulatory/ccpa-faq)), HIPAA-HITECH (Lei de privacidade de cuidados de saúde dos Estados Unidos) e a Lei de Bliley de Graham Leach (GLBA). Regulamentos adicionais específicos do estado também estão in-in-or em desenvolvimento. 

Em todo o mundo, exemplos adicionais incluem a Lei Nacional de Implementação do RGPD (BDSG) da Alemanha, a Lei de Proteção de Dados do Brasil (LGPD) e muitos outros.

## <a name="regulation-mapping-to-microsoft-365-technical-control-categories"></a>Mapeamento de regulamentação para categorias de controle técnico do Microsoft 365

Muitos dos regulamentos relacionados à privacidade de dados têm requisitos sobrepostos, portanto, você deve entender quais regulamentos eles estão sujeitos antes de desenvolver qualquer esquema de controle técnico. 

Para referência posterior nos artigos desta solução geral, esta tabela fornece trechos de uma amostra de regulamentos de privacidade de dados. 

| Regulamentação | Artigo/seção | Trecho | Categorias de controle técnico aplicáveis |
|:-------|:-----|:-------|:-------|
| RGPD | Artigo 5(1)(f) | Os dados pessoais devem ser processados de maneira que garanta a segurança apropriada dos dados pessoais, incluindo a proteção contra processamento não autorizado ou ilegal e contra perdas acidentais, destruição ou danos, usando medidas técnicas ou organizacionais apropriadas ('integridade e confidencialidade'.  |  (Todos) <br> Identity <br> Device <br> Proteção contra Ameaças <br> Proteger informações <br> Govern information <br> Descobrir e responder |
|  | Artigo (32)(1)(a) | Levando em conta o estado da arte, os custos de implementação e a natureza, o escopo, o contexto e as finalidades do processamento, bem como o risco de probabilidade e gravidade variáveis para os direitos e liberdades das pessoas naturais, o controlador e o processador devem implementar medidas técnicas e organizacionais apropriadas para garantir um nível de segurança apropriado ao risco , incluindo entre alias conforme apropriado: (a) a pseudonimização e a criptografia de dados pessoais. | Proteger informações |
|  | Artigo (13)(2)(a) | "... o controlador deve, no momento em que os dados pessoais são obtidos, fornecer ao assunto de dados as seguintes informações adicionais necessárias para garantir o processamento justo e transparente: (a) o período para o qual os dados pessoais serão armazenados ou, se isso não for possível, os critérios usados para determinar esse período. | Govern information |
|  | Artigo (15)(1)(e) | O sujeito dos dados deve ter o direito de obter do controlador a confirmação de se os dados pessoais sobre ele ou não estão sendo processados e, nesse caso, o acesso aos dados pessoais e as seguintes informações: (e) a existência do direito de solicitar ao controlador retificação ou apagamento de dados pessoais ou restrição de processamento de dados pessoais referentes ao assunto de dados ou para se opor a esse processamento | Descobrir e responder |
| LGPD | Artigo 46 | Os agentes de processamento devem adotar medidas de segurança, técnicas e administrativas capazes de proteger dados pessoais contra acessos não autorizados e situações acidentais ou ilegais de destruição, perda, alteração, comunicação ou qualquer tipo de processamento impróprio ou ilegal. | Proteger informações <br> Govern information <br> Descobrir e responder|
|  | Artigo 48 | O controlador deve se comunicar à autoridade nacional e ao titular dos dados a ocorrência de um incidente de segurança, que pode criar riscos ou danos relevantes aos titulares de dados. | Descobrir e responder |
| HIPPA-HITECH | 45 CFR 164.312 (e) (1) | Implementar medidas técnicas de segurança para se proteger contra o acesso não autorizado às informações de saúde eletrônicas protegidas que estão sendo transmitidas por uma rede de comunicações eletrônicas. | Proteger informações |
|  | 45 C.F.R. 164.312(e)(2)(ii) | Implementar um mecanismo para criptografar as informações de saúde eletrônicas protegidas sempre que se julgar apropriado. | Proteger informações |
|  | 45 CFR 164.312(c)(2) | Implementar mecanismos eletrônicos para corroborar se as informações de saúde eletrônicas protegidas não foram alteradas nem destruídas de maneira não autorizada. | Govern information |
|  | 45 CFR 164.316(b)(1)(i) | Se uma ação, atividade ou avaliação for necessária para que essa subparte seja documentada, mantenha um registro escrito (que pode ser eletrônico) da ação, atividade ou avaliação | Govern information |
|  | 45 CFR 164.316(b)(1)(ii) | Reter a documentação exigida pelo parágrafo (b)(1) desta seção por seis (6) anos a partir da data de criação ou da data em que esteve em vigor pela última vez, o que tiver ocorrido por último. | Govern information |
|  | 45 C.F.R. 164.308(a)(1)(ii)(D) | Implementar procedimentos para revisar regularmente registros de atividade do sistema de informações, como logs de auditoria, relatórios de acesso e relatórios de controle de incidentes de segurança | Descobrir e responder |
|  | 45 C.F.R. 164.308(a)(6)(ii) | Identificar e responder a incidentes de segurança suspeitos ou conhecidos; atenuar, na medida do possível, os efeitos nocivos dos incidentes de segurança conhecidos pela entidade coberta ou parceiro comercial; e documentar incidentes de segurança e seus resultados. | Descobrir e responder |
|  | 45 C.F.R. 164.312(b) | Implemente mecanismos de hardware, software e procedimentos que registram e examinam atividades em sistemas de informações que contêm ou usam informações de saúde eletrônicas protegidas. | Descobrir e responder |
| CCPA | 1798.105(c) | Uma empresa que recebe uma solicitação verificável de um consumidor para excluir as informações pessoais do consumidor de acordo com a subdivisão (a) desta seção deve excluir as informações pessoais do consumidor de seus registros e direcionar quaisquer provedores de serviços para excluir as informações pessoais do consumidor de seus registros | Descobrir e responder |
|  | 1798.105(d) | (exceções a 1798.105(c) <br> Uma empresa ou um provedor de serviços não deve ser obrigado a atender à solicitação de um consumidor para excluir as informações pessoais do consumidor, se for necessário que a empresa ou o provedor de serviços mantenha as informações pessoais do consumidor para: (consulte a regulamentação atual para obter informações adicionais). | Descobrir e responder |
|||||

>[!Important]
>Isso não se destina a ser uma lista exaustiva. Consulte o [Gerenciador de](../compliance/compliance-manager.md) Conformidade ou seu consultor jurídico ou de conformidade para obter mais informações sobre a aplicabilidade das seções citadas para as categorias de controle técnico listadas.
>

## <a name="knowing-your-data"></a>Conhecendo seus dados

Independentemente dos regulamentos aos quais você está sujeito, onde diferentes tipos de dados do usuário dentro e fora da sua organização interagem com seus sistemas são todos fatores importantes que podem afetar sua estratégia geral de proteção de dados pessoais, sujeitos aos regulamentos do setor e do governo que se aplicam à sua organização. Isso inclui onde os dados pessoais são armazenados, qual tipo são e quanto deles existem e em que circunstâncias eles foram coletados.
 
![Conhecendo seus dados: qual tipo são e quanto deles há e em que circunstâncias eles foram coletados](../media/information-protection-deploy-assess/information-protection-deploy-assess-knowing-data.png)

### <a name="data-portability"></a>Portabilidade de dados 

Os dados também se movem ao longo do tempo à medida que são processados, refinados e outras versões são derivados dele. Um instantâneo inicial nunca é suficiente. É necessário que haja um processo em andamento para conhecer seus dados. Isso representa um dos maiores desafios para grandes organizações que lidam com volumes significativos de dados pessoais. As organizações que não abordam o problema de "conhecer seus dados" podem acabar com riscos muito altos e possíveis multas de agências regulatórias.

![O ciclo de vida dos dados](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-lifecycle.png)
 
### <a name="where-the-personal-data-is"></a>Onde os dados pessoais estão

Para lidar com os regulamentos de privacidade de dados, você não pode confiar em noções gerais de onde você acha que os dados pessoais podem existir, agora ou no futuro. Os regulamentos de privacidade de dados exigem que as organizações provem que sabem onde os dados pessoais estão em andamento. Isso torna importante tirar um instantâneo inicial de todas as fontes de dados para um possível armazenamento de informações pessoais, incluindo seu ambiente do Microsoft 365, e estabelecer mecanismos para monitoramento e detecção em andamento.

Se você ainda não tiver avaliado sua preparação geral e o risco associados aos regulamentos de privacidade de dados, use a estrutura de três etapas a seguir para começar. 

![Etapas para avaliar a preparação geral e o risco associados às regulamentações de privacidade de dados](../media/information-protection-deploy-assess/information-protection-deploy-assess-grid.png)

>[!Note]
>Este artigo e seu conteúdo não são destinados a assumir o lugar de serviços de consultoria jurídica. Ele apenas fornece algumas diretrizes básicas e links para ferramentas que podem ser úteis nos estágios iniciais da sua avaliação.
>
 
## <a name="step-1-develop-a-foundational-understanding-of-your-organizations-personal-data-scenarios"></a>Etapa 1: Desenvolver um entendimento fundamental dos cenários de dados pessoais da sua organização 

Você precisa avaliar a exposição ao risco de privacidade de dados com base no tipo de dados pessoais que ele gerencia atualmente, onde eles estão armazenados, quais controles de proteção são colocados nele, como seu ciclo de vida é gerenciado e quem tem acesso a ele. 

Como ponto de partida, é importante inventariar quais tipos de dados pessoais existem em seu ambiente do Microsoft 365. Use estas categorias:

- Dados dos funcionários necessários para executar funções comerciais diárias
- Dados que a organização tem sobre seus clientes corporativos, parceiros e outros relacionamentos no cenário de negócios para empresas (B2B)
- Dados que a organização tem sobre os consumidores que fornecem informações aos serviços online que a organização gerencia no cenário de negócios para cliente (B2C)

Aqui está um exemplo dos diferentes tipos de dados para departamentos típicos de uma organização.

![Tipos de dados pessoais](../media/information-protection-deploy-assess/information-protection-deploy-assess-data-types.png)

Grande parte dos dados pessoais sujeitos à regulamentação de privacidade de dados geralmente é coletada e armazenada fora do Microsoft 365. Qualquer dado pessoal de aplicativos móveis ou web voltados para o consumidor precisaria ter sido exportado desses aplicativos para o Microsoft 365 para estar sujeito ao exame de privacidade de dados no Microsoft 365. 

Sua exposição à privacidade de dados no Microsoft 365 pode ser mais limitada em relação aos seus aplicativos Web e sistemas CRM, que essa solução não aborda.

Também é importante pensar nos seguintes desafios comuns de conformidade de privacidade de dados ao avaliar seu perfil de risco:

 - **Distribuição de dados pessoais.** Quão dispersas são as informações sobre um determinado assunto? É conhecido o suficiente para convencer os órgãos regulatórios de que os controles adequados estão no local? Pode ser investigado e remediado, se necessário?
- **Protegendo contra a exfiltração.** Como você protege os dados pessoais de um determinado tipo ou fonte de serem comprometidos e como responder se foi?
- **Proteção versus risco.** Quais mecanismos de proteção de informações são apropriados em relação ao risco e como manter a continuidade e a produtividade dos negócios e minimizar o impacto do usuário final se a intervenção do usuário final for necessária? Por exemplo, a classificação manual ou a criptografia devem ser usadas?
- **Retenção de dados pessoais.** Por quanto tempo as informações que contêm dados pessoais precisam ser mantidas por motivos comerciais válidos e como evitar práticas de manutenção para sempre passadas, balanceadas com as necessidades de retenção para a continuidade dos negócios?
- **Manipulando solicitações de assunto de dados.** Quais mecanismos serão necessários para lidar com solicitações de assunto de dados (DSRs) e quaisquer ações corretivas, como anonimização, redação e exclusão?
- **Monitoramento e relatórios contínuos.** Que tipo de técnicas de monitoramento, investigação e relatório do dia a dia estão disponíveis para os diferentes tipos de dados e fontes?
- **Limitações no processamento de dados.** Há limitações no uso de dados para informações coletadas ou armazenadas por meio desses métodos que a organização deve refletir nos controles de privacidade? Por exemplo, os compromissos de que os dados pessoais não serão usados pela equipe de vendas podem exigir que sua organização coloque mecanismos para impedir a transferência ou armazenamento dessas informações em sistemas associados à organização de vendas.

### <a name="employee-data-required-to-carry-out-day-to-day-business-functions"></a>Dados dos funcionários necessários para executar funções comerciais diárias

Por natureza, as organizações precisam coletar dados sobre funcionários para fins de identidade eletrônica e RH, sujeitos ao que concordam em seus contratos de funcionários. Desde que uma pessoa trabalhe para uma empresa, isso normalmente não é um problema. A organização pode querer colocar mecanismos para evitar que os atores mal-intencionados exfiltram ou vazem dados pessoais dos funcionários. 

Se uma pessoa sair de uma empresa, as organizações geralmente têm processos, procedimentos e agendamentos de retenção e exclusão para remover contas de usuário, desmantelar caixas de correio e unidades pessoais e alterar o status do funcionário em coisas como sistemas de recursos humanos. Para situações em que o litígio está envolvido, um funcionário ou outra parte de uma investigação legal pode ter motivos válidos para obter informações sobre dados pessoais armazenados nos sistemas da organização. Em algumas ocasiões, essa parte pode solicitar que esses dados sejam removidos ou anonimizados. 

Para atender a essas necessidades, as organizações devem ter processos e procedimentos no local que abordam necessidades preventivas, detetives e corretivas para facilitar essas solicitações, notando que algumas informações sobre um funcionário podem ser razoavelmente consideradas cruciais para a continuidade dos negócios. Por exemplo, informações de que um indivíduo escreveu um arquivo ou realizou uma função. 

>[!Note]
>Para técnicas de investigação e correção de dados pessoais no Microsoft 365, consulte [o monitor e responda ao artigo](information-protection-deploy-monitor-respond.md). Você também pode querer empregar esquemas automatizados de classificação e proteção para garantir que os dados pessoais são controlados enquanto estão dentro da organização, bem como impedir que eles deixe a organização em situações mal-intencionadas de ator. Consulte o [artigo proteger informações para](information-protection-deploy-protect-information.md) obter mais informações.
>
 
### <a name="data-the-organization-has-about-its-business-customers-in-the-b2b-scenario"></a>Dados que a organização tem sobre seus clientes comerciais no cenário B2B

A coleção de informações B2B também é um desafio, pois sua organização pode precisar manter registros de nomes de clientes e transações em seus vários sistemas para fins de continuidade de negócios e ainda assim proteger essas informações contra exfiltração inadvertida ou mal-intencionada. Assim como os dados dos funcionários, as organizações devem ter políticas, procedimentos e controles técnicos no local para proteger esses dados, bem como age-los de acordo com os agendamentos de retenção e exclusão definidos. 

Normalmente, contratos com clientes externos, parceiros e outras entidades com as quais a organização faz negócios terão linguagem que aborda a manipulação desses dados, incluindo proteção, retenção e exclusão durante e depois que a entidade tiver uma relação com a organização. 

### <a name="data-the-organization-has-about-consumers-who-provide-information-to-online-services-that-the-organization-manages-in-the-b2c-scenario"></a>Dados que a organização tem sobre os consumidores que fornecem informações aos serviços online que a organização gerencia no cenário B2C

Essa categoria é a que a maioria das pessoas pensa para privacidade de dados, devido a muitas instâncias públicas de vazamento de dados do cliente. Isso pode ser intencional, como um terceiro sob contrato com o provedor ou não intencional, como a exfiltração por um ator mal-intencionado. A proteção de dados do consumidor é um dos principais motivos pelos quais a UE e outros aprovaram esses regulamentos. Os regulamentos de privacidade de dados, como o RGPD e o CCPA, exigem que você faça o planejamento para:

- [Planos de ação](/compliance/regulatory/gdpr-action-plan) e listas de verificação de [prontidão de responsabilidade](/compliance/regulatory/gdpr-arc-Office365)
- [Avaliações de impacto da proteção de dados](/compliance/regulatory/gdpr-data-protection-impact-assessments)
- [Notificações de violação](/compliance/regulatory/gdpr-breach-Office365)
- [Solicitações de entidades de dados](/compliance/regulatory/gdpr-dsr-Office365)

Se sua organização não fizer uma grande quantidade de coleta de dados direta do consumidor, essa categoria poderá ser menos um problema. No entanto, talvez você ainda precise passar pelos processos descritos nestes artigos para atingir a conformidade.

### <a name="step-1-summary"></a>Resumo da Etapa 1

Compreender sua exposição ao risco e à regulamentação de privacidade de dados é um primeiro passo importante que se baseia em um entendimento fundamental dos cenários de dados pessoais da sua organização.

Se você não tiver dados pessoais de consumidores em seu ambiente do Microsoft 365 ou ele estiver limitado a determinadas partes do ambiente e a necessidade de um controle técnico estiver predicado em que haja exposição de dados do tipo consumidor, esse controle técnico pode precisar ser empregado apenas em partes de alto risco do ambiente, não em todos os lugares.

Embora uma organização externa ou uma recomendação de conjunto de controle padrão, como o Gerenciador de Conformidade no Microsoft 365, possa ajudar a informar sua estratégia de controle, sua escolha de implementação deve ser orientada pelo reconhecimento do inventário de dados para quantificar sua exposição real a riscos.

A maioria das organizações terá alguma exposição a um dos cenários acima. Fazer uma abordagem holística para a avaliação é importante.

## <a name="step-2-assess-your-readiness-for-complying-with-data-privacy-regulations"></a>Etapa 2: Avaliar sua preparação para estar em conformidade com os regulamentos de privacidade de dados

Embora específicas para o RGPD, as perguntas colocadas na ferramenta gratuita de avaliação do [RGPD](https://www.microsoft.com/cyberassessment/en/gdpr/uso365) da Microsoft fornecem um bom início para entender sua preparação geral de privacidade de dados. 

As organizações sujeitas a outras regulamentações de privacidade de dados, como CCPA nos Estados Unidos ou LGPD do Brasil, também podem se beneficiar do inventário de preparação dessa ferramenta devido às disposições sobrepostas com o RGPD.

A avaliação do RGPD consiste nessas seções:

| Seção | Descrição |
|:-------|:-----|
| Governança | <ol><li>Sua política de privacidade informa explicitamente quais informações de dados estão sendo processadas? </li><li>Você executar regularmente as Avaliações de Impacto na Privacidade (PIAs)? </li><li> Você usa uma ferramenta para gerenciar informações pessoais (PI)? </li><li> Você tem autoridade legal para conduzir negócios usando dados pi em qualquer indivíduo? Você rastreia o consentimento para dados? </li><li> Você controla, implementa e gerencia controles de auditoria? Você monitora vazamentos de dados? </li></ol>|
| Exclusão e notificação | <ol><li>Você dá instruções explícitas sobre como os dados dos usuários podem ser acessados? </li><li> Você tem processos documentados em andamento para lidar com o consentimento de não aceitação? </li><li> Você tem um processo de Exclusão Automatizada para dados? </li><li>   Você tem um processo para validar a identidade ao se envolver com um cliente? </li></ol>|
| Mitigação de riscos e segurança de informações | <ol><li>Você usa ferramentas para examinar dados não estruturados? </li><li>Todos os servidores estão atualizados e você aproveita firewalls para protegê-los? </li><li>Você executar backups regulares de seus servidores? </li><li>Você monitora ativamente vazamentos de dados? </li><li>Você criptografa seus dados em repouso e em transmissão? </li></ol>|
| Gerenciamento de políticas | <ol><li>Como você gerencia suas regras corporativas vinculativas (BCRs)? </li><li>Você rastreia o consentimento para dados? </li><li> Em uma escala de 1 a 5, 5 sendo totalmente coberto, seus contratos abrangem classificações de dados e requisitos de tratamento? </li><li>Você tem e testa regularmente um plano de resposta a incidentes? </li><li>Qual política você usa para gerenciar o acesso? </li></ol>|
|||
 
## <a name="step-3-identify-sensitive-information-types-that-occur-in-your-microsoft-365-environment"></a>Etapa 3: Identificar tipos de informações confidenciais que ocorrem em seu ambiente do Microsoft 365. 

Esta etapa envolve a identificação de tipos específicos de informações confidenciais que estão sujeitos a controles regulatórios específicos, bem como a ocorrência deles em seu ambiente do Microsoft 365. 

Localizar conteúdo em seu ambiente contendo pessoal pode ser uma tarefa excelente, anteriormente envolvendo uma combinação de uso de Pesquisa de Conformidade, Descoberta Virtual, Descoberta Digital Avançada, DLP e auditoria. 

Com a  nova solução de Classificação de Dados no Centro de administração de Conformidade da Microsoft, isso se tornou muito mais fácil com a funcionalidade do [Explorador](../compliance/data-classification-content-explorer.md) de Conteúdo, que funciona com tipos de informações confidenciais integrados ou personalizados, incluindo os relacionados a dados pessoais.
 
### <a name="sensitive-information-types"></a>Tipos de informações confidenciais

O Centro de administração de Conformidade da Microsoft vem pré-carregado com mais de 100 tipos de informações confidenciais, a maioria deles relacionados à identificação e localização de dados pessoais. Esses tipos de informações confidenciais integrados podem ajudar a identificar e proteger números de cartão de crédito, números de conta bancária, números de passaporte e muito mais, com base em padrões definidos por uma expressão regular (regex) ou uma função. Para saber mais, consulte [O que os tipos de informações confidenciais procuram](../compliance/sensitive-information-type-entity-definitions.md).

Se você precisar identificar e proteger um tipo específico da organização ou regional de itens confidenciais, como um formato personalizado para IDs de funcionários ou outras informações pessoais ainda não cobertas por um tipo de informação confidenciais integrado, você pode criar um tipo de informação confidenciais personalizado com esses métodos: 

- PowerShell
- Regras personalizadas com EDM (exact data match)
- Por meio da interface do usuário do administrador do Centro de Conformidade, conforme destacado no [artigo Use Compliance Score and Compliance Manager](information-protection-deploy-compliance.md)

Você também pode personalizar um tipo de informação confidenciais existente e integrado.

Confira estes artigos para obter mais informações:

- [Personalizar um tipo de informação confidencial interno](../compliance/customize-a-built-in-sensitive-information-type.md)
- [Aprenda sobre os tipos de informações confidenciais](../compliance/sensitive-information-type-learn-about.md)
- [Criar um tipo personalizado de informação confidencial no Centro de Conformidade e Segurança](../compliance/create-a-custom-sensitive-information-type.md)
- [Crie um tipo personalizado de informação confidencial no PowerShell do Centro de Conformidade e Segurança](../compliance/create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Criar tipos personalizados de informações confidenciais com classificação baseada em Exact Data Match](../compliance/create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

### <a name="content-explorer"></a>Explorador de Conteúdo

Uma ferramenta importante que determina a ocorrência de itens confidenciais em seu ambiente é o novo [Explorador](../compliance/data-classification-content-explorer.md) de Conteúdo no Centro de administração de Conformidade do Microsoft 365. É uma ferramenta automatizada para verificação inicial e contínua de toda a sua assinatura do Microsoft 365 para a ocorrência de tipos de informações confidenciais e a exibição dos resultados.
 
A nova ferramenta do Explorador de Conteúdo permite identificar rapidamente os locais de itens confidenciais em seu ambiente, usando tipos de informações confidenciais ou personalizados. Isso pode envolver o estabelecimento de um processo e a responsabilidade atribuída para investigar regularmente a presença e a localização de itens confidenciais.

Junto com as outras etapas destacadas neste artigo, isso fornece um ponto de partida para identificar sua exposição geral de risco, preparação e localização de itens confidenciais para proteger por meio da configuração e monitoramento planejados do Microsoft 365. 

### <a name="other-methods-to-identify-personal-data-in-your-environment"></a>Outros métodos para identificar dados pessoais em seu ambiente

Além do Explorador de Conteúdo, as organizações têm acesso ao recurso Pesquisa de Conteúdo para produzir pesquisas personalizadas para encontrar dados pessoais em seu ambiente, usando critérios de pesquisa avançados e filtros personalizados.

Orientações detalhadas sobre o uso da Pesquisa de Conteúdo para descoberta de dados pessoais são fornecidas [neste artigo](/compliance/regulatory/gdpr). A Pesquisa de Conteúdo e outras técnicas de descoberta também são exploradas [em DSRs para o RGPD e CCPA](/compliance/regulatory/gdpr-dsr-Office365#introduction-to-dsrs).

Informações adicionais sobre técnicas de investigação e correção de dados pessoais no Microsoft 365 são fornecidas no monitor e [respondem ao artigo](information-protection-deploy-monitor-respond.md).

> [!NOTE]
> Para encontrar quais informações confidenciais você tem em arquivos armazenados no local, consulte [a Proteção de Informações do Azure.](/azure/information-protection/quickstart-findsensitiveinfo)