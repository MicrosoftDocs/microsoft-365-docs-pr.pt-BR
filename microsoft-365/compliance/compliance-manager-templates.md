---
title: Trabalhar com modelos de avaliação no Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
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
ms.openlocfilehash: 2d20fa69345f2ff2624252972cb0e017e401f0dd
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149125"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Trabalhar com modelos de avaliação no Gerenciador de Conformidade

**Neste artigo:** Entenda **como os modelos funcionam** e como **gerenciá-los** na página de modelos de avaliação. Obter instruções para **criar** novos **modelos,** estender e modificar modelos existentes, **formatar** seus dados de modelo com Excel e exportar relatórios de **modelo.** 

> [!IMPORTANT]
> Os modelos de avaliação que estão disponíveis para sua organização dependem do contrato de licenciamento. [Revise os detalhes](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="templates-overview"></a>Visão geral dos modelos

Um modelo é uma estrutura de controles para criar uma avaliação no Gerenciador de Conformidade. Nosso conjunto abrangente de modelos pode ajudar sua organização a cumprir requisitos nacionais, regionais e específicos do setor que regem a coleta e o uso de dados. Nos referimos a modelos com o mesmo nome de sua certificação ou regulamentação subjacente, como o modelo RGPD da UE e o modelo ISO/IEC 27701:2019.

## <a name="template-availability-and-licensing"></a>Disponibilidade e licenciamento do modelo

Os modelos disponíveis para uso são baseados no contrato de licenciamento da sua organização ([exibir detalhes de licenciamento).](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager) Há duas categorias de modelos: incluídas e premium.

#### <a name="included-and-premium-templates"></a>Modelos premium e incluídos

1. **Modelos incluídos são concedidos** pela sua licença e abrangem os requisitos e regulamentos principais.
2. **Premium modelos podem** ser comprados para expandir sua biblioteca e abranger necessidades específicas. Depois de comprado, você pode criar o máximo de avaliações de um modelo conforme necessário. [Saiba como comprar modelos premium.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

Exibir a [lista completa de modelos](compliance-manager-templates-list.md).

#### <a name="active-and-inactive-templates"></a>Modelos ativos e inativos

Os modelos exibirão um status de ativação como ativo ou inativo:

- Um modelo é considerado **ativo depois** que você cria uma avaliação a partir desse modelo.
- Um modelo é considerado **inativo** se sua organização não o estiver usando para uma avaliação.

Quando você compra um modelo premium e cria uma avaliação dele, esse modelo fica ativo por um ano. Sua compra será renovada automaticamente, a menos que você cancele.

Você também pode experimentar modelos premium em uma base de avaliação. As licenças de avaliação são válidas para até 25 modelos por 30 dias. Quando a avaliação começar, os modelos deverão ficar disponíveis em seu locatário dentro de 48 horas. As tentativas podem ser ativadas por meio do Centro de administração do Microsoft 365.

#### <a name="activated-templates-counter"></a>Contador de modelos ativados

Sua página de avaliação e modelos de avaliação têm um contador **de modelos ativados** perto da parte superior. O contador exibe o número de modelos em uso fora do número que você está qualificado a usar de acordo com seu contrato de licenciamento. O uso do modelo é contado no nível de certificação.

Por exemplo, se o contador mostrar 2/5, isso significa que sua organização ativou 2 modelos dos 5 que estão disponíveis para uso.

Se o contador mostrar 5/2, isso indica que sua organização excede seus limites e precisa comprar 3 dos modelos premium em uso.

Para obter mais detalhes, consulte Diretrizes de [licenciamento do Gerenciador de Conformidade.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

## <a name="view-and-manage-templates"></a>Exibir e gerenciar modelos

A página modelos de avaliação no Gerenciador de Conformidade exibe uma lista de modelos e detalhes importantes sobre eles. A lista inclui modelos fornecidos pelo Gerenciador de Conformidade, bem como todos os modelos que sua organização modificou ou criou. Você pode aplicar filtros para encontrar um modelo com base na certificação, escopo do produto, país, setor, quem o criou e se o modelo está habilitado para criação de avaliação.

Selecione um modelo em sua linha para trazer sua página de detalhes. Esta página contém uma descrição do modelo e informações adicionais sobre detalhes de certificação, escopo e controles. Nesta página, você pode selecionar os botões apropriados para criar uma avaliação, exportar os dados do modelo para Excel ou modificar o modelo.

## <a name="format-template-data-with-excel"></a>Formatar dados de modelo com Excel

A Excel ([baixar](https://go.microsoft.com/fwlink/?linkid=2124865)um exemplo ) usada para criar ou modificar modelos tem um formato e esquema específicos que devem ser usados para importar corretamente para o Gerenciador de Conformidade. Ele contém quatro guias, três das quais são necessárias:

1. [Modelo](#template-tab) (obrigatório)
2. [ControlFamily](#controlfamily-tab) (obrigatório)
3. [Ações](#actions-tab) (necessárias)
4. [Dimensões](#dimensions-tab) (opcional)

Ao preencher sua planilha com dados de modelo, a planilha deve incluir as guias na ordem listada acima , caso contrário, seus dados não serão **importados** com êxito para um modelo.

##### <a name="template-tab"></a>Guia Modelo

A **guia** Modelo é necessária. As informações nesta guia fornece metadados sobre o modelo. Há quatro colunas necessárias. As colunas devem manter a ordem na Excel conforme listado abaixo. Você pode adicionar sua própria coluna **após** as quatro colunas para fornecer suas próprias dimensões. Se você fizer isso, certifique-se de adicioná-los à **guia** Dimensões.

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
    - **Técnico** - ações concluídas usando tecnologia e mecanismos contidos nos componentes de hardware, software ou firmware do sistema de informações para proteger a confidencialidade, a integridade e a disponibilidade de sistemas organizacionais e dados (exemplo: autenticação multifatores)
    - **Documentação** - ações implementadas por meio de políticas e procedimentos documentados que estabelecem e definem os controles necessários para proteger a confidencialidade, a integridade e a disponibilidade de sistemas organizacionais, ativos, dados e funcionários (exemplo: uma política de segurança de informações)

- **actionScore**: Neste campo necessário, forneça um valor de pontuação numérica para sua ação. O valor deve ser um número inteiro que varia de 1 a 99; não pode ser 0, nulo ou em branco. Quanto maior o número, maior o valor para melhorar a postura de conformidade. A imagem a seguir demonstra como o Gerenciador de Conformidade pontua controles:

![O Gerenciador de Conformidade controla valores de pontos](../media/compliance-score-action-scoring.png "O Gerenciador de Conformidade controla valores de pontos")

- **actionDescriptionTitle**: este é o título da descrição e é obrigatório. Este título de descrição permite que você tenha a mesma ação em vários modelos e superfície uma descrição diferente em cada modelo.  Este campo ajuda você a esclarecer qual modelo a descrição está fazendo referência. Na maioria dos casos, você pode colocar o nome do modelo que está criando neste campo.

- **actionDescription**: Forneça uma descrição da ação. Você pode aplicar formatação como texto em negrito e hiperlinks. Este campo é obrigatório.

- **dimension-Action Purpose**: Este é um campo opcional. Se você incluí-lo, o header deverá incluir o prefixo "dimension-". Todas as dimensões que você incluir aqui serão usadas como filtros no Gerenciador de Conformidade e aparecerão na página detalhes das ações de melhoria no Gerenciador de Conformidade.

##### <a name="dimensions-tab"></a>Guia Dimensões

A **guia Dimensões** é opcional. No entanto, se você fizer referência a uma dimensão em outro lugar, precisará especificá-la aqui se ela não existir em um modelo que você já criou ou em um modelo da Microsoft. As colunas desta guia estão listadas abaixo:

- **dimensionKey**: lista como "produto", "certificações", "finalidade de ação"
- **dimensionValue**: exemplos: Office 365, HIPPA, Preventivo, Detetive

Ao exportar um modelo existente, a planilha exportada terá a guia **Dimensões,** que lista todas as dimensões usadas no modelo.

## <a name="create-an-assessment-template"></a>Criar um modelo de avaliação

Para criar seu próprio novo modelo para avaliações personalizadas, você usará sua planilha de Excel especialmente formatada para montar os dados de controle necessários. Depois de concluir a planilha, você a importará para o Gerenciador de Conformidade.

#### <a name="required-roles"></a>Funções necessárias

Somente os usuários que têm uma função de Administrador Global ou Administração do Gerenciador de Conformidade podem criar e modificar modelos. Saiba mais sobre [funções e permissões.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

### <a name="create-new-template-in-compliance-manager"></a>Criar novo modelo no Gerenciador de Conformidade

1. Vá para a página **modelos de avaliação** no Gerenciador de Conformidade.
2. Selecione **Criar novo modelo**. Um assistente de criação de modelo será aberto.
3. Escolha o tipo de modelo que você deseja criar. Nesse caso, selecione **Criar um modelo personalizado** e selecione **Próximo**.
4. Na tela **Upload arquivo,** selecione **Procurar** para encontrar e carregar seu arquivo Excel formatado contendo todos os dados de modelo necessários.
5. Se não houver problemas com seu arquivo, o nome do arquivo carregado será exibido. Selecione **Avançar** para continuar. (Se você precisar alterar o arquivo, selecione **Upload um arquivo diferente**).
    - Se houver um erro com seu arquivo, uma mensagem de erro na parte superior explica o que está errado. Você precisará corrigir seu arquivo e carregar novamente. Os erros resultarão se sua planilha for formatada incorretamente ou se houver informações inválidas em determinados campos.
6. A **tela Revisar e concluir** mostra o número de ações de melhoria e controles e a pontuação máxima do modelo. Quando estiver pronto para aprovar, selecione **Criar modelo.** (Se precisar fazer alterações, selecione **Voltar**.)
7. A última tela confirma que um novo modelo foi criado. Selecione **Feito** para sair do assistente.
8. Você chegará à página de detalhes do novo modelo, onde poderá [criar sua avaliação.](compliance-manager-assessments.md#create-assessments)

## <a name="extend-an-assessment-template"></a>Estender um modelo de avaliação

O Gerenciador de Conformidade oferece a opção de adicionar seus próprios controles e ações de melhoria a um modelo fornecido pela Microsoft existente. Esse processo é chamado de extensão de um modelo da Microsoft. Quando você estende um modelo, ele ainda pode receber atualizações lançadas pela Microsoft, o que pode acontecer quando houver alterações na regulamentação ou produto relacionado (consulte [Accept updates to assessments](compliance-manager-assessments.md#accept-updates-to-assessments)).

Para se preparar, você precisará montar uma planilha de Excel especialmente formatada para importar os dados de modelo necessários. Os arquivos Excel seguem o mesmo formato geral descrito acima, mas há requisitos especiais para extensões. Confira estes pontos adicionais para ajudar a evitar erros:

- Sua planilha deve conter apenas as ações e controles que você deseja adicionar à avaliação.
- A planilha não pode conter nenhum dos controles ou ações que já existem na avaliação que você deseja modificar.
- Considere incluir "extensão" no título do modelo, por exemplo, "RGPD – extensão [nome da empresa]". Isso facilita a identificação na lista na página modelos de avaliação como **distintas** do modelo padrão fornecido pela Microsoft ou de um modelo personalizado com um nome semelhante.

Depois de formatar sua planilha, siga as etapas abaixo.

1. Vá para a **página Modelos de Avaliação** e selecione **Criar novo modelo**. Um assistente de criação de modelo será aberto.

2. Escolha o tipo de modelo que você deseja criar. Nesse caso, selecione **Estender um modelo da Microsoft** e selecione Modelo da **Microsoft.**

3. Um painel de destaque de seleção de modelo aparece no lado direito da tela, mostrando uma lista de todos os modelos e seu status de ativo ou inativo. O **contador de modelos ativados** mostra quantos modelos estão em uso no momento do número total disponível para uso. Se você estiver acima do limite, uma barra de mensagens fornecerá aviso.

4. Um painel de sobrevoo de seleção de modelo aparece no lado direito da tela. Use **a Pesquisa** para aplicar filtros para localizar o modelo que você deseja

5. Depois de localizar seu modelo, selecione o botão de opção à esquerda do nome e selecione **Salvar**.

6. A próxima tela mostra o modelo selecionado. Se estiver correto, selecione **Next**. (Se estiver incorreto, escolha **Selecionar um modelo diferente** para escolher novamente.)

7. Na tela **Upload arquivo,** selecione **Procurar** para encontrar e carregar seu arquivo Excel formatado contendo todos os dados de modelo necessários.

8. Se não houver problemas com seu arquivo, a próxima tela mostrará o nome do arquivo carregado. Selecione **Próximo** para continuar (se você precisar alterar o arquivo, selecione **Upload um arquivo diferente**).

    - Se houver um problema com seu arquivo, uma mensagem de erro na parte superior explica o que há de errado. Você precisará corrigir e carregar seu arquivo. Os erros resultarão se sua planilha for formatada incorretamente ou se houver informações inválidas em determinados campos.

9. A **tela Revisar e concluir** mostra o número de ações de melhoria e controles e a pontuação máxima do modelo. Quando estiver pronto para aprovar, selecione **Próximo**. (Se você precisar fazer alterações, selecione **Upload um arquivo diferente**.)

10. A última tela confirma que um novo modelo foi criado. Selecione **Feito** para sair do assistente.

11. Você chegará à página de detalhes do novo modelo. A partir daqui, você pode criar sua avaliação selecionando **Criar avaliação**. Para obter orientações, consulte [Build and manage assessments](compliance-manager-assessments.md#create-assessments).

## <a name="modify-a-template"></a>Modificar um modelo

Talvez você queira modificar um modelo que já criou, como adicionar controles ou adicionar ou remover ações de melhoria. O processo é semelhante ao processo de criação de modelo, em que você carregará um arquivo Excel formatado com os dados do modelo.

No entanto, há detalhes a serem cientes à medida que você formatar seu arquivo com alterações nos dados de modelo existentes. **Recomendamos que você revise essas instruções cuidadosamente para garantir que você não sobrescreva quaisquer dados existentes que você deseja reter.**

### <a name="format-your-excel-file-to-modify-an-existing-template"></a>Formatar seu Excel para modificar um modelo existente

Na página **modelos de avaliação,** selecione o modelo que você deseja modificar, o que   mostrará sua página de detalhes. Em seguida, **selecione Exportar para Excel**. Um Excel com todos os dados do modelo será baixado. Salve o arquivo no computador local.

Para trabalhar com esse arquivo, pule para uma seção abaixo para encontrar rapidamente as instruções de que você precisa:

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

### <a name="modify-template-info-in-compliance-manager"></a>Modificar informações do modelo no Gerenciador de Conformidade

Depois que seu Excel arquivo for concluído e salvo, siga estas etapas.

1. Abra a página do modelo de avaliação novamente e selecione seu modelo. Na página de detalhes do modelo, selecione **Modificar modelo** para iniciar o assistente de modificação.
2. Na tela **Upload arquivo,** selecione **Procurar** para encontrar e carregar seu arquivo Excel arquivo.
3. Se não houver problemas com seu arquivo, a próxima tela mostrará o nome do arquivo carregado. Selecione **Próximo** para continuar (se você precisar alterar o arquivo, selecione **Upload um arquivo diferente**).
    - Se houver um problema com seu arquivo, uma mensagem de erro na parte superior explica o que há de errado. Você precisará corrigir seu arquivo e carregar novamente. Os erros resultarão se sua planilha for formatada incorretamente ou se houver informações inválidas em determinados campos.

4. A **tela Revisar e concluir** mostra o número de ações de melhoria e controles e a pontuação máxima do modelo. Quando estiver pronto para aprovar, selecione **Próximo**.
5. A última tela confirma que o modelo foi modificado. Selecione **Feito** para sair do assistente.

Seu modelo agora incluirá as alterações feitas. Todas as avaliações que usam esse modelo modificado agora mostrarão atualizações pendentes e você precisará aceitar as atualizações das avaliações para refletir as alterações feitas no modelo. Saiba mais sobre [atualizações para avaliações.](compliance-manager-assessments.md#accept-updates-to-assessments)

> [!NOTE]
> Se você usar o Gerenciador de Conformidade em um idioma diferente do inglês, você notará que algum texto aparece em inglês ao exportar um modelo para Excel. Os títulos das ações (suas ações de melhoria e ações da Microsoft) devem estar em inglês para serem reconhecidos pelos controles. Se você fizer alterações em um título de ação, certifique-se de escrevê-lo em inglês para que o arquivo importe corretamente.

## <a name="export-a-template"></a>Exportar um modelo

Você pode exportar um arquivo Excel que contém todos os dados de um modelo. Você precisará exportar um modelo para modificá-lo, pois esse será o arquivo Excel que você editar e carregar no processo [de modificação.](#modify-a-template)

Para exportar seu modelo, vá até a página de detalhes do modelo e selecione **o botão Exportar para Excel.**

Observe que, ao exportar um modelo estendido de um modelo do Gerenciador de Conformidade, o arquivo exportado conterá apenas os atributos adicionados ao modelo. O arquivo exportado não incluirá os dados do modelo original fornecidos pela Microsoft. Para obter esse relatório, consulte as instruções para [exportar um relatório de avaliação.](compliance-manager-assessments.md#export-an-assessment-report)
