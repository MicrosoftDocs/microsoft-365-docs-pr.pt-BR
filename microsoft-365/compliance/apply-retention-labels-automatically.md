---
title: Aplicar automaticamente um rótulo de retenção para reter ou excluir conteúdo
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Criar e publicar automaticamente os rótulos de retenção para que você possa aplicar automaticamente os rótulos para reter o que precisa e excluir o que não
ms.openlocfilehash: 9ab456cd5b1f5f1bf47a1e24a3d7e58b7992ede0
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196374"
---
# <a name="automatically-apply-a-retention-label-to-retain-or-delete-content"></a>Aplicar automaticamente um rótulo de retenção para reter ou excluir conteúdo

>*[Diretrizes de licenciamento do Microsoft 365 para segurança e conformidade](https://aka.ms/ComplianceSD).*

> [!NOTE]
> Não há suporte para esse cenário para [registros regulatórios](records-management.md#records).

Um dos recursos mais poderosos dos [rótulos de retenção](retention.md) é a capacidade de aplicá-los automaticamente ao conteúdo que corresponde a determinadas condições. Nesse caso, as pessoas da sua organização não precisam aplicar os rótulos de retenção. O Microsoft 365 faz o trabalho para elas.
  
Os rótulos de retenção de aplicação automática são excelentes porque:
  
- Você não precisa treinar os usuários com relação a todas as classificações.
    
- Você não precisa depender dos usuários para classificar corretamente o conteúdo.
    
- Os usuários não precisam mais conhecer as políticas de governança de dados; assim podem se concentrar no próprio trabalho.
    
Você pode aplicar rótulos de retenção ao conteúdo automaticamente quando esse conteúdo contiver informações confidenciais, palavras-chave, propriedades pesquisáveis ou uma correspondência para [classificadores treináveis](classifier-get-started-with.md).

> [!TIP]
> Agora, no modo de visualização, use as propriedades pesquisáveis para identificar [gravações das reuniões do Teams](#microsoft-teams-meeting-recordings).

Os processos para aplicar automaticamente um rótulo de retenção com base nessas condições:

![Diagrama de funções e tarefas para aplicação automática de rótulos](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)

Use as instruções a seguir para as duas etapas de administrador.

> [!NOTE]
> As políticas automáticas usam o rotulamento do lado do serviço com condições para aplicar automaticamente os rótulos de retenção. Você também pode aplicar um rótulo de retenção automaticamente a uma política de rótulo ao fazer o seguinte: 
>
> - Aplicar um rótulo de retenção padrão a uma biblioteca do Microsoft Office SharePoint Online, uma pasta ou um conjunto de documentos para que o conteúdo não rotulado no contêiner seja rotulado automaticamente
>- Aplicar automaticamente um rótulo de retenção ao email usando regras
>
> Nesses cenários, confira [Criar e aplicar rótulos de retenção em aplicativos](create-apply-retention-labels.md).

## <a name="before-you-begin"></a>Antes de começar

O administrador global da sua organização tem permissões completas para criar e editar os rótulos de retenção e suas políticas. Se você não estiver entrando como um administrador global, confira [Permissões necessárias para criar e gerenciar políticas e rótulos de retenção](get-started-with-retention.md#permissions-required-to-create-and-manage-retention-policies-and-retention-labels).

## <a name="how-to-auto-apply-a-retention-label"></a>Como aplicar automaticamente um rótulo de retenção

Primeiro, crie seu rótulo de retenção. Em seguida, crie uma política automática para aplicar esse rótulo. Se você já tiver criado seu rótulo de retenção, vá para [Criar uma política automática](#step-2-create-an-auto-apply-policy).

As instruções de navegação dependem se você estiver usando o [gerenciamento de relatórios](records-management.md) ou não. São fornecidas instruções para ambos os cenários.

### <a name="step-1-create-a-retention-label"></a>Etapa 1: Criar uma política de retenção

1. No [Centro de conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:
    
    - Se você estiver usando o gerenciamento de registros:
        - **Soluções** > **Gerenciamento de Registros** >  guia **Plano de Arquivos** > **+ Criar um Rótulo** > **Rótulo de Retenção**
        
    - Se você não estiver usando o gerenciamento de registros:
       - **Soluções** > **Governança de Informações** >  guia **Rótulos** > + **Criar um Rótulo**
    
    Não vê a opção imediatamente? Primeiro, selecione **Mostrar Tudo**. 

2. Siga as instruções do assistente. Se você estiver usando o gerenciamento de registros:
    
    - Para saber mais sobre os descritores de plano de arquivo, confira [Usar o plano de arquivo para gerenciar os rótulos de retenção](file-plan-manager.md)
    
    - Para usar o rótulo de retenção para declarar registros, selecione **Marcar itens como registros** ou **Marcar itens como registros regulatórios**. Para saber mais, confira [Configuração de rótulos de retenção para declarar registros](declare-records.md#configuring-retention-labels-to-declare-records).

3. Depois de criar o rótulo, você verá as opções para publicar a etiqueta, aplicar automaticamente a etiqueta, ou apenas salvar o rótulo: Selecione **Aplicar o rótulo automaticamente a um tipo específico de conteúdo** e, em seguida, selecione **concluído** para iniciar o assistente criar rotulagem automática, que o levará diretamente para a etapa 2 do procedimento a seguir.

Para editar um rótulo existente, selecione-o e, em seguida, selecione **Editar rótulo** para iniciar o Assistente do editor de retenção que permite alterar as descrições de rótulo e quaisquer [configurações qualificadas](#updating-retention-labels-and-their-policies) na etapa 2.


### <a name="step-2-create-an-auto-apply-policy"></a>Etapa 2: Criar uma política de aplicação automática

Ao criar uma política de aplicação automática, selecione um rótulo de retenção a ser aplicado automaticamente ao conteúdo com base nas condições que você especificar.

1. No [Centro de Conformidade do Microsoft 365 ](https://compliance.microsoft.com/), navegue até um dos seguintes locais:
    
    - Se você estiver usando o gerenciamento de registros: **Governança de Informações**:
        - **Soluções** > **Gerenciamento de Registros** guia  > **Políticas de Rótulo** > **Aplicar rótulo automaticamente**
    
    - Se você não estiver usando o gerenciamento de registros:
        - **Soluções** > **Governança de Informações** >  guia **Políticas de Rótulo** > **Aplicar rótulo automaticamente**
    
    Não vê a opção imediatamente? Primeiro, selecione **Mostrar Tudo**. 

2. Siga os avisos no assistente Criar rotulação automática.
    
    Para saber mais sobre como configurar condições que aplicam automaticamente o rótulo de retenção, confira o [Configurar condições para a aplicação automática de rótulos de retenção](#configuring-conditions-for-auto-apply-retention-labels) nesta página.
    
    Para obter informações sobre os locais suportados pelos rótulos de retenção, confira a seção[Rótulos e locais de retenção](retention.md#retention-label-policies-and-locations).

Para editar uma política de aplicação automática existente, selecione-a para iniciar o assistente para editar política de retenção que permite alterar o rótulo de retenção selecionado e quaisquer [configurações elegíveis](#updating-retention-labels-and-their-policies) da etapa 2.


### <a name="configuring-conditions-for-auto-apply-retention-labels"></a>Configurar condições para a aplicação automática de rótulos de retenção

Você pode aplicar os rótulos de retenção automaticamente ao conteúdo quando esse conteúdo apresentar:

- [Tipos específicos de informações confidenciais](#auto-apply-labels-to-content-with-specific-types-of-sensitive-information)

- [Palavras-chave específicas ou Propriedades pesquisáveis que correspondem a uma consulta criada](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [Uma correspondência de classificadores treináveis](#auto-apply-labels-to-content-by-using-trainable-classifiers)

#### <a name="auto-apply-labels-to-content-with-specific-types-of-sensitive-information"></a>Aplicar automaticamente rótulos a conteúdo com tipos específicos de informações confidenciais

Ao criar rótulos de retenção de aplicação automática para informações confidenciais, você vê a mesma lista de modelos de política que quando cria uma política de prevenção contra perda de dados (DLP). Cada modelo de política é pré-configurado para procurar tipos específicos de informações confidenciais. Por exemplo, o modelo mostrado aqui procura os números dos EUA ITIN, SSN e passaporte da categoria **Privacidade** e **Modelo de dados de Informações de Identificação Pessoal (PII) dos EUA**:

![Modelos de política com tipos de informações confidenciais](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)

Para obter mais informações sobre os tipos de informações confidenciais, confira [Definições da entidade de tipo de informações confidenciais](sensitive-information-type-entity-definitions.md).

Após selecionar um modelo de política, você pode adicionar ou remover quaisquer tipos de informações confidenciais e pode alterar a contagem de instâncias e a precisão da correspondência. Na captura de tela de exemplo mostrada a seguir, um rótulo de retenção será automaticamente aplicado apenas quando:
  
- O tipo de informações confidenciais detectadas tiver uma precisão de correspondência (ou um nível de confiança) de pelo menos 75. Muitos tipos de informações confidenciais são definidos com vários padrões, em que um padrão com maior precisão de correspondência requer mais evidências para ser encontrado (como palavras-chave, datas ou endereços), enquanto um padrão com precisão de correspondência inferior requer menos evidências. Quanto menor for a precisão de correspondência **min**, mais fácil será que o conteúdo corresponda à condição.

- O conteúdo contém entre uma e nove instâncias de qualquer um destes três tipos de informações confidenciais. Você pode excluir o valor **a** para que ele se transforme em **Qualquer**.

Para obter mais informações sobre essas opções, confira as diretrizes a seguir na documentação da DLP [Regras de ajuste para torná-las mais fáceis ou difíceis de corresponder aos](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match).
    
![Opções para identificar tipos de informações confidenciais](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
#### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>Aplicar rótulos automaticamente a conteúdos com palavras-chave ou propriedades pesquisáveis

Você pode aplicar automaticamente os rótulos ao conteúdo usando uma consulta que inclui palavras ou frases específicas, ou valores de propriedades pesquisáveis. Você pode refinar a consulta usando os operadores de pesquisa AND, OR e NOT.

![Editor de consultas](../media/new-retention-query-editor.png)

Para obter mais informações sobre a sintaxe de consulta que usa a Linguagem de Consulta de Palavra-chave (KQL), consulte [Referência de sintaxe da Linguagem de Consulta de Palavra-chave (KQL) no MSDN](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference).

Observe que os rótulos baseados em consulta usam o índice de pesquisa para identificar conteúdo. Para obter mais informações sobre as propriedades pesquisáveis que você pode usar, consulte:

- [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md)
- [Visão geral de propriedades rastreadas e gerenciadas no SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

> [!NOTE]
> Embora as propriedades gerenciadas do SharePoint ofereçam suporte a aliases, não os use quando configurar seus rótulos de retenção. Especifique sempre o nome real da propriedade gerenciada, por exemplo, RefinableString01.

Consultas de exemplos:

| Workload | Exemplo |
|:-----|:-----|
|Exchange   | `subject:"Quarterly Financials"` |
|Exchange   | `recipients:garthf@contoso.com` |
|Microsoft Office SharePoint Online | `contenttype:contract` |
|SharePoint | `site:https://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract`|

##### <a name="microsoft-teams-meeting-recordings"></a>Gravações de reunião do Microsoft Teams

> [!NOTE]
> A capacidade de reter e excluir gravações de reunião de equipes é distribuída na visualização e não funciona antes de as gravações serem salvas no Microsoft OneDrive ou no Microsoft Office SharePoint Online. Para saber mais, confira[Usar o OneDrive for Business e o SharePoint Online ou Stream para gravações de reunião](https://docs.microsoft.com/MicrosoftTeams/tmr-meeting-recording-change).

Para identificar as gravações de reunião do Microsoft Teams que estão armazenadas nas contas do OneDrive do usuário ou no SharePoint, especifique o seguinte para o **Editor de consulta palavra-chave**:

``` 
ProgID:Media AND ProgID:Meeting
```

Para esse rótulo de retenção, você também deve publicá-lo em contas do Microsoft OneDrive ou sites do Microsoft Office SharePoint Online relevantes dos usuários, criando uma política de rótulo. Na maioria das vezes, as gravações de reunião são salvas no Microsoft OneDrive, mas para reuniões do canal, elas são salvas no Microsoft Office SharePoint Online.

Depois de salvar a política de aplicação automática:

1. Selecionar **Políticas de rótulos** guia > **Publicar rótulos**

2. Quando for pedido para selecionar um rótulo, escolha o rótulo que você criou com a consulta KQL para identificar as gravações de reunião do Teams.

3. Quando for solicitado o local, escolha **Sites do Microsoft Office SharePoint Online** e **Contas do Microsoft OneDrive**. Em seguida, você pode manter o padrão de **Todas**ou especificar locais individuais, como incluir ou excluir contas específicas do Microsoft OneDrive.

4. Conclua o assistente e salve essa política de rótulo.

#### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>Aplicar rótulos automaticamente ao conteúdo usando classificadores treináveis

Ao escolher a opção de um classificador treinado, você pode selecionar um dos classificadores internos ou um classificador personalizado. Os classificadores internos incluem **Currículos**, **SourceCode**, **Assédio Direcionado**, **Profanação** e **Ameaças**:

![Escolha classificador treinável](../media/retention-label-classifers.png)

> [!CAUTION]
> Vamos substituir o classificador interno **Idioma Ofensivo** porque ele tem uma grande quantidade de falsos positivos. Não use esse classificador interno e se você estiver usando-o no momento, você deve migrar seus processos de negócios para fora dele. É recomendável usar os classificadores internos **Assédio Direcionado**, **Profanidade**e **Ameaças**.

Para aplicar um rótulo automaticamente usando essa opção, os sites e as caixas de correio do SharePoint devem conter pelo menos 10 MB de dados.

Para saber mais sobre esses classificadores treináveis, confira [Saiba mais sobre classificadores treináveis (visualização)](classifier-learn-about.md).

> [!TIP]
> Se você usar classificadores treináveis para o Exchange, confira [Como treinar novamente um classificador no explorador de conteúdo (visualização)](classifier-how-to-retrain-content-explorer.md) lançado recentemente.

## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>Quanto tempo demora para os rótulos de retenção entrarem em vigor

Quando você aplica rótulos de retenção automaticamente, pode levar até sete dias para que os rótulos de retenção sejam aplicados a todo o conteúdo existente que corresponde às condições.
  
![Diagrama de quando a aplicação automática de rótulos entra em vigor](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
## <a name="updating-retention-labels-and-their-policies"></a>Atualizar os rótulos de retenção e suas políticas

Se você editar um rótulo de retenção ou política de aplicação automática e o rótulo de retenção já estiver aplicado ao conteúdo, as configurações atualizadas serão aplicadas automaticamente a esse conteúdo, além do conteúdo recentemente rotulado.

Algumas configurações não podem ser alteradas depois que o rótulo ou política é criado e salvo, que incluem:
- As configurações de retenção, exceto o período de retenção, a menos que você tenha configurado o rótulo para reter ou excluir o conteúdo com base em quando ele foi criado.
- A opção para marcar os itens como um registro.

## <a name="next-steps"></a>Próximas etapas

Confira [Usar rótulos de retenção para gerenciar o ciclo de vida dos documentos armazenados no SharePoint](auto-apply-retention-labels-scenario.md) para um exemplo de cenário que usa uma política de aplicação automática com propriedades gerenciadas no SharePoint, e retenção baseada em evento para iniciar o período de retenção.
