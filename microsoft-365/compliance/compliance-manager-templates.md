---
title: Trabalhar com modelos de avaliação no Microsoft Compliance Manager
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
description: Entenda como usar e gerenciar modelos para criar avaliações no Microsoft Compliance Manager. Crie e modifique modelos usando um arquivo Excel formatado.
ms.openlocfilehash: ac5fe5f0a62c3b20021a9829499d8cec9339f72a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499018"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Trabalhar com modelos de avaliação no Gerenciador de Conformidade

**Neste artigo:** Entenda **como os modelos funcionam** e como **gerenciá-los** na página de modelos de avaliação. Obter instruções para **criar novos** **modelos,** modificar modelos existentes, **formatar** seus dados de modelo com Excel e exportar relatórios de **modelo.**

> [!IMPORTANT]
> Os modelos de avaliação disponíveis para sua organização dependem do contrato de licenciamento. [Revise os detalhes](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="templates-overview"></a>Visão geral dos modelos

Um modelo é uma estrutura de controles para criar uma avaliação no Gerenciador de Conformidade. Nosso conjunto abrangente de modelos pode ajudar sua organização a cumprir requisitos nacionais, regionais e específicos do setor que regem a coleta e o uso de dados. Nos referimos a modelos com o mesmo nome de sua certificação ou regulamentação subjacente, como o modelo RGPD da UE e o modelo ISO 27001:2013.

 Exibir a [lista completa de modelos](compliance-manager-templates-list.md).

## <a name="template-types-included-and-premium-active-and-inactive"></a>Tipos de modelo: incluídos e premium, ativos e inativos

#### <a name="included-and-premium-templates"></a>Modelos premium e incluídos

Os modelos disponíveis para uso são baseados no contrato de licenciamento da sua organização ([exibir detalhes de licenciamento).](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager) Há duas categorias de modelos: incluídas e premium.

1. **Modelos incluídos** estão disponíveis para uso como parte do contrato de licenciamento da sua organização.
2. **Premium modelos devem** ser comprados para criar avaliações a partir deles. Depois de comprado, você pode criar o máximo de avaliações de um modelo conforme necessário. [Saiba como comprar modelos premium.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

#### <a name="active-and-inactive-templates"></a>Modelos ativos e inativos

Os modelos exibirão um status de ativação como ativo ou inativo:

- Um modelo é considerado **ativo depois** que você cria uma avaliação a partir desse modelo.
- Um modelo é considerado **inativo** se sua organização não o estiver usando para uma avaliação.

Quando você compra um modelo premium e cria uma avaliação dele, esse modelo fica ativo por um ano. Sua compra será renovada automaticamente, a menos que você cancele a renovação.

**Contador de modelos ativados**

Sua página de avaliação e modelos de avaliação têm um contador **de modelos ativados** perto da parte superior. O contador exibe o número de modelos em uso fora do número qualificado para usar de acordo com seu contrato de licenciamento.

Por exemplo, se o contador mostrar 2/5, isso significa que sua organização ativou 2 modelos dos 5 que estão disponíveis para uso.

Se o contador mostrar 5/2, isso indica que sua organização excede seus limites e precisa comprar 3 dos modelos premium em uso.

Consulte [Diretrizes de licenciamento do Gerenciador de Conformidade](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager) para obter mais detalhes.

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Exibindo e gerenciando modelos da página modelos de avaliação

A página modelos de avaliação no Gerenciador de Conformidade exibe uma lista de modelos e detalhes importantes. A lista inclui modelos fornecidos pelo Gerenciador de Conformidade, bem como todos os modelos que sua organização modificou ou criou. Você pode aplicar filtros para encontrar um modelo com base na certificação, escopo do produto, país, setor, quem o criou e se o modelo está habilitado para criação de avaliação.

Selecione um modelo em sua linha para trazer sua página de detalhes. Esta página contém uma descrição do modelo e informações adicionais sobre detalhes de certificação, escopo e controles. Nesta página, você pode selecionar os botões apropriados para criar uma avaliação, exportar os dados do modelo para Excel ou modificar o modelo.

## <a name="creating-and-modifying-templates-overview"></a>Visão geral de criação e modificação de modelos

Para modificar um modelo existente ou para criar seu próprio novo modelo, você usará uma planilha de Excel especialmente formatada ([baixe](https://go.microsoft.com/fwlink/?linkid=2124865)um exemplo ) para montar os dados de controle necessários. Depois de concluir a planilha, você a importa para o Gerenciador de Conformidade durante o processo de criação ou modificação de um modelo.

> [!NOTE]
> A planilha tem um formato e esquema específicos que devem ser usados ou não serão importados corretamente para o Gerenciador de Conformidade. As [instruções de formatação estão](#formatting-your-template-data-with-excel) abaixo.

**Funções necessárias**

Somente os usuários que têm uma função de Administrador Global ou Administração do Gerenciador de Conformidade podem criar e modificar modelos. Saiba mais sobre [funções e permissões.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

## <a name="create-a-new-template"></a>Criar um novo modelo

Para criar seu próprio novo modelo (usado para criar avaliações personalizadas), siga as etapas a seguir.

1. Vá para a página **modelos de avaliação** no Gerenciador de Conformidade.
2. Selecione **Criar novo modelo**. Um assistente de criação de modelo será aberto.
3. Escolha o tipo de modelo que você deseja criar. Nesse caso, selecione **Criar um modelo personalizado** e selecione **Próximo**.
4. Na tela **Upload** arquivo, selecione  Procurar para encontrar e carregar seu arquivo Excel formatado contendo todos os dados de modelo necessários (consulte instruções para formatar corretamente seu [arquivo](#formatting-your-template-data-with-excel)).
5. Se não houver problemas com seu arquivo, o nome do arquivo carregado será exibido. Selecione **Avançar** para continuar. (Se você precisar alterar o arquivo, selecione **Upload um arquivo diferente**).
    - Se houver um erro com seu arquivo, uma mensagem de erro na parte superior explica o que está errado. Você precisará corrigir seu arquivo e carregar novamente. Os erros resultarão se sua planilha for formatada incorretamente ou se houver informações inválidas em determinados campos (consulte novamente as instruções [de formatação](#formatting-your-template-data-with-excel)).  
    
6. A **tela Revisar e concluir** mostra o número de ações de melhoria e controles e a pontuação máxima do modelo. Quando estiver pronto para aprovar, selecione **Criar modelo.** (Se precisar fazer alterações, selecione **Voltar**.)
7. A última tela confirma que um novo modelo foi criado. Selecione **Feito** para sair do assistente.
8. Você chegará à página de detalhes do novo modelo, onde poderá [criar sua avaliação.](compliance-manager-assessments.md#create-your-own-custom-assessment)

## <a name="formatting-your-template-data-with-excel"></a>Formatando os dados do modelo com Excel

A Excel usada para criar modelos contém quatro guias, das quais três são necessárias:

1. [Modelo](#template-tab) (obrigatório)
2. [ControlFamily](#controlfamily-tab) (obrigatório)
3. [Ações](#actions-tab) (necessárias)
4. [Dimensões](#dimensions-tab) (opcional)

Ao preencher sua planilha com dados de modelo, a planilha deve incluir as guias na ordem listada acima , caso contrário, seus dados não serão  **importados** com êxito para um modelo.

##### <a name="template-tab"></a>Guia Modelo

A **guia** Modelo é necessária. As informações nesta guia fornece metadados sobre o modelo. Há quatro colunas necessárias. As colunas devem manter a ordem na Excel conforme listado abaixo. Você pode adicionar sua própria coluna **após** as quatro colunas para fornecer suas próprias dimensões. Se você fizer isso, certifique-se de adicioná-los à guia **Dimensões** usando as [instruções abaixo](#dimensions-tab).

- **title**: Este é o título do seu modelo, que deve ser exclusivo. Ele não pode compartilhar um nome com outro modelo que você tenha no Gerenciador de Conformidade, incluindo seus próprios modelos ou um modelo do Gerenciador de Conformidade.

- **product**: Esta é uma dimensão necessária. Listar o produto associado ao modelo.

- **certification**: Esta é a regulamentação que você está usando para o modelo.

- **inScopeServices**: esses são os serviços dentro do produto que essa avaliação aborda (por exemplo, se você listou Office 365 como o produto, Microsoft Teams poderia ser um serviço no escopo). Você pode listar vários serviços separados por dois pontos e vírgulas.

> [!NOTE]
> Os dados inseridos nas  células **de** produto e certificação não podem ser editados depois de importar a planilha para criar ou personalizar um modelo. Além disso, um grupo não pode conter duas avaliações que tenham a mesma **combinação de produto/certificação.** Você pode ter vários modelos com a mesma combinação de produto/certificação.

##### <a name="controlfamily-tab"></a>Guia ControlFamily

A **guia ControlFamily** é necessária.  As colunas necessárias nesta guia, que devem seguir a ordem fornecida na planilha de exemplo, são:

- **controlName**: Esse é o nome de controle da certificação, padrão ou regulamentação, que normalmente é algum tipo de ID. Os nomes de controle devem ser exclusivos em um modelo. Não é possível ter vários controles com o mesmo nome na planilha.

- **controlFamily**: forneça uma palavra ou frase para controlFamily, que identifica um amplo grupo de controles. Um controlFamily não precisa ser exclusivo; ele pode ser listado mais de uma vez em uma planilha. O mesmo controlFamily também pode ser listado em vários modelos, embora eles não tenham nenhuma relação entre si. Cada controlFamily deve ser mapeado para pelo menos um controle.

- **controlTitle**: forneça um título para o controle. Enquanto controlName é um código de referência, o título é um formato de texto rico normalmente visto nos regulamentos.

- **controlDescription**: forneça uma descrição do controle.

- **controlActionTitle**: este é o título de uma ação que você deseja se relacionar com esse controle. Você pode adicionar várias ações separando por dois pontos e vírgulas sem espaço entre eles. Cada controle que você lista deve incluir pelo menos uma ação, e a ação  deve existir (o que significa que você pode listar uma ação listada na guia Ações da mesma planilha, uma ação que existe em um modelo diferente ou uma ação criada pela Microsoft). Controles diferentes podem fazer referência à mesma ação.

##### <a name="actions-tab"></a>Guia Ações

A **guia Ações** é necessária.  Ele designa ações de melhoria gerenciadas pela sua organização e não as da Microsoft, que já existem no Gerenciador de Conformidade. As colunas necessárias para essa guia, que devem seguir a ordem fornecida na planilha de exemplo, são:

- **actionTitle**: este é o título da sua ação e é um campo obrigatório. O título que você fornece deve ser exclusivo. **Importante**: se você referenciar uma ação que já existe (como em outro modelo) e modificar qualquer um de seus elementos nas colunas subsequentes, essas alterações serão propagadas para a mesma ação em outros modelos.

- **implementationType**: Neste campo necessário, lista um dos três tipos de implementação abaixo:
    - **Operacional** - ações implementadas por pessoas e processos para proteger a confidencialidade, integridade e disponibilidade de sistemas organizacionais, ativos, dados e funcionários (exemplo: reconhecimento e treinamento de segurança)
    - **Técnico** - ações concluídas por meio do uso de tecnologia e mecanismos contidos nos componentes de hardware, software ou firmware do sistema de informações para proteger a confidencialidade, a integridade e a disponibilidade de sistemas organizacionais e dados (exemplo: autenticação multifatores)
    - **Documentação** - ações implementadas por meio de políticas e procedimentos documentados que estabelecem e definem os controles necessários para proteger a confidencialidade, a integridade e a disponibilidade de sistemas organizacionais, ativos, dados e funcionários (exemplo: uma política de segurança de informações)

- **actionScore**: Neste campo necessário, forneça um valor de pontuação numérica para sua ação. Deve ser um número inteiro que varia de 1 a 99; não pode ser 0, nulo ou em branco. Quanto maior o número, maior o valor para melhorar a postura de conformidade. A imagem a seguir demonstra como o Gerenciador de Conformidade pontua controles:

![O Gerenciador de Conformidade controla valores de pontos](../media/compliance-score-action-scoring.png "O Gerenciador de Conformidade controla valores de pontos")

- **actionDescriptionTitle**: este é o título da descrição e é obrigatório. Este título de descrição permite que você tenha a mesma ação em vários modelos e superfície uma descrição diferente em cada modelo.  Este campo ajuda você a esclarecer qual modelo a descrição está fazendo referência. Na maioria dos casos, você pode colocar o nome do modelo que está criando neste campo.

- **actionDescription**: Forneça uma descrição da ação. Você pode aplicar formatação como texto em negrito e hiperlinks. Este campo é obrigatório.

- **dimension-Action Purpose**: Este é um campo opcional. Se você incluí-lo, o header deverá incluir o prefixo "dimension-". Todas as dimensões que você incluir aqui serão usadas como filtros no Gerenciador de Conformidade e aparecerão na página detalhes das ações de melhoria no Gerenciador de Conformidade.

##### <a name="dimensions-tab"></a>Guia Dimensões

A **guia Dimensões** é opcional. No entanto, se você fizer referência a uma dimensão em outro lugar, precisará especificá-la aqui se ela não existir em um modelo que você já criou ou em um modelo da Microsoft. As colunas desta guia estão listadas abaixo:

- **dimensionKey**: lista como "produto", "certificações", "finalidade de ação"
- **dimensionValue**: exemplos: Office 365, HIPPA, Preventivo, Detetive

Você pode exibir suas dimensões existentes indo para Gerenciamento de **Locatários** e selecionando a **guia** Dimensões. Além disso, sempre que você exportar um modelo existente, a planilha exportada terá a guia **Dimensões,** que lista todas as dimensões usadas no modelo.

## <a name="modify-a-template"></a>Modificar um modelo

Talvez você queira modificar um modelo que já criou, como adicionar controles ou adicionar ou remover ações de melhoria. O processo é semelhante ao processo de criação de modelo, em que você carregará um arquivo Excel formatado com os dados do modelo.

No entanto, há detalhes específicos a serem cientes à medida que você formatar seu arquivo com alterações nos dados de modelo existentes. **Recomendamos que você revise essas instruções cuidadosamente para garantir que você não sobrescreva quaisquer dados existentes que você deseja reter.**

### <a name="template-modification-process-steps"></a>Etapas do processo de modificação do modelo

Para modificar um modelo, siga as etapas abaixo:

1. Na página **modelos de avaliação,** selecione o modelo que você deseja modificar, o que mostrará sua página de detalhes.
2. Selecione **Exportar para Excel**. Um Excel com todos os dados do modelo será baixado. Salve o arquivo no computador local.
3. Faça alterações no modelo [modificando o arquivo Excel usando as instruções abaixo](#formatting-your-excel-file-to-modify-a-template).
4. Quando terminar de fazer alterações no arquivo Excel, salve o arquivo.
5. Na página de detalhes do modelo, selecione **Modificar modelo** para iniciar o assistente de modificação. 
6. Na tela **Upload arquivo,** selecione **Procurar** para encontrar e carregar seu arquivo Excel arquivo.
7. Se não houver problemas com seu arquivo, a próxima tela mostrará o nome do arquivo carregado. Selecione **Próximo** para continuar (se você precisar alterar o arquivo, selecione **Upload um arquivo diferente**).
    - Se houver um problema com seu arquivo, uma mensagem de erro na parte superior explica o que há de errado. Você precisará corrigir seu arquivo e carregar novamente. Os erros resultarão se sua planilha for formatada incorretamente ou se houver informações inválidas em determinados campos.

8. A **tela Revisar e concluir** mostra o número de ações de melhoria e controles e a pontuação máxima do modelo. Quando estiver pronto para aprovar, selecione **Próximo**.
9. A última tela confirma que o modelo foi modificado. Selecione **Feito** para sair do assistente.

Seu modelo agora incluirá as alterações feitas. Todas as avaliações que usam esse modelo modificado agora mostrarão atualizações pendentes e você precisará aceitar as atualizações das avaliações para refletir as alterações feitas no modelo. Saiba mais sobre [atualizações para avaliações.](compliance-manager-assessments.md#accepting-updates-to-assessments)

> [!NOTE]
> Se você usar o Gerenciador de Conformidade em um idioma diferente do inglês, você notará que algum texto aparece em inglês ao exportar um modelo para Excel. Os títulos das ações (suas ações de melhoria e ações da Microsoft) devem estar em inglês para serem reconhecidos pelos controles. Se você fizer alterações em um título de ação, certifique-se de escrevê-lo em inglês para que o arquivo importe corretamente.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Formatando seu arquivo Excel para modificar um modelo

Pule para uma seção abaixo para encontrar rapidamente as instruções de que você precisa:

- [Editar os atributos principais do modelo](#edit-the-main-template-attributes)
- [Adicionar uma ação de melhoria](#add-an-improvement-action)
- [Editar informações de uma ação de melhoria](#edit-an-improvement-actions-information)
- [Alterar o nome de uma ação de melhoria](#change-an-improvement-actions-name)
- [Remover uma ação de melhoria](#remove-an-improvement-action)
- [Remover um controle](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Editar os atributos principais do modelo

Na guia **Modelos,** você pode editar qualquer coisa na coluna **título,** na coluna **inScopeServices** e em qualquer outra coluna que você possa ter adicionado. No entanto, você não pode editar nada nas colunas **de** produto **ou** certificação.

#### <a name="add-an-improvement-action"></a>Adicionar uma ação de melhoria

1. Vá para a **guia Ações.** Adicione suas informações nos campos necessários na primeira linha vazia sob suas ações existentes.
2. Vá para a **guia ControlFamily.** Encontre a linha que contém o controle para o que sua ação de melhoria mapeia. Adicione sua nova ação à coluna **controlActionTitle** nessa linha (lembre-se de separar várias ações neste campo com dois pontos e vírgulas, sem espaço entre eles).
3. Salve sua planilha.

#### <a name="edit-an-improvement-actions-information"></a>Editar informações de uma ação de melhoria

Você pode alterar as informações de qualquer ação de *melhoria, exceto seu título*. Você pode editar qualquer célula das colunas B em diante e, quando você importar o arquivo de volta para o modelo, as ações de melhoria nesse modelo agora conterão os dados atualizados.

Não é possível editar **a actionTitle** (coluna A) porque, se fizer isso, o Gerenciador de Conformidade considerará essa uma nova ação de melhoria. Se você quiser alterar o nome de uma ação de melhoria, consulte as instruções imediatamente abaixo.

#### <a name="change-an-improvement-actions-name"></a>Alterar o nome de uma ação de melhoria

Se você quiser alterar o nome de uma ação de melhoria, será preciso designar explicitamente na planilha que você está substituindo um nome existente por um novo nome. Siga estas etapas:

1. Na guia **Ações** da planilha, adicione uma nova coluna à planilha após a coluna A.
2. Nesta nova coluna, que agora é a coluna B, coloque como seu header na linha 1: **oldActionTitle**.
3. Copie o conteúdo da coluna A e colá-los na coluna B. Isso coloca seus títulos de ação de melhoria existentes, que são o que você deseja alterar, na coluna B.
4. Na coluna A, **actionTitle**, exclua o nome antigo e substitua-o pelo novo nome para sua ação de melhoria.

Observe que os títulos de ação, tanto para suas ações de melhoria quanto para ações da Microsoft, devem ser escritos em inglês para serem reconhecidos quando referenciados em controles.

#### <a name="remove-an-improvement-action"></a>Remover uma ação de melhoria

Para remover uma ação de melhoria de um modelo, você precisará removê-la de todos os controles que o referenciam. Siga as etapas abaixo para modificar sua planilha:

1. Na guia **ControlFamily,** procure o título da ação de melhoria que você deseja remover.
2. Exclua o título da ação de melhoria nas células em que ele aparece. Se a ação de melhoria for a única ação nessa linha, exclua a linha inteira (que remove o controle).
3. Na guia **Ações,** exclua a linha que contém a ação de melhoria que você está excluindo.
4. Salve sua planilha.

Quando você importar sua planilha de volta para o modelo, sua ação de melhoria será removida do modelo.

Remover uma ação de melhoria de um modelo não remove completamente a ação de melhoria do Gerenciador de Conformidade. Essa ação ainda pode ser referenciada por outro modelo.

#### <a name="remove-a-control"></a>Remover um controle

Para remover um controle, modifique sua planilha seguindo as etapas abaixo e importe sua planilha de novo:

1. Na guia **ControlFamily,** encontre o controle que você deseja remover na **coluna controlName.**
2. Exclua a linha desse controle.
    - Se esse controle excluído contiver ações de melhoria que não são referenciadas por nenhum outro controle, você precisará remover essas ações de melhoria da guia **Ações.** Caso contrário, você receberá um erro de validação.

3. Salve sua planilha.

Quando você importar sua planilha de volta para o modelo, seu controle será removido do modelo.

## <a name="export-a-template"></a>Exportar um modelo

Você pode exportar um arquivo Excel que contém todos os dados de um modelo. Você precisará exportar um modelo para modificar o modelo, pois esse será o arquivo Excel que você editar e carregar no processo [de modificação.](#modify-a-template)

Para exportar seu modelo, vá até a página de detalhes do modelo e selecione **o botão Exportar para Excel.**

Observe que, ao exportar um modelo estendido de um modelo do Gerenciador de Conformidade, o arquivo exportado conterá apenas os atributos adicionados ao modelo. O arquivo exportado não incluirá os dados do modelo original fornecidos pela Microsoft. Para obter esse relatório, consulte as instruções para [exportar um relatório de avaliação.](compliance-manager-assessments.md#export-an-assessment-report)