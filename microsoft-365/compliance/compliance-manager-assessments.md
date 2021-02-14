---
title: Criar e gerenciar avaliações no Gerenciador de Conformidade da Microsoft
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
description: Crie avaliações no Gerenciador de Conformidade da Microsoft para ajudá-lo a atender aos requisitos de regulamentações e certificações importantes para sua organização.
ms.openlocfilehash: d09103f58be3a5fa39b57ca35da411e8046aace5
ms.sourcegitcommit: 61d7284b412d0f7bbd8bbb2225c2e6324f86b717
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/24/2020
ms.locfileid: "48262286"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Criar e gerenciar avaliações no Gerenciador de Conformidade

**Neste artigo:** Saiba como personalizar o Gerenciador de Conformidade para sua organização criando e gerenciando **avaliações.** Este artigo o orienta sobre como criar avaliações, como organizá-las em **grupos,** trabalhar com **controles,** aceitar atualizações e exportar relatórios de **avaliação.**

> [!IMPORTANT]
> As avaliações disponíveis para sua organização dependem do seu contrato de licenciamento. [Revise os detalhes.](https://go.microsoft.com/fwlink/?linkid=2132371)

## <a name="introduction-to-assessments"></a>Introdução às avaliações

O Gerenciador de Conformidade ajuda você a gerenciar a conformidade com avaliações para as regulamentações e certificações que se aplicam à sua organização. As avaliações são agrupações de controles de uma regulamentação, padrão ou política específica. O Gerenciador de Conformidade facilita o rastreamento da conformidade, fornecendo avaliações pré-criadas que abrangem uma variedade de regulamentações e certificações regionais e do setor.

Cada avaliação é criada a partir de um [modelo de avaliação.](compliance-manager-templates.md) Os modelos servem como uma estrutura que contém os controles necessários, ações de melhoria e ações da Microsoft para concluir a avaliação. Configurar as avaliações mais relevantes para sua organização pode ajudá-lo a implementar políticas e procedimentos operacionais para limitar o risco de conformidade.

Todas as avaliações estão listadas na página de avaliações. Saiba mais sobre [como filtrar sua exibição de avaliações e interpretar estados de status.](compliance-manager-setup.md#assessments-page)

## <a name="data-protection-baseline-default-assessment"></a>Avaliação padrão da Linha de Base de Proteção de Dados

Para começar, a Microsoft fornece uma avaliação padrão no Gerenciador de Conformidade para **a** linha de base de proteção de dados do **Microsoft 365.** Esta avaliação de linha de base tem um conjunto de controles para os principais regulamentos e padrões de proteção de dados e governança de dados gerais. Esta linha de base desenha elementos principalmente do NIST CSF (National Institute of Standards and Technology Cybersecurity Framework) e da ISO (International Organization for Standardization), bem como do FedRAMP (Federal Risk and Authorization Management Program) e do RGPD (Regulamento Geral sobre a Proteção de Dados da União Europeia).

Essa avaliação é usada para calcular sua pontuação de conformidade inicial na primeira vez que você chega ao Gerenciador de Conformidade, antes de configurar outras avaliações. O Gerenciador de Conformidade coleta sinais iniciais de suas soluções do Microsoft 365. Você verá rapidamente o desempenho da sua organização em relação aos principais padrões e regulamentos de proteção de dados e verá as ações de melhoria sugeridas a tomar.

O Gerenciador de Conformidade se torna mais útil à medida que você cria e gerencia suas próprias avaliações para atender às necessidades específicas da sua organização.

## <a name="assessment-creation-overview"></a>Visão geral da criação da avaliação

Há três maneiras de configurar avaliações:

1. [Use uma avaliação pré-criada.](#use-a-pre-built-assessment)
2. [Estenda uma avaliação pré-criada para atender às suas necessidades.](#extend-a-pre-built-assessment)
3. [Crie sua própria avaliação personalizada.](#create-your-own-custom-assessment)

> [!NOTE]
> Somente os usuários que têm uma função de Administrador Global ou Administração do Gerenciador de Conformidade podem criar e modificar avaliações. Saiba mais sobre [funções e permissões.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

**Usar uma avaliação pré-criada**

Inicia sua jornada de conformidade escolhendo uma avaliação já configurada pelo Gerenciador de Conformidade. Fornecemos uma ampla [](compliance-manager-templates.md) seleção de modelos para regulamentações e certificações que se alinham a setores, regiões e padrões comuns de proteção de dados, como rgpd e ISO 27001. Os modelos contêm os controles e as ações de melhoria para ajudá-lo a atender aos requisitos de uma certificação específica. Você será solicitado a escolher um modelo quando começar a criar [uma avaliação.](#use-a-pre-built-assessment)

**Estender uma avaliação pré-criada para atender às suas necessidades**

Você pode modificar uma avaliação do Gerenciador de Conformidade , um processo que nos referimos como "extensão", adicionando seus próprios controles e ações para melhor atender às necessidades da sua organização. Por exemplo, se você geralmente precisar estar em conformidade com a HIPAA, mas precisar de proteção de dados adicional ou controles de segurança, poderá estender nosso modelo HIPAA adicionando seus próprios controles a ele. Consulte as instruções para [estender uma avaliação pré-criada.](#extend-a-pre-built-assessment)

**Criar sua própria avaliação personalizada**

Você pode criar sua própria avaliação inteiramente do zero para rastrear com precisão o que sua organização precisa. Criar sua própria avaliação exige que você primeiro crie seu próprio modelo para a avaliação no Gerenciador de Conformidade. Consulte as instruções para criar [sua própria avaliação personalizada.](#create-your-own-custom-assessment)

## <a name="understand-groups-before-creating-assessments"></a>Compreender os grupos antes de criar avaliações

Antes de criar ou modificar avaliações, é importante entender como os grupos funcionam. Ao criar uma avaliação, você precisará atribuí-la a um grupo durante o processo. É por isso que recomendamos planejar uma estratégia de grupo para suas avaliações antes de criar avaliações.

### <a name="what-are-groups"></a>O que são grupos

Os grupos são contêineres que permitem organizar avaliações. Você pode agrupar avaliações de maneira lógica, como por ano ou regulamentação, ou com base nas divisões ou regiões geográficas da sua organização. A seguir estão exemplos de dois grupos e suas avaliações subjacentes:

- **Avaliação FFIEC IS 2020**
  - FFIEC IS
- **Avaliações de segurança e privacidade de dados**
  - ISO 27001:2013
  - ISO 27018:2014

Quando duas avaliações diferentes no mesmo grupo compartilham ações de melhoria gerenciadas por você, todas as atualizações feitas nos detalhes ou status de implementação de uma ação serão sincronizadas automaticamente com a mesma ação em qualquer outra avaliação do grupo. Essa sincronização permite implementar uma ação de melhoria e atender a vários requisitos em vários regulamentos.

### <a name="how-to-create-a-group"></a>Como criar um grupo

Você cria um grupo durante o processo de [criação de uma nova avaliação.](#to-create-an-assessment)

Os grupos não podem ser criados como entidades autônomas. Um grupo deve conter pelo menos uma avaliação. Para criar um grupo, você precisa primeiro criar uma avaliação para colocá-lo no grupo.

### <a name="what-to-know-when-working-with-groups"></a>O que saber ao trabalhar com grupos

- Os nomes de grupo devem ser exclusivos em sua organização.
- Os grupos não têm propriedades de segurança. Todas as permissões estão associadas a avaliações.
- Depois de adicionar uma avaliação a um grupo, o grupo não pode ser alterado.
- Os controles de avaliação relacionados em avaliações diferentes no mesmo grupo são atualizados automaticamente quando concluídos.
- Se você adicionar uma nova avaliação a um grupo existente, as informações comuns das avaliações desse grupo serão copiadas para a nova avaliação.
- Os grupos podem conter avaliações para a mesma certificação ou regulamentação, mas cada grupo pode conter apenas uma avaliação para um par específico de certificação de produto. Por exemplo, um grupo não pode conter duas avaliações para o Office 365 e o NIST CSF. Um grupo pode conter várias avaliações para o mesmo produto somente se a certificação ou regulamentação correspondente para cada uma delas for diferente.
- A exclusão de uma avaliação quebra a relação entre essa avaliação e o grupo.
- Os grupos não podem ser excluídos.
- Quando uma alteração é feita para uma melhoria que aparece em vários grupos, essa alteração é refletida em todas as instâncias dessa ação de melhoria.

## <a name="use-a-pre-built-assessment"></a>Usar uma avaliação pré-criada

Há dois pontos de partida para criar uma avaliação a partir de um modelo do Gerenciador de Conformidade.

Você pode começar o processo na página de avaliações selecionando o botão **Adicionar avaliação** e, em seguida, trabalhando com o assistente de criação de avaliação. As etapas para esse processo estão abaixo.

Você também pode começar na página de modelos de avaliação encontrando o modelo que deseja e selecionando-o na lista para chegar à sua página de detalhes. Na página de detalhes do modelo, selecione **Criar avaliação.** Em seguida, você entrará no assistente com seu modelo já selecionado.

### <a name="to-create-an-assessment"></a>Para criar uma avaliação

1. Saiba a qual grupo você atribuirá sua avaliação ou esteja preparado para criar uma nova para essa avaliação. [Saiba mais sobre grupos.](#understand-groups-before-creating-assessments)  

2. Vá para a página **de avaliações** no Gerenciador de Conformidade e selecione **Adicionar avaliação.** Um assistente de avaliação aparecerá em um painel grande.

3. **Selecione um modelo:** escolha um modelo para servir como base para sua avaliação. Selecione o botão de opção ao lado do modelo escolhido e selecione **Próximo.**

4. **Nome e grupo:** Insira um nome para sua avaliação no campo **Nome da Avaliação.** Os nomes de avaliação devem ser exclusivos dentro de grupos. Se o nome da sua avaliação corresponde ao nome de outra avaliação em um determinado grupo, você receberá um erro solicitando que você crie um nome diferente.

5. Atribua sua avaliação a um grupo. Você pode:
    - Selecione **Usar grupo existente** para atribuí-lo a um grupo que você já criou; ou
    - Selecione **Criar novo grupo** para criar um novo grupo e atribuir essa avaliação a ele:
        - Determine um nome para o grupo e insira-o no campo abaixo do botão de rádio.
        - Você pode **copiar dados de um grupo existente,** como detalhes e documentos de implementação e teste, selecionando as caixas apropriadas.

    Quando terminar, selecione **Next**.

6. **Revise e termine:** A última tela do assistente mostra o modelo, o nome e o grupo escolhidos para a avaliação. Você pode editar qualquer uma dessas configurações nos links na tela, o que o levará de volta para as etapas relevantes no assistente. Quando estiver pronto, selecione Criar **avaliação.**

7. A próxima tela confirma que você criou com êxito sua nova avaliação. Selecione **Feito** para fechar o assistente, e a página de detalhes da nova avaliação aparecerá na tela.

Se você vir uma **tela de Avaliação** com falha após selecionar Criar **avaliação,** selecione **Tentar novamente** para criar novamente sua avaliação.

Você pode alterar o nome da avaliação  depois de criar a avaliação selecionando o botão Editar nome no canto superior direito da página de [detalhes da avaliação.](#monitor-assessment-progress-and-controls)

## <a name="extend-a-pre-built-assessment"></a>Estender uma avaliação pré-criada

Você pode modificar uma avaliação pré-criada adicionando seus próprios controles e ações de melhoria ao modelo da avaliação. Esse processo é chamado de "estender um modelo da Microsoft" no Gerenciador de Conformidade. Quando você estender o modelo de uma avaliação, ele receberá as atualizações lançadas pela Microsoft, o que pode acontecer quando houver alterações na regulamentação ou produto relacionado (consulte Aceitando atualizações para [avaliações).](#accepting-updates-to-assessments)

Você concluirá esse processo começando na página de modelos **de** avaliação em vez da **página de avaliações.**

**Antes de começar**

Para se preparar para esse processo, primeiro você precisará montar uma planilha do Excel especialmente formatada para importar os dados de modelo necessários. Há requisitos especiais para os [arquivos formatados do Excel](compliance-manager-templates.md#formatting-your-template-data-with-excel) usados no processo de extensão. Consulte estes pontos adicionais para ajudar a evitar erros no processo de importação:

- Sua planilha deve conter apenas as ações e os controles que você deseja adicionar à avaliação. 
- A planilha não pode conter nenhum dos controles ou ações que já existem na avaliação que você deseja modificar.
- Considere incluir "extensão" no título do seu modelo, por exemplo, "RGPD – extensão [nome da sua empresa]". Isso facilita a identificação na lista  na página de modelos de avaliação como diferente do modelo padrão fornecido pela Microsoft ou de um modelo personalizado com um nome semelhante.

Depois de formatar sua planilha, siga as etapas abaixo.

**Etapas para estender um modelo do Gerenciador de Conformidade**

1. Vá para a **página Modelos de Avaliação** e selecione **Criar novo modelo.** Um assistente de criação de modelo será aberto.

2. Escolha o tipo de modelo que você deseja criar. Nesse caso, selecione **Estender um modelo da Microsoft** e selecione . 

3. Um painel de seleção de modelo aparece no lado direito da tela. Use **a Pesquisa** para aplicar filtros para localizar o modelo que você deseja

4. Depois de localizar seu modelo, selecione o botão de opção à esquerda do nome dele e selecione **Salvar.**

5. A próxima tela mostra o modelo que você selecionou. Se estiver correto, selecione **Next**. (Se estiver incorreto, **escolha Selecionar um modelo diferente** para escolher novamente.)

6. Na tela **Carregar arquivo,** selecione **Procurar** para encontrar e carregar o arquivo formatado do Excel contendo todos os dados de modelo necessários.

7. Se não houver problemas com seu arquivo, a próxima tela mostrará o nome do arquivo carregado. Select **Next** to continue (if you need to change the file, select **Upload a different file**).

    - Se houver um problema com o arquivo, uma mensagem de erro na parte superior explica o que há de errado. Você precisará corrigir e carregar seu arquivo. Os erros ocorrerão se sua planilha for formatada incorretamente ou se houver informações inválidas em determinados campos.
 
8. A **tela Revisar e concluir** mostra o número de ações e controles de melhoria e a pontuação máxima para o modelo. Quando estiver pronto para aprovar, selecione **Próximo**. (Se você precisar fazer alterações, selecione **Carregar um arquivo diferente.)**

9. A última tela confirma que um novo modelo foi criado. Selecione **Feito** para sair do assistente.

10. Você chegará à página de detalhes do novo modelo. A partir daqui, você pode criar sua avaliação selecionando **Criar avaliação.** Para obter orientações, comece na etapa #4 nas instruções de criação [da avaliação acima.](#to-create-an-assessment)

## <a name="create-your-own-custom-assessment"></a>Criar sua própria avaliação personalizada

Criar uma avaliação personalizada no Gerenciador de Conformidade exige que você crie seu próprio modelo. Para criar seu próprio modelo, primeiro você montará uma planilha do Excel formatada para importar os dados de modelo necessários. Isso também ajuda a decidir com antecedência a qual grupo você atribuirá sua avaliação ao criar (saiba mais sobre [grupos).](#what-are-groups)

**Siga as etapas abaixo para criar sua avaliação personalizada:**

1. **Formatar seu arquivo do Excel.** Comece formatando os dados do modelo em uma planilha do Excel usando [estas instruções.](compliance-manager-templates.md#formatting-your-template-data-with-excel)

2. **Crie seu modelo** seguindo [estas instruções.](compliance-manager-templates.md#create-a-new-template)

3. **Crie sua avaliação** a partir do modelo. Você pode começar abrindo a página de detalhes do modelo  e selecionando Criar avaliação **ou** vá até a página de avaliações e selecione **Criar avaliação.**

4. Um assistente de criação de avaliação aparecerá em um painel grande. A partir daqui, você pode seguir as orientações [](#to-create-an-assessment)que começam na etapa #3 instruções de criação da avaliação, usando seu novo modelo personalizado para sua avaliação.

## <a name="delete-an-assessment"></a>Excluir uma avaliação

A exclusão de uma avaliação a remove da lista na página de avaliações. Observe estes pontos importantes sobre a exclusão de avaliações:

- **A exclusão de uma avaliação é permanente; você não pode obter de volta.** Se você quiser usar a mesma avaliação novamente, será necessário re-crie-la.
- Se as ações de melhoria na avaliação não aparecerem em nenhuma outra avaliação, elas serão excluídas quando a avaliação for excluída.
- Recomendamos [exportar um relatório da](#export-an-assessment-report) avaliação antes de excluí-lo permanentemente.

Para excluir uma avaliação, siga as etapas abaixo:

1. Na página **de avaliações,** selecione a avaliação que deseja excluir para abrir a página de detalhes dessa avaliação.

2. Selecione **Excluir avaliação** no canto superior direito da tela.

3. Uma janela será exibida solicitando que você confirme que deseja excluir permanentemente a avaliação. Selecione **Excluir avaliação** para fechar a janela. Você obterá uma janela de confirmação de que sua avaliação foi excluída do Gerenciador de Conformidade.

Se você excluir a única avaliação em um grupo, esse grupo também será excluído do Gerenciador de Conformidade.

> [!NOTE]
> Você não pode excluir todas as avaliações. As organizações precisam de pelo menos uma avaliação para que o Gerenciador de Conformidade funcione corretamente. Se a avaliação que você deseja excluir for a única, adicione outra avaliação antes de excluir a outra avaliação.

## <a name="monitor-assessment-progress-and-controls"></a>Monitorar o progresso e os controles da avaliação

Cada avaliação tem uma página de detalhes que fornece uma visão rápida do seu progresso ao concluir a avaliação. A página mostra seu progresso na conclusão de controles e o status de teste das principais ações de melhoria dentro desses controles.

### <a name="overview-tab"></a>Guia Visão geral

A guia visão geral contém um gráfico mostrando sua porcentagem para a conclusão da avaliação. Esse gráfico contém uma divisão de pontos de ações que você possui e pontos de ações pertencentes à Microsoft, para que você possa ver quantos pontos mais você precisa para concluir a avaliação.

As principais ações de melhoria dos controles na avaliação são listadas na ordem de maior impacto potencial para ganhar pontos. O gráfico associado detalha o status de teste agregado de suas ações de melhoria para que você possa avaliar rapidamente o que foi testado e o que ainda precisa ser feito.

Para acessar ações de melhoria individuais, visite a guia **Controles** ou **a guia Suas ações de melhoria.**

### <a name="controls-tab"></a>Guia Controles

A guia controles exibe informações detalhadas para cada controle mapeado para a avaliação. Um **gráfico de divisão de status** de controle mostra o status dos controles por família, para que você possa ver rapidamente quais grupos de controles precisam de atenção.

Abaixo do gráfico, uma tabela lista informações detalhadas sobre cada controle dentro da avaliação. Os controles são agrupados por família de controles. Expanda cada nome de família para revelar os controles individuais que ele contém. As informações listadas para cada controle incluem:

- **Título do controle**
- **Status**: reflete o status do teste das ações de melhoria dentro do controle 
    - **Aprovado** - todas as ações de melhoria têm um status de teste "aprovado", ou pelo menos uma é aprovada e o restante está "fora do escopo"
    -  **Falha** – pelo menos uma ação de melhoria tem um status de teste de "falha"
    - **Nenhum** - todas as ações de melhoria não foram testadas
    - **Fora do escopo** - todas as ações de melhoria estão fora do escopo desta avaliação
    - **Em andamento** - as ações de melhoria têm um status diferente dos listados acima, o que pode incluir "em andamento", "crédito parcial" ou "não detectado"
- **ID do** controle: o número de identificação do controle, atribuído pela regulamentação, padrão ou política correspondente
- **Pontos alcançados:** o número de pontos obtidos ao concluir ações, fora do número total de pontos alcançados 
- **Suas ações:** o número de suas ações concluídas fora do número total de ações a serem realizadas
- **Ações da Microsoft**: o número de ações concluídas pela Microsoft 

Para exibir os detalhes de um controle, selecione-o em sua linha na tabela. A página de detalhes do controle mostra um gráfico indicando o status do teste das ações dentro desse controle. Uma tabela abaixo do gráfico mostra as principais ações de melhoria para esse controle.

Selecione uma ação de melhoria na lista para detalhar a página de detalhes da ação de melhoria. As páginas de detalhes mostram o status do teste, notas de implementação e iniciam a solução recomendada.

### <a name="your-improvement-actions-tab"></a>Guia Suas ações de melhoria

A guia para suas ações de melhoria lista todos os controles na avaliação que são gerenciados pela sua organização. A barra de status detalha o status de teste agregado de suas ações de melhoria na avaliação para que você possa avaliar rapidamente o que foi testado e o que ainda precisa ser feito. Abaixo da barra está a lista completa de ações de melhoria e detalhes importantes, incluindo: status do teste, o número de pontos potenciais e obtidos, regulamentos e padrões associados, solução aplicável, tipo de ação e família de controles. Saiba mais sobre como [as ações contribuem para sua pontuação de conformidade.](compliance-score-calculation.md#action-types-and-points)

Selecione uma ação de melhoria para exibir sua página de detalhes e selecione o **link** Iniciar agora para abrir a solução para tomar uma ação.

### <a name="microsoft-actions-tab"></a>Guia ações da Microsoft

A guia Ações da Microsoft lista todas as ações na avaliação gerenciadas pela Microsoft. A lista mostra os principais detalhes da ação, incluindo: status do teste, pontos que contribuem para sua pontuação geral de conformidade, regulamentos e padrões associados, solução aplicável, tipo de ação e família de controles. Selecione uma ação de melhoria para exibir sua página de detalhes.

Saiba mais sobre [como controles e ações de melhoria são controladas e pontuadas.](compliance-score-calculation.md)

## <a name="accepting-updates-to-assessments"></a>Aceitando atualizações para avaliações

Quando uma atualização estiver disponível para uma avaliação, você verá uma notificação e terá a opção de aceitar a atualização ou adiá-la mais tarde.

### <a name="what-causes-an-update"></a>O que causa uma atualização

Uma atualização de avaliação ocorre quando há alterações de modelo subjacentes que impactam na pontuação. As alterações podem envolver o ajuste do mapeamento de controles ou outras diretrizes com base em alterações regulamentar ou alterações do produto. As atualizações de avaliação podem se originar da sua organização (por exemplo, quando um modelo personalizado é [modificado)](compliance-manager-templates.md#modify-a-template)e da Microsoft.

Se a Microsoft atualizar um modelo do Gerenciador de Conformidade que você estendeu, sua avaliação herdará essas atualizações assim que você aceitá-las. Sua avaliação manterá os atributos adicionais que você aplicou à avaliação quando a estendeu.

As avaliações personalizadas que você cria não recebem atualizações de modelo da Microsoft. As avaliações personalizadas podem receber atualizações de ação de melhoria, mas as atualizações da Microsoft para controlar o mapeamento entre avaliações e ações de melhoria não se aplicam a modelos personalizados.

> [!NOTE]
> As atualizações das avaliações se aplicam somente no nível do grupo. Se você tiver duas avaliações criadas a partir do mesmo modelo que existem em dois grupos diferentes, cada avaliação terá uma notificação de atualização pendente, e você precisará aceitar a atualização para cada avaliação em seu respectivo grupo individualmente.

#### <a name="where-youll-see-assessment-update-notifications"></a>Onde você verá as notificações de atualização de avaliação

A página de detalhes da avaliação também mostra **um rótulo de atualização** pendente ao lado da avaliação com uma atualização. Selecione essa avaliação para chegar à sua página de detalhes.

Uma mensagem na parte superior da página de detalhes da avaliação mostra que uma atualização está disponível para essa avaliação. Selecione o **botão Revisar atualização** na faixa para revisar as alterações específicas e aceitar ou adiar a atualização.

A página de detalhes da avaliação também pode listar ações de melhoria que têm um rótulo **de atualização** pendente ao lado deles. Essas atualizações são para alterações específicas nas ações de melhoria em si e precisam ser aceitas separadamente. Visite [aceitando atualizações para ações de melhoria](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) para saber mais.

#### <a name="review-update-to-accept-or-defer"></a>Revisar a atualização para aceitar ou adiar

Depois de **selecionar Revisar atualização** na página de detalhes da avaliação, um painel demenu é exibido no lado direito da tela. O painel de sobremenu fornece os principais detalhes abaixo sobre a atualização pendente:

- O título do modelo
- Origem da atualização (Microsoft, sua organização ou um usuário específico)
- A data em que a atualização foi criada
- Uma visão geral explicando a atualização
- Detalhes específicos sobre as alterações, incluindo o impacto na pontuação de conformidade, a quantidade de progresso na conclusão da avaliação e o número específico de alterações nas ações e controles de melhoria.

Selecionar o link **de modelo** Atualizado baixará um arquivo do Excel contendo dados de controle para a versão do modelo com as atualizações pendentes. Selecionar o link **modelo** atual baixa um arquivo do modelo existente sem as alterações.

Para aceitar a atualização e fazer as alterações em sua avaliação, selecione **Aceitar atualização.** As alterações aceitas são permanentes.

Se você selecionar **Cancelar,** a atualização não será aplicada à avaliação. No entanto, você continuará a ver a notificação **de** atualização pendente até aceitar a atualização.

**Por que recomendamos aceitar atualizações**

Aceitar atualizações ajuda a garantir que você tenha as orientações mais atualizadas sobre como usar soluções e tomar as ações de melhoria apropriadas para ajudá-lo a atender aos requisitos da certificação em mãos.

**Por que você talvez queira adiar uma atualização**

Se você estiver no meio da conclusão de uma avaliação, talvez queira garantir que terminou de trabalhar nele antes de aceitar uma atualização para a avaliação que possa interromper o mapeamento de controles. Você pode adiar a atualização mais tarde selecionando **Cancelar** no painel do flyout de atualização de revisão.

## <a name="export-an-assessment-report"></a>Exportar um relatório de avaliação

Você pode exportar uma avaliação para um arquivo do Excel para participantes de conformidade em sua organização ou para auditores e reguladores externos. Na página de detalhes  da avaliação, selecione o botão Gerar relatório na parte superior da página, que cria um arquivo do Excel que você pode salvar e compartilhar.

O relatório é um instantâneo da avaliação a partir da data e hora da exportação. Ele contém os detalhes dos controles gerenciados por você e pela Microsoft, incluindo o status da implementação, a data de teste e os resultados do teste.