---
title: Regulamento Geral sobre a Proteção de Dados
description: Saiba mais sobre as diretrizes técnicas da Microsoft e encontre informações úteis para a Norma Geral de Proteção de Dados (GDPR).
keywords: Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fb89a24e48dbdadd9a1af863cb8c44ded46435b1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036204"
---
# <a name="general-data-protection-regulation-summary"></a>Resumo do Regulamento Geral sobre a Proteção de Dados

O Regulamento Geral sobre a Proteção de Dados (RGPD) introduz novas regras para organizações que oferecem bens e serviços às pessoas na União Europeia (UE) ou que coletam e analisam dados vinculados a residentes da UE. O RGPD se aplica onde quer que você e sua empresa estejam localizados. Este documento o orienta com informações para respeitar os direitos e cumprir com as obrigações do RGPD ao usar produtos e serviços da Microsoft. Um [Plano de ação recomendado para o RGPD](gdpr-action-plan.md) e as [Listas de Verificação de Preparação de Responsabilidade](gdpr-arc.md) fornecem recursos adicionais para avaliar e implementar a conformidade de RGPD.

## <a name="terminology"></a>Terminologia

Definições úteis para os termos do RGPD usados neste documento:

- **Controlador de Dados (Controlador**): uma pessoa jurídica, uma autoridade pública, uma agência ou outro corpo que, isoladamente ou em conjunto com outras pessoas, determina a finalidade e o meio de processamento de dados pessoais.  
- **Dados pessoais e entidade de dados**: qualquer informação relacionada a uma pessoa natural identificada ou identificável (entidade de dados); uma pessoa natural identificável é uma que pode ser identificada, direta ou indiretamente.  
- **Processador:** uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.  
- **Dados do cliente**: dados produzidos e armazenados nas operações do dia a dia para o funcionamento do seu negócio.

## <a name="what-is-the-gdpr"></a>O que é o RGPD?

O RGPD concede direitos para as pessoas gerenciarem dados pessoais coletados por uma organização. Esses direitos podem ser exercidos por meio de uma Solicitação do Titular dos Dados (DSR). A organização deve fornecer informações adequadas sobre violações de dados e DSRs, e executar Avaliações do Impacto sobre a Proteção de Dados (DPIAs).

Vários pontos devem ser considerados ao implementar ou avaliar os requisitos do RGPD:

- Desenvolver ou avaliar a conformidade da sua política de privacidade de dados com o RGPD.
- Avaliar a segurança dos dados da sua organização.
- Quem é seu controlador de dados?
- Quais processos de segurança de dados talvez você precise executar?

O [Plano de ação recomendado para o RGPD](gdpr-action-plan.md) e as [Listas de Verificação de Preparação de Responsabilidade](gdpr-arc.md) podem solicitar os pontos adicionais a serem considerados.

As seguintes tarefas estão envolvidas para atender aos padrões RGPD. Siga os links da lista para obter detalhes sobre a sua implementação.  

- **[Solicitações do Titular de Dados (DSR)](gdpr-data-subject-requests.md)**. Uma solicitação formal feita por um titular de dados a um controlador para executar uma ação (alteração, restrição, acesso) em relação aos seus dados pessoais. 
- **[Notificação de violação](gdpr-breach-notification.md)**. Sob o RGPD, uma violação de dados pessoais é “uma violação de segurança que resulta em destruição acidental ou ilegal, perda, alteração, divulgação não autorizada ou acesso a dados pessoais transmitidos, armazenados ou processados”.
- **[Avaliações do Impacto sobre a Proteção dos Dados (DPIA)](gdpr-data-protection-impact-assessments.md)**. O RGPD exige que os controladores preparem um DPIA para operações de dados que "provavelmente resultariam em alto risco para os direitos e a liberdade de pessoas físicas".

Conforme mencionado acima, o plano de ação recomendado para o RGPD e as Listas de Verificação de Preparação de Responsabilidade fornece um guia para implementar ou avaliar a conformidade com o RGPD usando produtos e serviços da Microsoft.

## <a name="data-subject-request-dsr"></a>Solicitação do Titular de Dados (DSR)

O GDPR concede a indivíduos (ou a entidades de dados) certos direitos relacionados ao processamento de seus dados pessoais, incluindo o direito de corrigir dados incorretos, apagar dados ou restringir seu processamento, receber seus dados e atender a uma solicitação para transmitir seus dados a outro controlador. O controlador é responsável por fornecer uma resposta adequada e consistente com o RGPD. Para obter detalhes técnicos, confira [Solicitações do titular de dados](gdpr-data-subject-requests.md).  

### <a name="dsr-faqs"></a>FAQs do DSR

**Quais ações serão necessárias para concluir um DSR?**

DSRs envolvem seis atividades: descoberta, acesso, retificação, restrição, exportação e exclusão.

**Quais são suas fontes de dados?**

A maioria dos dados de uma organização é gerada em [aplicativos do Office](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs), como o Excel e o Outlook. Você também pode encontrar dados relevantes para um DSR em [Informações](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365), gerados por produtos e serviços da Microsoft, e [logs gerados pelo sistema](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs).

**Quais tipos de dados precisam ser pesquisados?**

Dados pessoais podem ser encontrados em dados de clientes, informações geradas por produtos e serviços da Microsoft, além de logs gerados pelo sistema.

**Como os dados pessoais serão pesquisados?**

Procurar dados pessoais pode variar em produtos e serviços da Microsoft. As ferramentas de pesquisa incluem [Pesquisa de Conteúdo](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) ou recurso [de pesquisa no aplicativo](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-in-app-functionality-to-respond-to-dsrs). Os administradores podem acessar [logs gerados pelo sistema](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs) associados à atividade de um usuário.  

**Em que formatos os dados pessoais devem estar disponíveis?**

O "direito de portabilidade dos dados" do RGPD permite que o titular de dados solicite uma cópia dos dados pessoais que estejam em um "formato estruturado, frequentemente usado, que possa ser lido por máquina", bem como solicite que sua organização transmita esses arquivos para outro controlador de dados.

**Quais são as exigências do GDPR e minhas responsabilidades como controlador?**

Como controlador, o GDPR exige que você seja capaz de:

- Fornecer aos titulares dos dados uma cópia de seus dados pessoais, juntamente com uma explicação das categorias dos seus dados que estão sendo processados, os objetivos desse processamento e as categorias de terceiros para os quais esses dados podem ser divulgados.
- Ajudar cada indivíduo a exercer seu direito de corrigir dados pessoais incorretos, apagar dados ou restringir seu processamento, receber seus dados em formato legível e, se for caso, atender a uma solicitação para transmitir seus dados para outro controlador.

**Quais são as exigências do RGPD e as responsabilidades da Microsoft como processador?**

Precisamos implementar as medidas técnicas e organizacionais apropriadas para ajudá-lo a responder a Solicitações de Entidades de Dados que exercem seus direitos conforme discutido acima.

**Onde posso encontrar as informações relacionadas ao RGPD para servidores locais?**

Você pode encontrar uma série de artigos relacionados a RGPD. Produzidos pela Microsoft, eles fornecem abordagens recomendadas para a carga de trabalho local para o SharePoint Server, o Exchange Server, o Project Server, o servidor do Office Web Apps, o Office Online Server e os compartilhamentos de arquivos locais.

**Como a Microsoft permite que você responda a solicitações de entidades de dados?**

Os serviços online oferecem uma série de recursos para permitir que você, como controlador, responda à solicitação de um titular de dados. Os serviços online corporativos e os controles administrativos da Microsoft ajudam você a agir em dados pessoais em reação às solicitações de direitos dos titulares dos dados, o que permite descobrir, acessar, corrigir, restringir, excluir e exportar dados pessoais que residem nos dados gerenciados pelo controlador armazenados na nuvem da Microsoft. Os serviços online também fornecem dados em formato legível por máquina, caso você precise.

## <a name="data-protection-impact-assessment"></a>Avaliações do Impacto sobre a Proteção dos Dados

O RGPD exige que os controladores preparem uma [Avaliação de Impacto de Proteção de Dados](gdpr-data-protection-impact-assessments.md) (DPIA) para operações que "provavelmente resultariam em alto risco para os direitos e a liberdade de pessoas físicas". Não há nada inerente aos produtos e serviços da Microsoft que precisem da criação de um DPIA. Em vez disso, depende dos detalhes da sua configuração da Microsoft. Uma lista de detalhes que devem ser considerados no Office pode ser encontrada no [Conteúdo de DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia)

### <a name="dpia-faqs"></a>Perguntas frequentes sobre DPIA

**Quando executar um DPIA?**

Os controladores devem executar um DPIA para lidar com os riscos para a segurança de dados pessoais ou como resultado de uma violação de dados. Os exemplos específicos de fatores de risco no Office são abordados em [Determinar se um DPIA é necessário](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed).  

**O que é necessário para concluir um DPIA?**

O RGPD exige que um DPIA inclua:

- Avaliação da necessidade e da proporcionalidade do processamento de dados em relação aos objetivos do DPIA.
- Avaliação dos riscos aos direitos e às liberdades dos titulares dos dados.
- As medidas desejadas para lidar com os riscos, incluindo proteções, medidas de segurança e mecanismos para garantir a proteção de dados pessoais e demonstrar a conformidade com o RGPD.

**Quais são minhas responsabilidades como Controlador?**

Segundo o GDPR, como controlador, é necessário que você realize DPIAs antes de práticas de processamento de dados que provavelmente resultarão em um alto risco aos direitos e às liberdades dos indivíduos, em particular, o processamento com o uso de novas tecnologias. O GDPR fornece a seguinte lista não exaustiva de casos em que DPIAs devem ser realizadas:

- Processamento automatizado para fins de criação de perfis e atividades semelhantes que tenham efeitos legais ou que, de modo semelhante, afetem significativamente os titulares dos dados;  
- Processamento em grande escala de categorias especiais de dados pessoais – dados reveladores de origem racial ou étnica, opinião política e semelhantes – ou de dados relacionados a condenações e delitos penais;  
- Monitoramento sistemático de uma área de acesso público em grande escala.  

O RGPD também exige que você consulte sua Autoridade de Proteção de Dados (DPA) antes de iniciar qualquer processamento caso não consiga identificar processos suficientes para minimizar os altos riscos aos titulares dos dados.

**Quais são as responsabilidades da Microsoft?**

A Microsoft pratica princípios de privacidade estrutural e privacidade por padrão em suas funções de engenharia e negócios. Como parte desses esforços, a Microsoft realiza análises de privacidade abrangentes em operações de processamento de dados que têm o potencial de causar impactos nos direitos e nas liberdades dos titulares dos dados. As equipes de privacidade integradas nos grupos de serviços analisam o design e a implementação de serviços para garantir que os dados pessoais sejam processados de maneira respeitosa, de acordo com a lei internacional, as expectativas dos usuários e nossos compromissos expressos.

Essas análises de privacidade tendem a ser granulares – um serviço específico pode receber dezenas ou centenas de análises. A Microsoft implementa essas análises de privacidade granulares em Avaliações do Impacto sobre a Proteção dos Dados (DPIAs) que abrangem os principais agrupamentos de processamento, que então são examinadas pelo Oficial de Proteção de Dados (DPO) da Microsoft EU. O DPO avalia os riscos relacionados ao processamento de dados para garantir que existam mitigações suficientes em vigor. Se o DPO detectar riscos não mitigados, as alterações repassadas ao grupo de engenharia. As DPIAs serão revisadas e atualizadas à medida que os riscos à proteção dos dados mudarem.


A Microsoft, como processador, tem o dever de ajudar os controladores a assegurar a conformidade com os requisitos para DPIA estabelecidos no RGPD. Para dar suporte aos nossos clientes, as seções relevantes de DPIAs da Microsoft foram abstraídas e serão fornecidas por meio desta seção em atualizações futuras, com a intenção de permitir que os controladores que dependem de serviços Microsoft aproveitem os resumos para criar suas próprias DPIAs.

## <a name="breach-notification"></a>Notificação de falha

O RGPD impõe requisitos de notificação para controladores e processadores de dados para uma violação de dados pessoais. Como um processador de dados, a Microsoft garante que os clientes possam atender aos requisitos de notificação de violação do RGPD. Os controladores de dados são responsáveis por avaliar os riscos à privacidade de dados e determinar se uma violação exige uma notificação de DPA do cliente. A Microsoft fornece as informações necessárias para a avaliação. Para obter mais informações sobre como a Microsoft detecta e responde a uma violação de dados pessoais, confira [Notificação de violação de dados no RGPD](gdpr-breach-notification.md).

### <a name="breach-notification-faqs"></a>Perguntas frequentes sobre notificação de falha

**O que constitui uma violação de dados pessoais no âmbito do RGPD?**

Dados pessoais significam quaisquer informações relacionadas a um indivíduo que possam ser usadas para identificá-los direta ou indiretamente. Uma violação de dados pessoais é “uma violação de segurança que resulta em destruição acidental ou ilegal, perda, alteração, divulgação não autorizada ou acesso a dados pessoais transmitidos, armazenados ou processados”.

**Quais são as suas responsabilidades como controlador?**

Se a violação de dados pessoais que possa resultar em alto risco aos direitos e às liberdades dos indivíduos (como discriminação, roubo de identidade, fraude, perda financeira ou danos à reputação) ocorrer, o RGPD exige que você:

- Notifique a Autoridade de Proteção de Dados (DPA) apropriada dentro de 72 horas após tomar conhecimento da violação, por exemplo, depois que a  notificar você. Se você não notificar o DPA nesse período, precisará explicar a ele o motivo. Este aviso ao DPA é necessário mesmo quando existe risco para os indivíduos que não seja suscetível de se transformar em um alto risco.
- Notifique os titulares dos dados sobre a violação sem demora injustificada.

- Documente a violação, incluindo uma descrição de sua natureza da violação, como quantas pessoas foram afetadas, o número de registros de dados afetados, as consequências da violação e qualquer ação corretiva que a sua organização esteja propondo ou adotando.

**Quais são as responsabilidades da Microsoft como Processador?**

Depois de tomarmos conhecimento de uma violação de dados pessoais, o RGPD exige que o notifiquemos sem atrasos indevidos. Nos casos em que a Microsoft é um processador, nossas obrigações refletem tanto os requisitos do RGPD quanto nossas cláusulas contratuais mundiais padrão. Consideramos que todas as violações de dados pessoais confirmadas estão dentro do escopo; não há risco de limites de danos. Notificaremos nossos clientes se a violação de dados tiver sido sofrida diretamente pela Microsoft ou por qualquer um de nossos subprocessadores. Temos processos para identificar e contatar rapidamente a equipe de incidentes de segurança que você identificou na sua organização. Além disso, todos os subprocessadores são contratualmente obrigados a relatar suas próprias violações à Microsoft e a fornecer garantias para esse efeito.

**Como a MIcrosoft detectará uma violação de dados?**

Todos os nossos serviços e funcionários seguem os procedimentos internos de gerenciamento de incidentes, para garantir que tomemos as devidas precauções para evitar violações de dados antes de mais nada. No entanto, além disso, os serviços de nuvem corporativos da Microsoft possuem controles de segurança específicos em nossas plataformas para detectar violações de dados no raro evento de elas ocorrerem.

**Como a Microsoft responderá a uma violação de dados?**

Para dar suporte em caso de uma violação de dados pessoais, a Microsoft tem:
    - Pessoal de segurança treinado sobre os procedimentos específicos a serem seguidos.
    - Políticas, procedimentos e controles em vigor para garantir que a Microsoft mantenha registros detalhados. Essa resposta inclui uma documentação que captura os fatos do incidente, seus efeitos e ação corretiva, bem como informações de acompanhamento e armazenamento em nossos sistemas de gerenciamento de incidentes.

**Como a Microsoft me notificará no caso de uma violação de dados?**

A Microsoft tem políticas e procedimentos em vigor para notificá-lo imediatamente. Para atender aos seus requisitos de notificação ao DPA, forneceremos uma descrição do processo que utilizamos para determinar se uma violação de dados pessoais ocorreu, uma descrição da natureza da violação e uma descrição das medidas tomadas para mitigar essa violação.

## <a name="accountability-readiness-checklists-for-the-gdpr"></a>Listas de Verificação de Preparação de Responsabilidade para o RGPD

Essas [listas de verificação](gdpr-arc.md) fornecem uma forma conveniente de acessar as informações necessárias para dar suporte ao RGPD ao usar os produtos da Microsoft. Você pode gerenciar os itens nesta lista de verificação com a [Pontuação de Conformidade](compliance-score.md) fazendo referência à ID de controle e ao Título do controle em Controles gerenciados pelo cliente no bloco do RGPD.

## <a name="gdpr-faqs"></a>Perguntas frequentes do RGPD

**A Microsoft faz os compromissos com seus clientes em relação ao RGPD?**

Sim. O RGPD exige que os controladores (por exemplo, organizações que usam os serviços online da Microsoft) usem apenas processadores (como a Microsoft) que forneçam garantias suficientes para atender aos principais requisitos do RGPD. A Microsoft tomou a iniciativa de se comprometer com todos os clientes de Licenciamento por Volume como parte de seus acordos.

**Como a Microsoft me ajuda a consentir?**

A Microsoft fornece ferramentas e documentação para dar suporte à sua responsabilidade ao RGPD. Isso inclui suporte para Direitos de Dados, realização de suas próprias Avaliações do Impacto sobre a Proteção dos Dados e trabalho em conjunto para resolver violações de dados pessoais.

**Quais compromissos estão nos termos RGPD?**

Os Termos de RGPD da Microsoft refletem os compromissos obrigatórios dos processadores no Artigo 28. O artigo 28 exige que os processadores se comprometam a:

- Usar somente os subprocessadores com o consentimento do controlador e se responsabilizar por subprocessos.
- Processe dados pessoais somente nas instruções do controlador, incluindo em relação a transferências.
- Garanta que as pessoas que processam dados pessoais estejam comprometidas com a confidencialidade.
- Implemente medidas técnicas e organizacionais apropriadas para garantir um nível de segurança de dados pessoais apropriado para o risco.
- Auxiliar os controladores em suas obrigações de responder às solicitações dos titulares de dados para exercer seus direitos RGPD.
- Atender aos requisitos de notificação e assistência de violação.
- Auxiliar os controladores nas avaliações de impacto na proteção de dados e na consulta com as autoridades de supervisão.
- Excluir ou retornar dados pessoais no final do provisionamento de serviços.
- Dar suporte ao controlador com evidências de conformidade com o RGPD.

**Em que base a Microsoft facilita a transferência de dados pessoais fora da UE?**

A Microsoft tem usado por extenso as Cláusulas Contratuais Padrão (também conhecidas como as Cláusulas Modelo) como base para a transferência de dados dos serviços online corporativos. As Cláusulas Contratuais Padrão são termos padrão fornecidos pela Comissão Europeia, que podem ser usados para transferir dados de fora da área europeia de maneira compatível. A Microsoft incorporou as Cláusulas Contratuais Padrão em todos os acordos de licenciamento por volume pelos [Termos de Serviços Online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46). O Grupo de Trabalho do Artigo 29 concluiu que a implementação das Cláusulas Contratuais Padrão da Microsoft é compatível. E quando o Escudo de Privacidade UE-EUA ficou disponível, a Microsoft foi a primeira empresa a certificar. Confira a[Certificação de Escudo de Privacidade da Microsoft](https://www.privacyshield.gov/participant?id=a2zt0000000KzNaAAK&status=Active)e leia os [Termos de Serviços Online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46). O Escudo de Privacidade da UE ajuda os clientes que desejam transferir seus dados para os Estados Unidos, de uma maneira coerente com as obrigações de proteção de dados.

**Quais são as outras ofertas de conformidade da Microsoft?**

Por ser uma empresa global com clientes em quase todos os países do mundo, a Microsoft tem um portfólio de conformidade robusto para ajudar nossos clientes. Para exibir uma lista completa de nossas ofertas de conformidade, incluindo FedRamp, HIPAA/biotipo, ISO 27001, ISO 27002, ISO 27018, NIST 800-171, UK G-Cloud e muitos outros visite nossos [tópicos de oferta de conformidade](offering-home.md).

**Como o RGPD afetará a minha empresa?**

O RGPD impõe uma ampla variedade de requisitos às organizações que coletam ou processam dados pessoais, incluindo um requisito para atender a seis princípios principais:

- *Transparência*,*imparcialidade* e *legalidade* no gerenciamento e no uso de dados pessoais. Você precisará ser claro com as pessoas sobre como você está usando dados pessoais e também precisará de uma "base legal" para processar esses dados.
- Limitar o processamento de dados pessoais a finalidades *especificadas*, *explícitas* e *legítimas*. Você não poderá reutilizar ou divulgar dados pessoais para fins que não sejam "compatíveis" com a finalidade para a qual os dados foram originalmente coletados.
- *Minimizar a coleta e o armazenamento de dados pessoais* que são adequados e relevantes para o propósito desejado.
- Garantindo a *precisão de dados pessoais* e permitindo que eles sejam *apagados ou retificados*. Você precisará tomar medidas para garantir que os dados pessoais que você possui sejam precisos e possam ser corrigidos se ocorrerem erros.
- *Limitando o armazenamento de dados pessoais*. Será necessário garantir que os dados pessoais sejam retidos apenas pelo tempo necessário para alcançar o propósito para o qual os dados foram coletados.
- Garantindo *segurança*, *integridade* e *confidencialidade de dados pessoais*. Sua organização deve tomar medidas para manter os dados pessoais protegidos por meio de medidas de segurança técnica e organizacional.

Você precisará entender as obrigações específicas da sua organização com o RGPD, e como as atenderá, embora a Microsoft esteja disponível para te ajudar em sua jornada.

**Quais direitos as empresas precisam garantir segundo os termos do RGDP?**

O RGDP fornece aos residentes da UE o controle sobre seus dados pessoais por meio de um conjunto de “direitos de assunto de dados”. Isso inclui o direito de:

- Acessar informações sobre como os dados pessoais são usados.
- Acessar dados pessoais mantidos por uma organização.
- Ter dados pessoais incorretos excluídos ou corrigidos.
- Ter dados pessoais corrigidos e apagados em determinadas circunstâncias (às vezes chamado de "direito a ser esquecido").
- Restringir ou se opor ao processamento automático de dados pessoais.
- Receber uma cópia dos dados pessoais.

**O que são processadores e controladores?**

Um controlador é uma pessoa física ou jurídica, autoridade pública, agência ou outro órgão que, individualmente ou em conjunto com outras pessoas, determina a finalidade e os meios de processamento de dados pessoais. O processador é uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.

**O RGPD se aplica a processadores e controladores?**

Sim, o RGPD se aplica a controladores e processadores. Os controladores devem usar apenas processadores que utilizam medidas para atender aos requisitos do RGPD. De acordo com o RGPD, os processadores enfrentam deveres e responsabilidades adicionais por não conformidade ou por agir fora das instruções fornecidas pelo controlador, em comparação com a Diretiva de Proteção de Dados. As tarefas de processador incluem, mas não se limitam a:

- Processar os dados somente conforme as instruções do controlador.
- Usar medidas técnicas e organizacionais apropriadas para proteger dados pessoais.
- Auxiliar o controlador com as solicitações de assunto de dados.
- Garantir que os subprocessadores envolvidos atendam a esses requisitos.

**Qual o valor máximo da multa pela não conformidade das empresas?**

As empresas podem ser multadas em até &euro;20m ou 4% do faturamento global anual, o que for maior, por não atender a determinados requisitos do RGPD. Outras soluções individuais podem aumentar o risco caso você não cumpra aos requisitos do RGPD.

**Minha empresa precisa indicar um DPO (Diretor de Proteção de Dados)?**

Isso depende de vários fatores identificados dentro da regulamentação. O artigo 37 da RGPD afirma que os controladores e os processadores devem designar um diretor de proteção de dados em qualquer caso em que: (a) o processamento tenha sido feito por uma autoridade pública ou corpo, exceto por tribunais atuando em sua capacidade judicial; (b) as principais atividades do controlador ou do processador consiste em operações de processamento que, em virtude da natureza, do escopo e/ou de seus propósitos, exigem o monitoramento regular e sistemático dos assuntos de dados em uma grande escala; ou (c) as principais atividades do controlador ou processador consistem em processamento em uma grande escala de categorias especiais de dados, de acordo com o artigo 9 e dados pessoais relacionados a condenações e infrações penais referidas no artigo 10.

**Quanto custará atender à conformidade com o RGPD?**

Atender a conformidade com o RGPD custará tempo e dinheiro para a maioria das organizações, embora possa ser uma transição mais suave para quem está operando em um modelo de serviços de nuvem bem estruturado e que tenham um programa de governança de dados eficaz no local.

**Como faço para saber se os dados que a minha organização está processando são cobertos pelo RGPD?**

O RGPD regula o conjunto, armazenamento, uso e compartilhamento de "dados pessoais". Os dados pessoais são definidos em linhas gerais no RGPD como todos os dados relacionados a uma pessoa física identificada ou identificável.

Os dados pessoais podem incluir, mas não se limitam a identificadores online (por exemplo, endereços de IP), informações de funcionários, bancos de dados de vendas, dados de atendimento ao cliente, formulários de comentários do cliente, dados de localização, dados biométricos, imagens de CCTV, registros de esquemas de fidelidade, informações de saúde e financeiras e muito mais. Pode inclusive incluir informações que não parecem ser pessoais, como uma foto de um paisagem sem pessoas, onde essas informações são vinculadas por um número de conta ou código exclusivo a uma pessoa identificável. E mesmo dados pessoais que foram pseudonimizados podem ser dados pessoais se o pseudônimo puder ser vinculado a um indivíduo em particular. 

O processamento de determinadas categorias "especiais" de dados pessoais, como dados pessoais que revelem origem racial ou étnica de uma pessoa ou que fale sobre saúde ou orientação sexual, está sujeito a regras mais estritas do que o processamento de dados pessoais "simples". Essa avaliação de dados pessoais é muito específica, portanto, recomendamos envolver um especialista para avaliar as circunstâncias específicas.

**Minha organização só processa dados em nome de outras pessoas. Ainda é necessário obedecer à RGPD?**

Sim. Embora as regras sejam diferentes, o RGPD se aplica à organizações que coletam e processam os dados para fins próprios ("controladores"), bem como para as organizações que processam os dados em nome de outras pessoas ("processadores"). Esse requisito é uma mudança da Diretiva de Proteção de Dados existente, que se aplica a controladores.

**O que é considerado especificamente dados pessoais?**

Os dados pessoais são quaisquer informações relacionadas a uma pessoa, identificável ou não. Não há distinção entre as funções pública, privada ou de trabalho de uma pessoa. Os dados pessoais podem incluir:

- Nome
- Endereço residencial
- Endereço comercial
- Telefone
- Celular
- Endereço de email
- Número do passaporte
- RG
- CPF (ou equivalente)
- Habilitação
- Informações físicas, fisiológicas ou genéticas
- Informações médicas
- Identidade cultural
- Detalhes bancários/números de conta
- Número de contribuinte
- Endereço comercial
- Números de cartão de crédito/débito
- Postagens em mídia social
- Postagens em mídia social
- Endereço IP (região da UE)
- Dados de localização/GPS
- Cookies

**Posso transferir dados de fora da UE?**

Sim, no entanto, o RGPD regula estritamente as transformações de dados pessoais de residentes na Europa, para destinos fora da Área Econômica Europeia. Talvez seja necessário configurar um mecanismo legal específico, como um contrato, ou obedecer a um mecanismo de certificação para habilitar essas transferências. A Microsoft detalha os mecanismos que usamos nos termos de serviços online.

**Tenho requisitos de retenção de dados por meio de conformidade. Esses requisitos substituirão o direito de fazer o apagamento?**

No caso em que existam motivos legítimos para o processamento contínuo e para a retenção de dados, como “o cumprimento de uma obrigação legal, que exige o processamento pela legislação da União ou Estado-Membro a que o responsável pelo tratamento está sujeito" (Artigo 17(3)(b)). O RGPD reconhece que as organizações podem ser obrigadas a reter dados. No entanto, você deve ter a certeza de que está envolvido em contato com a assessoria legal, para garantir que o aterramento da retenção seja avaliado em relação aos direitos e às suas expectativas, no momento em que os dados foram coletados, etc.

**O RGPD lida com criptografia?**

A criptografia é identificada na RGPD como uma medida de proteção que processa dados pessoais ininteligíveis quando eles forem afetados por uma violação. Portanto, o uso ou não da criptografia pode afetar os requisitos para a notificação de uma violação de dados pessoais. O RGPD também aponta para a criptografia como uma medida técnica ou organizacional adequada em alguns casos, dependendo do risco. A criptografia também é um requisito do Padrão de Segurança de dados do setor de cartão de crédito e parte das diretrizes de conformidade estritas específicas para o setor de serviços financeiros. Os produtos e serviços da Microsoft, como o Azure, o Dynamics 365, o Enterprise Mobility + Security, o Office Microsoft 365, o banco de dados SQL Server/Azure SQL e o Windows 10 oferecem criptografia robusta para dados em trânsito e dados em repouso.

**Como o RGPD altera a resposta de uma organização a violações de dados pessoais?**

O RGPD alterará os requisitos de proteção de dados e tomará obrigações mais estritas para processadores e controladores em relação a notificações de violações de dados pessoais. Sob a nova regulamentação, o processador deve notificar o controlador de dados de uma violação de dados pessoal, depois de ter ciência, sem atrasos inesperados. Depois de conhecer um vazamento de dados pessoal, o controlador deve notificar a autoridade de proteção de dados relevante em até 72 horas. Se a violação provavelmente resultar em um alto risco para os direitos e as liberdade das pessoas, os controladores também precisarão notificar as pessoas afetadas sem atrasos indesejados. As diretrizes adicionais neste tópico estão sendo elaboradas pelo Grupo de Trabalho do Artigo 29 da UE.

Os produtos e serviços da Microsoft, como o Azure, o Dynamics 365, o Enterprise Mobility + Security, o Microsoft Office 365 e o Windows 10, têm soluções disponíveis para ajudar você a detectar e avaliar ameaças e violações de segurança e cumprir as obrigações de notificação de violações do RGPD.

## <a name="additional-resources"></a>Recursos adicionais

- [Atenda às suas necessidades em torno de GDPR com um dos nossos parceiros globais, oferecendo soluções baseadas na Microsoft](https://aka.ms/findgdprpartner)
- [Saiba como a Microsoft gerencia seus dados, onde ele está localizado, quem pode acessá-los, os termos e muito mais.](https://www.microsoft.com/trust-center/privacy)
- [Saiba como a Microsoft adere aos princípios da estrutura do Escudo de Segurança EU-U.S](https://blogs.microsoft.com/eupolicy/2016/07/11/eu-u-s-privacy-shield-progress-for-privacy-rights/)
- [Como a Microsoft detecta e responde a uma violação de dados pessoais e notifica o usuário segundo o RGPD](https://www.microsoft.com/trust-center/privacy/gdpr-data-breach)
- [Avaliar a preparação do RGPD hoje](https://discover.microsoft.com/gdpr-readiness-assessment/)
