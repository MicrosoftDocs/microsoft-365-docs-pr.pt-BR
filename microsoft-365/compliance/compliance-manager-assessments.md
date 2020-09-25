---
title: Criar e gerenciar avaliações no Microsoft Compliance Manager
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
description: Criar avaliações no Microsoft Compliance Manager para ajudá-lo a atender aos requisitos de normas e certificações que são importantes para sua organização.
ms.openlocfilehash: d09103f58be3a5fa39b57ca35da411e8046aace5
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262286"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Criar e gerenciar avaliações no gerente de conformidade

**Neste artigo:** Saiba como personalizar o Gerenciador de conformidade para sua organização criando e gerenciando **avaliações**. Este artigo descreve como criar avaliações, como organizá-las em **grupos**, trabalhar com **controles**, aceitar **atualizações**e exportar **relatórios**de avaliação.

> [!IMPORTANT]
> As avaliações disponíveis para sua organização dependem do contrato de licenciamento. [Revise os detalhes](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="introduction-to-assessments"></a>Introdução às avaliações

O Gerenciador de conformidade ajuda você a gerenciar a conformidade com as avaliações das normas e certificações que se aplicam à sua organização. As avaliações são agrupamentos de controles de uma regulamentação, padrão ou política específica. O Gerenciador de conformidade facilita a inicialização do controle da conformidade, fornecendo avaliações pré-configuradas que abrangem uma variedade de normas e certificações regionais e de setores.

Cada avaliação é criada a partir de um [modelo de avaliação](compliance-manager-templates.md). Os modelos servem como uma estrutura que contém os controles, as ações de aprimoramento e as ações da Microsoft necessárias para concluir a avaliação. A configuração das avaliações mais relevantes para a sua organização pode ajudá-lo a implementar políticas e procedimentos operacionais para limitar o risco de conformidade.

Todas as avaliações estão listadas na página avaliações. Saiba mais sobre [como filtrar a exibição de suas avaliações e interpretar os Estados de status](compliance-manager-setup.md#assessments-page).

## <a name="data-protection-baseline-default-assessment"></a>Avaliação padrão da linha de base da proteção de dados

Para começar, a Microsoft fornece uma avaliação **padrão** no gerente de conformidade da **linha de base de proteção de dados 365 da Microsoft**. Essa avaliação da linha de base tem um conjunto de controles para regulamentações e padrões fundamentais para proteção de dados e governança de dados gerais. Essa linha de base desenha elementos primariamente da NIST CSF (National Institute of Standards and Technology cybersecurity Framework) e ISO (International Organization for Standardization), bem como do FedRAMP (programa de gerenciamento de riscos e autorização federal) e RGPD (regulamentação geral de proteção de dados da União Europeia).

Esta avaliação é usada para calcular a pontuação de conformidade inicial na primeira vez que você se deparar com o Gerenciador de conformidade, antes de configurar qualquer outra avaliação. O gerente de conformidade coleta os sinais iniciais de suas soluções da Microsoft 365. Você verá rapidamente como sua organização está realizando em relação aos principais padrões e regulamentos de proteção de dados e veja as ações sugeridas de melhoria a serem tomadas.

O Gerenciador de conformidade fica mais útil ao criar e gerenciar suas próprias avaliações para atender às necessidades específicas da sua organização.

## <a name="assessment-creation-overview"></a>Visão geral da criação da avaliação

Há três maneiras de configurar avaliações:

1. [Use uma avaliação previamente criada](#use-a-pre-built-assessment).
2. [Estender uma avaliação previamente criada para atender às suas necessidades](#extend-a-pre-built-assessment).
3. [Crie sua própria avaliação personalizada](#create-your-own-custom-assessment).

> [!NOTE]
> Somente usuários que retêm uma função de administração global ou de administrador de conformidade podem criar e modificar avaliações. Saiba mais sobre [funções e permissões](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

**Usar uma avaliação previamente criada**

Iniciar sua jornada de conformidade, escolhendo uma avaliação já configurada pelo gerente de conformidade. Fornecemos uma ampla seleção de [modelos](compliance-manager-templates.md) para regulamentações e certificações que se alinham a indústrias, regiões e padrões comuns de proteção de dados, como RGPD e ISO 27001. Os modelos contêm os controles e ações de melhorias para ajudá-lo a atender aos requisitos de uma certificação específica. Você será solicitado a escolher um modelo quando começar a [criar uma avaliação](#use-a-pre-built-assessment).

**Estender uma avaliação previamente criada para atender às suas necessidades**

Você pode modificar uma avaliação do Gerenciador de conformidade — um processo que nos referimos como "estendendo", adicionando seus próprios controles e ações para atender melhor às necessidades da sua organização. Por exemplo, se você geralmente precisa estar em conformidade com a HIPAA, mas exigir proteção adicional de dados ou controles de segurança, você pode estender o modelo HIPAA adicionando seus próprios controles a ele. Consulte as instruções para [estender uma avaliação previamente criada](#extend-a-pre-built-assessment).

**Criar sua própria avaliação personalizada**

Você pode criar sua própria avaliação totalmente a partir do zero para acompanhar precisamente o que sua organização precisa. Criar sua própria avaliação exige que você primeiro crie seu próprio modelo para a avaliação no Gerenciador de conformidade. Consulte as instruções para [criar sua própria avaliação personalizada](#create-your-own-custom-assessment).

## <a name="understand-groups-before-creating-assessments"></a>Entender grupos antes de criar avaliações

Antes de criar ou modificar avaliações, é importante entender como os grupos funcionam. Ao criar uma avaliação, você precisará atribuí-la a um grupo durante o processo. É por isso que recomendamos o planejamento de uma estratégia de agrupamento para as avaliações antes da criação de avaliações.

### <a name="what-are-groups"></a>O que são grupos

Os grupos são contêineres que permitem organizar avaliações. Você pode agrupar avaliações de uma forma que seja lógica para você, como por ano ou regulamento, ou com base nas divisões ou geografias da sua organização. Veja a seguir exemplos de dois grupos e suas avaliações subjacentes:

- **O FFIEC é a avaliação 2020**
  - FFIEC É
- **Avaliações de privacidade e segurança de dados**
  - ISO 27001:2013
  - ISO 27018:2014

Quando duas avaliações diferentes no mesmo grupo ações de melhorias de compartilhamento são gerenciadas por você, todas as atualizações feitas nos detalhes ou no status da implementação da ação serão automaticamente sincronizadas com a mesma ação em qualquer outra avaliação do grupo. Essa sincronização permite implementar uma ação de melhoria e atender a vários requisitos em várias regulamentações.

### <a name="how-to-create-a-group"></a>Como criar um grupo

Você cria um grupo durante o processo de [criação de uma nova avaliação](#to-create-an-assessment).

Os grupos não podem ser criados como entidades autônomas. Um grupo deve conter pelo menos uma avaliação. Para criar um grupo, você precisa primeiro criar uma avaliação para colocar no grupo.

### <a name="what-to-know-when-working-with-groups"></a>O que saber ao trabalhar com grupos

- Os nomes de grupos devem ser exclusivos dentro da sua organização.
- Grupos não têm propriedades de segurança. Todas as permissões são associadas a avaliações.
- Após adicionar uma avaliação a um grupo, o agrupamento não pode ser alterado.
- Controles de avaliação relacionados em avaliações diferentes no mesmo grupo são atualizados automaticamente quando concluído.
- Se você adicionar uma nova avaliação a um grupo existente, as informações comuns de avaliações nesse grupo serão copiadas para a nova avaliação.
- Os grupos podem conter Avaliações para a mesma certificação ou regulamentação, mas cada grupo só pode conter uma avaliação para um par específico de certificação de produto. Por exemplo, um grupo não pode conter duas avaliações para o Office 365 e o NIST CSF. Um grupo pode conter várias avaliações para o mesmo produto apenas se a certificação ou regulamentação correspondente de cada um for diferente.
- A exclusão de uma apuração interrompe a relação entre essa avaliação e o grupo.
- Não é possível excluir grupos.
- Quando uma alteração é feita em uma melhoria que aparece em vários grupos, essa alteração é refletida em todas as instâncias dessa ação de aprimoramento.

## <a name="use-a-pre-built-assessment"></a>Usar uma avaliação previamente criada

Há dois pontos de partida para a criação de uma avaliação de um modelo do Gerenciador de conformidade.

Você pode começar o processo da página de avaliações selecionando o botão **Adicionar avaliação** e, em seguida, trabalhando no assistente de criação de avaliação. As etapas deste processo estão abaixo.

Você também pode iniciar na página de modelos de avaliação encontrando o modelo desejado e selecionando-o na lista para chegar à página de detalhes. Na página detalhes do modelo, selecione **criar avaliação**. Em seguida, você pode inserir o assistente com seu modelo já selecionado.

### <a name="to-create-an-assessment"></a>Para criar uma avaliação

1. Saiba de qual grupo você atribuirá sua avaliação ou prepare-se para criar uma nova para esta avaliação. [Saiba mais sobre grupos](#understand-groups-before-creating-assessments).  

2. Vá até a página **avaliações** no Gerenciador de conformidade e selecione **Adicionar avaliação**. Um assistente de avaliação será exibido em um painel de submenu grande.

3. **Selecione um modelo**: escolha um modelo para servir como base para sua avaliação. Selecione o botão de opção ao lado do modelo escolhido e, em seguida, selecione **Avançar**.

4. **Nome e Grupo:** Insira um nome para a avaliação no campo **nome da avaliação** . Os nomes de avaliação devem ser exclusivos nos grupos. Se o nome de sua avaliação corresponder ao nome de outra avaliação em um determinado grupo, você receberá um erro solicitando que você crie um nome diferente.

5. Atribua sua avaliação a um grupo. Você pode:
    - Selecione **usar grupo existente** para atribuí-lo a um grupo que você já criou; ou
    - Selecione **criar novo grupo** para criar um novo grupo e atribuir esta avaliação a ele:
        - Determine um nome para o seu grupo e insira-o no campo abaixo do botão de opção.
        - Você pode **copiar dados de um grupo existente**, como detalhes de implementação e teste e documentos, selecionando as caixas apropriadas.

    Quando terminar, selecione **Avançar**.

6. **Revisar e concluir:** A última tela do assistente mostra o modelo, nome e grupo escolhido para a avaliação. Você pode editar qualquer uma dessas configurações dos links na tela, que o levará de volta às etapas relevantes no assistente. Quando estiver pronto, selecione **criar avaliação**.

7. A próxima tela confirma que você criou com êxito sua nova avaliação. Selecione **concluído** para fechar o assistente e a página de detalhes da nova avaliação aparecerá na tela.

Se você vir uma **falha na** tela de avaliação após selecionar **criar avaliação**, selecione **tentar novamente** recriar sua avaliação.

Você pode alterar o nome da avaliação depois de criá-la selecionando o botão **Editar nome** no canto superior direito da [página detalhes da avaliação](#monitor-assessment-progress-and-controls).

## <a name="extend-a-pre-built-assessment"></a>Estender uma avaliação previamente criada

Você pode modificar uma avaliação previamente criada adicionando seus próprios controles e ações de melhoria ao modelo da avaliação. Esse processo é chamado de "estender um modelo da Microsoft" no Gerenciador de conformidade. Ao estender o modelo de uma avaliação, ele receberá todas as atualizações liberadas pela Microsoft, o que pode acontecer quando houver alterações na regulamentação ou produto relacionado (consulte [aceitando atualizações para avaliações](#accepting-updates-to-assessments)).

Você concluirá esse processo, começando na página **modelos de avaliação** , e não na página de **avaliação** .

**Antes de começar**

Para se preparar para esse processo, primeiro você precisará montar uma planilha do Excel especialmente formatada para importar os dados de modelo necessários. Há requisitos especiais para os [arquivos do Excel formatados](compliance-manager-templates.md#formatting-your-template-data-with-excel) usados no processo de extensão. Confira estes pontos adicionais para ajudar a evitar erros no processo de importação:

- Sua planilha deve conter somente as ações e os controles que você deseja adicionar à avaliação. 
- A planilha não pode conter nenhum dos controles ou ações que já existam na avaliação que você deseja modificar.
- Considere a inclusão de "Extension" no título do seu modelo, por exemplo, "RGPD – [Your Company Name] Extension". Isso facilita a identificação na lista na página de modelos de **avaliação** , conforme distinto do modelo padrão fornecido pela Microsoft ou de um modelo personalizado com um nome semelhante.

Após Formatar sua planilha, siga as etapas abaixo.

**Etapas para estender um modelo do Gerenciador de conformidade**

1. Vá para a página **modelos de avaliação** e selecione **criar novo modelo**. Um assistente de criação de modelo será aberto.

2. Escolha o tipo de modelo que você deseja criar. Nesse caso, selecione **estender um modelo da Microsoft**e, em seguida, **selecione**.

3. Um painel de submenu de seleção de modelo aparece no lado direito da tela. Use a **pesquisa** para aplicar filtros para localizar o modelo desejado

4. Depois de localizar o modelo, selecione o botão de opção à esquerda do nome e selecione **salvar**.

5. A próxima tela mostra o modelo selecionado. Se correto, selecione **Avançar**. (Se estiver incorreto, escolha **selecionar um modelo diferente** para escolher novamente.)

6. Na triagem **arquivo de upload** , selecione **procurar** para localizar e carregar seu arquivo Excel formatado contendo todos os dados de modelo necessários.

7. Se não houver problemas com o arquivo, a tela seguinte mostrará o nome do arquivo carregado. Selecione **Avançar** para continuar (se precisar alterar o arquivo, selecione **carregar um arquivo diferente**).

    - Se houver um problema com seu arquivo, uma mensagem de erro na parte superior explicará o que há de errado. Você precisará corrigir e recarregar o arquivo. Os erros ocorrerão se sua planilha estiver formatada incorretamente ou se houver informações inválidas em determinados campos.
 
8. A tela **revisão e término** mostra o número de ações e controles de aperfeiçoamento e a pontuação máxima do modelo. Quando estiver pronto para aprovar, selecione **Avançar**. (Se você precisar fazer alterações, selecione **carregar um arquivo diferente**.)

9. A última tela confirma que um novo modelo foi criado. Selecione **concluído** para sair do assistente.

10. Você chegará à página de detalhes do novo modelo. Aqui você pode criar sua avaliação selecionando **criar avaliação**. Para obter orientação, comece na etapa #4 nas [instruções de criação de avaliação acima](#to-create-an-assessment).

## <a name="create-your-own-custom-assessment"></a>Criar sua própria avaliação personalizada

A criação de uma avaliação personalizada no Gerenciador de conformidade exige que você crie seu próprio modelo. Para criar seu próprio modelo, primeiro você montará uma planilha do Excel formatada para importar os dados de modelo necessários. Também ajuda a decidir antes do momento em que grupo você atribuirá sua avaliação ao criá-lo (Saiba mais sobre [grupos](#what-are-groups)).

**Siga as etapas abaixo para criar sua avaliação personalizada:**

1. **Formatar o arquivo do Excel.** Comece Formatando seus dados de modelo em uma planilha do Excel usando [estas instruções](compliance-manager-templates.md#formatting-your-template-data-with-excel).

2. **Crie seu modelo** seguindo [estas instruções](compliance-manager-templates.md#create-a-new-template).

3. **Crie sua avaliação** do modelo. Você pode começar abrindo a página de detalhes do modelo e selecionando **criar avaliação**ou ir até a página **avaliações** e selecionar **criar avaliação**.

4. Um assistente de criação de avaliação será exibido em um painel de submenu grande. A partir daqui, você pode seguir as diretrizes que começam na etapa #3 das [instruções de criação de avaliação](#to-create-an-assessment), usando seu novo modelo personalizado para sua avaliação.

## <a name="delete-an-assessment"></a>Excluir uma avaliação

A exclusão de uma avaliação a remove da lista na página avaliações. Observe estes pontos importantes sobre como excluir avaliações:

- **A exclusão de uma avaliação é permanente; Não é possível obtê-lo novamente.** Se quiser usar a mesma avaliação novamente, você precisará recriá-la.
- Se as ações de melhoria na avaliação não aparecerem em qualquer outra avaliação, elas serão excluídas quando a avaliação for excluída.
- É recomendável [exportar um relatório](#export-an-assessment-report) da avaliação antes de excluí-lo permanentemente.

Para excluir uma avaliação, siga as etapas abaixo:

1. Na página **avaliações** , selecione a avaliação que você deseja excluir para abrir a página detalhes da avaliação.

2. Selecione **excluir avaliação** no canto superior direito da tela.

3. Uma janela será exibida solicitando que você confirme se deseja excluir permanentemente a avaliação. Selecione **excluir avaliação** para fechar a janela. Você receberá uma janela de confirmação de que a avaliação foi excluída do Gerenciador de conformidade.

Se você excluir a única avaliação em um grupo, esse grupo também será excluído do Gerenciador de conformidade.

> [!NOTE]
> Você não pode excluir todas as avaliações. As organizações precisam de, pelo menos, uma avaliação para que o Gerenciador de conformidade funcione corretamente. Se a avaliação que você deseja excluir for a única, adicione outra avaliação antes de excluir a outra avaliação.

## <a name="monitor-assessment-progress-and-controls"></a>Monitorar o progresso e os controles da avaliação

Cada avaliação tem uma página de detalhes que oferece uma visão geral de seu progresso ao concluir a avaliação. A página mostra o andamento da conclusão dos controles e o status do teste das ações de aprimoramento de chave nesses controles.

### <a name="overview-tab"></a>Guia Visão geral

A guia Visão geral contém um gráfico mostrando sua porcentagem em direção à conclusão da avaliação. Este gráfico contém uma divisão de pontos de ações que você possui e aponta de ações de propriedade da Microsoft, para que você possa ver quantos pontos você precisa para concluir a avaliação.

As principais ações de aprimoramento para controles na avaliação são listadas em ordem de maior impacto potencial para ganhar pontos. O gráfico associado detalha o status de teste agregado de suas ações de aprimoramento, para que você possa avaliar rapidamente o que foi testado e o que ainda precisa ser feito.

Para acessar ações de melhorias individuais, visite a guia **controles** ou a guia **ações de aprimoramento** .

### <a name="controls-tab"></a>Guia Controles

A guia controles exibe informações detalhadas para cada controle mapeado para a avaliação. Um gráfico de **detalhamento de status de controle** mostra o status dos controles por família, para que você possa ver rapidamente quais agrupamentos de controles precisam de atenção.

Sob o gráfico, uma tabela lista informações detalhadas sobre cada controle na avaliação. Os controles são agrupados pela família de controle. Expanda cada nome de família para revelar os controles individuais que ele contém. As informações listadas para cada controle incluem:

- **Título do controle**
- **Status**: reflete o status do teste das ações de melhoria dentro do controle 
    - **Passed** -todas as ações de aperfeiçoamento têm um status de teste de "Passed", ou pelo menos um é passado e o restante estão "fora do escopo"
    -  **Falha** -pelo menos uma ação de melhoria tem um status de teste de "falha"
    - **None** -todas as ações de aperfeiçoamento não foram testadas
    - **Fora do escopo** -todas as ações de melhoria estão fora do escopo desta avaliação
    - **Em andamento** – as ações de melhoria têm um status diferente daqueles listados acima, que podem incluir "em andamento", "crédito parcial" ou "não detectado"
- **ID de controle**: o número de identificação do controle, atribuído por sua regulamentação, padrão ou política correspondente
- **Pontos alcançados**: o número de pontos obtidos por meio da conclusão de ações, do número total de pontos atingíveis 
- **Suas ações**: o número de ações concluídas do número total de ações a serem realizadas
- **Ações da Microsoft**: o número de ações concluídas pela Microsoft 

Para exibir os detalhes de um controle, selecione-o na sua linha na tabela. A página detalhes do controle mostra um gráfico que indica o status do teste das ações dentro desse controle. Uma tabela abaixo do gráfico mostra as principais ações de aperfeiçoamento para esse controle.

Selecione uma ação de aprimoramento na lista para analisar a página de detalhes da ação de aprimoramento. As páginas de detalhes mostram o status do teste, as notas de implementação e o lançamento na solução recomendada.

### <a name="your-improvement-actions-tab"></a>Guia ações de melhoria

A guia para suas ações de melhoria lista todos os controles na avaliação que são gerenciados por sua organização. A barra de status detalha o status de teste agregado de suas ações de aprimoramento na avaliação para que você possa avaliar rapidamente o que foi testado e o que ainda precisa ser feito. Abaixo da barra é a lista completa de ações de aperfeiçoamento e detalhes importantes, incluindo: status do teste, o número de pontos potenciais e ganhos, normas e padrões associados, solução aplicável, tipo de ação e família de controle. Saiba mais sobre [como as ações contribuem para sua pontuação de conformidade](compliance-score-calculation.md#action-types-and-points).

Selecione uma ação de melhoria para exibir sua página de detalhes e selecione o link **Iniciar agora** para abrir a solução para executar a ação.

### <a name="microsoft-actions-tab"></a>Guia de ações da Microsoft

A guia Microsoft Actions lista todas as ações na avaliação que são gerenciados pela Microsoft. A lista mostra os principais detalhes da ação, incluindo: testar o status, pontos que contribuem para a pontuação de conformidade geral, normas e padrões associados, solução aplicável, tipo de ação e família de controle. Selecione uma ação de melhoria para exibir sua página de detalhes.

Saiba mais sobre [como os controles e as ações de aperfeiçoamento são rastreados e pontuados.](compliance-score-calculation.md)

## <a name="accepting-updates-to-assessments"></a>Aceitação de atualizações para avaliações

Quando uma atualização estiver disponível para uma avaliação, você verá uma notificação e terá a opção de aceitar ou adiar a atualização para um momento posterior.

### <a name="what-causes-an-update"></a>O que causa uma atualização

Uma atualização de avaliação ocorre quando há alterações de modelo subjacente que causam impacto na pontuação. As alterações podem envolver o ajuste do mapeamento de controle ou outras orientações com base em alterações regulamentativas ou alterações de produto. As atualizações de avaliação podem ser originadas da sua organização (como, quando um [modelo personalizado é modificado](compliance-manager-templates.md#modify-a-template)) e da Microsoft.

Se a Microsoft atualizar um modelo do Gerenciador de conformidade estendido, sua avaliação herdará essas atualizações quando você aceitá-las. A avaliação manterá os atributos adicionais que você aplicou à avaliação ao estendeu-os.

As avaliações personalizadas criadas não recebem nenhuma atualização de modelo da Microsoft. As avaliações personalizadas podem receber atualizações de ações de melhoria, mas qualquer atualização da Microsoft para controlar o mapeamento entre avaliações e ações de melhoria não se aplica a modelos personalizados.

> [!NOTE]
> As atualizações nas avaliações aplicam-se apenas no nível do grupo. Se você tiver duas avaliações criadas a partir do mesmo modelo que existem em dois grupos diferentes, cada avaliação terá uma notificação de atualização pendente e você precisará aceitar a atualização para cada avaliação em seu respectivo grupo individualmente.

#### <a name="where-youll-see-assessment-update-notifications"></a>Onde você verá as notificações de atualização de avaliação

A página detalhes da avaliação também mostra um rótulo de **atualização pendente** ao lado da avaliação com uma atualização. Selecione essa avaliação para acessar sua página de detalhes.

Uma mensagem próxima à parte superior da página detalhes da avaliação mostra que uma atualização está disponível para essa avaliação. Selecione o botão **examinar atualização** no banner para examinar as alterações específicas e aceitar ou adiar a atualização.

A página detalhes da avaliação também pode listar ações de melhoria que têm um rótulo de **atualização pendente** ao lado. Essas atualizações são para alterações específicas nas ações de melhoria e precisam ser aceitas separadamente. Visite [aceitar atualizações para ações de melhoria](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) para saber mais.

#### <a name="review-update-to-accept-or-defer"></a>Revisar atualização para aceitar ou adiar

Após selecionar a **atualização de revisão** na página detalhes da avaliação, um painel de submenu aparece no lado direito da tela. O painel de submenus fornece os principais detalhes abaixo sobre a atualização pendente:

- O título do modelo
- Fonte da atualização (Microsoft, sua organização ou um usuário específico)
- A data em que a atualização foi criada
- Uma visão geral explicando a atualização
- Detalhes específicos sobre as alterações, incluindo o impacto em sua pontuação de conformidade, a quantidade de progresso para a conclusão da avaliação e o número específico de alterações para ações e controles de melhoria.

Selecionar o link de **modelo atualizado** baixará um arquivo do Excel contendo dados de controle para a versão do modelo com as atualizações pendentes. Selecionar o link de **modelo atual** baixa um arquivo do modelo existente sem as alterações.

Para aceitar a atualização e fazer as alterações na avaliação, selecione **aceitar atualização**. As alterações aceitas são permanentes.

Se você selecionar **Cancelar**, a atualização não será aplicada à avaliação. No entanto, você continuará a ver a notificação de **atualização pendente** até aceitar a atualização.

**Por que recomendamos aceitar atualizações**

A aceitação de atualizações ajuda a garantir que você tenha a orientação mais atualizada sobre como usar soluções e tomar as ações apropriadas de melhorias para ajudá-lo a atender aos requisitos de certificação em mãos.

**Por que você pode querer adiar uma atualização**

Se estiver no meio da conclusão de uma avaliação, convém garantir que você tenha concluído o trabalho antes de aceitar uma atualização para a avaliação que pode causar o mapeamento de controle. Você pode adiar a atualização mais tarde selecionando **Cancelar** no painel revisar atualização de submenu.

## <a name="export-an-assessment-report"></a>Exportar um relatório de avaliação

Você pode exportar uma avaliação para um arquivo do Excel para stakeholders de conformidade em sua organização ou para auditores externos e reguladores. Na página detalhes da avaliação, selecione o botão **gerar relatório** próximo à parte superior da página, que cria um arquivo do Excel que você pode salvar e compartilhar.

O relatório é um instantâneo da avaliação a partir da data e hora da exportação. Ele contém os detalhes de controles gerenciados por você e pela Microsoft, incluindo status de implementação, data de teste e resultados de teste.