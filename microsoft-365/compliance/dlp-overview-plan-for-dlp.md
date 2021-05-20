---
title: Plano de prevenção contra perda de dados
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Visão geral do processo de planejamento para prevenção de perda de dados
ms.openlocfilehash: 6a72a8bab27db4d8b11d3e0b3d7a1dac7a1f0092
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52581580"
---
# <a name="plan-for-data-loss-prevention-dlp"></a>Plano de prevenção contra perda de dados (DLP)

Todas as organizações planejarão e implementarão a prevenção contra perda de dados (DLP) de forma diferente, porque as necessidades, as metas, os recursos e a situação de cada organização são exclusivas para eles. No entanto, há elementos que são comuns a todas as implementações de DLP bem-sucedidas. Este artigo apresenta as práticas recomendadas usadas pelas organizações em seu planejamento de DLP.

## <a name="multiple-starting-points"></a>Vários pontos de partida

Muitas organizações optam por implementar a DLP para cumprir vários regulamentos governamentais ou do setor. Por exemplo, o RGPD (Regulamento Geral de Proteção de Dados) da União Europeia ou a Lei de Responsabilidade e Responsabilidade do Seguro de Saúde (HIPAA) ou a Lei de Privacidade do Consumidor da Califórnia (CCPA). Eles também implementam a prevenção contra perda de dados para proteger sua propriedade intelectual. Mas o local inicial e o destino final na jornada DLP variam. 

As organizações podem iniciar sua jornada de DLP:

- de um foco de plataforma, como querer Teams proteger informações em mensagens de chat e canal ou em Windows 10 dispositivos
- saber quais informações confidenciais eles querem priorizar a proteção, como registros de saúde, e ir direto para a definição de políticas para protegê-las
- sem saber quais são suas informações confidenciais, onde estão e quem está fazendo o que com ela para que eles comecem com a descoberta e categorização e a tomar uma abordagem mais metodista
- sem saber quais são suas informações confidenciais, ou onde estão, ou quem está fazendo o que com ela, mas eles se moverão diretamente para definir políticas e usar esses resultados como um ponto de partida e refinar suas políticas a partir daí
- sabendo que eles precisam implementar a pilha completa Microsoft 365 Proteção de Informações e, portanto, pretendem ter uma abordagem metodista e de longo prazo

Estes são apenas alguns exemplos de como os clientes podem se aproximar da DLP e não importa de onde você começa, Microsoft 365 DLP é flexível o suficiente para acomodar vários tipos de jornadas de proteção de informações do início a uma estratégia de prevenção contra perda de dados totalmente realizada. 

## <a name="overview-of-planning-process"></a>Visão geral do processo de planejamento

O [Learn about data loss prevention](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) apresenta os três aspectos diferentes do processo de planejamento de [DLP.](dlp-learn-about-dlp.md#plan-for-dlp) Vamos entrar em mais detalhes aqui sobre os elementos que são comuns a todos os planos de DLP.

### <a name="identify-stakeholders"></a>Identificar participantes

Quando implementadas, as políticas de DLP podem ser aplicadas em grandes partes da sua organização. A TI não pode desenvolver um plano abrangente por conta própria sem consequências negativas. Você precisa identificar os participantes que podem:

- descrever os regulamentos, leis e padrões do setor aos que sua organização está sujeita
- as categorias de itens confidenciais a serem protegidos
- os processos de negócios em que eles são usados
- o comportamento de risco que deve ser limitado
- priorizar quais dados devem ser protegidos primeiro com base na sensibilidade dos itens e no risco envolvido
- delinear o processo de revisão e correção de eventos de match de política de DLP 
 
Em geral, essas necessidades tendem a ser 85% de proteção regulamentar e de conformidade e proteção de propriedade intelectual de 15%. Aqui estão algumas sugestões sobre funções a incluir em seu processo de planejamento:

- Agentes de conformidade e regulamentação
- Diretor de risco principal
- Oficiais jurídicos
- Agentes de segurança e conformidade
- Proprietários de negócios para os itens de dados
- Usuários de negócios
- TI

### <a name="describe-the-categories-of-sensitive-information-to-protect"></a>Descrever as categorias de informações confidenciais para proteger

Em seguida, os participantes descrevem as categorias de informações confidenciais a serem protegidas e o processo de negócios em que são usados. Por exemplo, Microsoft 365 DLP define essas categorias:

- Financeiro 
- Informações médicas e de saúde
- Privacidade
- Personalizado

As partes interessadas podem identificar as informações confidenciais como "Somos um processador de dados, portanto, precisamos implementar proteções de privacidade em informações de titulares de dados e informações financeiras".

 
  <!-- The business process is important as it informs the ‘data at rest’, ‘data in transit’, ‘data in use’ aspect of DLP planning and who should be sharing the items and who should not.-->

### <a name="set-goals-and-strategy"></a>Definir metas e estratégia

Depois de identificar seus participantes e saber quais informações confidenciais precisam de proteção e onde são usadas, as partes interessadas podem definir suas metas de proteção e a TI pode desenvolver um plano de implementação. 


 <!--
### Discovery
 for the locations (DLP workloads) of these types of items.  (mapping DLP locations and data at rest, data in transit, data in use)

### IT can start coding test policies
start small and always in test mode. Note that DLP policies can feed into insider risk.

### Business process owners help with tuning
 false positive/false negative results and fitting DLP into their business processes.

-->

### <a name="set-implementation-plan"></a>Definir plano de implementação

Seu plano de implementação deve incluir:

- Mapeando seu estado inicial e o estado final desejado e as etapas para ir de um para o outro
- como você abordará a descoberta de itens confidenciais
- planejamento de política e a ordem que eles serão implementados
- como você abordará quaisquer pré-requisitos
- planejando como as políticas serão testadas primeiro antes de passar para a imposição
- como você treinará seus usuários finais
- como você testará e ajustará suas políticas
- como você revisará e atualizará sua estratégia de prevenção contra perda de dados com base na alteração das necessidades regulatórias, legais, padrão do setor ou de propriedade intelectual e necessidades comerciais

#### <a name="map-out-path-from-start-to-desired-end-state"></a>Mapear o caminho do início ao estado final desejado

Documentar como sua organização vai passar do estado inicial para o estado final desejado é essencial para se comunicar com seus participantes e definir o escopo do projeto. Aqui estão um conjunto de etapas que são comumente usadas para implantar a DLP. Você vai querer mais detalhes do que isso, mas pode usá-lo para enquadrar seu caminho de adoção de DLP.

![gráfico mostrando a ordem comum para implantar a DLP](../media/dlp-deployment-planning.png)

#### <a name="sensitive-item-discovery"></a>Descoberta de itens confidenciais

Há várias maneiras de descobrir quais itens confidenciais individuais são e onde eles estão localizados. Você pode ter rótulos de sensibilidade já implantados ou pode ter decidido implantar uma política DLP muito ampla em todos os locais que só descobre e audita itens. Para saber mais, confira [Conhecer seus dados.](information-protection.md#know-your-data)

#### <a name="policy-planning"></a>Planejamento de políticas

Ao iniciar a adoção de DLP, você pode usar essas perguntas para concentrar seus esforços de implementação e design de política.

##### <a name="what-laws-regulations-and-industry-standards-must-your-organization-comply-with"></a>Quais leis, regulamentos e padrões do setor devem estar em conformidade com sua organização?

Como muitas organizações vêm para a DLP com o objetivo de conformidade regulamentar, responder a essa pergunta é um ponto de partida natural para planejar sua implementação de DLP. Mas, como implementador de TI, você provavelmente não está posicionado para respondê-lo. Ele precisa ser atendido por sua equipe jurídica e executivos de negócios. 
 
**Exemplo** Sua organização está sujeita ao Reino Unido. regulamentos financeiros.


##### <a name="what-sensitive-items-does-your-organization-have-that-must-be-protected-from-leakage"></a>Quais itens confidenciais sua organização tem que devem ser protegidos contra vazamento?

Depois que sua organização souber onde ela está em termos de necessidades de conformidade regulamentar, você terá alguma ideia de quais itens confidenciais precisam ser protegidos contra vazamentos e como você deseja priorizar a implementação de política para protegê-los. Isso ajudará você a escolher os modelos de política DLP mais apropriados. Microsoft 365 vem com modelos de DLP pré-configurados para Financeiro, Médico e saúde, Privacidade e você pode criar seu próprio usando o modelo Personalizado. Ao projetar e criar suas políticas de DLP reais, conhecer a resposta a essa pergunta também ajudará você a escolher o tipo de informação [confidenciais correto.](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)

**Exemplo** Para começar rapidamente, escolha o modelo de `U.K. Financial Data` política que inclui os tipos de informações , e `Credit Card Number` `EU Debit Card Number` `SWIFT Code` confidenciais. 

##### <a name="where-are-the-sensitive-items-and-what-business-processes-are-they-involved-in"></a>Onde estão os itens confidenciais e em quais processos de negócios eles estão envolvidos?

Os itens que contêm informações confidenciais de suas organizações são usados todos os dias durante a negociação. Você precisa saber onde instâncias dessas informações confidenciais podem ocorrer e em quais processos de negócios eles são usados. Isso ajudará você a escolher os locais certos para aplicar suas políticas de DLP. Microsoft 365 As políticas DLP são aplicadas a locais:

- Trocar email
- Sites do SharePoint
- Contas OneDrive
- Bater papo e canal de mensagens do Teams
- Windows 10 Dispositivos
- Microsoft Cloud App Security
- Repositórios locais

**Exemplo** Os auditores internos de suas organizações estão rastreando um conjunto de números de cartão de crédito. Eles mantêm uma planilha deles em um site SharePoint seguro. Vários funcionários fazem cópias e as salvam em seu site de OneDrive for Business que é sincronizado com seu Windows 10 dispositivo. Um deles colará uma lista de 14 deles em um email e tentará enviá-la para os auditores externos para revisão. Você gostaria de aplicar a política ao site de SharePoint seguro, todos os auditores internos OneDrive for Business contas, seus dispositivos Windows 10 e Exchange email.

##### <a name="what-is-your-organizations-tolerance-for-leakage"></a>Qual é a tolerância de suas organizações para vazamento?

Grupos diferentes em sua organização podem ter diferentes exibições sobre o que é um nível aceitável de vazamento de itens confidenciais e o que não é. Alcançar a perfeição de vazamento zero pode ter um custo muito alto para a empresa.

**Exemplo** O grupo de segurança de suas organizações, juntamente com a equipe jurídica, acha que não deve haver compartilhamento de números de cartão de crédito com qualquer pessoa fora da organização e insistem em não haver vazamento. Porém, como parte da revisão regular da atividade de número de cartão de crédito, os auditores internos devem compartilhar alguns números de cartão de crédito com auditores de terceiros. Se sua política de DLP proibir todo o compartilhamento de números de cartão de crédito fora da organização, haverá uma interrupção significativa do processo de negócios e um custo adicionado para reduzir a interrupção para que os auditores internos concluam o rastreamento. Esse custo extra é inaceitável para a liderança executiva. Para resolver isso, é necessário haver uma conversa interna para decidir um nível aceitável de vazamento. Depois que isso for decidido, a política poderá fornecer exceções para determinados indivíduos compartilharem as informações ou ela pode ser aplicada apenas no modo de auditoria.

#### <a name="planning-for-prerequisites"></a>Planejamento de pré-requisitos

Antes de monitorar alguns locais de DLP, há pré-requisitos que devem ser atendidos. Consulte as **seções Antes de começar** de:

- [Obter o scanner local de prevenção contra perda de dados (visualização)](dlp-on-premises-scanner-get-started.md#before-you-begin)
- [Introdução à Prevenção contra perda de dados do ponto de extremidade](endpoint-dlp-getting-started.md#before-you-begin)
- [Começar com a extensão de conformidade da Microsoft (visualização)](dlp-chrome-get-started.md#before-you-begin)
- [Usar políticas de prevenção contra perda de dados para aplicativos de nuvem que não são da Microsoft (visualização)](dlp-use-policies-non-microsoft-cloud-apps.md#before-you-begin)

#### <a name="policy-deployment"></a>Implantação de política

Depois de criar as políticas de DLP, você deve considerar a implementação gradual delas para avaliar o impacto e testar a eficácia delas antes de aplicá-las completamente. Por exemplo, você não deseja que uma nova política de DLP bloqueie sem querer o acesso a milhares de documentos ou quebre um processo comercial existente.
  
Se estiver criando políticas DLP com um grande impacto em potencial, é recomendável seguir esta sequência:
  
1. **Iniciar no modo de teste sem Dicas de Política** e, em seguida, usar os relatórios de DLP e de qualquer incidente para avaliar o impacto. Você pode usar relatórios de DLP para exibir o número, o local, o tipo e a gravidade das correspondências de política. Com base nos resultados, você pode ajustar as políticas conforme necessário. No modo de teste, as políticas de DLP não afetarão a produtividade das pessoas que trabalham na sua organização. Além disso, use este estágio para testar seu fluxo de trabalho para revisão de eventos DLP e correção de problemas.
    
2. **Vá para o modo teste** com notificações e políticas Dicas para que você possa começar a ensinar os usuários sobre suas políticas de conformidade e prepará-los para as políticas que serão aplicadas. É útil ter um link para uma página de política de organização que fornece detalhes adicionais sobre a política na dica de política. Neste estágio, você também pode solicitar que os usuários reportem falsos positivos para que você possa refinar ainda mais as políticas. Vá para esse estágio depois que você tiver confiança de que os resultados do aplicativo de política corresponderão ao que os participantes tinham em mente. 
    
3. **Inicie a imposição total das políticas** para que as ações sejam aplicadas nas regras e o conteúdo seja protegido. Continue a monitorar os relatórios de DLP e qualquer relatório de incidente ou notificações para se certificar de que os resultados sejam os desejados. 

    ![Opções para usar o modo de teste e ativar a política](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    Você pode desativar uma política de DLP a qualquer momento, o que afeta todas as regras da política. No entanto, as regras também podem ser desativadas individualmente, alternando o status no editor de regras.

    ![Opções para desativar uma regra em uma política](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    Você também pode alterar a prioridade de várias regras em uma política. Para fazer isso, abra uma política para edição. Em uma linha para uma regra, escolha as reticências (**...**) e, em seguida, escolha uma opção, como **Mover para baixo** ou **Colocar como mais baixa**.

    ![Definir prioridade da regra](../media/dlp-set-rule-priority.png)

#### <a name="end-user-training"></a>Treinamento do usuário final

Quando uma política de DLP é disparada, você pode configurar suas políticas para Enviar notificações por email e mostrar dicas de política para políticas [DLP](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) para administradores e usuários finais. Enquanto suas políticas ainda estão no modo de teste e antes que elas sejam definidas para impor uma ação de bloqueio, as dicas de política são maneiras úteis de aumentar a conscientização sobre comportamentos arriscados em itens confidenciais e treinar os usuários para evitar esses comportamentos no futuro.  

#### <a name="review-dlp-requirements-and-update-strategy"></a>Analisar os requisitos de DLP e a estratégia de atualização

Os regulamentos, leis e padrões do setor aos que sua organização está sujeita mudarão com o tempo e suas metas de negócios para DLP também. Certifique-se de incluir análises regulares de todas essas áreas para que sua organização permaneça em conformidade e sua implementação DLP continue a atender às suas necessidades comerciais.

## <a name="approaches-to-deployment"></a>Abordagens para implantação

|A descrição das necessidades de negócios do cliente  | approach  |
|---------|---------|
|**O Banco Contoso** está em um setor altamente regulamentado e tem muitos tipos diferentes de itens confidenciais em muitos locais diferentes. </br> - sabe quais tipos de informações confidenciais são prioridade máxima. </br> - deve minimizar a interrupção dos negócios à medida que as políticas são roladas. </br> - tem recursos de IT e pode contratar especialistas para ajudar a planejar, projetar a implantação </br> - tem um contrato de suporte premier com a Microsoft| - Aproveite o tempo para entender quais regulamentos devem estar em conformidade e como eles vão estar em conformidade. </br> -Aproveite o tempo para entender o melhor valor da pilha Microsoft 365 Proteção de Informações </br> - Desenvolver um esquema de rotulagem de sensibilidade para itens priorizados e aplicar </br> - Envolver proprietários de processos de negócios </br>- Políticas de design/código, implantar no modo de teste, treinar usuários </br>- repetir|
|**Os Brinquedos TailSpin** não sabem o que têm ou onde estão e têm pouco ou nenhum recurso de profundidade. Eles usam Teams, ODB e Exchange extensivamente.     |- Comece com políticas simples nos locais priorizados. </br>- Monitorar o que é identificado </br>- Aplicar rótulos de sensibilidade de acordo </br>- Refinar políticas, treinar usuários       |
|**A Fabrikam** é uma pequena startup e deseja proteger sua propriedade intelectual e deve se mover rapidamente. Eles estão dispostos a dedicar alguns recursos, mas não podem pagar a contratação de especialistas externos. </br>- Os itens confidenciais estão todos Microsoft 365 OneDdrive for Business/SharePoint </br>- A adoção de OneDrive for Business e SharePoint é lenta, funcionários/sombra usam o DropBox e a unidade do Google para compartilhar/armazenar itens </br>- Os funcionários valorizam a velocidade do trabalho sobre a disciplina de proteção de dados </br>- O cliente splurged and bought all 18 employees new Windows 10 devices     |- Tire proveito da política de DLP padrão no Teams </br>- Use restrito por configuração padrão para SharePoint itens </br>- Implantar políticas que impeçam o compartilhamento externo </br>- Implantar políticas em locais priorizados </br>- Implantar políticas para Windows 10 dispositivos </br>- Bloquear carregamentos para armazenamento em OneDrive for Business nuvem      |

<!--

## Planning for workloads

### Exchange

### SharePoint

### OneDrive for Business

### Teams

### Windows 10 Devices

### Microsoft Cloud App Security (MCAS)

### On-premises Scanner
-->

## <a name="see-also"></a>Confira também
- [Saiba mais sobre prevenção contra perda de dados](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
