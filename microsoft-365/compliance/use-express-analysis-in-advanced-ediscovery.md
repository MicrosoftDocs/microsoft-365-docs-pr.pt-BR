---
title: Usar a análise expressa na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 50580099-3dc0-44a1-a9b6-5ca6d396316b
description: Saiba como executar o modo de análise expressa da descoberta eletrônica avançada e, em seguida, exportar os resultados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ccc81ccf4446af3d6e5584924883a1c8049ed962
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034303"
---
# <a name="use-express-analysis-in-advanced-ediscovery-classic"></a>Usar a análise expressa na descoberta eletrônica avançada (clássica) 

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Você pode usar a **análise expressa** para analisar rapidamente um caso e exportar os resultados. 
  
Você pode usar a análise expressa para calcular quase duplicatas e threads de email e calcular temas. Você também pode definir determinados parâmetros para temas, semelhança de documentos e exportar arquivos nas [Configurações avançadas para a análise expressa](use-express-analysis-in-advanced-ediscovery.md#BK_AdvancedSettings).
  
## <a name="run-express-analysis"></a>Executar análise expressa

1. Na guia **análise expressa** (1), selecione um contêiner para habilitar os botões * * Express Analysis * * (2) e **Advanced Settings** . 
    
    ![Captura de tela da página de análise expressa](../media/60009974-5d1f-4971-8ebe-e5ec74e7fd2a.jpg)
  
2. Em **analisar parâmetros**:
    
  - Marque **calcular Near-duplicates e threads de email** se quiser executar a análise. Ele é selecionado por padrão. 
    
  - Marque **calcular temas** para processar todos os arquivos e atribuir temas a eles. Ele é selecionado por padrão. 
    
3. Em **Exportar destino**:
    
  - Verifique **download no computador local** para baixar para o computador local. 
    
  - Se você marcar **exportar para o blob do Azure definido pelo usuário** , também poderá especificar uma URL de contêiner e um token SAS. 
    
    > [!NOTE]
    > Depois que um pacote de exportação é armazenado para o blob do Azure definido pelo usuário, os dados não são mais gerenciados pela descoberta eletrônica avançada. é gerenciado pelo blob do Azure. Isso significa que, se você excluir o caso, os arquivos exportados ainda permanecerão no blob do Azure. 
  
  - **Salvar token SAS para sessão de exportação futura**: se estiver marcada, o token SAS será criptografado no banco de dados interno da descoberta eletrônica avançada para uso futuro.
    
    > [!NOTE]
    > No momento, o token SAS expira após um mês. Se você tentar baixar após mais de um mês, será necessário desfazer a última sessão e exportar novamente. 
  
4. Para iniciar a análise expressa com as configurações padrão, escolha **análise expressa**e a página **status da tarefa** será exibida 
    
    Na página **status da tarefa** , você pode expandir as guias **processo**, **analisar** e **Exportar** para exibir detalhes sobre a execução expressa. 
    
    ![Captura de tela da página de status da tarefa de análise de descoberta eletrônica avançada](../media/bf30ab02-9828-4a6d-a485-0babc2c49ae5.jpg)
  
5. Escolha a página de **Resumo de análise expressa** para listar informações detalhadas sobre a execução. 
    
    Na parte inferior da página de **Resumo de análise expressa** , escolha **baixar última sessão** para baixar os arquivos de análise TP no computador local. Primeiro, você precisará baixar a ferramenta de exportação de descoberta eletrônica e colar a chave de exportação na ferramenta de exportação de descoberta eletrônica. 
    
## <a name="advanced-settings-for-express-analysis"></a>Configurações avançadas para a análise expressa
<a name="BK_AdvancedSettings"> </a>

Opcionalmente, você pode definir **Configurações avançadas** para alterar os parâmetros de análise expressa padrão. 
  
1. Na seção **analisar** : 
    
  - Nos **threads próximos duplicados e email**, insira o valor de **similaridade do documento** ou aceite o padrão de 65%. 
    
  - No **número máximo de temas** , insira ou selecione um valor para o número de temas a serem criados. O padrão é 200. 
    
    > [!NOTE]
    > Aumentar o número de temas afeta o desempenho, bem como a capacidade de um tema generalizar. Quanto maior o número de temas, mais granulares eles são. Por exemplo, se um conjunto de 50 temas incluir um tema como "basquete, Spurs, clipes, Lakers"; 300 temas podem incluir temas separados: "Spurs", "Clippings", "Lakers". Se você não teve conhecimento do tema "basquete" e usar esse recurso para ECA, ver o tema "basquete" pode ser útil. Mas, se o processamento tiver muitos temas, talvez você nunca veja a palavra "basquete" e talvez não saiba que Spurs e recortes são bons temas de basquete para revisar, em vez de itens que entram em inicializações e usados para cabelo. 
  
  - Nos **temas sugeridos** , escolha **Modificar** para sugerir que as palavras do tema controlem o processamento de temas. A descoberta eletrônica avançada se concentrará nessas palavras sugeridas e tentará criar um ou mais temas relevantes, com base nas configurações de "número máximo de temas". 
    
    Por exemplo, se a palavra sugerida for "computador" e você tiver especificado "2" como o "número máximo de temas", a descoberta eletrônica avançada tentará gerar dois temas relacionados à palavra "computador". Os dois temas podem ser "software de computador" e "hardware de computador", por exemplo.
    
    ![Adicionar tema sugerido](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
  - **Modo** Na lista suspensa, selecione uma opção de **temas** : 
    
  - **Criar e aplicar modelo**: calcula temas por modelos de um segmento dos arquivos e, em seguida, distribui arquivos entre eles.
    
  - **Criar modelo**: calcula um modelo de temas de um segmento dos arquivos. O processo de aplicação de divisão de arquivos é feito separadamente em outro momento.
    
  - **Aplicar modelo**: essa opção só será mostrada se um modelo foi criado anteriormente e ainda não foi aplicado. Isso irá dividir os arquivos com base nos temas.
    
2. Na seção **Exportar** : 
    
1. Em **selecionar lote de exportação**:
    
  - Na lista **Exportar lote** , selecione o nome do lote ou exportar os resultados para exportar o lote 01 (o lote padrão). 
    
  - Para exportar resultados para novos arquivos que você adicionou a um caso existente, continue com seu lote atual. Para criar uma sessão no lote, selecione o mesmo número de lote e clique em **criar sessão de exportação** você pode usar essa opção para exportar os mesmos parâmetros que o lote anterior, de forma incremental. 
    
  - Para exportar para um novo lote, clique em **Adicionar** ![ícone](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) de adição e insira um novo nome em **lote** (ou aceite o padrão) e uma descrição na **Descrição em lote**. Clique em **OK**.
    
  - Para editar um nome de lote ou descrição, selecione o nome **em lote de exportação**, clique em](../media/3d613660-7602-4df2-bdb9-14e9ca2f9cf2.png) **Editar** ![ícone de edição e modifique os campos.
    
    > [!NOTE]
    > Depois de executar sessões para um lote de exportação, elas não podem ser excluídas. Além disso, apenas alguns parâmetros podem ser editados depois que a primeira sessão é executada. 
  
  - Para criar um lote de exportação duplicado, escolha o **lote** ![de exportação duplicado crie](../media/3f6d5f59-e842-4946-a493-473528af0119.jpg) um ícone de lote de exportação duplicado e insira um nome e uma descrição para o lote duplicado no painel. 
    
  - Para excluir um lote de exportação, escolha **excluir** ![excluir um ícone](../media/92a9f8e0-d469-48da-addb-69365e7ffb6f.jpg)de lote de exportação.
    
  - Para exibir o histórico de um lote, escolha **Batch history** ![o ícone](../media/a80cc320-d96c-4d91-8884-75fe2cb147e2.jpg)histórico de exibição do histórico de lotes.
    
2. Em definir p **opulation:** selecione **incluir somente os arquivos acima da classificação de recorte de relevância** e/ou **refinar lote de exportação** se quiser ajustar as configurações para o lote de exportação. Se você selecionar **incluir apenas arquivos acima da Pontuação de recorte de relevância**, o **problema** será habilitado, e se a pontuação de relevância do arquivo for maior do que a pontuação de recorte do problema selecionado, o arquivo será exportado. O arquivo será exportado, a menos que seja excluído pelo filtro " **para revisão** . Se você selecionar **refinar lote de exportação**, os botões **de opção de eliminação de duplicação** e **filtro por "para revisão"** estão habilitados. Se **você escolher a eliminação da duplicação**, os arquivos duplicados serão filtrados de acordo com a política definida: [nível de caso (padrão): de cada conjunto de arquivos duplicados em todo o caso, todos exceto um arquivo serão eliminados. Nível do responsáveis: de cada conjunto de arquivos duplicados do mesmo mesmo, todos os arquivos, exceto um, serão eliminados de duplicação. Um registro de todos os arquivos duplicados está disponível na saída para exportação. Se você escolher **Filtrar por "para revisão"** , selecione **Modificar em metadados** para inserir as configurações de campo **"para revisão"**. Selecione **incluir arquivos de entrada**para incluir arquivos de origem no conteúdo do pacote. Você pode desmarcar essa opção para acelerar o processo de exportação. Observe que os arquivos nativos serão exportados em qualquer caso.
    
3. Em **definir metadados**, selecione uma das seguintes opções na lista **Exportar modelo** (uma vez por sessão). 
    
  - **Standard**: conjunto básico de itens de dados, metadados e propriedades. Use essa opção quando a importação de dados já foi processada em descoberta eletrônica avançada e os dados de exportação são carregados em um sistema que já contém os arquivos. Por padrão, as colunas exportar modelo são criadas e preenchidas.
    
  - **All**: conjunto completo de metadados padrão, incluindo todos os dados de processamento, bem como as pontuações de análise e relevância. Este modelo é obrigatório quando a descoberta eletrônica avançada realiza o processamento e os dados de arquivo são carregados para um sistema externo pela primeira vez.
    
  - **Problemas**: selecione **todos os problemas** ou selecione um determinado problema que você criou. 
    
Escolha **OK**para salvar as configurações avançadas, **Restaurar padrões** para usar valores padrão ou **Cancelar** para cancelar a configuração das configurações avançadas. 
  
## <a name="see-also"></a>Confira também
<a name="BK_AdvancedSettings"> </a>

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)

