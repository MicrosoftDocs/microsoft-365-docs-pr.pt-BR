---
title: Exportar resultados de Pesquisa de conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: Exporte os resultados da pesquisa de uma pesquisa de conteúdo no Microsoft 365 de conformidade para um computador local. Os resultados do email são exportados como arquivos PST. O conteúdo SharePoint e OneDrive for Business sites são exportados como documentos Office nativos.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b5e900d44e59c2c37263c1162a7e631b1635cb06
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311938"
---
# <a name="export-content-search-results"></a>Exportar resultados de Pesquisa de conteúdo

Depois que uma pesquisa de conteúdo for realizada com êxito, você poderá exportar os resultados da pesquisa para um computador local. Quando você exporta os resultados de email, eles são baixados para seu computador como arquivos PST. Quando você exporta conteúdo de sites SharePoint e OneDrive for Business, cópias de documentos Office nativos são exportadas. Há outros documentos e relatórios incluídos nos resultados de pesquisa exportados.
  
Exportar os resultados de uma pesquisa de conteúdo envolve a preparação dos resultados e, em seguida, baixá-los para um computador local.
  
## <a name="before-you-export-search-results"></a>Antes de exportar resultados de pesquisa

- Para exportar os resultados da pesquisa, você precisa ter a função de gerenciamento Exportar no Centro de Conformidade & Segurança. Essa função é atribuída ao grupo de função do Gerente de Descoberta Eletrônica interno. Ela não é atribuída por padrão ao grupo de funções Gerenciamento da Organização. Para obter mais informações, confira [Atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).

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
  
- Recomendamos baixar os resultados da pesquisa para um computador local. Para eliminar a infraestrutura de firewall ou proxy da sua empresa de causar problemas ao baixar os resultados da pesquisa, você pode considerar baixar os resultados da pesquisa para uma área de trabalho virtual fora da sua rede. Isso pode diminuir os tempos-de-tempo que ocorrem nas conexões de dados do Azure ao exportar um grande número de arquivos. Para obter mais informações sobre áreas de trabalho virtuais, [consulte Windows Área de Trabalho Virtual](https://azure.microsoft.com/services/virtual-desktop).

- Para melhorar o desempenho ao baixar resultados da pesquisa, considere dividir pesquisas que retornam um grande conjunto de resultados em pesquisas menores. Por exemplo, você pode usar intervalos de datas em consultas de pesquisa para retornar um conjunto menor de resultados que podem ser baixados mais rapidamente.
  
- Quando você exporta os resultados da pesquisa, os dados são temporariamente armazenados em um local de Armazenamento do Azure fornecido pela Microsoft na nuvem da Microsoft antes que eles são baixados para o computador local. Certifique-se de que sua organização possa se conectar ao ponto de extremidade no Azure, que é **\* .blob.core.windows.net** (o caractere curinga representa um identificador exclusivo para sua exportação). Os dados de resultados da pesquisa são excluídos do local de Armazenamento do Azure duas semanas após a criação. 
  
- Se sua organização usa um servidor proxy para se comunicar com a Internet, você precisará definir as configurações do servidor proxy no computador que você usa para exportar os resultados da pesquisa (para que a ferramenta de exportação possa ser autenticada pelo servidor proxy). Para fazer isso, abra o *arquivomachine.config* no local que corresponde à sua versão do Windows. 
  
  - **32 bits:**`%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64 bits:**`%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    Adicione as linhas a seguir ao arquivo  *machine.config*  em algum lugar entre  `<configuration>` as marcas  `</configuration>` e. Certifique-se de  `ProxyServer` substituir e pelos valores  `Port` corretos para sua organização; por exemplo, `proxy01.contoso.com:80` . 
  
    ```xml
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="https://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

- Se os resultados de uma pesquisa de conteúdo são mais antigos do que 7 dias e você envia um trabalho de exportação, uma mensagem de erro é exibida solicitando que você reprise a pesquisa para atualizar os resultados da pesquisa. Se isso acontecer, cancele a exportação, reprise a pesquisa e inicie a exportação novamente.

## <a name="step-1-prepare-search-results-for-export"></a>Etapa 1: Preparar resultados da pesquisa para exportação

A primeira etapa é preparar os resultados da pesquisa para a exportação. Quando você prepara os resultados, eles são carregados em um local de Armazenamento do Azure fornecido pela Microsoft na nuvem da Microsoft. O conteúdo de caixas de correio e sites é carregado com uma taxa máxima de 2 GB por hora.
  
1. No centro Microsoft 365 de conformidade, selecione a pesquisa de conteúdo da onde você deseja exportar resultados.
  
2. No menu **Ações** na parte inferior da página de sobrevoo, clique em **Exportar resultados**.

   ![Opção Exportar resultados no menu Ações](../media/ActionMenuExportResults.png)

   A **página de sobrevoo** Exportar resultados é exibida. As opções de exportação disponíveis para exportar conteúdo dependem se os resultados da pesquisa estão localizados em caixas de correio ou sites ou uma combinação de ambos.

3. Em **Opções de saída,** escolha uma das seguintes opções:
  
   ![Exportar opções de saída](../media/ExportOutputOptions.png)

    - **Todos os itens, excluindo aqueles** que têm formato não reconhecedo, são criptografados ou não indexados por outros motivos. Essa opção exporta apenas itens indexados.
  
    - Todos os itens, incluindo aqueles que não têm formato não reconhecedo, são criptografados ou **não foram indexados por outros motivos.** Essa opção exporta itens indexados e não indexados.
  
    - Somente os itens que têm um formato não reconhecedo, são criptografados ou **não foram indexados por outros motivos.** Essa opção exporta apenas itens não índicedos.

      Consulte a [seção Mais informações](#more-information) para obter uma descrição sobre como os itens parcialmente indexados são exportados. Para obter mais informações sobre itens parcialmente indexados, consulte [Itens parcialmente indexados na pesquisa de conteúdo](partially-indexed-items-in-content-search.md).

4. Em **Exportar Exchange conteúdo como**, escolha uma das seguintes opções:
  
   ![Exchange opções](../media/ExchangeExportOptions.png)

    - **Um arquivo PST para cada caixa de correio:** exporta um arquivo PST para cada caixa de correio de usuário que contém resultados de pesquisa. Todos os resultados da caixa de correio de arquivo morto do usuário são incluídos no mesmo arquivo PST. Essa opção reproduz a estrutura da pasta de caixa de correio da caixa de correio de origem.
  
    - **Um arquivo PST** contendo todas as mensagens : exporta um único arquivo PST (chamado *Exchange.pst*) que contém os resultados da pesquisa de todas as caixas de correio de origem incluídas na pesquisa. Essa opção reproduz a estrutura da pasta de caixa de correio para cada mensagem.
  
    - **Um arquivo PST que contém** todas as mensagens em uma única pasta : exporta os resultados da pesquisa para um único arquivo PST onde todas as mensagens estão localizadas em uma única pasta de nível superior. Essa opção permite que os revisadores revisem itens em ordem cronológica (os itens são classificação por data de enviado) sem precisar navegar na estrutura de pasta de caixa de correio original para cada item.
  
    - **Mensagens individuais**: Exporta resultados de pesquisa como mensagens de email individuais, usando o formato .msg. Se você selecionar essa opção, os resultados da pesquisa de email serão exportados para uma pasta no sistema de arquivos. O caminho da pasta para mensagens individuais é o mesmo usado se você exportou os resultados para um arquivo PST.
  
5. Configure as seguintes opções adicionais:

   ![Exchange opções](../media/OtherExportOptions.png)

   1. Selecione a **caixa de seleção Habilitar a duplicação de Exchange conteúdo** para excluir mensagens duplicadas.
  
      Se você selecionar essa opção, apenas uma cópia de uma mensagem será exportada mesmo que várias cópias da mesma mensagem sejam encontradas nas caixas de correio pesquisadas. O relatório de resultados de exportação (que é um arquivo chamado Results.csv) conterá uma linha para cada cópia de uma mensagem duplicada para que você possa identificar as caixas de correio (ou pastas públicas) que contêm uma cópia da mensagem duplicada. Para obter mais informações sobre a des duplicação e como os itens duplicados são identificados, consulte [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).
  
   2. Marque a **caixa de seleção Incluir versões SharePoint arquivos** para exportar todas as versões de SharePoint documentos. Essa opção será exibida somente se as fontes de conteúdo da pesquisa incluirem SharePoint ou OneDrive for Business sites.
  
   3. Selecione a **pasta Exportar arquivos em uma pasta compactada (compactada). Inclui apenas mensagens individuais e SharePoint caixa** de seleção de documentos para exportar resultados de pesquisa para pastas compactadas. Essa opção aparece somente quando você escolhe exportar Exchange itens como mensagens individuais e quando os resultados da pesquisa incluem SharePoint ou OneDrive documentos. Essa opção é usada principalmente para trabalhar em torno do limite de 260 caracteres Windows nomes de caminho de arquivo quando os itens são exportados. Consulte a seção "Nomes de arquivo de itens exportados" na [seção Mais](#more-information) informações.
  
6. Clique **em Exportar** para iniciar o processo de exportação. Os resultados da pesquisa estão preparados para download, o que significa que eles são coletados dos locais de conteúdo original e, em seguida, carregados para um local de Armazenamento do Azure na nuvem da Microsoft. Isso pode levar alguns minutos.

Consulte a próxima seção para obter instruções para baixar os resultados de pesquisa exportados.
  
## <a name="step-2-download-the-search-results"></a>Etapa 2: Baixar os resultados da pesquisa

A próxima etapa é baixar os resultados da pesquisa do local de Armazenamento do Azure para o computador local.
  
1. Na página **Pesquisa de** conteúdo no centro de conformidade Microsoft 365, selecione a **guia Exportações**
  
   Talvez seja preciso clicar em **Atualizar para** atualizar a lista de trabalhos de exportação para que ela mostre o trabalho de exportação criado. Os trabalhos de exportação têm o mesmo nome da pesquisa correspondente **_Export** anexado ao nome da pesquisa.
  
2. Selecione o trabalho de exportação que você criou na Etapa 1.

3. Na página sub-sub-texto em **Tecla Exportar,** clique **em Copiar para área de transferência**. Use essa chave na etapa 6 para baixar os resultados da pesquisa.
  
   > [!IMPORTANT]
   > Como qualquer pessoa pode instalar e iniciar a Ferramenta de Exportação de Descoberta Eletrônica e, em seguida, usar essa chave para baixar os resultados da pesquisa, tenha o cuidado de proteger essa chave exatamente como faria com senhas ou outras informações relacionadas à segurança. 

4. Na parte superior da página de sobrevoo, clique **em Baixar resultados**.

5. Se você for solicitado a instalar a Ferramenta de Exportação **de Descoberta Digital,** clique em **Instalar**.

6. Na Ferramenta de Exportação de Descoberta **e**, faça o seguinte:

   ![Ferramenta de Exportação de Descoberta Digital](../media/eDiscoveryExportTool.png)

   1. Colar a chave de exportação que você copiou na etapa 3 na caixa apropriada.
  
   2. Clique em **Procurar** para especificar o local onde deseja baixar os arquivos de resultado da pesquisa.
  
      > [!IMPORTANT]
      >  Devido à alta atividade de rede durante o download, você deve baixar os resultados da pesquisa apenas para um local em uma unidade interna em seu computador local. Para a melhor experiência de download, siga estas diretrizes: <br/>
      >- Não baixe os resultados da pesquisa para um caminho UNC, uma unidade de rede mapeada, uma unidade USB externa ou uma conta OneDrive for Business sincronizada.<br/>
      >- Desabilite a verificação de antivírus para a pasta para a que você baixa o resultado da pesquisa.<br/>
      >- Baixe os resultados da pesquisa em pastas diferentes para trabalhos de download simultâneos.

6. Clique em **Iniciar** para baixar os resultados da pesquisa em seu computador.
  
    A **Ferramenta de Exportação de Descoberta Eletrônica** exibe informações de status sobre o processo de exportação, incluindo uma estimativa do número (e tamanho) dos itens restantes a serem baixados. Quando o processo de exportação estiver concluído, você poderá acessar os arquivos no local onde eles foram baixados.

## <a name="more-information"></a>Mais informações

Veja mais informações sobre a exportação de resultados da pesquisa.
  
[Limites de exportação](#export-limits)
  
[Exportar relatórios](#export-reports)
  
[Exportando itens parcialmente indexados](#exporting-partially-indexed-items)

[Exportando mensagens individuais ou arquivos PST](#exporting-individual-messages-or-pst-files)

[Descriptografando mensagens de email protegidas por RMS e anexos de arquivo criptografados](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[Nomes de arquivos de itens exportados](#filenames-of-exported-items)  
  
[Miscellaneous](#miscellaneous)
  
### <a name="export-limits"></a>Limites de exportação

Para obter informações sobre limites ao exportar resultados da pesquisa de conteúdo, consulte a seção "Limites de exportação" em [Limites para pesquisa de conteúdo.](limits-for-content-search.md#export-limits)

### <a name="export-reports"></a>Exportar relatórios
  
- Quando você exporta os resultados da pesquisa, os relatórios a seguir são incluídos além dos resultados da pesquisa.
  
  - **Resumo de Exportação** Um Excel que contém um resumo da exportação. Isso inclui informações como o número de fontes de conteúdo pesquisadas, os tamanhos estimados e baixados dos resultados da pesquisa e o número estimado e baixado de itens que foram exportados.
  
  - **Manifesto** Um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa.
  
  - **Resultados** Um Excel que contém informações sobre cada item que é baixado como resultado da pesquisa. Para emails, o log do resultado contém informações sobre cada mensagem, incluindo:
  
    - O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).
  
    - A data na qual a mensagem foi enviada ou recebida.

    - A linha de assunto da mensagem.

    - O remetente e os destinatários da mensagem.

    - Se a mensagem é uma mensagem duplicada se você habilitar a opção de des duplicação ao exportar os resultados da pesquisa. As mensagens duplicadas têm um valor na coluna **Duplicar para Item** que identifica a mensagem como uma duplicata. O valor na coluna **Duplicar para Item** contém a identidade do item da mensagem que foi exportada. Para obter mais informações, consulte [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).

      Para documentos de SharePoint sites OneDrive for Business, o log de resultados contém informações sobre cada documento, incluindo:

      - A URL para o documento.

      - A URL para o conjunto de sites onde o documento está localizado.

      - A data em que o documento foi modificado pela última vez.

      - O nome do documento (que está localizado na coluna Assunto no log de resultados).

  - **Itens nãoindexados** Um Excel que contém informações sobre todos os itens parcialmente indexados que seriam incluídos nos resultados da pesquisa. Se você não incluir itens parcialmente indexados ao gerar o relatório de resultados da pesquisa, esse relatório ainda será baixado, mas estará vazio.

  - **Erros e avisos** Contém erros e avisos para arquivos encontrados durante a exportação. Consulte a coluna Detalhes do Erro para obter informações específicas de cada erro ou aviso individual.

  - **Itens ignorados** Quando você exporta resultados de pesquisa de SharePoint sites OneDrive for Business, a exportação geralmente incluirá um relatório de itens ignorados (SkippedItems.csv). Os itens citados neste relatório geralmente são itens que não serão baixados, como uma pasta ou um conjunto de documentos. Não exportar esses tipos de itens é por design. Para outros itens ignorados, o campo "Tipo de Erro" e "Detalhes de Erro" no relatório de itens ignorados mostram o motivo pelo qual o item foi ignorado e não foi baixado com os outros resultados da pesquisa.

  - **Trace.log** Contém informações detalhadas sobre o processo de exportação e pode ajudar a descobrir problemas durante a exportação. Se você abrir um tíquete com o Suporte da Microsoft sobre um problema relacionado à exportação de resultados da pesquisa, talvez seja solicitado a fornecer esse log de rastreamento.
  
    > [!NOTE]
    > Você pode simplesmente exportar esses documentos sem precisar exportar os resultados reais da pesquisa. Consulte [Exportar um relatório de pesquisa de conteúdo](export-a-content-search-report.md).
  
### <a name="exporting-partially-indexed-items"></a>Exportando itens parcialmente indexados
  
- Se você estiver exportando itens de caixa de correio de uma pesquisa de conteúdo que retorna todos os itens de caixa de correio nos resultados da pesquisa (porque nenhuma palavra-chave incluída na consulta de pesquisa), os itens parcialmente indexados não serão copiados para o arquivo PST que contém os itens não indexados. Isso acontece porque todos os itens, incluindo itens parcialmente indexados, são incluídos automaticamente nos resultados regulares da pesquisa. Isso significa que os itens parcialmente indexados serão incluídos em um arquivo PST (ou como mensagens individuais) que contém os outros itens indexados.

    Se você exportar os itens indexados e parcialmente indexados ou se você exportar apenas os itens indexados de uma pesquisa de conteúdo que retorna todos os itens, o mesmo número de itens será baixado. Isso acontece mesmo que os resultados estimados da pesquisa de conteúdo (exibidos nas estatísticas de pesquisa no Centro de Conformidade e Segurança) ainda incluam uma estimativa separada para o número de itens parcialmente & indexados. Por exemplo, digamos que a estimativa de uma pesquisa que inclua todos os itens (sem palavras-chave na consulta de pesquisa) mostra que 1.000 itens foram encontrados e que 200 itens parcialmente indexados também foram encontrados. Nesse caso, os 1.000 itens incluem os itens parcialmente indexados porque a pesquisa retorna todos os itens. Em outras palavras, há 1.000 itens totais retornados pela pesquisa e não 1.200 itens (como você pode esperar). Se você exportar os resultados dessa pesquisa e optar por exportar itens indexados e parcialmente indexados (ou exportar apenas itens parcialmente indexados), 1.000 itens serão baixados. Novamente, isso acontece porque itens parcialmente indexados são incluídos nos resultados regulares (indexados) quando você usa uma consulta de pesquisa em branco para retornar todos os itens. Neste mesmo exemplo, se você optar por exportar apenas itens parcialmente indexados, apenas os 200 itens não indexados serão baixados.

    Observe também que, no exemplo anterior (quando você exporta itens indexados e  parcialmente indexados ou exporta apenas itens indexados), o relatório Resumo de Exportação incluído nos resultados da pesquisa exportada listaria 1.000 itens estimados e 1.000 itens baixados pelos mesmos motivos descritos anteriormente. 

- Se a pesquisa de que você está exportando resultados foi uma pesquisa de locais de conteúdo específicos ou de todos os locais de conteúdo em sua organização, apenas os itens parciais de locais de conteúdo que contêm itens que corresponderem aos critérios de pesquisa serão exportados. Em outras palavras, se nenhum resultado de pesquisa for encontrado em uma caixa de correio ou site, os itens parcialmente indexados nessa caixa de correio ou site não serão exportados. O motivo disso é que a exportação de itens parcialmente indexados de muitos locais na organização pode aumentar a probabilidade de erros de exportação e aumentar o tempo necessário para exportar e baixar os resultados da pesquisa.

    Para exportar itens parcialmente indexados de todos os locais de conteúdo para uma pesquisa, configure a pesquisa para retornar todos os itens (removendo todas as palavras-chave da consulta de pesquisa) e exporte apenas itens parcialmente indexados quando você exportar os resultados da pesquisa.

    ![Use a terceira opção de exportação para exportar apenas itens não índicedos](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- Ao exportar resultados de pesquisa de sites SharePoint ou OneDrive for Business, a capacidade de exportar itens não indexados também depende da opção de exportação selecionada e se um site que foi pesquisado contém um item indexado que corresponde aos critérios de pesquisa. Por exemplo, se você pesquisar sites específicos SharePoint ou OneDrive for Business e nenhum resultado de pesquisa for encontrado, nenhum item não indexado desses sites será exportado se você escolher a segunda opção de exportação para exportar itens indexados e não indexados. Se um item indexado de um site corresponder aos critérios de pesquisa, todos os itens não indexados desse site serão exportados ao exportar itens indexados e não indexados. A ilustração a seguir descreve as opções de exportação com base em se um site contém um item indexado que corresponde aos critérios de pesquisa.

    ![Escolha a opção de exportação com base em se um site contém um item indexado que corresponde aos critérios de pesquisa](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    a. Somente itens indexados que corresponderem aos critérios de pesquisa são exportados. Nenhum item parcialmente indexado é exportado.

    b. Se nenhum item indexado de um site corresponder aos critérios de pesquisa, os itens parcialmente indexados desse mesmo site não serão exportados. Se os itens indexados de um site são retornados nos resultados da pesquisa, os itens parcialmente indexados desse site são exportados. Em outras palavras, apenas os itens parcialmente indexados de sites que contêm itens que corresponderem aos critérios de pesquisa são exportados.

    c. Todos os itens parcialmente indexados de todos os sites na pesquisa são exportados, independentemente de um site conter itens que corresponderem aos critérios de pesquisa.

    Se você optar por exportar itens parcialmente indexados, os itens de caixa de correio parcialmente indexados serão exportados em um arquivo PST separado, independentemente da opção escolhida em Exportar Exchange **conteúdo como**.

- Se os itens parcialmente indexados são retornados nos resultados da pesquisa (porque outras propriedades de itens parcialmente indexados corresponderam aos critérios de pesquisa), esses parcialmente indexados são exportados com os resultados regulares da pesquisa. Portanto, se você optar por exportar itens indexados e itens parcialmente indexados (selecionando todos os itens, incluindo aqueles que têm formato não **registrado,** são criptografados ou não indexados por outros motivos de exportação), os itens parcialmente indexados exportados com os resultados regulares serão listados no relatório de Results.csv. Eles não serão listados no relatório de items.csv não items.csv.
  
### <a name="exporting-individual-messages-or-pst-files"></a>Exportando mensagens individuais ou arquivos PST
  
- Se o nome do caminho do arquivo de uma mensagem exceder o limite máximo de caracteres para Windows, o nome do caminho do arquivo será truncado. Mas o nome do caminho do arquivo original será listado no Manifesto e ResultsLog.
  
- Conforme explicado anteriormente, os resultados da pesquisa de email são exportados para uma pasta no sistema de arquivos. O caminho da pasta para mensagens individuais replicaria o caminho da pasta na caixa de correio do usuário. Por exemplo, para uma pesquisa chamada "ContosoCase101" mensagens na caixa de entrada de um usuário estaria localizada no caminho da pasta  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` .

- Se você optar por exportar mensagens de email em um arquivo PST contendo todas as mensagens em uma única pasta, uma pasta **Itens** Excluídos e uma pasta Pastas de Pesquisa serão **incluídas** no nível superior da pasta PST. Essas pastas estão vazias.

- Conforme mencionado anteriormente, você deve exportar resultados de pesquisa de email como mensagens individuais para descriptografar mensagens protegidas por RMS quando elas são exportadas. As mensagens criptografadas permanecerão criptografadas se você exportar os resultados da pesquisa de email como um arquivo PST.
  
### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>Descriptografando mensagens de email protegidas por RMS e anexos de arquivo criptografados

Todas as mensagens de email protegidas por direitos (protegidas por RMS) incluídas nos resultados de uma pesquisa de conteúdo serão descriptografadas ao exportá-las. Além disso, qualquer arquivo criptografado com uma tecnologia de criptografia [da Microsoft](encryption.md) e anexado a uma mensagem de email incluída nos resultados da pesquisa também será descriptografado quando exportado. Essa funcionalidade de descriptografia é habilitada por padrão para membros do grupo de funções do Gerenciador de Descobertas E. Isso porque a função de gerenciamento de descriptografia RMS é atribuída a esse grupo de funções por padrão. Lembre-se das seguintes coisas ao exportar mensagens de email criptografadas e anexos:
  
- Conforme explicado anteriormente, para descriptografar mensagens protegidas por RMS ao exportá-las, você precisa exportar os resultados da pesquisa como mensagens individuais. Se você exportar resultados de pesquisa para um arquivo PST, as mensagens protegidas por RMS permanecerão criptografadas.

- As mensagens descriptografadas são identificadas no relatório **ResultsLog.** Este relatório contém uma coluna chamada Status de **Decodificação** e um valor **de Decodificado** nesta coluna identifica as mensagens que foram descriptografadas.

- Além de descriptografar anexos de arquivo ao exportar resultados de pesquisa, você também pode visualizar o arquivo descriptografado ao visualizar os resultados da pesquisa. Você só pode exibir a mensagem de email protegida por direitos depois de exportá-la.

- Neste momento, o recurso de descriptografia ao exportar resultados de pesquisa não inclui conteúdo criptografado de sites SharePoint e OneDrive for Business. No entanto, o suporte está chegando em breve para documentos criptografados com tecnologias de criptografia da Microsoft e armazenados no SharePoint Online e OneDrive for Business.

- Se você precisar impedir que alguém descriptografe mensagens protegidas por RMS e anexos de arquivo criptografados, você precisará criar um grupo de função personalizado (copiando o grupo de função do Gerenciador de Descobertas Escrivante integrado) e, em seguida, remover a função de gerenciamento de descriptografia RMS do grupo de função personalizado. Em seguida, adicione a pessoa que você não deseja descriptografar mensagens como membro do grupo de função personalizado.
  
### <a name="filenames-of-exported-items"></a>Nomes de arquivos de itens exportados
  
- Há um limite de 260 caracteres (imposto pelo sistema operacional) para o nome completo do caminho para mensagens de email e documentos de site exportados para o computador local. O nome completo do caminho para itens exportados inclui o local original do item e o local da pasta no computador local para o qual os resultados da pesquisa são baixados. Por exemplo, se você especificar para baixar os resultados da pesquisa na ferramenta Exportação de Descoberta Eletrônico, o nome completo do caminho para um item de email baixado  `C:\Users\Admin\Desktop\SearchResults` será  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` .

- Se o limite de 260 caracteres for excedido, o nome de caminho completo de um item será truncado, com base no seguinte:

  - Se o nome do caminho completo tiver mais de 260 caracteres, o nome do arquivo será reduzido para ficar abaixo do limite; observe que o nome de arquivo truncado (excluindo a extensão de arquivo) não terá menos de oito caracteres.

  - Se o nome completo do caminho ainda for muito longo depois de reduzir o nome do arquivo, o item será movido de seu local atual para a pasta pai. Se o nome do caminho ainda for muito longo, o processo será repetido: reduza o nome do arquivo e, se necessário, mova-se novamente para a pasta pai. Esse processo é repetido até que o nome completo do caminho está sob o limite de 260 caracteres.

  - Se um nome de caminho completo truncado já existir, um número de versão será adicionado ao final do nome do arquivo; por exemplo, `statusmessage(2).msg` .

    Para ajudar a atenuar esse problema, considere baixar os resultados da pesquisa para um local com um nome de caminho curto; por exemplo, baixar resultados de pesquisa para uma pasta chamada adicionaria menos caracteres aos nomes de caminho de itens exportados do que baixá-los  `C:\Results` para uma pasta chamada  `C:\Users\Admin\Desktop\Results` .

- Quando você exporta documentos de site, também é possível que o nome de arquivo original de um documento seja modificado. Isso acontece especificamente para documentos que foram excluídos de um site SharePoint ou OneDrive for Business que foi colocado em espera. Depois que um documento que está em um site que está em espera é excluído, o documento excluído é movido automaticamente para a biblioteca de Reter preservação do site (que foi criada quando o site foi colocado em espera). Quando o documento excluído é movido para a biblioteca de Reter Preservação, uma ID exclusiva e gerada aleatoriamente é anexada ao nome de arquivo original do documento. Por exemplo, se o nome do arquivo de um documento for e esse documento for posteriormente excluído e movido para a biblioteca de Reter Preservação, o nome do arquivo do documento movido para a biblioteca de Reter Preservação será modificado para algo como  `FY2017Budget.xlsx`  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` . Se um documento na biblioteca de Preservação de Espera corresponde à consulta de uma pesquisa de Conteúdo e você exporta os resultados dessa pesquisa, o arquivo exportado tem o nome de arquivo modificado; neste exemplo, o nome do arquivo do documento exportado seria  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` .

    Quando um documento em um site que está em espera é modificado (e o versioning para a biblioteca de documentos no site foi habilitado), uma cópia do arquivo é criada automaticamente na biblioteca de Suspensão de Preservação. Nesse caso, uma ID gerada aleatoriamente e exclusiva também é anexada ao nome do arquivo do documento copiado para a biblioteca de Ressalto de Preservação.

    O motivo pelo qual nomes de arquivo de documentos que são movidos ou copiados para a biblioteca de Espera de Preservação é para evitar nomes de arquivo conflitantes. Para obter mais informações sobre como colocar uma responsabilidade nos sites e na biblioteca de Preservação de Espera, consulte [Overview of in-place hold in-place in SharePoint Server 2016](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95).

### <a name="miscellaneous"></a>Diversos
  
- Ao baixar os resultados da pesquisa usando a Ferramenta de Exportação de Descoberta Armazenamento, é possível que você receba o seguinte erro: Este é um erro transitório, que normalmente ocorre no local de Armazenamento `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` do Azure. Para resolver esse problema, baixe novamente [os](#step-2-download-the-search-results)resultados da pesquisa , que reiniciarão a Ferramenta de Exportação de Descoberta e.

- Todos os resultados da pesquisa e os relatórios de exportação são incluídos em uma pasta que tem o mesmo nome da pesquisa conteúdo. As mensagens de email que foram exportadas estão localizadas em uma pasta chamada **Exchange**. Os documentos estão localizados em uma pasta chamada **SharePoint**.

- Os metadados do sistema de arquivos para documentos SharePoint sites OneDrive for Business são mantidos quando os documentos são exportados para o computador local. Isso significa as propriedades do documento, tais como data de criação e última modificação, não são alteradas quando os documentos são exportados.

- Se os resultados da pesquisa incluirem um item de lista do SharePoint que corresponde à consulta de pesquisa, todas as linhas da lista serão exportadas, além do item que corresponde à consulta de pesquisa e a todos os anexos da lista. O motivo desse comportamento é fornecer um contexto para itens de lista retornados nos resultados da pesquisa. Os itens de lista adicionais e anexos podem fazer com que a contagem de itens exportados seja diferente da estimativa original dos resultados da pesquisa.
