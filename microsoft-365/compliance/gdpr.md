---
title: Regulamento Geral sobre a Proteção de Dados
description: Diretrizes técnicas da Microsoft para o RGPD (Regulamento Geral sobre a Proteção de Dados)
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
ms.openlocfilehash: 0ead7cbabc87b7d852cf61fc414df65315c25e39
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596328"
---
# <a name="general-data-protection-regulation-summary"></a>Resumo do Regulamento Geral sobre a Proteção de Dados

O Regulamento Geral sobre a Proteção de Dados (RGPD) introduz novas regras para organizações que oferecem bens e serviços às pessoas na União Europeia (UE) ou que coletam e analisam dados vinculados a residentes da UE. O RGPD se aplica onde quer que você e sua empresa estejam localizados.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrOQI] 

Este documento o orienta com informações para respeitar os direitos e cumprir com as obrigações do RGPD ao usar produtos e serviços da Microsoft. Um [Plano de ação recomendado para o RGPD](gdpr-action-plan.md) e as [Listas de Verificação de Preparação de Responsabilidade](gdpr-arc.md) fornecem recursos adicionais para avaliar e implementar a conformidade de RGPD.

## <a name="terminology"></a>Terminologia

Definições úteis para os termos do RGPD usados neste documento:

- *Controlador de Dados (Controlador*): uma pessoa jurídica, uma autoridade pública, uma agência ou outro corpo que, isoladamente ou em conjunto com outras pessoas, determina a finalidade e o meio de processamento de dados pessoais.  
- *Dados pessoais* e *entidade de dados*: qualquer informação relacionada a uma pessoa natural identificada ou identificável (entidade de dados); uma pessoa natural identificável é uma que pode ser identificada, direta ou indiretamente.  
- *Processador:* uma pessoa física ou jurídica, autoridade pública, órgão ou outra entidade que processa dados pessoais em nome do controlador.  
- *Dados do cliente*: dados produzidos e armazenados nas operações do dia a dia para o funcionamento do seu negócio.

## <a name="what-is-the-gdpr"></a>O que é o RGPD?

O RGPD concede direitos para as pessoas gerenciarem dados pessoais coletados por uma organização. Esses direitos podem ser exercidos por meio de uma Solicitação do Titular dos Dados (DSR). A organização deve fornecer informações adequadas sobre violações de dados e DSRs, e executar Avaliações do Impacto sobre a Proteção de Dados (DPIAs).

Vários pontos devem ser considerados ao implementar ou avaliar os requisitos do RGPD.

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

## <a name="the-gdpr-in-action"></a>O RGPD na prática

Esta seção fornece uma estrutura de tópicos e os pontos a serem considerados para concluir as tarefas do RGPD mencionadas acima. A conclusão dessas tarefas pode variar dependendo da configuração da Microsoft.

### <a name="data-subject-request-dsr"></a>Solicitação do Titular de Dados (DSR)

As solicitações do titular de dados fornecem meios para que os titulares de dados exerçam seus direitos de acordo com o RGPD. O controlador é responsável por fornecer uma resposta adequada e consistente com o RGPD. As perguntas a serem consideraras são abordadas abaixo. Para obter detalhes técnicos, confira [Solicitações do titular de dados](gdpr-data-subject-requests.md).  

- **Quais ações são necessárias para concluir um DSR? **: DSRs envolvem seis atividades: descoberta, acesso, retificação, restrição, exportação e exclusão.
- **Quais são suas fontes de dados?**: A maioria dos dados de uma organização é gerada em [aplicativos do Office](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs), como o Excel e o Outlook. Você também pode encontrar dados relevantes para um DSR em [Informações](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-2-responding-to-dsrs-with-respect-to-insights-generated-by-office-365), gerados por produtos e serviços da Microsoft, e [logs gerados pelo sistema](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs).
- **Quais tipos de dados precisam ser pesquisados?**: dados pessoais podem ser encontrados em dados de clientes, informações geradas por produtos e serviços da Microsoft, além de logs gerados pelo sistema.
- **Como os dados pessoais serão pesquisados?**: procurar dados pessoais pode variar em produtos e serviços da Microsoft. As ferramentas de pesquisa incluem [Pesquisa de Conteúdo](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-the-content-search-ediscovery-tool-to-respond-to-dsrs) ou recurso [de pesquisa no aplicativo](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#using-in-app-functionality-to-respond-to-dsrs). Os administradores podem acessar [logs gerados pelo sistema](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-office365#part-3-responding-to-dsrs-for-system-generated-logs) associados à atividade de um usuário.  
- **Em quais formatos os dados pessoais devem ser disponibilizados?**: o "direito de portabilidade dos dados" do RGPD permite que o titular de dados solicite uma cópia dos dados pessoais que estejam em um "formato estruturado, frequentemente usado, que possa ser lido por máquina", bem como solicite que sua organização transmita esses arquivos para outro controlador de dados.

### <a name="data-protection-impact-assessment"></a>Avaliações do Impacto sobre a Proteção dos Dados

O RGPD exige que os controladores preparem uma [Avaliação de Impacto de Proteção de Dados](gdpr-data-protection-impact-assessments.md) (DPIA) para operações que "provavelmente resultariam em alto risco para os direitos e a liberdade de pessoas físicas". Não há nada inerente aos produtos e serviços da Microsoft que precisem da criação de um DPIA. Em vez disso, depende dos detalhes da sua configuração da Microsoft.

Veja abaixo algumas considerações sobre DPIA. Uma lista de detalhes que devem ser considerados no Office pode ser encontrada no [Conteúdo de DPIA](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-2--contents-of-a-dpia).

- Quais atividades de dados em sua organização podem comprometer a segurança de seus dados pessoais?
- A configuração de produtos e serviços da Microsoft pode estar vulnerável a violações de dados?
- Quando executar um DPIA?

    - Os controladores devem executar um DPIA para lidar com os riscos para a segurança de dados pessoais ou como resultado de uma violação de dados. Os exemplos específicos de fatores de risco no Office são abordados em [Determinar se um DPIA é necessário](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dpia-office365#part-1--determining-whether-a-dpia-is-needed).  

- O que é necessário para concluir um DPIA?

    O RGPD exige que um DPIA inclua:  
    - Avaliação da necessidade e da proporcionalidade do processamento de dados em relação aos objetivos do DPIA.
    - Avaliação dos riscos aos direitos e às liberdades dos titulares dos dados.
    - As medidas desejadas para lidar com os riscos, incluindo proteções, medidas de segurança e mecanismos para garantir a proteção de dados pessoais e demonstrar a conformidade com o RGPD.

### <a name="breach-notification"></a>Notificação de Violação

Como um processador de dados, a Microsoft garante que os clientes possam atender aos requisitos de notificação de violação do RGPD. Os controladores de dados são responsáveis por avaliar os riscos de privacidade de dados e determinar se uma violação exige uma notificação de DPA do cliente. A Microsoft fornece as informações necessárias para a avaliação. Para obter mais informações sobre como a Microsoft detecta e responde a uma violação de dados pessoais, confira [Notificação de violação de dados no RGPD](gdpr-breach-notification.md). Veja algumas perguntas sobre notificações de violação abaixo:

- Quais informações sobre uma violação devem ser comunicadas aos titulares de dados?
- Como você se comunicará com os titulares de dados (email, notificações por escrito etc.)?

### <a name="accountability-readiness-checklists-for-the-gdpr"></a>Listas de Verificação de Preparação de Responsabilidade para o RGPD

Essas [listas de verificação](gdpr-arc.md) fornecem uma forma conveniente de acessar as informações necessárias para dar suporte ao RGPD ao usar os produtos da Microsoft. Você pode gerenciar os itens nesta lista de verificação com a [Pontuação de Conformidade](compliance-score.md) fazendo referência à ID de controle e ao Título do controle em Controles gerenciados pelo cliente no bloco do RGPD.

## <a name="learn-more"></a>Saiba mais

- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
