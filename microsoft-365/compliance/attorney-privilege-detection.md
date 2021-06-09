---
title: Configurar a detecção de privilégio advogado-cliente em Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use o modelo de detecção de privilégio advogado-cliente para usar a detecção baseada em aprendizado de máquina de conteúdo privilegiado ao analisar o conteúdo em um Advanced eDiscovery caso.
ms.openlocfilehash: 73a0efeece7bc331045e9bbe1a1da56f9fd24700
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358037"
---
# <a name="set-up-attorney-client-privilege-detection-in-advanced-ediscovery"></a>Configurar a detecção de privilégio advogado-cliente em Advanced eDiscovery

Um aspecto importante e caro da fase de revisão de qualquer processo de Descoberta e é analisar documentos para conteúdo privilegiado. Advanced eDiscovery fornece detecção baseada em aprendizado de máquina de conteúdo privilegiado para tornar esse processo mais eficiente. Esse recurso é chamado de *detecção de privilégio advogado-cliente.*

## <a name="how-does-it-work"></a>Como funciona?

Quando a detecção de privilégio advogado-cliente estiver habilitada, todos os documentos em [](analyzing-data-in-review-set.md) um conjunto de revisão serão processados pelo modelo de detecção de privilégio advogado-cliente quando você analisar os dados no conjunto de revisão. O modelo procura duas coisas:

- Conteúdo privilegiado – O modelo usa o aprendizado de máquina para determinar a probabilidade de que o documento contenha conteúdo legal de natureza.

- Participantes – Como parte da configuração da detecção de privilégio advogado-cliente, você precisa enviar uma lista de advogados para sua organização. Em seguida, o modelo compara os participantes do documento com a lista de contatos para determinar se um documento tem pelo menos um participante.

O modelo produz as três propriedades a seguir para cada documento:

- **AttorneyClientPrivilegeScore:** A probabilidade de o documento ser legal; os valores da pontuação estão entre **0** e **1**.

- **HasAttorney:** Essa propriedade será definida como **true** se um dos participantes do documento estiver listado na lista de advogados; caso contrário, o valor é **false**. O valor também será definido como **falso** caso sua organização não tenha carregado uma lista de valores.

- **IsPrivilege:** Essa propriedade será definida como **true** se o valor **de AttorneyClientPrivilegeScore** estiver acima do limite ou se o documento tiver um participante de advogado;  caso contrário, o valor é definido como **false**.

Essas propriedades (e seus valores correspondentes) são adicionadas aos metadados de arquivo dos documentos em um conjunto de revisão, conforme mostrado na captura de tela a seguir:

![Propriedades de privilégio advogado-cliente mostradas em metadados de arquivo](../media/AeDAttorneyClientPrivilegeMetadata.png)

Essas três propriedades também podem ser pesquisadas em um conjunto de revisão. Para obter mais informações, [consulte Query the data in a review set](review-set-search.md).

## <a name="set-up-the-attorney-client-privilege-detection-model"></a>Configurar o modelo de detecção de privilégio advogado-cliente

Para habilitar o modelo de detecção de privilégio advogado-cliente, sua organização precisa ative-lo e carregar uma lista de advogados.

### <a name="step-1-turn-on-attorney-client-privilege-detection"></a>Etapa 1: Ativar a detecção de privilégio advogado-cliente

Uma pessoa que seja um Administrador de Descoberta e Descoberta Na sua organização (membro do subgrupo Administrador de Descoberta e No grupo de funções do Gerenciador de Descobertas E) deve disponibilizar o modelo em seus Advanced eDiscovery de descoberta.

1. No Centro de Conformidade & segurança, acesse **eDiscovery > Advanced eDiscovery**.

2. Na home **page Advanced eDiscovery,** no **Configurações,** clique em **Configurar configurações de análise global**.

   ![Selecione "Configurar recursos experimentais"](../media/AeDExperimentalFeatures.png)

3. Na guia **Configurações do Analytics,** selecione **Gerenciar a configuração de privilégio advogado-cliente.**

4. Na página **Privilégio do cliente de**, use o recurso de alternância para ativar o recurso e selecione **Salvar**.

### <a name="step-2-upload-a-list-of-attorneys-optional"></a>Etapa 2: Upload uma lista de advogados (opcional)

Para aproveitar ao máximo o modelo de detecção de privilégio advogado-cliente e usar os resultados da detecção **Has Attorney** ou **Potentially Privileged** que foi descrita anteriormente, recomendamos carregar uma lista de endereços de email para os advogados e a equipe jurídica que trabalham para sua organização. 

Para carregar uma lista de advogados para uso pelo modelo de detecção de privilégio advogado-cliente:

1. Crie um arquivo .csv (sem uma linha de cabeçalho) e adicione o endereço de email para cada pessoa apropriada em uma linha separada. Salve este arquivo em seu computador local.

2. Na home **page Advanced eDiscovery,** no  Configurações, selecione **Configurar** recursos experimentais e selecione Gerenciar configuração de privilégio **advogado-cliente.**

   A página de privilégio **advogado-cliente** é exibida, e a alternância de detecção de privilégio **advogado-cliente** está 2016.

   ![Página de sub-sub-subsisão de privilégio advogado-cliente](../media/AeDUploadAttorneyList.png)

3. Selecione **Procurar** e, em seguida, encontre e selecione o arquivo .csv que você criou na etapa 1.

4. Selecione **Salvar** para carregar a lista de advogados.

## <a name="use-the-attorney-client-privilege-detection-model"></a>Usar o modelo de detecção de privilégio advogado-cliente

Siga as etapas nesta seção para usar a detecção de privilégio advogado-cliente para documentos em um conjunto de revisão.

### <a name="step-1-create-a-smart-tag-group-with-attorney-client-privilege-detection-model"></a>Etapa 1: Criar um grupo de marca inteligente com o modelo de detecção de privilégio advogado-cliente

Uma das principais maneiras de ver os resultados da detecção de privilégios de cliente potencial em seu processo de revisão é usar um grupo de marca inteligente. Um grupo de marcas inteligentes indica os resultados da detecção de privilégios de cliente para análise e mostra os resultados alinhados ao lado das marcas em um grupo de marcas inteligentes. Isso permite identificar rapidamente documentos potencialmente privilegiados durante a revisão de documentos. Além disso, você também pode usar as marcas no grupo de marcas inteligentes para marcar documentos como privilegiados ou não privilegiados. Para obter mais informações sobre marcas inteligentes, consulte Configurar marcas [inteligentes em Advanced eDiscovery](smart-tags.md).

1. No conjunto de revisão que contém os documentos que  você analisou na Etapa 1, selecione Gerenciar conjunto de revisão e selecione **Gerenciar marcas**.
 
2. Em **Marcas,** selecione a pull-down ao lado de **Adicionar grupo** e selecione Adicionar grupo de marca **inteligente**.

   ![Selecione "Adicionar grupo de marca inteligente"](../media/AeDCreateSmartTag.png)

3. Na página **Escolher um modelo para sua marca inteligente,** escolha **Selecionar** ao lado do **privilégio Advogado-cliente**.

   Um grupo de marca chamado **Privilégio advogado-cliente** é exibido. Ele contém duas marcas filho chamadas **Positivo** e **Negativo**, que correspondem aos possíveis resultados produzidos pelo modelo.

   ![Grupo de marca inteligente de privilégio advogado-cliente](../media/AeDAttorneyClientSmartTagGroup.png)

3. Renomeie o grupo de marcas e as marcas conforme apropriado para sua revisão. Por exemplo, você pode renomear **Positivo** para **Privilegiado** e **Negativo** para **Não Privilegiado.**

### <a name="step-2-analyze-a-review-set"></a>Etapa 2: Analisar um conjunto de revisão

Quando você analisa os documentos em um conjunto de revisão, o modelo de detecção de privilégio advogado-cliente também será executado e as propriedades correspondentes (descritas em Como [funciona?](#how-does-it-work) serão adicionadas a cada documento no conjunto de revisão. Para obter mais informações sobre como analisar dados no conjunto de revisão, consulte [Analyze data in a review set in Advanced eDiscovery](analyzing-data-in-review-set.md).

### <a name="step-3-use-the-smart-tag-group-for-review-of-privileged-content"></a>Etapa 3: Usar o grupo de marca inteligente para revisão de conteúdo privilegiado

Depois de analisar o conjunto de revisão e configurar marcas inteligentes, a próxima etapa é revisar os documentos. Se o modelo tiver determinado que o documento é  potencialmente privilegiado, a marca inteligente correspondente no painel De marcação indicará os seguintes resultados produzidos pela detecção de privilégio advogado-cliente:

- Se o documento tiver conteúdo que possa ser legal, o rótulo **Conteúdo legal** será exibido ao lado da marca inteligente correspondente (que, nesse caso, é a marca **Positiva** padrão).

- Se o documento tiver um participante encontrado na lista de advogados da sua organização, o rótulo **Advogado** será exibido ao lado da marca inteligente correspondente (que, nesse caso, também é a marca Positiva **padrão).**

- Se o documento tiver conteúdo que  possa ser legal e tiver um participante  encontrado na lista de advogados, os rótulos Conteúdo **Legal** e Advogado serão exibidos. 

Se o modelo determinar que um documento não contém conteúdo legal ou que não contenha um participante da lista de advogados, nenhum rótulo será exibido no painel de marcação.

Por exemplo, as capturas de tela a seguir mostram dois documentos. O primeiro contém conteúdo legal e tem um participante encontrado na lista de advogados. O segundo não contém nenhum e, portanto, não exibe rótulos.

![Documento com rótulos de conteúdo jurídico e advogado](../media/AeDTaggingPanelLegalContentAttorney.png)

![Documento sem rótulos](../media/AeDTaggingPanelNegative.png)

Depois de revisar um documento para ver se ele contém conteúdo privilegiado, você pode marcar o documento com a marca apropriada.
