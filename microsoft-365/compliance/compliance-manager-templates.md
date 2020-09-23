---
title: Trabalhando com modelos de avaliação no Microsoft Compliance Manager
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
description: Saiba como usar e gerenciar modelos para a criação de avaliações no Microsoft Compliance Manager. Criar e modificar modelos usando um arquivo Excel formatado.
ms.openlocfilehash: 95cd6e90454b04f34014830008b9e7fbec04c38e
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204268"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Trabalhando com modelos de avaliação no gerente de conformidade

**Neste artigo:** Entenda **como os modelos funcionam** e **como gerenciá-los** na página modelos de avaliação. Obtenha instruções para a **criação** de novos modelos, **modificação** de modelos existentes, **formatação de dados de modelo com o Excel**e exportação de **relatórios**de modelo.

> [!IMPORTANT]
> Os modelos de avaliação disponíveis para sua organização dependem do contrato de licenciamento. [Revise os detalhes](https://go.microsoft.com/fwlink/?linkid=2132371).

## <a name="templates-overview"></a>Visão geral de modelos

Um modelo é uma estrutura para criar uma avaliação no Gerenciador de conformidade. Eles contêm os controles para atender aos requisitos de uma certificação usando um determinado produto. O Gerenciador de conformidade fornece um conjunto abrangente de modelos para ajudar sua organização a cumprir os requisitos nacionais, regionais e específicos do setor que regem a coleta e o uso de dados.

## <a name="list-of-pre-built-templates-for-assessments"></a>Lista de modelos predefinidos para avaliações

O Gerenciador de conformidade fornece modelos para a criação de Avaliações para ajudá-lo a cumprir várias normas e padrões. Exiba a [lista de modelos](compliance-manager-templates-list.md) fornecidos pelo gerente de conformidade. Novos modelos são adicionados regularmente, portanto, verifique a lista com frequência.

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Exibindo e Gerenciando modelos da página modelos de avaliação

A página modelos de avaliação no Gerenciador de conformidade exibe uma lista de modelos e detalhes principais. A lista inclui modelos fornecidos pelo gerente de conformidade, bem como quaisquer modelos modificados ou criados por sua organização. Você pode aplicar filtros para localizar um modelo com base em certificação, escopo do produto, país, setor, quem o criou e se o modelo está habilitado para a criação da avaliação.

Selecione um modelo de sua linha para exibir sua página de detalhes. Esta página contém uma descrição do modelo e mais informações sobre a certificação, o escopo e os detalhes dos controles. Nessa página, você pode selecionar os botões apropriados para criar uma avaliação, exportar os dados do modelo para o Excel ou modificar o modelo.

## <a name="creating-and-modifying-templates-overview"></a>Criando e modificando modelos de visão geral

Para modificar um modelo existente ou para criar seu próprio novo modelo, você usará uma planilha do Excel especialmente formatada ([baixar um exemplo](https://go.microsoft.com/fwlink/?linkid=2124865)) para montar os dados de controle necessários. Após concluir a planilha, importe-a para o Gerenciador de conformidade durante o processo de criação ou modificação de um modelo.

> [!NOTE]
> A planilha tem um formato e esquema específicos que deve ser usado ou não será importado corretamente para o Gerenciador de conformidade. As [instruções de formatação](#formatting-your-template-data-with-excel) estão abaixo.

**Funções necessárias**

Somente os usuários que retêm uma função de administração global de administrador ou gerente de conformidade podem criar e modificar modelos. Saiba mais sobre [funções e permissões](compliance-manager-setup.md#set-user-permissions-and-assign-roles).

## <a name="create-a-new-template"></a>Criar um novo modelo

Para criar seu próprio modelo novo (usado para compilar avaliações personalizadas), siga as etapas abaixo.

1. Vá para a página **modelos de avaliação** no Gerenciador de conformidade.
2. Selecione **criar novo modelo**. Um assistente de criação de modelo será aberto.
3. Escolha o tipo de modelo que você deseja criar. Nesse caso, selecione **criar um modelo personalizado**e, em seguida, selecione **Avançar**.
4. Na triagem de **arquivo de upload** , selecione **procurar** para localizar e carregar seu arquivo Excel formatado que contém todos os dados de modelo necessários (consulte as [instruções para formatar corretamente o arquivo](#formatting-your-template-data-with-excel)).
5. Se não houver problemas no arquivo, o nome do arquivo carregado será exibido. Selecione **Avançar** para continuar. (Se você precisar alterar o arquivo, selecione **carregar um arquivo diferente**).
    - Se houver um erro com seu arquivo, uma mensagem de erro na parte superior explicará o que há de errado. Você precisará corrigir o arquivo e carregá-lo novamente. Os erros ocorrerão se sua planilha estiver formatada incorretamente ou se houver informações inválidas em determinados campos (consulte novamente as [instruções de formatação](#formatting-your-template-data-with-excel)).  
    
6. A tela **revisão e término** mostra o número de ações e controles de aperfeiçoamento e a pontuação máxima do modelo. Quando estiver pronto para aprovar, selecione **criar modelo.** (Se você precisar fazer alterações, selecione **voltar**).
7. A última tela confirma que um novo modelo foi criado. Selecione **concluído** para sair do assistente.
8. Você chegará à página de detalhes de seu novo modelo, onde você pode [criar sua avaliação](compliance-manager-assessments.md#create-your-own-custom-assessment).

## <a name="formatting-your-template-data-with-excel"></a>Formatando os dados do modelo com o Excel

A planilha do Excel usada para criar modelos contém quatro guias, três das quais são necessárias:

1. [Modelo](#template-tab) (obrigatório)
2. [ControlFamily](#controlfamily-tab) (obrigatório)
3. [Ações](#actions-tab) (obrigatório)
4. [Dimensões](#dimensions-tab) (opcional)

Ao preencher sua planilha com dados de modelo, a planilha  **deve incluir as guias na ordem listada acima**, caso contrário, seus dados não serão importados com êxito para um modelo.

##### <a name="template-tab"></a>Guia modelo

A guia **modelo** é necessária. As informações nesta guia fornecem metadados sobre o modelo. Há quatro colunas obrigatórias. As colunas devem reter a ordem na planilha do Excel, conforme listado abaixo. Você pode adicionar sua própria coluna **depois** das quatro colunas para fornecer suas próprias dimensões. Se você fizer isso, adicione-os à guia **dimensões** usando as [instruções abaixo](#dimensions-tab).

- **título**: Este é o título do seu modelo, que deve ser exclusivo. Não é possível compartilhar um nome com outro modelo que você tem no Gerenciador de conformidade, incluindo seus próprios modelos ou um modelo do Gerenciador de conformidade.

- **produto**: esta é uma dimensão obrigatória. Listar o produto associado ao modelo.

- **certificação**: esta é a regulamentação que você está usando para o modelo.

- **Inscopeservices**: estes são os serviços do produto que esta avaliação resolve (por exemplo, se você listou o Office 365 como produto, o Microsoft Teams pode ser um serviço no escopo). Você pode listar vários serviços separados por dois pontos e vírgulas.

> [!NOTE]
> Os dados inseridos no **produto** e nas células de **certificação** não podem ser editados após a importação da planilha para criar ou personalizar um modelo. Além disso, um grupo não pode conter duas avaliações que tenham a mesma combinação de **produto/certificação** . Você pode ter vários modelos com a mesma combinação de produto/certificação.

##### <a name="controlfamily-tab"></a>Guia ControlFamily

A guia **ControlFamily** é necessária.  As colunas obrigatórias nesta guia, que devem seguir a ordem fornecida na planilha de exemplo, são:

- **ControlName**: Este é o nome do controle da certificação, padrão ou regulamentação, que normalmente é um tipo de ID. Os nomes de controle devem ser exclusivos em um modelo. Não é possível ter vários controles com o mesmo nome na planilha.

- **controlFamily**: forneça uma palavra ou frase para o controlFamily, que identifica um amplo agrupamento de controles. Um controlFamily não precisa ser exclusivo; Ele pode ser listado mais de uma vez em uma planilha. O mesmo controlFamily também pode ser listado em vários modelos, embora não tenham nenhuma relação entre si. Cada controlFamily deve ser mapeado para pelo menos um controle.

- **controlTitle**: forneça um título para o controle. Enquanto o ControlName é um código de referência, o título é um formato Rich Text geralmente visto nas regulamentações.

- **controlDescription**: forneça uma descrição do controle.

- **controlActionTitle**: Este é o título de uma ação que você deseja relacionar a este controle. Você pode adicionar várias ações separando por dois pontos e vírgulas sem espaço entre elas. Todos os controles que você lista deve incluir pelo menos uma ação, e a ação deve existir (o que significa que você pode listar uma ação listada na guia **ações** da mesma planilha, uma ação que existe em um modelo diferente ou uma ação criada pela Microsoft). Diferentes controles podem fazer referência à mesma ação.

##### <a name="actions-tab"></a>Guia ações

A guia **ações** é necessária.  Ele designa as ações de melhoria gerenciadas pela sua organização e não as da Microsoft, que já existem no gerente de conformidade. As colunas necessárias para esta guia, que devem seguir a ordem fornecida na planilha de exemplo, são:

- **actionTitle**: Este é o título da ação e é um campo obrigatório. O título fornecido deve ser exclusivo. **Importante**: se você se referir a uma ação que já existe (como em outro modelo) e modificar qualquer um de seus elementos nas colunas subsequentes, essas alterações serão propagadas para a mesma ação em outros modelos.

- **ImplementationType**: neste campo obrigatório, liste um dos três tipos de implementação abaixo:
    - **Operações operacionais** implementadas por pessoas e processos para proteger a confidencialidade, integridade e disponibilidade de sistemas organizacionais, ativos, dados e funcionários (exemplo: reconhecimento de segurança e treinamento)
    - **Técnicas** -ações concluídas por meio do uso de tecnologia e mecanismos contidos nos componentes de hardware, software ou firmware do sistema de informações para proteger a confidencialidade, integridade e disponibilidade de sistemas e dados organizacionais (exemplo: autenticação multifator)
    - **Documentação** -ações implementadas por meio de políticas e procedimentos documentados que estabelecem e definem os controles necessários para proteger a confidencialidade, integridade e disponibilidade de sistemas organizacionais, ativos, dados e funcionários (exemplo: uma política de segurança de informações)

- **actionScore**: neste campo obrigatório, forneça um valor numérico de Pontuação para a ação. Deve ser um número inteiro variando de 1 a 99; Ele não pode ser 0, nulo ou vazio. Quanto maior o número, maior o valor para melhorar a postura de conformidade. A imagem abaixo demonstra como o Gerenciador de conformidade classifica os controles:

![Valores de pontos de controles do Gerenciador de conformidade](../media/compliance-score-action-scoring.png "Valores de pontos de controles do Gerenciador de conformidade")

- **actionDescriptionTitle**: Este é o título da descrição e é obrigatório. Este título de descrição permite que você tenha a mesma ação em vários modelos e, em seguida, uma descrição diferente em cada modelo.  Este campo ajuda você a esclarecer em qual modelo a descrição faz referência. Na maioria dos casos, é possível colocar o nome do modelo que você está criando nesse campo.

- **actionDescription**: forneça uma descrição da ação. Você pode aplicar formatação, como texto em negrito e hiperlinks. Este é um campo obrigatório.

- **Dimension-propósito de ação**: Este é um campo opcional. Se você incluir, o cabeçalho deve incluir o prefixo "Dimension-". Todas as dimensões incluídas aqui serão usadas como filtros no gerente de conformidade e serão exibidas na página de detalhes de ações de melhoria no Gerenciador de conformidade.

##### <a name="dimensions-tab"></a>Guia dimensões

A guia **dimensões** é opcional. No entanto, se você fizer referência a uma dimensão em outro lugar, precisará especificá-la aqui se ela não existir em um modelo já criado ou em um modelo do Microsoft. As colunas desta guia estão listadas abaixo:

- **dimensionKey**: list como "Product", "certifications", "Action purpose"
- **dimensionvalue**: exemplos: Office 365, HIPPA, preventivo, detecção

Você pode exibir as dimensões existentes indo para o **Gerenciamento de locatários** e selecionando a guia **dimensões** . Além disso, sempre que você exportar um modelo existente, a planilha exportada terá a guia **dimensões** , que lista todas as dimensões usadas no modelo.

## <a name="modify-a-template"></a>Modificar um modelo

Talvez você queira modificar um modelo já criado, como adicionar ou adicionar ou remover ações de aperfeiçoamento. O processo é semelhante ao processo de criação de modelo no qual você carregará o arquivo Excel formatado com seus dados de modelo.

No entanto, há detalhes específicos que devem ser cientes à medida que você formata o arquivo com as alterações nos dados de modelo existentes. **Recomendamos que você leia estas instruções cuidadosamente para garantir que não substitua nenhum dado existente que você deseja manter.**

### <a name="template-modification-process-steps"></a>Etapas do processo de modificação de modelo

Para modificar um modelo, siga as etapas abaixo:

1. Na página **modelos de avaliação** , selecione o modelo que você deseja modificar, que exibirá a página de detalhes.
2. Selecione **exportar para o Excel**. Um arquivo do Excel com todos os seus dados de modelo será baixado. Salve o arquivo no computador local.
3. Faça as alterações de modelo [modificando o arquivo do Excel usando as instruções abaixo](#formatting-your-excel-file-to-modify-a-template).
4. Quando você terminar de fazer alterações no arquivo do Excel, salve o arquivo.
5. Na página detalhes do seu modelo, selecione **Modificar modelo** para iniciar o assistente de modificação. 
6. Na tela **carregar arquivo** , selecione **procurar** para localizar e carregar seu arquivo do Excel.
7. Se não houver problemas com o arquivo, a tela seguinte mostrará o nome do arquivo carregado. Selecione **Avançar** para continuar (se precisar alterar o arquivo, selecione **carregar um arquivo diferente**).
    - Se houver um problema com seu arquivo, uma mensagem de erro na parte superior explicará o que há de errado. Você precisará corrigir o arquivo e carregá-lo novamente. Os erros ocorrerão se sua planilha estiver formatada incorretamente ou se houver informações inválidas em determinados campos.

8. A tela **revisão e término** mostra o número de ações e controles de aperfeiçoamento e a pontuação máxima do modelo. Quando estiver pronto para aprovar, selecione **Avançar**.
9. A última tela confirma que o modelo foi modificado. Selecione **concluído** para sair do assistente.

Agora, o modelo incluirá as alterações feitas. Todas as avaliações que usam esse modelo modificado agora mostrarão atualizações pendentes e você precisará aceitar as atualizações para as avaliações para refletir as alterações feitas no modelo. Saiba mais sobre [atualizações de avaliações](compliance-manager-assessments.md#accepting-updates-to-assessments).

> [!NOTE]
> Se você usar o Gerenciador de conformidade em um idioma diferente do inglês, observará que parte do texto aparece em inglês ao exportar um modelo para o Excel. Os títulos de ações (as ações de aperfeiçoamento e as ações da Microsoft) devem estar em inglês para serem reconhecidos pelos controles. Se você fizer alterações em um título de ação, certifique-se de escrevê-la em inglês para que o arquivo seja importado corretamente.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Formatando o arquivo do Excel para modificar um modelo

Vá para uma seção abaixo para encontrar rapidamente as instruções de que você precisa:

- [Editar os atributos de modelo principal](#edit-the-main-template-attributes)
- [Adicionar uma ação de melhoria](#add-an-improvement-action)
- [Editar as informações de uma ação de aprimoramento](#edit-an-improvement-actions-information)
- [Alterar o nome de uma ação de aperfeiçoamento](#change-an-improvement-actions-name)
- [Remover uma ação de melhoria](#remove-an-improvement-action)
- [Remover um controle](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Editar os atributos de modelo principal

Na guia **modelos** , é possível editar qualquer coisa na coluna **título** , a coluna **inscopeservices** , e em qualquer outra coluna que você possa ter adicionado. No entanto, não é possível editar nada nas colunas **produto** ou **certificação** .

#### <a name="add-an-improvement-action"></a>Adicionar uma ação de melhoria

1. Vá para a guia **ações** . Adicione suas informações nos campos obrigatórios da primeira linha vazia abaixo de suas ações existentes.
2. Vá para a guia **ControlFamily** . Localize a linha que contém o controle para o qual sua ação de aprimoramento é mapeada. Adicione sua nova ação à coluna **controlActionTitle** nessa linha (Lembre-se de separar várias ações nesse campo com dois pontos e vírgulas, sem espaço entre elas).
3. Salve sua planilha.

#### <a name="edit-an-improvement-actions-information"></a>Editar as informações de uma ação de aprimoramento

Você pode alterar as informações de ações de melhoria *, exceto o título*. Você pode editar qualquer célula das colunas B em diante e, quando importar o arquivo de volta para o modelo, as ações de aperfeiçoamento nesse modelo agora conterá os dados atualizados.

Não é possível editar o **actionTitle** (coluna A) porque, se você fizer isso, o Gerenciador de conformidade considera que isso seja uma nova ação de aprimoramento. Se você quiser alterar o nome de uma ação de aprimoramento, consulte as instruções imediatamente abaixo.

#### <a name="change-an-improvement-actions-name"></a>Alterar o nome de uma ação de aperfeiçoamento

Se quiser alterar o nome de uma ação de aperfeiçoamento, você terá que designar explicitamente na planilha que está substituindo um nome existente por um novo nome. Siga estas etapas:

1. Na guia **ações** da planilha, adicione uma nova coluna à planilha após A coluna a.
2. Nesta nova coluna, que agora é a coluna B, coloque o cabeçalho na linha 1: **oldActionTitle**.
3. Copie o conteúdo da coluna A e cole-o na coluna B. Isso coloca os títulos de ações de melhorias existentes, que são o que você deseja alterar, para a coluna B.
4. Na coluna A, **actionTitle**, exclua o nome antigo e substitua-o pelo novo nome da ação de aprimoramento.

Observe que os títulos de ação, tanto para suas ações aprimoradas quanto para ações da Microsoft, devem ser escritos em inglês para serem reconhecidos quando mencionados nos controles.

#### <a name="remove-an-improvement-action"></a>Remover uma ação de melhoria

Excluir uma ação de melhoria de uma linha em uma **planilha não** remove a ação do modelo que você está editando. Em vez disso, siga o processo abaixo:

1. Na guia **ações** , insira uma nova coluna como A coluna a **e colocar na linha de cabeçalho** , que é a linha número um.
2. Na linha da ação de aprimoramento que você deseja remover, coloque **delete** na coluna A para essa linha.
3. Certifique-se de que essa ação de aprimoramento não é mais referenciada por um controle. Vá para a guia **ControlFamily** e procure o título da ação de aprimoramento na coluna F, que é **controlActionTitle**.
4. Quando você encontrar sua ação de aprimoramento listada na coluna **controlActionTitle** , exclua-a.
5. Salve sua planilha.

Quando você importar sua planilha de volta para o modelo, sua ação será removida do modelo. Remover uma ação de um modelo não remove completamente a ação. Essa ação ainda pode ser referenciada por outro modelo.

Se você estiver removendo a última ação de aprimoramento que um controle faz referência, será necessário remover o controle.

#### <a name="remove-a-control"></a>Remover um controle

Para remover um controle, siga o mesmo processo para remover uma ação de melhoria conforme descrito acima. Na guia **ControlFamily** , adicione uma coluna de **operação** e coloque **delete** ao lado do controle que você deseja remover.

## <a name="export-a-template"></a>Exportar um modelo

É possível exportar um arquivo do Excel que contenha todos os dados de um modelo. Você precisará exportar um modelo para modificar o modelo, pois será o arquivo do Excel editado e carregado no [processo de modificação](#modify-a-template).

Para exportar o modelo, vá para a página de detalhes do modelo e selecione o botão **exportar para o Excel** .

Observe que ao exportar um modelo estendido de um modelo do Gerenciador de conformidade, o arquivo exportado só conterá os atributos adicionados ao modelo. O arquivo exportado não incluirá os dados de modelo originais fornecidos pela Microsoft. Para obter esse relatório, consulte as instruções para [exportar um relatório de avaliação](compliance-manager-assessments.md#export-an-assessment-report).