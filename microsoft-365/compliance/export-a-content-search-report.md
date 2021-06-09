---
title: Exportar um relatório de Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExportReport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 5c8c1db6-d8ac-4dbb-8a7a-f65d452169b9
description: Em vez de exportar os resultados reais de uma Pesquisa de Conteúdo no Centro de Conformidade & segurança no Office 365, você pode exportar um relatório de resultados de pesquisa. O relatório contém um resumo dos resultados da pesquisa e um documento com informações detalhadas sobre cada item que seria exportado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 094e67812b45ab1544d629ba6ddabcd86c70c633
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311563"
---
# <a name="export-a-content-search-report"></a>Exportar um relatório de Pesquisa de conteúdo

Em vez de exportar o conjunto completo de resultados de pesquisa de uma pesquisa de conteúdo no Centro de conformidade do Microsoft 365 (ou de uma pesquisa associada a um caso de Descoberta Básica), você pode exportar os mesmos relatórios gerados ao exportar os resultados reais da pesquisa.
  
Quando você exporta um relatório, os arquivos de relatório são baixados para uma pasta em seu computador local que tem o mesmo nome da Pesquisa de Conteúdo, mas isso é anexado ao _ReportsOnly *.* Por exemplo, se a Pesquisa de Conteúdo for chamada  *ContosoCase0815*, o relatório será baixado para uma pasta chamada *ContosoCase0815_ReportsOnly*. Para uma lista de documentos incluídos no relatório, consulte [O que está incluído no relatório](#whats-included-in-the-report).

## <a name="before-you-export-a-search-report"></a>Antes de exportar um relatório de pesquisa

- Para exportar um relatório de pesquisa, você precisa ter a função de gerenciamento de Pesquisa de Conformidade no Centro de Conformidade & Segurança. Essa função é atribuída por padrão aos grupos de função de Gerenciamento de Descoberta e Gerenciamento de Organização integrados. Para obter mais informações, confira [Atribuir permissões de Descoberta eletrônica](assign-ediscovery-permissions.md).

- Quando você exporta um relatório, os dados são temporariamente armazenados em um local Armazenamento do Azure na nuvem da Microsoft antes de ser baixado para o computador local. Certifique-se de que sua organização possa se conectar ao ponto de extremidade no Azure, que é **\* .blob.core.windows.net** (o caractere curinga representa um identificador exclusivo para sua exportação). Os dados de resultados da pesquisa são excluídos do local de Armazenamento do Azure duas semanas após a criação.

- O computador que você usa para exportar os resultados da pesquisa devem atender aos seguintes requisitos de sistema:

  - Versão mais recente do Windows (32 bits ou 64 bits)

  - Microsoft .NET Framework 4.7

- Você precisa usar um dos seguintes navegadores com suporte para executar a Ferramenta de Exportação de Descoberta e<sup>1</sup>:

  - Microsoft Edge <sup>2</sup>

    OU

  - Internet Explorer 10 e versões posteriores

  > [!NOTE]
  > <sup>1</sup> A Microsoft não fabrica extensões ou complementos de terceiros para ClickOnce aplicativos. Não há suporte para a exportação de resultados de pesquisa usando um navegador sem suporte com extensões ou complementos de terceiros.<br/>
  > <sup>2</sup> Como resultado de alterações recentes no Microsoft Edge, ClickOnce suporte não está mais habilitado por padrão. Para obter instruções sobre como habil ClickOnce suporte no Edge, [consulte Use the eDiscovery Export Tool in Microsoft Edge](configure-edge-to-export-search-results.md).

- Se o tamanho total estimado dos resultados retornados pela pesquisa exceder 2 TB, a exportação dos relatórios falhará. Para exportar os relatórios com êxito, tente restringir o escopo e reprisar a pesquisa para que o tamanho estimado dos resultados seja menor que 2 TB.

- Se os resultados de uma pesquisa são mais antigos do que 7 dias e você envia um trabalho de relatório de exportação, uma mensagem de erro é exibida solicitando que você reprise a pesquisa para atualizar os resultados da pesquisa. Se isso acontecer, cancele a exportação, reprise a pesquisa e inicie a exportação novamente.

- A exportação de relatórios de pesquisa conta com o número máximo de exportações em execução ao mesmo tempo e o número máximo de exportações que um único usuário pode executar. Para obter mais informações sobre limites de exportação, consulte [Exportar resultados da pesquisa de conteúdo.](export-search-results.md#export-limits)
  
## <a name="step-1-generate-the-report-for-export"></a>Etapa 1: Gerar o relatório para exportação

A primeira etapa é preparar o relatório para download no computador que está sendo exportado. Quando você exporta o relatório, os documentos do relatório são carregados em uma área Armazenamento do Azure na nuvem da Microsoft.
  
1. No centro Microsoft 365 de conformidade, selecione a pesquisa de conteúdo da onde você deseja exportar o relatório.
  
2. No menu **Ações** na parte inferior da página de sobrevoo de pesquisa, clique **em Exportar relatório**.

   ![Opção Exportar relatório no menu Ações](../media/ActionMenuExportReport.png)

   A **página de sobrevoo** Exportar relatório é exibida. As opções de relatório de exportação disponíveis para exportar informações sobre a pesquisa dependem se os resultados da pesquisa estão localizados em caixas de correio ou sites ou uma combinação de ambos.
  
3. Em **Opções de saída,** escolha uma das seguintes opções:
  
   ![Exportar opções de saída](../media/ExportOutputOptions.png)

    - **Todos os itens, excluindo aqueles** que têm formato não reconhecedo, são criptografados ou não indexados por outros motivos. Essa opção exporta apenas informações sobre itens indexados.
  
    - Todos os itens, incluindo aqueles que não têm formato não reconhecedo, são criptografados ou **não foram indexados por outros motivos.** Essa opção exporta informações sobre itens indexados e não indexados.
  
    - Somente os itens que têm um formato não reconhecedo, são criptografados ou **não foram indexados por outros motivos.** Essa opção exporta apenas informações sobre itens não índicedos.

4. Configure a **opção Habilitar a duplicação para Exchange conteúdo.**
  
   - Se você selecionar essa opção, a contagem de mensagens duplicadas (antes da des duplicação e após a duplicação) será incluída no relatório de resumo de exportação. Além disso, apenas uma cópia de uma mensagem será incluída no arquivo manifest.xml. Mas o relatório de resultados de exportação conterá uma linha para cada cópia de uma mensagem duplicada para que você possa identificar as caixas de correio que contêm uma cópia da mensagem duplicada. Para obter mais informações sobre os relatórios exportados, consulte [O que está incluído no relatório](#whats-included-in-the-report).

   - Se você não selecionar essa opção, os relatórios de exportação conterão informações sobre todas as mensagens retornadas pela pesquisa, incluindo duplicatas.

     Para obter mais informações sobre a des duplicação e como os itens duplicados são identificados, consulte [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).

5. Clique **em Gerar relatório**.

   Os relatórios de pesquisa estão preparados para download, o que significa que os documentos do relatório são carregados em um local Armazenamento do Azure na nuvem da Microsoft. Isso pode levar alguns minutos.

Consulte a próxima seção para obter instruções para baixar os relatórios de pesquisa exportados.
  
## <a name="step-2-download-the-report"></a>Etapa 2: Baixar o relatório

A próxima etapa é baixar o relatório da área de Armazenamento do Azure para o computador local.

1. Na página **Pesquisa de** conteúdo no centro de conformidade Microsoft 365, selecione a **guia Exportações**
  
   Talvez seja preciso clicar em **Atualizar para** atualizar a lista de trabalhos de exportação para que ela mostre o trabalho de exportação criado. Os trabalhos de relatório de exportação têm o mesmo nome que a pesquisa correspondente **_ReportsOnly** anexado ao nome da pesquisa.
  
2. Selecione o trabalho de exportação que você criou na Etapa 1.

3. Na página **Sobrevoo** Exportar relatório em **Tecla Exportar,** clique **em Copiar para área de transferência**. Use essa chave na etapa 6 para baixar os resultados da pesquisa.
  
   > [!IMPORTANT]
   > Como qualquer pessoa pode instalar e iniciar a ferramenta De Exportação de Descoberta Digital e, em seguida, usar essa chave para baixar o relatório de pesquisa, certifique-se de tomar precauções para proteger essa chave da mesma forma que você protegeria senhas ou outras informações relacionadas à segurança.

4. Na parte superior da página de sobrevoo, clique **em Baixar resultados**.

5. Se você for solicitado a instalar a Ferramenta de Exportação **de Descoberta Digital,** clique em **Instalar**.

6. Na Ferramenta de Exportação de Descoberta **e**, faça o seguinte:

   ![Ferramenta de Exportação de Descoberta Digital](../media/eDiscoveryExportTool.png)

   1. Colar a chave de exportação que você copiou na etapa 3 na caixa apropriada.
  
   2. Clique **em Procurar** para especificar o local onde você deseja baixar os arquivos de relatório de pesquisa.

7. Clique em **Iniciar** para baixar os resultados da pesquisa em seu computador.
  
    A **Ferramenta de Exportação de Descoberta Eletrônica** exibe informações de status sobre o processo de exportação, incluindo uma estimativa do número (e tamanho) dos itens restantes a serem baixados. Quando o processo de exportação estiver concluído, você poderá acessar os arquivos no local onde eles foram baixados.
  
## <a name="whats-included-in-the-report"></a>O que está incluído no relatório

Quando você gera e exporta um relatório sobre os resultados de uma pesquisa de conteúdo, os seguintes documentos são baixados:
  
- **Resumo de exportação:** Um Excel que contém um resumo da exportação. Isso inclui informações como o número de fontes de conteúdo pesquisadas, o número de resultados de pesquisa de cada local de conteúdo, o número estimado de itens, o número real de itens que seriam exportados e o tamanho estimado e real dos itens que seriam exportados.

   Se você incluir itens não índicedos ao exportar o relatório, o número de itens não índicedos será incluído no número total de resultados estimados da pesquisa e no número total de resultados de pesquisa baixados (se você fosse exportar os resultados da pesquisa) listados no relatório de resumo de exportação. Em outras palavras, o número total de itens que seriam baixados é igual ao número total de resultados estimados e ao número total de itens não índicedos.
  
- **Manifesto:** Um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa. Se você habilitar a opção de des duplicação, a mensagem duplicada não será incluída no arquivo de manifesto.

- **Resultados:** Um Excel que contém uma linha com informações sobre cada item indexado que seria exportado com os resultados da pesquisa. Para emails, o log do resultado contém informações sobre cada mensagem, incluindo: 

  - O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).

  - A data na qual a mensagem foi enviada ou recebida.

  - A linha de assunto da mensagem.

  - O remetente e os destinatários da mensagem.

  Para documentos de SharePoint sites OneDrive for Business, o log de resultados contém informações sobre cada documento, incluindo:

  - A URL para o documento.

  - A URL para o conjunto de sites onde o documento está localizado.

  - A data em que o documento foi modificado pela última vez.

  - O nome do documento (que está localizado na coluna Assunto no log de resultados).

  > [!NOTE]
  > O número de linhas  no relatório Resultados deve ser igual ao número total de resultados da pesquisa menos o número total de itens listados no relatório Itens Não **Índicedos.**
  
- **Trace.log**: um log de rastreamento que contém informações detalhadas sobre o processo de exportação e pode ajudar a descobrir problemas durante a exportação. Se você abrir um tíquete com o Suporte da Microsoft sobre um problema relacionado à exportação de relatórios de pesquisa, talvez seja solicitado a fornecer esse log de rastreamento.

- **Itens não índicedos:** Um Excel que contém informações sobre todos os itens não indexados incluídos nos resultados da pesquisa. Se você não incluir itens não índicedos ao gerar o relatório de resultados da pesquisa, esse relatório ainda será baixado, mas estará vazio.
