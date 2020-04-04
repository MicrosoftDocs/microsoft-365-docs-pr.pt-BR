---
title: Trabalhando com a pontuação de conformidade da Microsoft
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Saiba como usar as ferramentas de fluxo de trabalho na pontuação de conformidade da Microsoft para ajudá-lo a gerenciar a conformidade da sua organização.
ms.openlocfilehash: 8fe36f0cdf5e204e0fa6150141cc348b0d0e325f
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43142582"
---
# <a name="working-with-microsoft-compliance-score-preview"></a>Trabalhando com a pontuação de conformidade da Microsoft (visualização)

Este artigo explica como trabalhar com os principais elementos da Pontuação de conformidade. Você aprenderá a usar as **ações de melhoria** para gerenciar seu fluxo de trabalho de conformidade. Você também aprenderá a usar as informações em suas páginas de **soluções** e **avaliações** e como produzir relatórios.

## <a name="manage-your-workflow-with-improvement-actions"></a>Gerenciar seu fluxo de trabalho com ações aprimoradas

As **ações de melhoria** centralizam suas atividades de conformidade. Cada ação de melhoria fornece orientações detalhadas de implementação para ajudá-lo a se alinhar com regulamentos e padrões de proteção de dados. As ações podem ser atribuídas aos usuários em sua organização para executar o trabalho de implementação e teste. Você também pode armazenar documentação, anotações e registrar as atualizações de status na ação de melhoria.

## <a name="view-your-improvement-actions"></a>Exibir suas ações de aperfeiçoamento

O painel de Pontuação de conformidade mostra as **principais ações de aprimoramento**, as que têm os pontos mais disponíveis que tratam dos problemas mais importantes.

Para exibir todas as ações de aperfeiçoamento na página **ações de aprimoramento** , selecione a guia ações de **aprimoramento** no painel. Ou selecione **Exibir todas as ações de aprimoramento** abaixo da lista de ações de melhoria de chave no painel.

Se você tiver uma longa lista de ações, talvez seja útil filtrar o modo de exibição. Selecione **filtro** no canto superior direito da lista ações. Quando o painel de submenu **filtros** for exibido, selecione seus critérios com base em regulamentos e padrões, solução e grupo. Você também pode personalizar o modo de exibição selecionando **Agrupar** no canto superior direito. No menu suspenso, selecione para exibir por grupo, solução, categoria, tipo de ação ou status.

O modo de exibição padrão para esta página não mostra ações de aperfeiçoamento com um status de teste de **aprovado**. Para exibir ações que passaram no teste, marque a caixa **aprovado** no painel de submenu **filtros** . Somente as ações com um status de teste de contagem **passada** em relação à sua pontuação.

A página ações de melhoria mostra os seguintes pontos de dados para cada ação de melhoria:

- **Impacto da Pontuação**: os pontos pelos quais a pontuação geral aumentará ao concluir a ação
- **Regulamentos**: a regulamentação ou o padrão referente à ação
- **Grupo**: o grupo ao qual você atribuiu a ação
- **Soluções**: a solução onde você pode ir para executar a ação
- **Avaliações**: a avaliação (que organiza os controles para atender a um determinado objetivo de conformidade) no qual a ação reside
- **Categorias**: a categoria de proteção de dados relacionada (como proteger informações, gerenciar dispositivos etc.)
- **Status do teste**:
    - **Nenhuma** -nenhuma atualização de status registrada
    - **Não avaliado** -o teste não foi iniciado
    - **Não está no escopo** -é excluído do cálculo da Pontuação de conformidade e não aumenta sua pontuação
    - **Parcialmente testado** -o teste ainda não foi concluído
    - **Falha no alto risco** -o teste da implementação falhou e o risco de não conformidade com o padrão aplicável é alto
    - **Aprovado** -implementação testada com êxito
- **Indicada**: mostra pontos obtidos do máximo que podem ser obtidos

### <a name="improvement-actions-details"></a>Detalhes das ações de melhoria

Cada ação de melhoria tem uma página de detalhes. Esta página apresenta instruções de implementação detalhadas para concluir as ações recomendadas para atender aos padrões relacionados e requisitos normativos listados em um cabeçalho de **visão geral** .

A página detalhes é onde você pode iniciar a ação recomendada. Você também pode atribuir o trabalho a outro usuário, atualizar o status e anexar notas e documentação.

Para exibir a página de detalhes de uma ação de aprimoramento:

1. Vá para a página ações de aprimoramento.
2. Clique ou toque em qualquer lugar na linha da ação de aprimoramento pretendida, que abre sua página de detalhes.

Você pode facilmente exibir a ação de aperfeiçoamento seguinte ou anterior na lista selecionando a seta para cima ou para baixo no canto superior direito da tela. Se você tiver filtrado sua lista na página ações de aprimoramento, mover para cima ou para baixo levará você para o próximo item dentro da lista filtrada.

## <a name="assign-improvement-actions"></a>Atribuir ações de melhoria

Para iniciar o trabalho de implementação em uma ação de melhoria, você pode fazer o próprio trabalho ou atribuí-lo a outro usuário. A pessoa atribuída pode ser:

- Um proprietário de política da empresa
- Um implementador de TI
- Outro funcionário com responsabilidade de realizar a tarefa

Depois que a pessoa adequada for identificada, certifique-se de que ela tenha uma [função](compliance-score-setup.md#set-user-permissions-and-assign-roles) suficiente na pontuação de conformidade (administrador de conformidade, administrador de dados de conformidade, administrador de segurança ou administrador global) para executar o trabalho e siga estas etapas: 

1. Na página detalhes das ações de melhoria, selecione **Editar o status** próximo da seção superior esquerda da tela. 

2. No painel de submenu editar status, clique ou toque na caixa **atribuída a** , que preenche uma lista de **pessoas sugerida** dos usuários. Você pode selecionar o usuário na lista ou digitar o endereço de email da pessoa à qual você deseja atribuir a ação.

3. Selecione **salvar e fechar** para concluir a atribuição. O usuário atribuído receberá um email informando que a ação de aprimoramento foi atribuída a eles e, em seguida, poderá abrir a ação de aperfeiçoamento no painel.

O usuário atribuído pode então executar as ações recomendadas descritas nas instruções de implementação.

## <a name="perform-work-and-store-documentation"></a>Executar documentação de trabalho e armazenamento

Quando você executa o trabalho de implementação, é possível carregar arquivos e anotações diretamente para a ação de melhoria na seção **observações e documentação** .  Esse ambiente é um repositório seguro e centralizado para ajudá-lo a demonstrar a satisfação dos controles para atender aos padrões e às normas de conformidade. Qualquer usuário com acesso somente leitura pode ler o conteúdo desta seção. Somente os usuários com direitos de edição podem carregar e baixar arquivos e inserir ou editar anotações.

Os campos da seção **notas e documentação** incluem:

**Documentos carregados**

- Selecione **gerenciar documentos** para carregar qualquer arquivo relevante.
- Quando o painel gerenciar documentos for aberto, selecione **Adicionar documento**e, em seguida, selecione o arquivo do seu sistema. Tipos de arquivo aceitos: 
  - Documentos (. doc,. xls,. ppt,. txt,. pdf)
  - Imagens (. jpg,. png)
  - Vídeo (. mkv)
  - Arquivos compactados (. zip,. rar)
- Depois que o arquivo resolver no painel, selecione **fechar,** que salva automaticamente o anexo de arquivo. Em seguida, você verá o arquivo listado em **documentos carregados.** 
- Para baixar ou excluir o documento, selecione **gerenciar documentos** abaixo da lista de documentos. No painel de submenu, clique ou toque na linha de documento para realçá-lo e, em seguida, selecione **baixar** ou **excluir.**

**Implementação, teste e notas adicionais**

- Para adicionar anotações em qualquer um desses três campos, selecione **editar notas de implementação** abaixo de qualquer um desses campos.
- Quando o painel de submenu abrir, insira notas no campo de texto e, em seguida, selecione **salvar e fechar**.
- Para editar anotações, selecione **editar notas de implementação**, faça suas edições e, em seguida, selecione **salvar e fechar**.

Não há um limite de caracteres nos campos anotações. Recomendamos manter o Notes Brief para que você possa exibi-los facilmente e editá-los da página de detalhes de ações de melhoria.

## <a name="change-improvement-action-status"></a>Alterar status da ação de melhoria

Você pode registrar o status e a data de implementação e o status e a data do teste para cada ação de aprimoramento. Veja a seguir os campos disponíveis e as opções de status:

- **Status da implementação**: selecione uma destas opções de status:
    - **Não implementado** -ação ainda não implementada
    - **Implementado** -ação implementada
    - **Implementação alternativa** -Selecione esta opção se você usou outras ferramentas de terceiros ou executou outras ações não incluídas nas recomendações da Microsoft
    - **Planejado** -a ação é planejada para implementação
    - **Não está no escopo** -uma opção para ações não relevantes para sua organização; selecionar esse status exclui a ação da Pontuação; Se você desmarcar, a ação será incluída na Pontuação
- **Data de implementação**: campo disponível quando o status da implementação for definido como implementação **implementada** ou **alternativa**; alternar entre o pop-up do calendário para selecionar a data
- **Status do teste**: selecione uma destas opções:
    - **Não avaliado** -o teste não foi iniciado
    - **Aprovado**-implementação testada com êxito
    - Falha nos testes de **baixo risco** , baixo risco
    - Falha no teste de **risco médio** , risco médio
    - **Falha no alto risco** -falha no teste, alto risco
- **Data do teste**: alternar o pop-up calendário para selecionar a data

> [!NOTE]
> Os campos de status de implementação e teste podem ser editados por qualquer usuário com permissões de edição, não apenas os **atribuídos ao** usuário.

## <a name="assign-improvement-action-to-assessor-for-completion"></a>Atribuir ação de aprimoramento a consultor para conclusão

Após concluir o trabalho e carregar evidências, a próxima etapa é definir o status e a data de implementação e atribuir a ação de aprimoramento a um consultor para validação.

Os tipos de avaliadores incluem:

- Avaliadores internos que executam a validação de controles dentro da sua organização
- Avaliadores externos que examinam, verificam e certificam a conformidade, como organizações independentes de terceiros que auditam os serviços de nuvem da Microsoft

O consultor valida o trabalho e examina a documentação e seleciona o status de teste apropriado.

**Se o status do teste for "Passed"**: a ação foi concluída e os **pontos obtidos** mostrarão o número total de pontos possíveis alcançados e contados em relação à pontuação de conformidade geral.

**Se o status do teste for qualquer grau de "falha"**: a ação não atende aos requisitos, e o consultor pode atribuí-lo de volta ao usuário apropriado para trabalho adicional.

## <a name="solutions-page"></a>Página de soluções

A **página soluções** é outro ponto de partida para trabalhar em ações de melhorias para aumentar sua pontuação. 

Para acessar a página de soluções, selecione a guia **soluções** no painel ou selecione **Exibir todas as soluções** sob **soluções que afetam sua pontuação** na seção superior direita do seu painel.

A página soluções mostra o compartilhamento de pontos ganhos e potenciais como organizados por solução. Exibir os pontos e as ações de melhoria restantes desse modo de exibição ajuda a entender quais soluções precisam de mais atenção imediata.

### <a name="filtering-your-solutions-view"></a>Filtrando o modo de exibição de soluções

Para filtrar a exibição de soluções:

1. Selecione **filtro** no canto superior esquerdo da sua lista de avaliações.
2. No painel **filtros** de submenu, coloque uma marca ao lado dos critérios desejados (padrões e regulamentos, solução, tipo de ação, grupo Gerenciador de conformidade, categoria).
3. Selecione o botão **aplicar** . O painel de filtro será fechado e você verá o modo de exibição filtrado.

Você também pode modificar o modo de exibição para ver avaliações por grupo, produto ou regulamentação selecionando o tipo de agrupamento no menu suspenso de **grupo** acima da sua lista de avaliações.

### <a name="taking-actions-from-the-solutions-page"></a>Executando ações da página soluções

A página soluções exibe as soluções da sua organização que estão conectadas às ações de melhoria. A tabela lista a contribuição de cada solução para sua pontuação geral, os pontos de aumento de Pontuação obtidos e possíveis dentro dessa solução, e o número restante de ações de aprimoramento agrupadas nessa solução que podem aumentar sua pontuação.

Há duas maneiras de executar uma ação nesta tela:

1. Na linha da sua solução pretendida, na coluna **ações restantes** , selecione o número de hiperlink. Você verá um modo de exibição filtrado da tela ações de melhoria mostrando ações de aperfeiçoamento não testadas para essa solução.

2. Na linha da sua solução pretendida, na coluna **Abrir solução** , selecione **abrir**. Você verá a solução ou o local nos centros de segurança e conformidade do Microsoft 365 e do Office 365, onde você pode executar a ação recomendada.

## <a name="assessments-page"></a>Página de avaliações

A página avaliações lista as avaliações que você seleciona para acompanhar a organização. O denominador de Pontuação de conformidade é determinado por todas as avaliações rastreadas. Quanto mais avaliações você adicionar, mais ações de melhoria você verá na página ações de melhoria e maior será o denominador de pontuação.

Para acessar sua página de avaliações, selecione a guia **avaliações** no painel.

Nesta página, você pode exibir rapidamente informações importantes sobre cada avaliação:

- **Status**: o status para a conclusão de todas as ações de melhoria na avaliação será listado como:
    - **Sem conformidade**: as ações de melhoria na avaliação não foram implementadas e foram testadas com êxito; o trabalho ainda não foi iniciado
    - **Em andamento**: o trabalho está em andamento na implementação ou teste das ações de melhoria; por exemplo, uma ação de melhoria na avaliação foi atribuída para trabalho, está em processo de implementação e teste
- **Progresso da avaliação**: a porcentagem do trabalho realizado em relação à conclusão final da avaliação, conforme medido pelo número de controles testados com êxito.
- **Ações gerenciadas pelo cliente**: o número de ações concluídas para satisfazer a implementação dos seus controles gerenciados pelo cliente
- **Ações gerenciadas pela Microsoft**: o número de ações concluídas para satisfazer a implementação de controles gerenciados pela Microsoft
- **Grupo de avaliação**: o nome do grupo que você criou, no qual a avaliação reside
- **Serviços relacionados**: Microsoft 365 Service associado
- **Normas relacionadas**: o padrão normativo, política ou legislação que a avaliação busca satisfazer

### <a name="default-assessments"></a>Avaliações padrão

Por padrão, você verá a avaliação da linha de base de proteção de dados do Microsoft 365 na página avaliações. A pontuação de conformidade também fornece várias avaliações pré-configuradas ([exibir a lista completa](compliance-score.md#templates)). Você pode adicionar mais Avaliações para cobrir normas e padrões adicionais no Gerenciador de conformidade.

### <a name="managing-assessments"></a>Gerenciando avaliações

Durante a visualização pública, você vai para a ferramenta Gerenciador de conformidade para criar, personalizar e gerenciar avaliações.

Na página **avaliações** , em Pontuação de conformidade, selecione **gerenciar avaliações no Gerenciador de conformidade** na parte superior da lista de avaliações. Este link leva você para seu painel de **avaliações** no Gerenciador de conformidade.

O outro link na parte superior da lista de avaliações, **Microsoft Actions no gerente de conformidade**, leva você para o painel de **informações de controles** no gerente de conformidade mostrando os controles da Microsoft que contribuem para sua pontuação de conformidade.

### <a name="filtering-your-assessments-view"></a>Filtrando o modo de exibição de avaliações

Para filtrar a exibição de avaliações:

1. Selecione **filtro** no canto superior esquerdo da sua lista de avaliações.
2. No painel **filtros** de submenu, coloque uma marca ao lado dos critérios desejados (padrões e regulamentos, grupo Gerenciador de conformidade).
3. Selecione o botão **aplicar** . O painel de filtro será fechado e você verá o modo de exibição filtrado.

Você também pode modificar o modo de exibição para ver avaliações por grupo, produto ou regulamentação selecionando o tipo de agrupamento no menu suspenso de **grupo** acima da sua lista de avaliações.

### <a name="managing-improvement-actions-within-an-assessment"></a>Gerenciando ações de melhoria em uma avaliação

Na lista de avaliação, na coluna **ações gerenciadas pelo cliente** , selecione o texto vinculado na linha da avaliação pretendida. Isso leva você a um modo de exibição filtrado da página ações de melhoria que mostra as ações dentro dessa avaliação.

## <a name="reporting"></a>Reporting

Você pode exportar um relatório de todas as ações de melhorias na pontuação de conformidade. Na página **ações de melhoria** , selecione **Exportar** no canto superior esquerdo da tela, acima da lista de ações. Isso produzirá uma planilha do Excel com todas as ações de aperfeiçoamento e as categorias de filtro mostradas na página **ações de aprimoramento** .

Você também pode exportar um relatório do Gerenciador de conformidade seguindo estas etapas:

1. No gerente de conformidade, vá para o painel de **informações de controles** .
2. Você verá uma guia de **avaliação** e uma guia de **modelo** .  
3. Para exportar uma avaliação: selecione a guia **avaliação** . Use os menus suspensos de **grupo** e **avaliação** para selecionar a avaliação a ser exportada. Selecione **Exportar** perto da parte superior direita da tela. Um arquivo do Excel será baixado. Inclui uma lista de ações, agrupadas por controle, com seus detalhes de implementação e teste.
4. Para exportar um modelo: selecione a guia **modelo** e escolha o modelo que você deseja exportar do menu suspenso **modelo** . Selecione **Exportar** perto da parte superior direita da tela. Um arquivo do Excel será baixado. Inclui uma lista de ações, agrupadas por controle, com seus detalhes de implementação e teste.
