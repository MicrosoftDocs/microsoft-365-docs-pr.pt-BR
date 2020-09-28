---
title: Criar um modelo de processamento de formulários
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Criar um modelo de processamento de formulários no Microsoft SharePoint Syntex.
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295473"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Criar um modelo de processamento de formulários no Microsoft SharePoint Syntex

O conteúdo deste artigo é para a visualização privada do projeto Cortex. [Saiba mais sobre o Project Cortex](https://aka.ms/projectcortex).

Usando o [ai Builder](https://docs.microsoft.com/ai-builder/overview) -um recurso no Microsoft PowerApps-Project Cortex os usuários podem criar um [modelo de processamento de formulários](form-processing-overview.md) diretamente de uma biblioteca de documentos do SharePoint. 

A criação de um modelo de processamento de formulários envolve o seguinte:
 - Etapa 1: criar o modelo de processamento do para criar o tipo de conteúdo
 - Etapa 2: Adicionar e analisar arquivos de exemplo
 - Etapa 3: selecionar seus campos de formulário
 - Etapa 4: treinar e testar seu modelo
 - Etapa 5: publicar seu modelo
 - Etapa 6: usar o modelo

## <a name="requirements"></a>Requisitos

Você só pode criar um modelo de processamento de formulário em bibliotecas de documentos do SharePoint para os quais ele está habilitado. Se o processamento de formulários estiver habilitado, você poderá ver o **Construtor ai** **"criar um modelo de processamento de formulários** " no menu **automatizar** da biblioteca de documentos.  Se você precisar de processamento habilitado em sua biblioteca de documentos, você deve entrar em contato com seu administrador do SharePoint.

 ![Criar um modelo do AI Builder](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>Etapa 1: criar um modelo de processamento de formulário

A primeira etapa na criação de um modelo de processamento de formulários é nomeá-lo e criar o novo tipo de conteúdo e criar um novo modo de exibição de biblioteca de documentos.

1. Na biblioteca de documentos, selecione o menu **automatizar** , selecione **Construtor ai**e, em seguida, selecione **criar um modelo de processamento de formulários**.

    ![Criar um modelo](../media/content-understanding/create-ai-builder-model.png)</br>

2. No painel **novo modelo de processamento de formulário** , no campo  **nome** , digite um nome para o modelo (por exemplo, *ordens de compra*).

    ![Novo modelo de processamento de formulário](../media/content-understanding/new-form-model.png)</br> 

3. Ao criar um modelo de processamento de formulário, você cria um novo tipo de conteúdo do SharePoint. Um tipo de conteúdo do SharePoint representa uma categoria de documentos que têm características comuns e compartilham uma coleção de colunas ou propriedades de metadados para esse conteúdo específico. Os tipos de conteúdo do SharePoint são gerenciados por meio da [Galeria de tipos de conteúdo]().

    Selecione **Configurações avançadas** se quiser mapear esse modelo para um tipo de conteúdo existente na Galeria de tipos de conteúdo do SharePoint para usar seu esquema. 

4. Seu modelo cria um novo modo de exibição na biblioteca de documentos para os dados extraídos. Se você não quiser fazê-lo para o modo de exibição padrão, desmarque **definir o modo de exibição como padrão**.

5. Selecione **Criar**.

## <a name="step-2-add-and-analyze-documents"></a>Etapa 2: Adicionar e analisar documentos

Depois de criar seu novo modelo de processamento de formulário, seu navegador abre uma nova página de modelo de processamento de formulários do Construtor AI. Nesta página, você pode adicionar e analisar seus documentos de exemplo. </br>

> [!NOTE]
> Ao procurar por exemplos de arquivos a serem usados, consulte o [modelo de processamento de formulários de entrada e dicas de otimização](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

   ![Construtor AI de aplicativos de energia](../media/content-understanding/powerapps.png)</br> 
 
1. Selecione **adicionar documentos** para começar a adicionar documentos de exemplo analisados para determinar os pares de valores nomeados que podem ser extraídos. Em seguida, você pode escolher **carregar do armazenamento local**, **do SharePoint**ou **do armazenamento de blob do Azure**. Você precisa usar pelo menos cinco arquivos para treinamento.

2. Após adicionar arquivos, selecione **analisar** para verificar se há informações comuns em todos os arquivos. Isso pode levar alguns minutos para ser concluído.</br> 
 
    ![Analisar arquivos](../media/content-understanding/analyze.png)</br> 

3. Após a análise dos arquivos, na página **Selecione os campos de formulário que você deseja salvar** , selecione o arquivo para exibir os campos detectados.</br>

    ![Selecionar campos de formulário](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Etapa 3: selecionar seus campos de formulário

Após analisar os documentos de campos, agora você pode ver os campos que foram encontrados e identificar aqueles que você deseja salvar. Os campos salvos são exibidos como colunas no modo de exibição de biblioteca de documentos do seu modelo e mostram os valores extraídos de cada documento.

1. A próxima página exibe um de seus arquivos de amostra e realçará todos os campos comuns que foram detectados automaticamente pelo sistema. </br>

    ![Página Selecionar campos](../media/content-understanding/select-fields-page.png)</br> 

2. Selecione os campos que você deseja salvar e marque a caixa de seleção para confirmar sua seleção. Por exemplo, no modelo de ordem de compra, escolha a seleção dos campos *Data*, *OC*e *total* .  Observe que você também pode optar por renomear um campo se escolher. </br>

    ![Selecionar OC #](../media/content-understanding/po.png)</br> 

3. Se um campo não foi detectado pela análise, você ainda pode optar por adicioná-lo. Destaque as informações que você deseja extrair e, na caixa nome, digite o nome desejado. Em seguida, marque a caixa de seleção. Observe que você precisa confirmar campos não detectados em seus arquivos de amostra restantes.

4. Clique em **confirmar campos** depois de selecionar os campos que você deseja salvar. </br>
 
    ![Confirmar campos após selecionar campos](../media/content-understanding/confirm-fields.png)</br> 
 
5. Na página **selecionar os campos de formulário que você deseja salvar** , ele mostra o número de campos que você selecionou. Selecione **Concluído**.

## <a name="step-4-train-and-test-your-model"></a>Etapa 4: treinar e testar seu modelo

Depois de selecionar os campos que você deseja salvar, a página de **Resumo do modelo** permite treinar e testar o modelo.

1. Na página de **Resumo do modelo** , os campos salvos serão exibidos na seção **campos selecionados** . Selecione **treinar** para começar o treinamento nos seus arquivos de exemplo. Observe que isso pode levar alguns minutos para ser concluído.</br>

     ![Selecionar campos treinar](../media/content-understanding/select-fields-train.png)</br> 

2. Quando você vir a notificação de que o treinamento foi concluído, selecione **ir para a página de detalhes**. 

3. Na página **detalhes do modelo** , você pode optar por testar como funciona o modelo selecionando **teste rápido**. Isso permite que você arraste e solte arquivos para a página e veja se os campos foram detectados.

    ![Confirmar campos](../media/content-understanding/select-fields-train.png)</br> 

2. Quando você vir a notificação de que o treinamento foi concluído, selecione **ir para a página de detalhes**. 

3. Na página **detalhes do modelo** , escolha testar como funciona o modelo selecionando **teste rápido**. Isso permite que você arraste e solte arquivos para a página e veja se os campos foram detectados.

## <a name="step-5-publish-your-model"></a>Etapa 5: publicar seu modelo

1. Se estiver satisfeito com os resultados do modelo, selecione **publicar** para torná-lo disponível para uso.

2. Depois que o modelo for publicado, selecione **usar modelo**. Isso cria um fluxo de PowerAutomate que pode ser executado na biblioteca de documentos do SharePoint e extrai os campos que foram identificados no modelo e, em seguida, selecione **criar fluxo**.
  
3. Quando for concluída, você verá a mensagem **de que o fluxo foi criado com êxito**.
 
## <a name="step-6-use-your-model"></a>Etapa 6: usar o modelo

Após publicar o modelo e criar o fluxo de PowerAutomate, você pode usar o modelo na biblioteca de documentos do SharePoint.

1. Após publicar o modelo, selecione **ir para o SharePoint** para ir para a biblioteca de documentos.

2. No modo de exibição modelo de biblioteca de documentos, observe que os campos selecionados agora são exibidos como colunas.</br>

    ![Modelo de biblioteca de documentos aplicado](../media/content-understanding/doc-lib-view.png)</br> 

3. Observe que o link de informações ao lado de **documentos** avisa que um modelo de processamento de formulários é aplicado a esta biblioteca de documentos.

    ![Botão informações](../media/content-understanding/info-button.png)</br>  

4. Carregar arquivos para sua biblioteca de documentos. Qualquer arquivo que o modelo identifica como o tipo de conteúdo lista os arquivos em seu modo de exibição e exibe os dados extraídos nas colunas.</br>

    ![Concluído](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>Confira também
  
[Documentação da automatização de energia](https://docs.microsoft.com/power-automate/)</br>
[Treinamento: aprimore o desempenho de negócios com o Construtor AI](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
