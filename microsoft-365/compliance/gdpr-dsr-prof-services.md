---
title: Solicitações de titulares dos dados ao suporte e aos Serviços profissionais da Microsoft sobre o RGPD e CCPA
description: Como o suporte da Microsoft e os serviços profissionais cuidam das solicitações de entidades de dados para RGPD e CCPA
keywords: Serviços profissionais, Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
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
ms.openlocfilehash: 88dc03613a6a2b77ed9cb440d8c8d80c7cfbae2b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596488"
---
# <a name="microsoft-support-and-professional-services-data-subject-requests-for-the-gdpr-and-ccpa"></a>Solicitações de titulares dos dados ao suporte e aos Serviços profissionais da Microsoft sobre o RGPD e CCPA

## <a name="introduction-to-microsoft-professional-services"></a>Introdução aos serviços profissionais da Microsoft

Os Serviços profissionais da Microsoft incluem um grupo diverso de arquitetos, engenheiros, consultores técnicos e profissionais de suporte dedicados ao cumprimento da missão da Microsoft de capacitar os clientes a produzirem mais e conquistarem mais. Nossa equipe de Serviços profissionais tem mais de 21.000 consultores, Orientadores Digitais, Suporte Premier, engenheiros e profissionais de vendas trabalhando em 191 países, com suporte a 46 idiomas diferentes, gerenciando milhões de compromissos por mês e participando de interações com clientes e parceiros por meio de ferramentas locais, por telefone, na Web, na comunidade e automatizadas. A organização oferece uma ampla experiência no portfólio da Microsoft, utilizando uma ampla rede de parceiros, comunidades técnicas, ferramentas, diagnósticos e canais que nos conectam com nossos clientes corporativos.

Para saber mais sobre os Serviços Profissionais da Microsoft, acesse a [webpage de Documentação de Segurança dos Serviços Profissionais da Microsoft](https://www.microsoft.com/en-us/professionalservices/overview). Os Serviços profissionais da Microsoft levam a sério as suas obrigações no Regulamento Geral sobre a Proteção de Dados (RGPD). As informações neste documento foram projetadas para responder a perguntas de clientes sobre como as ofertas de suporte e consultoria responderão e auxiliarão clientes a responder a obrigações da Solicitação de Entidades de Dados (DSR) no RGPD.

### <a name="introduction-to-dsrs"></a>Introdução às DSRs 

O RGPD fornece direitos às pessoas (conhecidas na regulamentação como *titulares de dados*) para gerenciar os dados pessoais que foram coletados por um funcionário ou outro tipo de órgão ou organização (conhecido como *controlador de dados* ou apenas *controlador*). Os dados pessoais são definidos genericamente no RGPD como quaisquer dados relacionados a uma pessoa identificada ou identificável. O RGPD fornece aos titulares dos dados direitos específicos a seus dados pessoais; esses direitos incluem a obtenção de cópias, a solicitação de alterações, a restrição do processamento e a exclusão deles. Uma solicitação formal realizada por um titular dos dados para que um controlador realize um determinado pedido com os dados pessoais do titular é chamada de *Solicitação do Titular dos Dados* ou DSR. Além disso, ela obriga as empresas que trabalham em nome de um controlador (conhecido como *processador de dados* ou apenas *processador*) a ajudar razoavelmente o controlador a atender às DSRs.

Da mesma forma, a Lei de Privacidade do Consumidor da Califórnia (CCPA), fornece direitos e obrigações de privacidade aos consumidores da Califórnia, incluindo direitos semelhantes aos Direitos do Titular dos Dados do RGDP, como o direito de excluir, acessar e receber (portabilidade) suas informações pessoais.  O CCPA também fornece certas divulgações, proteções contra discriminação ao eleger direitos de exercício e requisitos de "auto-exclusão/opção de inclusão" para determinadas transferências de dados classificados como "vendas". As vendas são amplamente definidas para incluir o compartilhamento de dados para uma consideração valiosa. Para obter mais informações sobre o CCPA, confira a [Lei de Privacidade do Consumidor da Califórnia](offering-ccpa.md) e as [Perguntas Frequentes Sobre a Lei de Privacidade do Consumidor da Califórnia](ccpa-faq.md).

Este guia discute como localizar, acessar e atuar em dados pessoais que residem nos sistemas de TI da Microsoft que podem ter sido coletados para fornecer Suporte e outras ofertas dos Serviços Profissionais.

Ao desenvolver uma resposta para as DSRs, é importante para os clientes da Microsoft entenderem que os dados de consultoria e de suporte são separados dos dados de cliente nos Serviços Online ou de outros dados que eles ou seus titulares de dados possam ter fornecido à Microsoft. As ferramentas e os processos fornecidos para Serviços Online, o Painel de Privacidade da Microsoft ou outros sistemas da Microsoft para resposta às DSRs da Microsoft não podem ser usados para responder a DSRs relativas aos dados pessoais mantidos pelo Suporte da Microsoft ou outros Serviços profissionais.

Todas as solicitações precisam ser realizadas por meio de um representante do suporte, conforme descrito abaixo. Atualmente não há nenhuma ferramenta de autoatendimento para os clientes acessarem dados pessoais nas organizações de Serviços Profissionais.

#### <a name="overview-of-the-processes-outlined-in-this-guide"></a>Visão geral dos processos descritos neste guia

- **Descobrir** – use ferramentas de pesquisa e descoberta para localizar dados pessoais que possam ser a entidade de uma solicitação DSR. Após a coleta dos documentos que atendem à solicitação, você pode executar uma ou mais das ações de DSR a seguir para responder à solicitação. Como alternativa, você pode determinar que a solicitação não atende às diretrizes da sua organização para responder às solicitações DSR.
- **Acesso:** recupere dados pessoais que residem na nuvem da Microsoft e, se solicitado, faça uma cópia para disponibilizar para o titular dos dados.
- **Retificação:** faça alterações ou implemente outras ações solicitadas nos dados pessoais, onde for possível.
- **Restringir:** restrinja o processamento de dados pessoais, removendo licenças para vários serviços do Azure ou desativando os serviços desejados sempre que possível. Você também pode remover dados da nuvem da Microsoft e retê-los localmente ou em outro lugar.
- **Exclusão:** remova permanentemente os dados pessoais que residem na nuvem da Microsoft.
- **Exportar/Receber (Portabilidade): ** forneça uma cópia eletrônica (em formato legível para computador) de dados pessoais ou informações pessoais para o titular dos dados. Os dados pessoais do CCPA são quaisquer informações relacionadas a uma pessoa, identificável ou não. Não há distinção entre as funções pública, privada ou corporativa de uma pessoa. O termo definido como "informações pessoais" se alinha aproximadamente com "dados pessoais" do RGPD. No entanto, o CCPA também inclui dados da família e do domicílio. Para obter mais informações sobre o CCPA, confira a [Lei de Privacidade do Consumidor da Califórnia](offering-ccpa.md) e as [Perguntas Frequentes Sobre a Lei de Privacidade do Consumidor da Califórnia](ccpa-faq.md).

### <a name="terminology"></a>Terminologia

Vejamos abaixo as definições relevantes dos termos do RGPD para este guia:

- **Controlador:** a pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que, sozinha ou em conjunto com terceiros, determina os fins e os meios do processamento de dados pessoais, onde tais fins e meios são determinados por lei da União ou Estado-Membro, o controlador ou os critérios específicos para sua indicação podem ser fornecidos por lei da União ou Estado-Membro.
- **Dados pessoais e entidade de dados:** quaisquer informações relacionadas a uma pessoa física identificada ou identificável (“entidade de dados”); uma pessoa física identificável é aquela que pode ser identificada, direta ou indiretamente, especialmente por referência a um identificador, como nome, um número de identificação, dados de localização, um identificador online ou por um ou mais fatores específicos à identidade física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa física.
- **Processador:** uma pessoa singular ou coletiva, uma autoridade pública, uma agência ou outro organismo que processe dados pessoais em nome do controlador.

#### <a name="additional-terms-and-definitions-that-may-be-helpful-in-understanding-this-guide"></a>Outros termos e definições que podem ser úteis à compreensão deste guia

- **Dados de suporte e consultoria:** todos os dados, incluindo todo texto, som, vídeo, arquivo de imagem ou software, fornecidos à Microsoft pelo cliente ou em seu nome (ou que o cliente autorize a Microsoft a obter de um serviço online) por meio de uma interação com a Microsoft para obter suporte ou serviços profissionais. Para esclarecer, isso não inclui dados coletados cujo controlador de dados é a Microsoft, incluindo dados de contato do cliente.
- **Contato do cliente:** dados pessoais que podem fazer parte do seu relacionamento comercial com a Microsoft, como dados pessoais contidos nas informações de contato do cliente. Isso pode incluir o nome, email ou número de telefone do Gerente de Serviços de Contrato Premier (CSM), o Administrador Global ou de TI para um Serviço Online, ou funções semelhantes.
- **Dados sob pseudônimo:** quando você usa o suporte da Microsoft para produtos e serviços corporativos da Microsoft, a Microsoft gera algumas informações ligadas a um identificador numérico da Microsoft para fornecer o suporte. Isto é muitas vezes referido como "Dados sob pseudônimo". Embora estes dados não possam ser atribuídos a uma entidade de dados específica sem o uso de informações adicionais, alguns deles podem ser considerados pessoais segundo a ampla definição do RGPD para dados pessoais. Nos serviços profissionais, as solicitações para atender ou auxiliar no cumprimento de DSRs sempre incluirão automaticamente o tratamento de dados sob pseudônimo.

### <a name="how-to-use-this-guide"></a>Como usar este guia

Este guia trata de quatro cenários que um cliente pode encontrar se tiver utilizado os Serviços profissionais da Microsoft.

- **DSR para um contato do cliente envolvendo a Microsoft:** explicação de como a Microsoft responderá às solicitações de um contato do cliente ou administrador de TI para exercer os seus direitos de entidades de dados.
- **DSR para um usuário final envolvendo a Microsoft:** explicação de como a Microsoft responderá às solicitações dos funcionários de um cliente ou de outros sujeitos de dados para exercer seus direitos.
- **DSR para dados fornecidos pelo cliente: suporte comercial:** explicação de como receber assistência da Microsoft quando um cliente tiver recebido uma solicitação de um funcionário ou de outras entidades de dados para exercer seus direitos, e que os dados pessoais da entidade de dados foram coletados pelo suporte da Microsoft durante uma interação do suporte.
- **DSR para dados fornecidos pelo cliente: serviços de consultoria, incluindo serviços de migração FastTrack:** explicação de como receber assistência da Microsoft quando um cliente tiver recebido uma solicitação de um funcionário ou de outras entidades de dados para exercer seus direitos, e que os dados pessoais do usuário foram coletados pela Microsoft durante uma interação de consultoria.

## <a name="dsr-for-a-customer-contact-engaging-microsoft"></a>DSR para um contato do cliente à Microsoft

*Como a Microsoft responde às solicitações de um contato do cliente ou administrador de TI a fim de exercer os direitos do titular dos dados.*

Quando um cliente se envolve com a Microsoft para receber serviços de suporte ou consultoria, o Suporte da Microsoft coleta ou recupera automaticamente dos registros da conta os dados pessoais do Contato do Cliente (por exemplo, CSM Premier, Administrador Global, Administrador de TI). Isso provavelmente inclui o nome, email, telefone e outros dados pessoais do indivíduo que procura serviços de suporte e consultoria.

Os dados pessoais de Contato do Cliente são parte do relacionamento de negócios da Microsoft com o cliente, e a Microsoft é o controlador de dados. A Microsoft responderá às DSRs do Contato do Cliente sobre os seus dados pessoais, independentemente de eles ainda estarem com a organização.

Os clientes devem compreender que a DSR abrange apenas os dados pessoais do Contato do Cliente, e nenhuma alteração ou exclusão será feita em nenhum dos dados do cliente enviados como parte de interações (por exemplo, transcrições, descrições de casos, arquivos, produtos de trabalho), já que a Microsoft é o processador de dados. Além disso, para manter o registro histórico da interação, nenhuma mudança será feita em todas as interações encerradas, incluindo o registro de quem abriu uma interação.

Ao ser consultado por um Contato do Cliente sobre uma DSR, a equipe da Microsoft encaminhará um contato do cliente para o [Centro de Resposta de Privacidade](https://go.microsoft.com/fwlink/?LinkId=321116). Este é o mecanismo de entrada principal da Microsoft para consultas e reclamações sobre privacidade. Ao receber uma consulta, o Centro de Resposta de Privacidade identificará que isso faz parte de uma conta comercial ou organizacional e responderá de acordo.

Para garantir a continuidade de negócios do cliente, a Microsoft também não processará uma DSR associada a uma interação até a confirmação de um contato substituto. Após a confirmação de um novo contato, a Microsoft trocará o contato antigo pelo novo em interações abertas.

Os clientes podem optar por fazer alterações em seus dados coletados durante as interações com os Serviços profissionais pelo suporte normal ou por canais de consultoria, separado dessa DSR. Por exemplo, a Microsoft pode ajudá-lo a eliminar interações com o suporte, mediante solicitação (consulte abaixo na seção *Guia de DSR sobre os dados fornecidos pelo cliente*).

***Exemplo apenas para fins ilustrativos***

Davi é um administrador de TI de um cliente empresarial do O365, com uma interação de suporte aberta e duas interações fechadas. Agora, Davi está saindo da sua empresa e deseja excluir os seus dados. Davi entra em contato com o Centro de Respostas de Privacidade, que o identifica como o administrador de TI. Davi fica sabendo que seu nome não pode ser excluído das interações anteriores (fechadas) nem de qualquer dado nas interações abertas. No entanto, o Centro de Respostas de Privacidade substituirá Davi como contato no tíquete aberto atual caso ele indique um contato substituto. Davi avisa à Microsoft que Laura será o contato substituto e a Microsoft fará a alteração em todos os sistemas de suporte.

## <a name="dsr-for-an-end-user-engaging-microsoft"></a>DSR para um usuário final de envolvimento da Microsoft

*Como a Microsoft responderá às solicitações dos funcionários do cliente ou de outros titulares dos dados para exercer os direitos deles.*

Se os funcionários do cliente ou outros titulares dos dados entrarem em contato com a Microsoft para fazerem solicitações sobre seus dados coletados pela Microsoft na qualidade de processador de dados, o titular dos dados será informado de que precisará contatar o cliente da Microsoft, como o controlador de dados, para exercer esses direitos. Isso é tudo o que a Microsoft fará.

Se o titular dos dados também tiver contatado a Microsoft para exercer seus direitos sobre os dados que a Microsoft coletou em situações em que ela é a controladora de dados (por exemplo, suporte ao consumidor, contato do cliente comercial), a Microsoft responderá separadamente à solicitação de exercício de direito do titular dos dados do indivíduo relativa aos dados pessoais.

***Exemplo apenas para fins ilustrativos***

Jane é uma funcionária de um cliente corporativo, a Contoso, que forneceu a ela uma conta do Dynamics 365. Ela entra em contato com a Microsoft para excluir todos os dados e é encaminhada ao Privacy Response Center. Jane preenche o formulário de solicitação. O Privacy Response Center a identifica como um usuário final da empresa e permite que ela saiba que precisa solicitar a exclusão de seus dados corporativos à Contoso. Eles também a identificam como um usuário do Microsoft X-Box e excluem seus dados de sua conta de consumidor da Microsoft.

## <a name="dsr-for-customer-provided-data-commercial-support"></a>DSR para dados fornecidos pelo cliente: suporte comercial

*Como obter assistência da Microsoft quando um cliente recebe uma solicitação de seus funcionários ou de outros titulares de dados pedindo o exercício de direitos, e de que os dados pessoais do titular dos dados foram coletados pelo Suporte da Microsoft durante a interação com o suporte.*

Quando um cliente se envolve com o Suporte da Microsoft, a Microsoft coleta Dados de Suporte do cliente para resolver quaisquer problemas que requeiram uma interação do suporte. Esses Dados de Suporte incluem a interação da Microsoft com o cliente (por exemplo, bate-papo, telefone, email, envio pela Web) e quaisquer arquivos de conteúdo que o cliente envie à Microsoft ou que a Microsoft tenha extraído, com permissão do cliente, do ambiente de TI do cliente ou locação de serviços online para resolver o problema de suporte. No caso do suporte Premier, isso também incluirá todos os dados que coletarmos de você para evitar problemas futuros de maneira proativa. No entanto, isso exclui as informações de Contato do Cliente ou outras informações do relacionamento comercial da Microsoft com o cliente (por exemplo, registros de faturamento).

Para todos os Dados de Suporte, a Microsoft é o processador de dados. Dessa forma, a Microsoft não responderá às solicitações diretas dos titulares dos dados sobre os Dados de Suporte fornecidos quando foram associados a um cliente comercial da Microsoft. A Microsoft trabalhará com o cliente por meio dos canais de suporte normais para ajudá-lo a responder às DSRs.

## <a name="step-1-discover"></a>Etapa 1: Descoberta

O primeiro passo para obter assistência da Microsoft na resposta a uma DSR é encontrar os dados pessoais que são o assunto da DSR. Essa primeira etapa — encontrar e revisar os dados pessoais em questão — ajudará um cliente a determinar se uma DSR atende às políticas da organização para honrar uma solicitação de entidade de dados.

Depois que o cliente encontrar os dados, o cliente, em seguida, poderá executar a ação específica para atender à solicitação do titular dos dados. A determinação do nível de descoberta com que o cliente precisa se envolver dependerá do que o cliente está tentando fazer.

Quando a Microsoft auxilia um cliente com a solução de uma DSR, isso é uma função empresarial, e a solicitação é feita pelo canal de suporte normal, não por meio de uma solicitação ao Centro de Respostas de Privacidade.

Ao descobrir os dados relevantes e obter assistência da Microsoft, um cliente tem várias opções de abordagem da DSR:

*Opção A: DSR de cliente de suporte em toda a Microsoft*. Aplique a DSR a todos os dados de suporte do cliente no ambiente de suporte da Microsoft. Para fazer isso, um cliente só precisa pedir para a Microsoft aplicar a DSR a todos os Dados de Suporte coletados.

*Opção B — Interações Específicas do Cliente.* Use sistemas online para revisar tíquetes e, em seguida, identifique interações específicas que contenham os dados pessoais relevantes e relate-as à Microsoft. A Microsoft tentará fornecer assistência para realizar uma pesquisa se o cliente não puder pesquisar em interações (tíquetes).

***Assim que os contratos forem identificados, solicite a aplicação da DSR a uma parte específica do registro ou a tudo relacionado a essa interação na Microsoft.***

Para identificar interações específicas, os clientes precisam pesquisar as suas interações. Para os clientes Premier, o Gerente de Serviço de Contrato Premier (CSM) de um cliente tem a visibilidade de todas as Solicitações de Suporte (SRs) criadas sob essa Agenda do Contrato. Para os clientes não Premier, estão disponíveis portais de interação com o suporte equivalentes, como por meio das áreas de suporte dos Serviços Online.

![Pesquisar no SMC](media/Prof-Serv-DSR-Doc-Final_image3.png)O CSM pode acessar o portal em Support.Microsoft.Com ([https://support.microsoft.com/\<local código de idioma\>/premier](https://support.microsoft.com/%3clocal%20language%20code%3e/premier)) (“SMC”) e selecionar e revisar as Solicitações de Suporte. (Observação: na URL, substitua o seu código de idioma local).

>[!IMPORTANT]
>Além do histórico do caso no SMC, os clientes também podem ter dados pessoais de um usuário final em arquivos coletados pela Microsoft (ou, com a permissão do cliente, removidos do Serviço Online) durante uma interação do suporte. Os exemplos podem incluir cópias de caixas de correio do Exchange do cliente, VMs do Azure ou bancos de dados. Esses dados pessoais podem ou não ser mencionados no histórico do caso (ou seja, tíquete) para uma interação específica. Para revisar esses dados, o Contato do Cliente deve ser um contato de solicitação de suporte autenticado (via AAD ou MSA) específico que tenha recebido uma URL para um espaço de trabalho na Ferramenta de Gerenciamento e Transferência de Dados de Suporte da Microsoft (DTM). Um Contato do Cliente terá acesso aos arquivos, mas nenhuma visualização global está disponível, e o SMC não indicará se existem arquivos.

Depois que os clientes identificarem todos os dados relevantes nos tíquetes de suporte selecionados, os clientes poderão decidir se devem solicitar a exclusão de tudo o que estiver relacionado a um tíquete ou aplicar seletivamente a DSR a instâncias individuais dos dados pessoais.

## <a name="step-2-access"></a>Etapa 2: Acesso

Depois que um cliente encontrar Dados de Suporte que contenham dados pessoais potencialmente responsivos a uma DSR, cabe ao cliente decidir quais dados pessoais serão incluídos na resposta. Por exemplo, o cliente pode optar por remover dados pessoais sobre titulares dos dados e quaisquer informações confidenciais.

A resposta à DSR pode incluir uma cópia do documento real, uma versão adequadamente redigida ou uma captura de tela das partes que o cliente considerou adequadas ao compartilhamento. Para todas essas respostas a uma solicitação de acesso, o cliente precisará recuperar uma cópia do documento ou outro item que contenha dados responsivos.

O acesso aos dados pessoais de um usuário final pode provir de uma menção ou notação nos vários tipos de documentação de conteúdo. Como os clientes podem acessar o tíquete de interação e o conteúdo, eles podem fornecer um resumo dos dados pessoais sem a assistência da Microsoft.

Em casos raros, o cliente pode precisar obter cópias dos dados de interação do suporte (por exemplo, emails, cópias transcritas de gravações telefônicas, transcrições de bate-papo) entre um representante da Microsoft e o Representante do Cliente. Na medida do necessário, a Microsoft pode fornecer cópias redigidas dessas transcrições com base na necessidade, confidencialidade e dificuldade.

## <a name="step-3-rectify"></a>Etapa 3: Retificação

Se um titular dos dados pedir para o cliente retificar os dados pessoais residentes nos Dados de Suporte da organização, o cliente precisará determinar se é apropriado executar a solicitação. Se o cliente decidir atender à solicitação, poderá solicitar que a Microsoft faça a alteração. A Microsoft pode retificar ou excluir os dados do cliente dos sistemas de suporte e solicitar que o cliente os reenvie à Microsoft no formato corrigido.

## <a name="step-4-restrict"></a>Etapa 4: Restrição

O cliente pode, a qualquer momento, encerrar uma interação ou entrar em contato com a Microsoft e solicitar que o contrato seja encerrado. Uma interação encerrada impedirá que qualquer trabalho seja realizado.

Para garantia adicional, o cliente pode contatar a Microsoft e solicitar a colocação de uma observação no sistema de tíquetes de interação dizendo que o caso não deve ser reaberto por nenhum motivo sem a permissão do cliente.

Observação: os envolvimentos (tíquetes) também serão excluídos de acordo com um cronograma de retenção e exclusão, com base na confidencialidade dos dados, serviço e sistema. Se o cliente exigir uma cópia dos dados, ele deve garantir ter extraído os dados antes da exclusão.

## <a name="step-5-delete"></a>Etapa 5: Exclusão

O "direito de exclusão" pela remoção de dados pessoais dos Dados de Suporte de uma organização é uma proteção importante no RGPD. A remoção de dados pessoais inclui a exclusão de interações, documentos ou arquivos inteiros ou a exclusão de dados específicos em uma interação, documento ou arquivo.

Conforme um cliente investiga ou se prepara para excluir dados pessoais em resposta a uma DSR, existem alguns pontos importantes a serem entendidos sobre como a exclusão funciona para o Suporte da Microsoft.

Todos os dados da Microsoft têm uma política de retenção e exclusão aplicada a eles, que variam de acordo com o risco e outros fatores.

Os clientes que solicitarem a exclusão universal dos dados pessoais de um titular dos dados em todos os sistemas de suporte pode fazê-lo por meio do TAM ou apresentando uma Solicitação de Suporte (SR) no SMC ou sistema equivalente. Você *deve* indicar que essa é uma solicitação para ajudá-lo com a DSR em RGPD.

*Opção A — DSR de cliente de suporte em toda a Microsoft*. Para uma DSR de sistema cruzado, o cliente deve fornecer os dados pessoais que a Microsoft precisa para identificar os dados necessários (por exemplo, endereço de email, número de telefone). A Microsoft não irá correlacionar ou pesquisar registros e só pesquisará diretamente nos identificadores fornecidos pelo cliente. Quando dados forem encontrados, a Microsoft excluirá todas as interações e todos os dados associados.

> Observação Importante: isso pode resultar na perda de registros históricos importantes para a organização do cliente.

*Opção B — Interações Específicas do Cliente*. Para interações específicas que o cliente tenha identificado e deseje excluir, não exclua tíquetes do SMC. Isso resultará em dados pessoais remanescentes em logs e sistemas downstream que podem não ser excluídos dentro do período de tempo necessário. Em vez disso, identifique o tíquete ou os dados pessoais dentro do tíquete que deve ser excluído e entre em contato com o Suporte da Microsoft para ajudá-lo a excluir esses dados.

### <a name="microsoft-support-data-transfer-and-management-tool-dtm-instructions"></a>Instruções sobre a ferramenta de Gerenciamento e Transferência de Dados do Suporte da Microsoft (DTM)

Para todas essas pesquisas, a Microsoft não procurará na DTM devido à possível confidencialidade de conteúdo dos arquivos. No entanto, se o cliente quiser, a Microsoft excluirá todos os arquivos contidos na DTM associada à conta do cliente. Devido à possibilidade de implicações graves aos clientes, a Microsoft requer uma solicitação separada do cliente especificando a exclusão dos arquivos da DTM.

- Para casos abertos, o Contato do Cliente pode acessar a DTM e excluir os arquivos.
- Para os casos fechados há menos de 90 dias, deve ser feita uma solicitação de remoção de arquivos a um TAM ou em uma SR.
- Nos casos fechados depois de 90 dias, os arquivos já foram automaticamente excluídos.
- Ainda que os dados pessoais só estivessem localizados em um arquivo que foi excluído, os clientes ainda precisam pedir para a Microsoft executar uma busca por dados pessoais nos sistemas, pois alguns dados podem ter sido removidos da DTM no decorrer do suporte.

## <a name="step-6-export"></a>Etapa 6: Exportação

O "direito de portabilidade de dados" permite que um titular dos dados solicite uma cópia dos dados pessoais em um formato eletrônico e solicite que a sua organização os transmita para outro controlador. No caso dos Dados de Suporte, quaisquer informações úteis que a Microsoft tem estariam na forma de informações de interação ou arquivos que podem ser retornados para você para a retransmissão ou carregamento para outro controlador.

Observação: os dados exportados podem não incluir a propriedade intelectual da Microsoft ou quaisquer dados que possam comprometer a segurança ou a estabilidade do serviço.

***Exemplo apenas para fins ilustrativos***

Davi é um CSM Premier para um cliente empresarial, a Contoso, que usa o Office 365 para os emails dos funcionários e o Azure para hospedar um banco de dados SQL da Contoso. A Contoso tem vários tíquetes abertos e fechados. Recentemente, o Suporte da Microsoft, com permissão da Contoso, moveu uma cópia do banco de dados SQL para a DTM para fins de suporte e solução de problemas.

Davi recebe uma DSR de Laura solicitando a exclusão dos dados dela. Davi acessa o SMC e pesquisa as interações para identificar que Laura tinha problemas de conta de email, o que estava documentado em dois tíquetes por nome e endereço de email. Ele entra em contato com seu TAM, fornece ao TAM o nome e o endereço de email da Laura como um identificador e solicita que os dois tíquetes sejam excluídos, juntamente com todos os dados de downstream gerados a partir desses tíquetes.

Ele também suspeita que estava envolvido em uma conversa de chat com a equipe de suporte na qual menciona Laura, então solicita que o log do bate-papo seja excluído.

Ele também sabe que os dados pessoais de Laura estão no banco de dados SQL. Como a VM do SQL foi movida para a DTM há menos de 90 dias, ele pede separadamente a seu TAM que ajude na exclusão imediata do banco de dados da DTM.

Por fim, como ele sabe que os dados podem ter sido removidos do arquivo da DTM durante o suporte, ele pede que a Microsoft procure pelos dados pessoais de Laura nos sistemas de TI a partir do banco de dados SQL.

O Suporte da Microsoft executa todas essas exclusões e, com base na solicitação do cliente, o TAM lhe fornece uma instrução de atestado de que os dados necessários foram excluídos.

## <a name="dsr-guide-for-customer-provided-data-in-consulting-services-including-migration-services"></a>O Guia DSR para dados fornecidos pelo cliente em serviços de consultoria incluem os Serviços de migração

*Como obter assistência da Microsoft quando um cliente recebe uma solicitação de seus funcionários ou de outros titulares dos dados, pedindo o exercício de direitos, e os dados pessoais do titular dos dados foram coletados pela Microsoft durante a interação com a consultoria.*

## <a name="microsoft-consulting-services"></a>Serviços de consultoria da Microsoft

Para as interações com os serviços de consultoria da Microsoft contratadas em que se aplica o adendo de proteção de dados de Serviços profissionais da Microsoft (<https://aka.ms/professionalservicesdpa>).

A Microsoft é o controlador de dados dos Contatos do Cliente que trabalham com a equipe de interação. Esses indivíduos devem contatar o [Centro de Respostas de Privacidade](https://go.microsoft.com/fwlink/?LinkId=321116) para atender aos direitos do titular dos dados.

A Microsoft é o processador de dados para uma DSR localizada nos dados fornecidos durante a interação de consultoria. O cliente deve entrar em contato com o gerente de interação para criar um plano para ajudá-lo a responder à DSR com base nos dados coletados e, depois, no tipo específico dos serviços de consultoria fornecidos. Na extensão em que a sua solicitação constitui um nível de esforço geralmente visto dentro de uma interação dos Serviços de Consultoria da Microsoft, pode haver a necessidade de um pedido de trabalho adicional. Além disso, os dados pessoais serão excluídos após cada interação de consultoria em um período de tempo dependente do tipo de interação de consultoria. O cliente pode solicitar a exclusão de dados mais cedo e solicitar um atestado de exclusão.

## <a name="microsoft-fasttrack-services"></a>Serviços do Microsoft FastTrack

O [Microsoft FastTrack](https://na01.safelinks.protection.outlook.com/?url=https%3A%2F%2Ffasttrack.microsoft.com%2Fabout&data=02%7C01%7C%7Cd0521d8739c841df674508d596834585%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C636580412901207944&sdata=PO5eh56pm9IYk5Y%2Ff%2F31e%2BRVPmrC2Qi%2FCsw1NphR8gY%3D&reserved=0) fornece serviços de consultoria de TI às organizações para ajudá-las a integrar e usar os serviços em nuvem da Microsoft como o Microsoft 365, o Azure e o Dynamics 365.

A Microsoft é o controlador de dados para os Contatos do Cliente que trabalham com a equipe do FastTrack. Se os Contatos do Cliente quiserem acessar, analisar ou remover informações de contato dos registros do Microsoft FastTrack, os clientes poderão pedir que o titular dos dados envie a solicitação diretamente à caixa de entrada de Solicitação do RGPD do FastTrack do Office 365, \<<o365ftgdpr@microsoft.com>\>.

Para os serviços de migração do FastTrack, a Microsoft é o processador de dados. De acordo com nossa política do Fast Track de divulgação de privacidade adicional, todos os dados na migração são considerados “dados de migração”. Se precisar executar DSRs enquanto sua organização estiver envolvida em um projeto de migração do FastTrack, será necessário tomar cuidados especiais.
  
Se você precisar processar qualquer acesso ou retificar ou exportar solicitações de DSR enquanto os dados de um usuário estiverem sendo processados por meio de sistemas de migração FastTrack, será de responsabilidade do cliente cumprir tais DSRs por meio de seus sistemas de origem existentes nos quais os dados do usuário são armazenados. Depois que a migração do usuário for concluída e os dados tiverem sido migrados para o serviço de nuvem da Microsoft, a orientação fornecida pela Microsoft sobre como os clientes podem usar produtos, serviços e ferramentas administrativas da Microsoft para localizar e tomar ações em dados pessoais para responder à solicitação de assunto será então aplicada. Para visualizar essa orientação, confira [Solicitações de Entidades de Dados para o RGPD](https://docs.microsoft.com/microsoft-365/compliance/gdpr-data-subject-requests). 

Se precisar excluir a conta de um usuário do Office 365 em resposta a uma solicitação de DSR de exclusão enquanto sua organização estiver envolvida em um projeto de migração em andamento do FastTrack, você deverá estar ciente de que os sistemas de migração podem reter uma cópia dos dados de migração do usuário por um período de tempo após a conclusão da migração do usuário, e a exclusão da conta de usuário do Office 365 não excluirá automaticamente os dados de migração desse usuário armazenados nos sistemas de migração do FastTrack. Se você deseja que a equipe do Microsoft FastTrack exclua os dados de migração do usuário, [envie uma solicitação](https://go.microsoft.com/fwlink/?linkid=874544). No curso normal dos negócios, o Microsoft FastTrack excluirá todas as cópias de dados assim que a migração da organização for concluída.

## <a name="other-consulting-services"></a>Outros serviços de consultoria

O cliente que recebe outros Serviços Profissionais através da Microsoft deve trabalhar com a equipe de interação para atender a todos os requisitos do RGPD. Se a equipe de interação não puder fornecer instruções claras sobre o cumprimento do GDPR DSR, os clientes poderão pedir ajuda ao [Centro de Respostas de Privacidade](https://go.microsoft.com/fwlink/?LinkId=321116).
