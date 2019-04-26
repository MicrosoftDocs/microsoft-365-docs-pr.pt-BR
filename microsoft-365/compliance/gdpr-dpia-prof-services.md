---
title: 'Orientação para controladores de dados usando os Serviços Profissionais da Microsoft '
description: Este documento fornece aos controladores de dados informações sobre os Serviços Profissionais que os ajudarão a determinar se a AIPD é necessária e quais detalhes devem ser incluídos.
keywords: DPIA, Serviços Profissionais da Microsoft, Documentação do Microsoft 365 DPIA, GDPR
robots: NOINDEX,NOFOLLOW
author: herviicban
ms.localizationpriority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: heicba
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: d9dd822e7e9ef7a93a41c056fc7bc014274ad190
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285530"
---
# <a name="data-protection-impact-assessments-guidance-for-data-controllers-using-microsoft-professional-services"></a>Avaliações do Impacto sobre a Proteção dos Dados: orientações para controladores de dados que usam o Serviços Professionais da Microsoft 

## <a name="introduction-to-microsoft-professional-services"></a>Introdução aos serviços profissionais da Microsoft

Os serviços Profissionais da Microsoft incluem um grupo diversificado de arquitetos técnicos, engenheiros, consultores e profissionais de suporte dedicados a cumprir a missão da Microsoft de capacitar os clientes a fazer mais e obter mais. Saiba mais sobre os Serviços Profissionais da Microsoft acessando a seção Serviços Profissionais da Microsoft na Central de Confiabilidade da Microsoft (<https://www.microsoft.com/trustcenter/professional-services>).

Os Serviços Profissionais da Microsoft leva a sério suas obrigações sob o Regulamento Geral de Proteção de Dados (GDPR). As informações neste documento são projetadas para fornecer informações sobre ofertas de suporte e consultoria da Microsoft que os clientes podem usar ao preparar avaliações de impacto de proteção de dados (DPIAs) em GDPR.

### <a name="introduction-to-dpias"></a>Introdução às DPIAs

De acordo com o Regulamento Geral sobre a Proteção de Dados (RGPD), os controladores de dados devem preparar uma DPIA para processar operações que forem "suscetíveis de implicar um elevado risco para os direitos e as liberdades das pessoas singulares." Não há nada inerente nos Serviços Profissionais da Microsoft que necessariamente exigiria a criação da AIPD pelo Controlador de Dados que esteja usando esses produtos. Na verdade, a necessidade ou não de uma AIPD dependerá dos detalhes e do contexto do tipo de serviço e como o controlador de dados usa os serviços profisisonais.

O objetivo deste documento é fornecer informações sobre os Serviços Profissionais aos Controladores de Dados, para lhes ajudar a determinar se a AIPD é necessária e, se esse for o caso, a saber que detalhes devem ser incluídos.

## <a name="part-1--determining-whether-a-dpia-is-needed"></a>Parte 1 – Determinar se a AIPD é necessária

O Artigo 35 do RGPD exige que o controlador de dados crie uma AIPD "Quando um certo tipo de tratamento, em particular que utilize novas tecnologias e tendo em conta a sua natureza, âmbito, contexto e finalidades, for suscetível de implicar um elevado risco para os direitos e liberdades das pessoas singulares". O Artigo ainda apresenta os fatores particulares que indicam um risco elevado, os quais são discutidos na tabela a seguir. Para determinar se a AIPD é necessária, o controlador de dados deve considerar esses fatores, além de outros que possam ser relevantes, levando em conta as implementações e os usos específicos dos Serviços Profissionais.

***Tabela 1 – fatores de risco e informações relevantes***

<!--start table here NO HEADER -->

|||
|:-----|:-----|
|**Fator de risco**|**Informações relevantes sobre os Serviços Profissionais**|
|Avaliação sistemática e completa dos aspectos pessoais relacionados a pessoas singulares, baseada no tratamento automatizado, incluindo a criação de perfis, sendo com base nela adotadas decisões que produzem efeitos legais relativamente à pessoa singular ou que a afetem significativamente de forma semelhante;|Os Serviços Profissionais realizam determinados processamentos rotineiros ou automatizados de dados, como suporte a quebras / reparos (por exemplo, assistência a clientes quando o computador quebra), migração de contas e análise de vulnerabilidades do sistema. As soluções de Serviços Profissionais, excluindo o desenvolvimento do cliente cobertos pela observação abaixo, não têm como objetivo realizar o processamento no qual as decisões são baseadas e produzem efeitos legais ou de significância similar em indivíduos.|
|Processamento em largas escalas [^1] de categorias especiais de dados (dados pessoais que revelem a origem racial ou étnica, as opiniões políticas, as convicções religiosas ou filosóficas, ou a filiação sindical, bem como o tratamento de dados genéticos, dados biométricos para identificar uma pessoa de forma inequívoca, dados relativos à saúde ou dados relativos à vida sexual ou orientação sexual de uma pessoa) ou de dados pessoais relacionados a crimes e condenações criminais;|Os Serviços Profissionais não se destinam a ser utilizados em trabalhos que exijam o processamento de categorias especiais de dados pessoais, excluindo o desenvolvimento do cliente coberto pela observação abaixo.<p>No entanto, um controlador de dados pode usar soluções de consultoria de serviços profissionais para processar as categorias especiais de dados enumeradas. Por exemplo, os Serviços Profissionais oferecem desenvolvimento de banco de dados do setor de saúde que pode ser usado por um controlador de dados para processar dados pessoais associados a uma condição de integridade. É responsabilidade do controlador avaliar e restringir ou documentar esse uso conforme apropriado.</p>|
| Monitoramento sistemático de uma área de acesso público em grande escala|Os Serviços Profissionais não se destinam a ser utilizados em trabalhos que exijam ou facilitem ou facilitem esse monitoramento, excluindo o desenvolvimento do cliente coberto pela observação abaixo.<p>Se um controlador de dados usasse Serviços Profissionais para desenvolver esse tipo de sistema ou usasse sistemas de TI para processar dados coletados por meio desse monitoramento, isso seria responsabilidade do controlador de dados, conforme descrito abaixo.</p>|
|||

<!-- end of table -->
  
[Anotação de desenvolvimento personalizado] Os Serviços Profissionais oferecem uma ampla variedade de soluções de consultoria. Um controlador de dados poderia solicitar uma solução que, de acordo com os critérios acima, seria uma solução de alto risco. Por exemplo, um controlador de dados pode solicitar que os Serviços Profissionais criem uma solução para desenvolver um mecanismo de engenharia de negócios para decisões de emprego ou aplicativos de crédito ou uma solução que envolva rastreamento de usuários, uso especializado de Inteligência Artificial (AI) ou processamento de categorias especiais. de dados pessoais.

No início de um compromisso, os Serviços Profissionais têm processos para avaliar e abordar soluções de alto risco que podem ser solicitadas para o trabalho. Como parte disto, os Serviços Profissionais podem exigir garantias do controlador de dados sobre a conformidade com o GDPR (por exemplo, termos contratuais), um plano para o desenvolvimento de um DPIA ou outros critérios (por exemplo, diretrizes de operação acordadas) conforme requerido por um processador de dados sob o GDPR. No entanto, independentemente das ações da Microsoft, é responsabilidade do controlador de dados desenvolver o DPIA com a entrada, quando aplicável, do processador dos dados do cliente.

## <a name="part-2--contents-of-a-dpia"></a>Parte 2: Conteúdo de uma AIPD

O Artigo 35(7) exige que a Avaliação de Impacto sobre a Proteção de Dados especifique os propósitos para o processamento, além de uma descrição sistemática desse processamento previsto. A descrição sistemática de uma AIPD abrangente pode incluir fatores como os tipos de dados processados, por quanto tempo os dados ficarão retidos, onde os dados estão localizados e para onde serão transferidos e os terceiros que podem ter acesso a esses dados. Além disso, a AIPD deve incluir.

-   uma avaliação da necessidade e da proporcionalidade das operações de processamento em relação aos propósitos;

-   uma avaliação dos riscos aos direitos e às liberdades dos indivíduos; e

-   as medidas previstas para lidar com os riscos, incluindo garantias, medidas de segurança e mecanismos para garantir a proteção dos dados pessoais, além de demonstrar a conformidade com este Regulamento considerando os direitos e os interesses legítimos dos titulares dos dados e outras preocupações das pessoas.

A tabela a seguir contém informações sobre o Serviços Profissionais da Microsoft que são relevantes para cada um desses elementos. Assim como na Parte 1, os controladores de dados devem considerar os detalhes apresentados a seguir no contexto de implementação e uso específicos do Serviços Profissionais.

***Tabela 2, elementos de DPIA para Serviços Profissionais Relevantes***

<!--start table here -->

|||
|:-----|:-----|
|**Elementos de uma AIPD** |**Informações relevantes sobre Serviços Profissionais**|
|Propósitos de processamento|Os propósitos de processamento de dados usando o Serviços Profissionais são determinados pelo controlador que o implementa, configura e utiliza.<p>Conforme especificado pelo [Adendo de Proteção de Dados de Serviços Profissionais da Microsoft](http://aka.ms/professionalservicesdpa) (MPSDPA), a Microsoft, como processador de dados, processa Dados de Suporte e Consultoria apenas para fornecer os serviços solicitados ao nosso cliente, o controlador de dados. A Microsoft não usará dados de suporte e consultoria ou informações derivadas dela para fins comerciais ou similares.</p>|
|Os propósitos de processamento de dados usando o Serviços Profissionais são determinados pelo controlador que o implementa, configura e utiliza.|Conforme especificado pelo [Adendo de Proteção de Dados de Serviços Profissionais da Microsoft](http://aka.ms/professionalservicesdpa) (MPSDPA), a Microsoft, como processador de dados, processa Dados de Suporte e Consultoria apenas para fornecer os serviços solicitados ao nosso cliente, o controlador de dados. A Microsoft não usará dados de suporte e consultoria ou informações derivadas dela para fins comerciais ou similares.|
|Categorias de dados pessoais processados|Os dados de Suporte e Consultoria significam que todos os dados, incluindo todo o texto, som, vídeo, arquivos de imagens ou software, são fornecidos à Microsoft pelo Cliente ou em seu nome (ou que o Cliente autoriza a Microsoft a obtê-los de um Serviço Online) por meio de um envolvimento com a Microsoft para obter Serviços Profissionais ou Suporte. Isso pode incluir informações coletadas por telefone, chat, e-mail ou formulário da web. Pode incluir descrição de problemas, arquivos transferidos para a Microsoft para resolver problemas de suporte, solucionadores de problemas automatizados ou acessando remotamente os sistemas do cliente com a permissão do cliente.<p>Os dados do cliente e os dados de suporte não incluem dados de contato ou cobrança do cliente, como informações de assinatura e dados de pagamento, que a Microsoft coleta e processa na qualidade de controladora de dados.</p>|
|Retenção de dados|A Microsoft reterá os Dados de Suporte e Consultoria pela duração do envolvimento do cliente, além de um período de retenção após o término do contrato, conforme necessário, para garantir a qualidade e a continuidade do serviço. Por exemplo, depois que um caso de suporte é fechado, os dados são normalmente retidos por um período para garantir a capacidade de referenciá-lo se o problema voltar a surgir e o caso for reaberto.<p>Quando os Serviços Profissionais fornecem suporte, o comprimento do compromisso é definido quando o caso de suporte é fechado. Quando os Serviços Profissionais fornecem serviços de consultoria, a duração do trabalho é geralmente definida pela ordem de serviço. Em outros casos, a duração do trabalho é definida pela manutenção do relacionamento comercial. Em todos os casos, os Dados de Suporte e Consultoria serão excluídos ou devolvidos mediante solicitação ou de acordo com as instruções do cliente, sem atrasos indevidos, usando os recursos descritos no *Guia dos Direitos dos Titulares dos Dados* dos Serviços Profissionais.</p>|
|Localização e transferências de dados pessoais|Devido à natureza dos Serviços Profissionais, incluindo a necessidade de fornecer suporte 24 horas por dia, os dados podem ser transferidos para todo o mundo. Uma lista de locais em que a Microsoft opera está disponível mediante solicitação. Para serviços de consultoria, os dados podem ser mantidos no país, se acordados dentro da ordem de serviço.<p>Para os dados pessoais provenientes do Espaço Econômico Europeu e Suíça, a Microsoft garante que a realização de transferências de Dados Pessoais para um terceiro país ou uma organização internacional está sujeita às medidas de segurança apropriadas, conforme descritas no Artigo 46 do RGPD. Além dos compromissos da Microsoft regidos pelas Cláusulas Contratuais Padrão para processadores e outros modelos de contrato conforme descrito na [MPSDPA](http://aka.ms/professionalservicesdpa), a Microsoft tem a certificação Privacy Shield Frameworks UE-EUA e Suíça-EUA e os compromissos que ela envolve.|
|Compartilhamento de dados com terceiros|A Microsoft compartilha dados com terceiros que atuam como nossos sub-processadores e para oferecer funções como atendimento ao cliente e suporte técnico, manutenção de serviço e outras operações. Qualquer subcontratado para o qual a Microsoft transferir Dados de Consultoria e Suporte terá firmado contrato por escrito com a Microsoft com o mesmo nível de proteção dos Termos de Proteção de Dados dos [MPSDPA](http://aka.ms/professionalservicesdpa). Todos os sub-processadores de terceiros com os quais Dados de Suporte e Consultoria são compartilhados sob o [MPSDPA](http://aka.ms/professionalservicesdpa) estão incluídos na [Lista de Contratados de Suporte Comercial da Microsoft](http://aka.ms/servicesapprovedsuppliers).<p>A Microsoft não revelará os Dados de Suporte e Consultoria às autoridades legais, a menos que exigido por lei. Se as autoridades contatarem a Microsoft exigindo os Dados de Suporte e Consultoria, a Microsoft irá empenhar-se em redirecionar as autoridades para solicitar tais dados diretamente do cliente. Se for obrigada a divulgar os Dados de Suporte e Consultoria às autoridades, a Microsoft irá imediatamente notificar o cliente e fornecer uma cópia da solicitação, a menos que seja proibida por lei.<p>Se receber qualquer solicitação de terceiros para a obtenção dos Dados de Suporte e Consultoria, a Microsoft irá imediatamente notificar o cliente, a menos que seja proibida por lei. A Microsoft rejeitará a solicitação, a menos que seja obrigada por lei a atendê-la. Se a solicitação for válida, a Microsoft irá empenhar-se em redirecionar o terceiro para solicitar os dados diretamente do cliente.</p>|
|Direitos dos titulares dos dados|Como processadora, a Microsoft disponibiliza aos clientes (controladores de dados) os dados pessoais dos seus titulares de dados e a capacidade de atender às solicitações dos titulares ao exercer seus direitos de acordo com o RGPD. Fazemos isso de forma compatível com a funcionalidade do produto e com nossa função como processadora de dados. Se recebermos uma solicitação dos titulares com o fim de exercer um ou mais de seus direitos de acordo com o RGPD, encaminharemos esses titulares a fazer a solicitação diretamente ao controlador de dados.<p>A *Documentação GDPR de Solicitação de Direitos dos Titulares de Dados dos Serviços Profissionais* fornece uma descrição de como o cliente pode abordar suas obrigações de direitos dos titulares de dados em Serviços Profissionais.</p>|
Avaliação da necessidade e da proporcionalidade das operações de processamento em relação aos propósitos|Essa avaliação dependerá das necessidades e dos propósitos de processamento do controlador.<p>Em relação ao processamento realizado pela Microsoft, ele é necessário e proporcional ao propósito de fornecer os serviços ao controlador de dados. A Microsoft se compromete a isto na [MPSDPA](http://aka.ms/professionalservicesdpa).</p>|
|Avaliação dos riscos aos direitos e às liberdades dos titulares dos dados|Os principais riscos aos direitos e liberdades dos titulares de dados pelo uso dos Serviços Profissionais será uma função de como e do contexto em que o controlador dos dados implementa, configura e usa os serviços profissionais e qualquer solução fornecida pelos Serviços Profissionais.<p>No entanto, como com qualquer serviço, os dados pessoais mantidos no serviço podem correr o risco de acesso não autorizado ou divulgação inadvertida. As medidas que a Microsoft toma para lidar com tais riscos são discutidas a seguir.</p>|
| Medidas previstas para lidar com os riscos, incluindo garantias, medidas de segurança e mecanismos para garantir a proteção dos dados pessoais e demonstrar a conformidade com o RGPD considerando os direitos e os interesses legítimos dos titulares dos dados e de terceiros envolvidos<!--is this the correct ending? -->|A Microsoft está comprometida em ajudar a proteger a segurança das informações do cliente. Em conformidade com as cláusulas do Artigo 32 do RGPD, a Microsoft implementou, manterá e seguirá as medidas técnicas e organizacionais apropriadas com a intenção de proteger os Dados de Suporte e Consultoria contra o acesso, a divulgação, a alteração, a perda ou a destruição acidental, não autorizada ou ilegal.<p>Além disso, a Microsoft cumpre todas as demais obrigações do RGPD que se aplicam a processadores de dados, incluindo, entre outras, avaliações do impacto na proteção dos dados e manutenção de registros.</p>|
|||

<!-- end of table -->

[^1]: With respect to the criteria that the processing be on a “large scale,” Recital 91 of the GDPR clarifies that: “The processing of personal data should not be considered to be on a large scale if the processing concerns personal data from patients or clients by an individual physician, other health care professional or lawyer. In such cases, a data protection impact assessment should not be mandatory.”


#### <a name="learn-more"></a>Saiba mais
[Central de Confiabilidade da Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
