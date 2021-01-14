---
title: Trabalhar com modelos de avaliação no Gerenciador de Conformidade da Microsoft
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
description: Entenda como usar e gerenciar modelos para criar avaliações no Gerenciador de Conformidade da Microsoft. Criar e modificar modelos usando um arquivo do Excel formatado.
ms.openlocfilehash: 34adb79392b235152cc0e00f5b7d661e90c9005e
ms.sourcegitcommit: 00d231bf0100e843a5a93161695e87ceff9e1349
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49849605"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Trabalhar com modelos de avaliação no Gerenciador de Conformidade

**Neste artigo:** Entenda **como os modelos funcionam e** como **gerenciá-los na** página de modelos de avaliação. Get instructions for **creating** new templates, **modifying existing** templates, **formatting your template data with Excel**, and exporting template **reports**.

> [!IMPORTANT]
> Os modelos de avaliação que estão disponíveis para sua organização dependem do seu contrato de licenciamento. [Revise os detalhes.](https://go.microsoft.com/fwlink/?linkid=2132371)

## <a name="templates-overview"></a>Visão geral dos modelos

Um modelo é uma estrutura para criar uma avaliação no Gerenciador de Conformidade. Eles contêm os controles para atender aos requisitos de uma certificação usando um determinado produto. O Gerenciador de Conformidade fornece um conjunto abrangente de modelos para ajudar sua organização a atender aos requisitos nacionais, regionais e específicos do setor que regem a coleta e o uso de dados.

## <a name="list-of-pre-built-templates-for-assessments"></a>Lista de modelos pré-construídos para avaliações

O Gerenciador de Conformidade fornece modelos para criar avaliações para ajudá-lo a cumprir vários regulamentos e padrões. Exibir a [lista de modelos fornecidos](compliance-manager-templates-list.md) pelo Gerenciador de Conformidade. Novos modelos são adicionados regularmente, portanto, verifique a lista com frequência.

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Exibindo e gerenciando modelos da página de modelos de avaliação

A página de modelos de avaliação no Gerenciador de Conformidade exibe uma lista de modelos e detalhes importantes. A lista inclui modelos fornecidos pelo Gerenciador de Conformidade, bem como todos os modelos que sua organização modificou ou criou. Você pode aplicar filtros para encontrar um modelo baseado na certificação, escopo do produto, país, setor, quem o criou e se o modelo está habilitado para criação de avaliação.

Selecione um modelo de sua linha para abrir sua página de detalhes. Esta página contém uma descrição do modelo e mais informações sobre os detalhes de certificação, escopo e controles. Nesta página, você pode selecionar os botões apropriados para criar uma avaliação, exportar os dados do modelo para o Excel ou modificar o modelo.

## <a name="creating-and-modifying-templates-overview"></a>Visão geral da criação e modificação de modelos

Para modificar um modelo existente ou para criar seu próprio novo modelo, você usará uma planilha do Excel especialmente formatada[(baixe](https://go.microsoft.com/fwlink/?linkid=2124865)um exemplo) para montar os dados de controle necessários. Depois de concluir a planilha, importe-a para o Gerenciador de Conformidade durante o processo de criação ou modificação de um modelo.

> [!NOTE]
> A planilha tem um formato e um esquema específicos que devem ser usados ou não serão importados corretamente para o Gerenciador de Conformidade. As [instruções de formatação estão](#formatting-your-template-data-with-excel) abaixo.

**Funções necessárias**

Somente usuários que têm uma função de Administrador Global ou Administração do Gerenciador de Conformidade podem criar e modificar modelos. Saiba mais sobre [funções e permissões.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

## <a name="create-a-new-template"></a>Criar um novo modelo

Para criar seu próprio modelo (usado para criar avaliações personalizadas), siga as etapas abaixo.

1. Vá para a página **de modelos de avaliação** no Gerenciador de Conformidade.
2. Selecione **Criar novo modelo.** Um assistente de criação de modelo será aberto.
3. Escolha o tipo de modelo que você deseja criar. Nesse caso, selecione **Criar um modelo personalizado e,** em seguida, selecione **Próximo.**
4. Na tela **Carregar arquivo,** selecione Procurar para encontrar e carregar o arquivo formatado do Excel contendo todos os dados de modelo necessários (consulte as instruções para formatar corretamente [seu arquivo).](#formatting-your-template-data-with-excel) 
5. Se não houver problemas com seu arquivo, o nome do arquivo carregado será exibido. Selecione **Próximo** para continuar. (Se você precisar alterar o arquivo, selecione **Carregar um arquivo diferente).**
    - Se houver um erro com o arquivo, uma mensagem de erro na parte superior explica o que há de errado. Você precisará corrigir o arquivo e carregar-o novamente. Erros resultarão se sua planilha estiver formatada de forma incorreta ou se houver informações inválidas em determinados campos (consulte novamente as instruções [de formatação).](#formatting-your-template-data-with-excel)  
    
6. A **tela Revisar e concluir** mostra o número de ações e controles de melhoria e a pontuação máxima para o modelo. Quando estiver pronto para aprovar, selecione **Criar modelo.** (Se você precisar fazer alterações, selecione **Voltar.)**
7. A última tela confirma que um novo modelo foi criado. Selecione **Feito** para sair do assistente.
8. Você chegará à página de detalhes do novo modelo, onde poderá criar [sua avaliação.](compliance-manager-assessments.md#create-your-own-custom-assessment)

## <a name="formatting-your-template-data-with-excel"></a>Formatando seus dados de modelo com o Excel

A planilha do Excel usada para criar modelos contém quatro guias, sendo que três delas são necessárias:

1. [Modelo](#template-tab) (obrigatório)
2. [ControlFamily](#controlfamily-tab) (obrigatório)
3. [Ações](#actions-tab) (obrigatório)
4. [Dimensões](#dimensions-tab) (opcional)

Ao preencher sua planilha com dados de modelo, a planilha deve incluir as guias na ordem listada acima, caso contrário, seus dados não serão  **importados** com êxito para um modelo.

##### <a name="template-tab"></a>Guia Modelo

A **guia** Modelo é necessária. As informações nesta guia fornece metadados sobre o modelo. Há quatro colunas necessárias. As colunas devem manter a ordem na planilha do Excel conforme listado abaixo. Você pode adicionar sua própria coluna **após** as quatro colunas para fornecer suas próprias dimensões. Se você fizer isso, certifique-se de adicioná-los à guia **Dimensões** usando as [instruções abaixo.](#dimensions-tab)

- **title**: Este é o título do seu modelo, que deve ser exclusivo. Ele não pode compartilhar um nome com outro modelo que você tenha no Gerenciador de Conformidade, incluindo seus próprios modelos ou um modelo do Gerenciador de Conformidade.

- **product**: This is a required dimension. Liste o produto associado ao modelo.

- **certificação**: esta é a regulamentação que você está usando para o modelo.

- **inScopeServices**: estes são os serviços dentro do produto que esta avaliação aborda (por exemplo, se você listou o Office 365 como o produto, o Microsoft Teams poderia ser um serviço no escopo). Você pode listar vários serviços separados por dois pontos e vírgulas.

> [!NOTE]
> Os dados inseridos nas  células **de** certificação e produto não podem ser editados depois de importar a planilha para criar ou personalizar um modelo. Além disso, um grupo não pode conter duas avaliações que tenham a mesma combinação **de produto/certificação.** Você pode ter vários modelos com a mesma combinação de produto/certificação.

##### <a name="controlfamily-tab"></a>Guia ControlFamily

A **guia ControlFamily** é necessária.  As colunas necessárias nesta guia, que devem seguir a ordem fornecida na planilha de exemplo, são:

- **controlName**: esse é o nome do controle da certificação, padrão ou regulamentação, que normalmente é algum tipo de ID. Os nomes de controle devem ser exclusivos em um modelo. Não é possível ter vários controles com o mesmo nome na planilha.

- **controlFamily**: forneça uma palavra ou frase para o controlFamily, que identifica um amplo grupo de controles. Uma controlFamily não precisa ser exclusiva; ele pode ser listado mais de uma vez em uma planilha. A mesma controlFamily também pode ser listada em vários modelos, embora eles não tenham nenhuma relação entre si. Cada controlFamily deve ser mapeado para pelo menos um controle.

- **controlTitle:** forneça um título para o controle. Enquanto controlName é um código de referência, o título é um formato rich text normalmente visto nas regulamentações.

- **controlDescription**: forneça uma descrição do controle.

- **controlActionTitle**: este é o título de uma ação que você deseja relacionar a esse controle. Você pode adicionar várias ações separando por dois pontos e vírgulas sem espaço entre eles. Cada controle que você lista deve incluir pelo menos uma ação, e a ação  deve existir (o que significa que você pode listar uma ação listada na guia Ações da mesma planilha, uma ação que existe em um modelo diferente ou uma ação criada pela Microsoft). Controles diferentes podem fazer referência à mesma ação.

##### <a name="actions-tab"></a>Guia Ações

A **guia** Ações é necessária.  Ele designa as ações de melhoria gerenciadas pela sua organização e não as da Microsoft, que já existem no Gerenciador de Conformidade. As colunas necessárias para essa guia, que devem seguir a ordem fornecida na planilha de exemplo, são:

- **actionTitle**: este é o título da sua ação e é um campo obrigatório. O título que você fornece deve ser exclusivo. **Importante:** se você referenciar uma ação que já existe (como em outro modelo) e modificar qualquer um de seus elementos nas colunas subsequentes, essas alterações serão propagadas para a mesma ação em outros modelos.

- **implementationType**: neste campo obrigatório, liste um dos três tipos de implementação abaixo:
    - **Operacional** - ações implementadas por pessoas e processos para proteger a confidencialidade, a integridade e a disponibilidade de sistemas organizacionais, ativos, dados e funcionários (exemplo: reconhecimento e treinamento em segurança)
    - **Técnico** - ações concluídas por meio do uso de tecnologia e mecanismos contidos nos componentes de hardware, software ou firmware do sistema de informações para proteger a confidencialidade, a integridade e a disponibilidade de sistemas e dados organizacionais (exemplo: autenticação multifatores)
    - **Documentação** - ações implementadas por meio de políticas e procedimentos documentados que estabelecem e definem os controles necessários para proteger a confidencialidade, integridade e disponibilidade de sistemas organizacionais, ativos, dados e funcionários (exemplo: uma política de segurança de informações)

- **actionScore**: Neste campo obrigatório, forneça um valor de pontuação numérica para sua ação. Deve ser um número inteiro que varia de 1 a 99; não pode ser 0, nulo ou em branco. Quanto maior o número, maior o valor para melhorar a postura de conformidade. A imagem abaixo demonstra como o Gerenciador de Conformidade pontua controles:

![O Gerenciador de Conformidade controla valores de ponto](../media/compliance-score-action-scoring.png "O Gerenciador de Conformidade controla valores de ponto")

- **actionDescriptionTitle**: este é o título da descrição e é necessário. Esse título de descrição permite que você tenha a mesma ação em vários modelos e tenha uma descrição diferente em cada modelo.  Esse campo ajuda você a esclarecer qual modelo a descrição está fazendo referência. Na maioria dos casos, você pode colocar o nome do modelo que está criando neste campo.

- **actionDescription:** forneça uma descrição da ação. Você pode aplicar formatação como texto em negrito e hiperlinks. Este campo é obrigatório.

- **dimension-Action Purpose**: este é um campo opcional. Se você incluí-lo, o título deverá incluir o prefixo "dimension-". Todas as dimensões que você incluir aqui serão usadas como filtros no Gerenciador de Conformidade e aparecerão na página de detalhes das ações de melhoria no Gerenciador de Conformidade.

##### <a name="dimensions-tab"></a>Guia Dimensões

A **guia Dimensões** é opcional. No entanto, se você fizer referência a uma dimensão em outro lugar, precisará especificá-la aqui se ela não existir em um modelo que você já criou ou em um modelo da Microsoft. As colunas desta guia estão listadas abaixo:

- **dimensionKey**: lista como "produto", "certificações", "finalidade da ação"
- **dimensionValue**: exemplos: Office 365, HIPPA, Preventivo, Inspetor

Você pode exibir suas dimensões existentes indo **para** Gerenciamento de Locatários e selecionando **a guia** Dimensões. Além disso, sempre que você exportar um modelo  existente, a planilha exportada terá a guia Dimensões, que lista todas as dimensões usadas no modelo.

## <a name="modify-a-template"></a>Modificar um modelo

Talvez você queira modificar um modelo já criado, como adicionar controles, ou adicionar ou remover ações de melhoria. O processo é semelhante ao processo de criação de modelo em que você carregará o arquivo formatado do Excel com seus dados de modelo.

No entanto, há detalhes específicos a serem alertados à medida que você formatar o arquivo com alterações nos dados de modelo existentes. **Recomendamos que você revise essas instruções com cuidado para garantir que não sobrescreva quaisquer dados existentes que você deseja reter.**

### <a name="template-modification-process-steps"></a>Etapas do processo de modificação do modelo

Para modificar um modelo, siga as etapas abaixo:

1. Na página **de modelos de avaliação,** selecione o modelo que você deseja modificar, o que mostrará sua página de detalhes.
2. Selecione **Exportar para Excel**. Um arquivo do Excel com todos os seus dados de modelo será baixado. Salve o arquivo no computador local.
3. Faça alterações no modelo [modificando o arquivo do Excel usando as instruções abaixo.](#formatting-your-excel-file-to-modify-a-template)
4. Quando terminar de fazer alterações no arquivo do Excel, salve o arquivo.
5. Na página de detalhes do seu modelo, selecione **Modificar modelo** para iniciar o assistente de modificação. 
6. Na tela **Carregar arquivo,** selecione **Procurar** para encontrar e carregar o arquivo do Excel.
7. Se não houver problemas com seu arquivo, a próxima tela mostrará o nome do arquivo carregado. Select **Next** to continue (if you need to change the file, select **Upload a different file**).
    - Se houver um problema com o arquivo, uma mensagem de erro na parte superior explica o que há de errado. Você precisará corrigir o arquivo e carregar-o novamente. Os erros ocorrerão se sua planilha for formatada de forma incorreta ou se houver informações inválidas em determinados campos.

8. A **tela Revisar e concluir** mostra o número de ações e controles de melhoria e a pontuação máxima para o modelo. Quando estiver pronto para aprovar, selecione **Próximo**.
9. A última tela confirma que o modelo foi modificado. Selecione **Feito** para sair do assistente.

Seu modelo agora incluirá as alterações feitas. Todas as avaliações que usam esse modelo modificado agora mostrarão atualizações pendentes, e você precisará aceitar as atualizações das avaliações para refletir as alterações feitas no modelo. Saiba mais sobre [atualizações para avaliações.](compliance-manager-assessments.md#accepting-updates-to-assessments)

> [!NOTE]
> Se você usar o Gerenciador de Conformidade em um idioma diferente do inglês, perceberá que algum texto aparece em inglês quando você exporta um modelo para o Excel. Os títulos das ações (suas ações de melhoria e ações da Microsoft) devem estar em inglês para serem reconhecidos pelos controles. Se você fizer alterações em um título de ação, certifique-se de escrevê-lo em inglês para que o arquivo seja importado corretamente.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Formatando seu arquivo do Excel para modificar um modelo

Entre em uma seção abaixo para encontrar rapidamente as instruções de que você precisa:

- [Editar os atributos principais do modelo](#edit-the-main-template-attributes)
- [Adicionar uma ação de melhoria](#add-an-improvement-action)
- [Editar informações de uma ação de aperfeiçoamento](#edit-an-improvement-actions-information)
- [Alterar o nome de uma ação de melhoria](#change-an-improvement-actions-name)
- [Remover uma ação de melhoria](#remove-an-improvement-action)
- [Remover um controle](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>Editar os atributos principais do modelo

Na guia **Modelos,** você pode editar qualquer coisa na coluna **de** título, na coluna **inScopeServices** e em qualquer outra coluna que tenha adicionado. No entanto, não é possível editar nada no produto **ou** **nas** colunas de certificação.

#### <a name="add-an-improvement-action"></a>Adicionar uma ação de melhoria

1. Vá para a **guia** Ações. Adicione suas informações nos campos obrigatórios na primeira linha vazia abaixo de suas ações existentes.
2. Vá até a **guia ControlFamily.** Encontre a linha que contém o controle para o que sua ação de melhoria é mapeada. Adicione sua nova ação à **coluna controlActionTitle** nessa linha (lembre-se de separar várias ações nesse campo com dois pontos e vírgulas, sem espaço entre eles).
3. Salve sua planilha.

#### <a name="edit-an-improvement-actions-information"></a>Editar informações de uma ação de aperfeiçoamento

Você pode alterar as informações de qualquer ação de melhoria, *exceto seu título.* Você pode editar qualquer célula das colunas B em diante e, ao importar o arquivo de volta para o modelo, as ações de melhoria nesse modelo agora conterão os dados atualizados.

Não é possível editar **o actionTitle** (coluna A) porque, se fizer isso, o Gerenciador de Conformidade considerará essa uma nova ação de melhoria. Se você quiser alterar o nome de uma ação de melhoria, consulte as instruções imediatamente abaixo.

#### <a name="change-an-improvement-actions-name"></a>Alterar o nome de uma ação de melhoria

Se você quiser alterar o nome de uma ação de melhoria, será preciso designar explicitamente na planilha que você está substituindo um nome existente por um novo nome. Siga estas etapas:

1. Na guia **Ações** da planilha, adicione uma nova coluna à planilha após a coluna A.
2. In this new column, which is now column B, put as its header in row 1: **oldActionTitle**.
3. Copie o conteúdo da coluna A e colá-lo na coluna B. Isso coloca os títulos de ação de melhoria existentes, que são o que você deseja alterar, na coluna B.
4. Na coluna A, **actionTitle**, exclua o nome antigo e substitua-o pelo novo nome para sua ação de melhoria.

Observe que títulos de ação, tanto para suas ações de melhoria quanto para ações da Microsoft, devem ser escritos em inglês para serem reconhecidos quando referenciados nos controles.

#### <a name="remove-an-improvement-action"></a>Remover uma ação de melhoria

Para remover uma ação de melhoria de um modelo, você precisará removê-la de todos os controles que o referenciam. Siga as etapas abaixo para modificar sua planilha:

1. Na guia **ControlFamily,** procure o título da ação de melhoria que você deseja remover.
2. Exclua o título da ação de melhoria nas células em que ela aparece. Se a ação de melhoria for a única ação nessa linha, exclua a linha inteira (que remove o controle).
3. Na guia **Ações,** exclua a linha que contém a ação de melhoria que você está excluindo.
4. Salve sua planilha.

Quando você importar sua planilha de volta para o modelo, sua ação de melhoria será removida do modelo.

Remover uma ação de melhoria de um modelo não remove completamente a ação de melhoria do Gerenciador de Conformidade. Essa ação ainda pode ser referenciada por outro modelo.

#### <a name="remove-a-control"></a>Remover um controle

Para remover um controle, modifique sua planilha seguindo as etapas abaixo e importe-a de novo:

1. Na guia **ControlFamily,** encontre o controle que você deseja remover na **coluna controlName.**
2. Exclua a linha desse controle.
    - Se esse controle excluído contiver ações de melhoria que não sejam referenciadas por nenhum outro controle, você precisará remover essas ações de melhoria da **guia** Ações. Caso contrário, você receberá um erro de validação.

3. Salve sua planilha.

Quando você importar sua planilha de volta para o modelo, seu controle será removido do modelo.

## <a name="export-a-template"></a>Exportar um modelo

Você pode exportar um arquivo do Excel que contém todos os dados de um modelo. Você precisará exportar um modelo para modificar o modelo, pois esse será o arquivo do Excel que você edita e carrega no processo [de modificação.](#modify-a-template)

Para exportar seu modelo, vá até a página de detalhes do modelo e selecione o **botão Exportar para Excel.**

Observe que, ao exportar um modelo que você estendeu de um modelo do Gerenciador de Conformidade, o arquivo exportado conterá apenas os atributos que você adicionou ao modelo. O arquivo exportado não incluirá os dados originais do modelo fornecidos pela Microsoft. Para obter esse relatório, consulte as instruções para [exportar um relatório de avaliação.](compliance-manager-assessments.md#export-an-assessment-report)