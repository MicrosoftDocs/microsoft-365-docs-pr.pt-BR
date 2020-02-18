---
title: Gerenciar um incidente de derramamento de dados no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Este artigo descreve o uso da nova ferramenta de investigações de dados (visualização) no centro de conformidade & segurança para gerenciar um incidente de derramamento de dados.
ms.openlocfilehash: f02d5c42d42f6031202e874497f92fdfbe5d0bcf
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072019"
---
# <a name="manage-a-data-spillage-incident-in-microsoft-365"></a>Gerenciar um incidente de derramamento de dados no Microsoft 365

Data derramamento é quando um documento que contém informações confidenciais, confidenciais ou mal-intencionadas é liberado em um ambiente não confiável. Quando um incidente de derramamento de dados é detectado, é importante conter rapidamente o ambiente, avaliar o tamanho e os locais do derramamento, examinar as atividades do usuário em torno dele e, em seguida, excluir os dados derramados do serviço. Usando a ferramenta de investigações de dados (visualização), você pode pesquisar dados confidenciais, mal-intencionados ou incorretos no Office 365, investigar para descobrir o que aconteceu e tomar as medidas apropriadas.  

## <a name="scope-of-this-article"></a>Escopo deste artigo

Este artigo fornece uma lista de instruções sobre como excluir permanentemente os itens das caixas de correio do Office 365 para que eles não sejam mais acessíveis ou recuperáveis por usuários ou administradores. 

> [!NOTE]
> Quando você exclui itens localizados em um site do SharePoint ou do OneDrive for Business, eles são mantidos por 93 dias a partir do momento em que são excluídos do local original.

## <a name="scenario"></a>Cenário

Você é informado de um incidente de derramamento de dados em que um funcionário compartilhou inadvertidamente um documento altamente confidencial com várias pessoas por email. Você deseja avaliar rapidamente quem recebeu este documento, tanto dentro e fora da sua organização. Após investigar o incidente, você planeja compartilhar suas descobertas com outros investigadores para revisão e, em seguida, remover permanentemente os dados derramados de sua organização do Office 365. Após a conclusão da investigação, você deseja remover todas as evidências. 

> [!IMPORTANT]
> Embora você possa remover permanentemente os dados derramados dentro de sua própria organização, nenhum dado derramado fora da sua organização não pode ser removido com esses recursos.

## <a name="workflow"></a>Fluxo de trabalho

Este é o fluxo de trabalho para usar investigações de dados (visualização) para gerenciar um incidente de derramamento de dados:

1.  Criar uma investigação de dados.

2.  Pesquise dados confidenciais, mal-intencionados ou de local incorreto e colete-os como evidência.

3.  Revise e investigue as evidências.

4.  Excluir permanentemente os dados derramados.

5.  Feche ou exclua a investigação.


## <a name="before-you-begin"></a>Antes de começar

- Para criar uma investigação de dados, procurar por conteúdo e excluir dados derramados, você precisa ser membro do grupo de função do investigador de dados no centro de conformidade de & de segurança.

- Para controlar quais caixas de correio de usuário e contas do OneDrive podem pesquisar, sua organização pode configurar os limites de conformidade. Para obter mais informações, [Configure os limites de conformidade para investigações de descoberta eletrônica](tagging-and-assessment-in-advanced-ediscovery.md). 

## <a name="step-1-create-a-data-investigation"></a>Etapa 1: criar uma investigação de dados

Para criar uma investigação na ferramenta de investigações de dados (visualização):

1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre no Office 365 usando uma conta que seja membro do grupo de função do investigador de dados.
    
3. No centro de segurança e conformidade, clique em **investigações de dados**.
 
4. Na página **investigações de dados (visualização)** , clique em **criar nova investigação**.
    
5. Na nova página de submenu de **investigação de dados** , dê um nome à investigação (obrigatório) e digite um número de investigação e uma descrição opcionais. O nome deve ser exclusivo em sua organização.

6. Em **você deseja definir configurações adicionais depois de criar esta investigação?**, siga um destes procedimentos:

    - Clique em **Sim** para criar a investigação e exiba a página **configurações** no novo caso. Isso permite adicionar membros à investigação.
    
    - Clique em **não** para criar a investigação e exibi-la na lista de casos da página **investigações de dados (visualização)** . Se você escolher essa opção, será adicionado como o único membro da investigação, e as configurações padrão de pesquisa e análise serão usadas. Você pode adicionar membros ou alterar configurações a qualquer momento após a criação da investigação.

7. Clique em **salvar** para criar a investigação.

    A nova investigação é exibida na lista na página **investigações de dados (visualização)** . 

8. Para abrir uma investigação, clique no nome da investigação. 

    A guia **página inicial** da investigação é exibida. 

> [!TIP]
> Considere o estabelecimento de uma Convenção de nomenclatura para investigações e forneça tantas informações quantas forem necessárias no nome e na descrição para que você possa localizar e se referir a elas no futuro, se necessário.
 
## <a name="step-2-search-for-the-spilled-data"></a>Etapa 2: Pesquisar os dados derramados 
 
Se você souber quais usuários você deseja pesquisar por dados derramados, você pode adicioná-los como pessoas de interesse para mapear suas fontes de dados para a investigação e pesquisar rapidamente a sua caixa de correio e a conta do OneDrive. Para adicionar pessoas de interesse à investigação, clique em **pessoas de interesse**e, em seguida, clique em **adicionar pessoas de interesse**. Para obter mais informações, consulte [gerenciar pessoas de interesse](manage-people-of-interest.md).

Na guia **pesquisas** , você pode criar pesquisas para localizar os dados derramados. Para obter mais informações sobre como criar pesquisas, confira [Pesquisar dados em uma investigação](search-for-data.md).

Depois de executar a pesquisa, você pode Visualizar amostras de resultados de pesquisa e exibir estatísticas de pesquisa para avaliar a eficácia da consulta de pesquisa. Após identificar os itens que você deseja excluir do Office 365, você pode adicionar os resultados da pesquisa a um conjunto de evidência. Para fazer isso, clique na pesquisa que você deseja investigar. Na página do menu suspenso, clique em **Adicionar resultados a evidências** e siga as instruções. Em seguida, no conjunto de evidências, você pode revisar documentos individuais, investigar quem teve acesso aos documentos e exportar os documentos. Para excluir os documentos (ou um subconjunto de documentos) em vez de analisá-los, vá para a [etapa 4](#step-4-delete-the-spilled-data). 

> [!IMPORTANT]
> As palavras-chave que você usa na consulta de pesquisa podem conter os dados reais derramados que você está pesquisando. Por exemplo, se você procurar documentos que contenham um número de seguro social e usá-lo como uma palavra-chave na consulta de pesquisa, você deverá excluir a consulta posteriormente para evitar mais derramamento. Você pode excluir a pesquisa ou excluir toda a investigação na [etapa 5](#step-5-close-or-delete-the-investigation). 

## <a name="step-3-review-and-investigate"></a>Etapa 3: analisar e investigar 

Na investigação, vá para a guia **evidência** e clique no conjunto de evidências que você criou na etapa anterior. Após o trabalho de processamento ser concluído e os resultados da pesquisa serem adicionados à evidência, você pode revisar documentos individuais em seu formato nativo, formato de texto ou um formato Near-Native. Você pode criar consultas adicionais para restringir a lista de documentos e marcar documentos para indicar resultados de sua investigação. Para obter mais informações, consulte [Review data in Evidence](review-data-in-evidence.md)

Para agrupar documentos e obter mais assistência para revisão, clique em **gerenciar evidência**. No bloco de **análise** , clique em **analisar**. Isso executa análises avançadas, como detecção de duplicidades, encadeamento de emails e análise de temas. Para saber mais, confira:

- [Executar análise para investigar mais rápido](run-analytics-to-investigate-faster.md)
- [Próximo detecção duplicada](near-duplicates.md)
- [Threading de emails](email-threading.md)
- [Temas](themes.md)

Para determinar quais usuários estão envolvidos no derramamento de dados, você pode criar uma consulta no conjunto de evidências e, em seguida, usar as condições remetente/autor e destinatários. Isso cria uma lista de todos os remetentes, destinatários e autores encontrados nos dados coletados que foram adicionados à evidência. Certifique-se de examinar a lista para determinar se há usuários externos. Para obter mais informações sobre como usar condições para restringir os resultados da pesquisa, consulte [Search Conditions](keyword-queries-and-search-conditions.md#search-conditions).

## <a name="step-4-delete-the-spilled-data"></a>Etapa 4: excluir os dados derramados

Usando a ferramenta de investigações de dados, você pode excluir itens de seus locais originais. Por exemplo, você pode excluir itens de caixas de correio, sites do SharePoint e contas do OneDrive em sua organização. Lembre-se de que, como você coletou itens como evidência (adicionando os resultados da pesquisa ao conjunto de evidências na etapa 2), você tem cópias dos itens no conjunto de evidências para investigar ou preservá-los ainda mais.

Para excluir itens de seus locais originais:

1. No conjunto de evidências, selecione os itens que você deseja excluir. Se você selecionar itens que estão anexados a uma mensagem de email, a mensagem de email pai também será selecionada e excluída. 
 
2. Clique em **ação** e em **excluir itens de locais originais**.

   ![Clique em ação e em excluir itens de locais originais](../media/DataInvestigationsDeleteItems1.png)

3. Na página do menu suspenso, verifique o número de itens e documentos filhos relacionados que serão excluídos e clique em **excluir**.

No momento, quando você exclui itens de seu local original, os itens são excluídos de forma reversível. Isso significa que os itens excluídos serão retidos até que o período de recuperação de item excluído do item expire. Isso também significa que é possível que os usuários recuperem esses itens. Para obter mais informações sobre o que acontece quando itens são excluídos de caixas de correio e sites, consulte [excluir itens de seu local original](delete-items-from-original-locations.md).

## <a name="step-5-close-or-delete-the-investigation"></a>Etapa 5: fechar ou excluir a investigação

Após excluir documentos nos locais de conteúdo de origem (caixas de correio ou sites) no serviço Live, você ainda terá cópias desses documentos que você adicionou às evidências como parte da sua investigação. Para evitar mais dados derramamento, considere a possibilidade de excluir a própria investigação.

Para excluir uma investigação:

1. Na guia **configurações** , clique em **informações de investigação**.

2. Clique em **excluir investigação**. 

Se você não precisar excluir a investigação ou se quiser salvar as informações coletadas durante a investigação, clique em **fechar caso**. Posteriormente, você poderá reabrir investigações fechadas.
