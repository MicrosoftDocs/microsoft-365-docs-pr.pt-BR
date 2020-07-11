---
title: Considerações para o plano de gerenciamento de continuidade de negócios corporativos
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Aspectos a considerar ao desenvolver seu plano de continuidade de negócios com reconhecimento na nuvem.
ms.openlocfilehash: 35aa5fb74b8281a089ef0b58998cd297507cc46f
ms.sourcegitcommit: 3951147f74510e2ead6c11ceab92854f0937426b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2020
ms.locfileid: "45083500"
---
# <a name="developing-your-continuity-plan"></a>Desenvolvendo seu plano de continuidade

Este tópico fornece orientação sobre o desenvolvimento de um plano de continuidade de negócios que leva em conta as dependências da Microsoft 365. Aqui estão os métodos de análise das suas funções de negócios e da identificação das que dependem dos serviços do Microsoft 365. Você executará essa análise com a previsão de que haverá falhas de serviço e que você precisa se preparar para essas possibilidades.

Em geral, o planejamento de continuidade de negócios envolve quatro aspectos, avaliação, planejamento, validação de capacidade e comunicação e coordenação.

## <a name="assessment"></a>Avaliação
Primeiro, você deve identificar as funções de negócios da sua organização e os serviços e processos que dão suporte a eles. Isso inclui concluir uma análise de impacto nos negócios, em que cada função empresarial é classificada de acordo com o nível de importância delas e você identifica os processos e os serviços de que cada uma depende. Veja um exemplo de tabela que você pode fazer para obter ajuda para começar a usar sua própria avaliação.

**Amostra de Avaliação de impacto empresarial (BIA)**

Este é um documento de BIA para `name of the service, system, process, or function`

|campos de dados BIA|Descrição|
|---------|---------|
|Tipo de BIA|`is it a business process or technology, service or system?`|
|Nome de BIA|`name of the service/system/function/process`|
|Descrição de serviço|`give a full description of the service, process, or function`|
|Função empresarial|`some examples: customer services; legal; marketing; risk management, security, sales, information technology, production, manufacturing`|
|Ano fiscal|`the current fiscal year, re-evaluate these on a regular basis`|
|criticidade|`develop your own classifications, but here are some examples: mission critical, important, deferrable`|
|Unidade de negócios|`name of the business unit that owns this business function`|
|processo (serviço, recurso)|`the name of the process, service, or feature`|
|líder sênior do grupo de negócios|`the name and contact information of the senior leader of the business group that owns this business process`|
|A tecnologia tem um SLA **interno** ou OLA?|`please explain in as much detail as possible`|
|A tecnologia tem um SLA **externo** ou OLA?|`please explain in as much detail as possible`|
|A tecnologia tem uma missão executiva conhecida para um SLA de processo específico? Se sim, explique em detalhes.|`details here`|
|A perda ou o comprometimento dos dados associados a esses serviços acione um evento principal? Se sim, explique em detalhes.|`details here`|
|O serviço tem uma solução alternativa ou alternativa para algumas ou todas as suas funções e recursos importantes? Se sim, explique em detalhes.|`details here`|
|O serviço processa, armazena ou transmite dados de clientes, como informações de identificação pessoal (PII)? Se sim, explique em detalhes.|`details here`|
|Status de BIA|`develop your own status classification, here are some examples: planned, started, in-progress, complete, on-hold, expired`|
|Data de conclusão|`the date this BIA was completed`|
|Facilitador de BIA|`name of the person or group who is responsible for developing and maintaining this BIA`|
|Aprovação de BIA|`name of the person or group who is the executive sponsor of this BIA and who has responsibility for approving it.`|
|colaboradores|`optional list of the people who helped develop this BIA and their contact information`|
|Local de aprovação de BIA|`indicate where the executive approval is located, or attach proof to this document`|

## <a name="planning"></a>Planejamento

Em seguida, examine os processos de negócios para ver a existência de relações de dependência em cascata. Com base no resultado, você prioriza e direciona as estratégias de resiliência e os procedimentos operacionais padrão que oferecem suporte a suas estratégias.

Você pode usar [o mapa de serviços da Microsoft](https://docs.microsoft.com/azure/azure-monitor/insights/service-map) para ajudá-lo com esse mapeamento. O mapa de serviços da Microsoft descobre automaticamente os componentes do aplicativo nos sistemas Windows e Linux e mapeia todas as dependências TCP, identifica as conexões e sistemas remotos de terceiros dos quais o aplicativo depende. Além disso, ele mapeia as dependências em áreas da rede que são tradicionalmente escuras, como o Active Directory.

Aqui está um exemplo de análise de dependência (DA) da qual você pode começar. Em sua análise de dependência (DA), você identificará e examinará as dependências do processo. Certifique-se de incluir pessoas, fornecedores, clientes, parcerias e instalações. Os dados dessa análise serão usados para identificar os intervalos entre os requisitos de recuperação de um processo e os recursos de recuperação de dependências de suporte.


|campo|descrição|
|---------|---------|
|tipo de processo|         |
|facilitador|         |
|concluído por|         |
|data de conclusão|         |
|colaboradores|         |
  
## <a name="capability-validation"></a>Validação de recursos

Depois de criar o inventário de seus processos de negócios e ter mapeado relações para outro processo e tecnologias, você precisará criar cenários de validação para todos os processos. Basicamente, descubra como você vai validar seus planos de continuidade de processos de negócios. É provável que algumas pessoas sejam mais importantes, e você desejará priorizá-las.
Não se esqueça de que o treinamento regular dos funcionários sobre a resposta a incidentes e as medidas de continuidade será importante quando o plano for estabelecido. As revisões pós-incidente devem ser usadas para aprimorar suas estratégias de resiliência, incorporando o aprendizado de cada validação ou teste.

![validação de capacidade visio](../media/ebcm/capability-validation-visio.png)

## <a name="incident-coordination-and-communication"></a>Coordenação e comunicação de incidentes

Durante um incidente de serviço, os canais de comunicação normais podem ser afetados ou prejudicados, para que você possa dispor alternativas para ajudar sua organização a permanecer conectada durante um incidente. É fundamental que os canais de comunicação sejam estabelecidos, verificados para segurança e conformidade e os usuários treinados para o uso antes de uma interrupção. Deixar de usar um estado conhecido para outro estado conhecido é muito preferido para os usuários que estão chegando com as soluções ad-hoc desconhecidas no meio de uma crise.

Na Microsoft, todas as equipes de serviços estabeleceram canais de comunicação alternativa internos para nos ajudar a coordenar quando nossos canais de comunicação normais não estão disponíveis. Eles incluem as soluções de telefonia de backup e de conferência de áudio, grupos do Yammer, grupos do Teams, painéis de integridade do serviço internos e software de gerenciamento de incidentes internos.

Durante a análise de dependência de negócios e a análise de dependências, você mapeará os processos essenciais e as tecnologias ou serviços dos quais eles dependem. Preste atenção especial à comunicação durante essa fase de planejamento e das opções. Aqui estão alguns exemplos.

- Se o email for o seu principal método para manter os usuários e os participantes informados e o seu serviço de email estiver prejudicado ou indisponível, você poderá usar outro serviço, como o Microsoft Teams, o Yammer ou outro serviço de terceiros, como um backup. A chave é estabelecê-las antecipadamente e treinar seus usuários para onde ir. Uma conversa do Yammer não será útil se ninguém souber que existe ou se ninguém tiver um indicador.  
- Se os processos de gerenciamento de incidentes internos dependem das comunicações de voz para coordenar suas respostas, estabeleça uma solução de telefonia alternativa para ser usada durante uma crise. Essa solução não precisa ter a paridade total com o seu serviço principal, mas deve fornecer o nível mínimo de colaboração para coordenar suas equipes de continuidade de negócios e de gerenciamento de incidentes. Além disso, pedir aos usuários para publicar seus números de telefone celular na sua lista de endereços global pode fornecer uma camada adicional de comunicação de backup em casos extremos.
- Talvez você queira criar um painel de integridade de serviço personalizado ou outro site, que pode fornecer atualizações de status durante um incidente. Os usuários de treinamento para informações antecipadamente ajudam a reduzir as chamadas desnecessárias para o suporte técnico e a incutir confiança na sua base de usuários que a situação está sendo tratada de forma rápida e eficiente. Use a API de comunicações de serviço do O365 para associá-la ao M365 para um nível de visibilidade ainda maior.  
- É fundamental que o local dos planos de continuidade de negócios e os procedimentos operacionais padrão sejam conhecidos. É recomendável manter cópias online e offline de documentação crítica, como o SharePoint Online ou o OneDrive for Business configurado para sincronização automática com dispositivos locais. No caso de um centro de operações de rede e serviço, e outras equipes similares sejam absolutamente essenciais para a recuperação, você também pode manter cópias impressas disponíveis para uso em caso de emergência.

## <a name="know-your-external-points-of-integration"></a>Conheça seus pontos externos de integração

Independentemente do modelo de negócios, todas as empresas têm pontos de integração com seus clientes, parceiros e fornecedores. A cadeia de fornecimento de valor empresarial é a integração com entidades externas. Aumentar a continuidade de negócios no caso de interrupções de serviços exige considerações e proteção.  
À medida que você analisa sua cadeia de fornecedores, as comunicações externas devem ser consideradas da mesma forma que as comunicações internas são analisadas. Seus clientes contam com seus servidores Exchange Online como o único método de contatar você? Você estabeleceu e conscientizou seus fornecedores sobre métodos alternativos de comunicação, caso o tempo de atividade seja impactado? Veja um exemplo de tabela que sugere como organizar o pensamento.

|nome da entidade externa|afetar o cenário do incidente|Os serviços do Microsoft 365 incluem|alternativas|
|---------|---------|---------|---------|
|`vendor name`|fluxo de mensagens|O Exchange Online é o único meio de comunicação com a Contoso|configurar canais externos do Microsoft Teams ou software de colaboração de terceiros          |
|`service supplier name`|chat|Microsoft Teams|Mensagens instantâneas de terceiros|
|`partner name`|Voz|Microsoft Teams|Dispositivos móveis ou PSTN público      |
|`supplier name`|compartilhamento de arquivos|sites do SharePoint e OneDrive compartilhados externamente|compartilhamento de arquivos de terceiros         |
