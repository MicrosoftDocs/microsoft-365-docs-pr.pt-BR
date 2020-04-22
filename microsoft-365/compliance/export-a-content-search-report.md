---
title: Exportar um relatório de Pesquisa de Conteúdo
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
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
description: Em vez de exportar os resultados reais de uma pesquisa de conteúdo no centro de conformidade & segurança no Office 365, você pode exportar um relatório de resultados de pesquisa. O relatório contém um resumo dos resultados da pesquisa e um documento com informações detalhadas sobre cada item que seria exportado.
ms.openlocfilehash: 63acc8701973519f959ced9822333e893e6fd863
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43615925"
---
# <a name="export-a-content-search-report"></a>Exportar um relatório de Pesquisa de Conteúdo

Em vez de exportar o conjunto completo de resultados de pesquisa de uma pesquisa de conteúdo no centro de conformidade de & de segurança (e de uma pesquisa de conteúdo associada a uma ocorrência de descoberta eletrônica), você pode exportar os mesmos relatórios gerados ao exportar os resultados da pesquisa.
  
Quando você exporta um relatório, ele é baixado para uma pasta que tem o mesmo nome da pesquisa de conteúdo, mas que é acrescentado com *_ReportsOnly*. Por exemplo, se a pesquisa de conteúdo for chamada de *ContosoCase0815*, o relatório será baixado para uma pasta chamada *ContosoCase0815_ReportsOnly*. Para obter uma lista de documentos incluídos no relatório, confira o [que está incluído no relatório](#whats-included-in-the-report).

## <a name="before-you-begin"></a>Antes de começar

- Para exportar um relatório de pesquisa de conteúdo, você precisa ter a função de gerenciamento de pesquisa de conformidade no centro de conformidade de segurança &. Essa função é atribuída ao Gerenciador de descoberta eletrônica interno e aos grupos de função de gerenciamento da organização. Ela não é atribuída por padrão ao grupo de funções Gerenciamento da Organização. Para obter mais informações, confira [Atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).
    
- Quando você exporta um relatório, os dados são temporariamente armazenados em uma área de armazenamento exclusiva do Azure na nuvem da Microsoft antes de ele ser baixado para o computador local. Certifique-se de que sua organização possa se conectar ao ponto de extremidade no Azure, que é ** \*. blob.Core.Windows.net** (o caractere curinga representa um identificador exclusivo para sua exportação). Os dados dos resultados da pesquisa são excluídos da área de armazenamento do Azure duas semanas após sua criação. 
    
- O computador que você usa para exportar os resultados da pesquisa devem atender aos seguintes requisitos de sistema:
    
  - versões de 32 bits ou 64 bits do Windows 7 e versões posteriores
    
  - Microsoft .NET Framework 4,7
    
- Você precisa usar um dos seguintes navegadores suportados para executar a ferramenta de exportação de descoberta eletrônica<sup>1</sup>:

  - Microsoft Edge <sup>2</sup>

    OU

  - Microsoft Internet Explorer 10 e versões posteriores

  > [!NOTE]
  > <sup>1</sup> a Microsoft não fabrica extensões ou complementos de terceiros para aplicativos ClickOnce. Não há suporte para a exportação de resultados de pesquisa usando um navegador sem suporte com extensões ou complementos de terceiros.<br/>
  > <sup>2</sup> como resultado de alterações recentes no Microsoft Edge, o suporte do ClickOnce não está mais habilitado por padrão. Para obter instruções sobre como habilitar o suporte do ClickOnce no Edge, consulte [usar a ferramenta de exportação de descoberta eletrônica no Microsoft Edge](configure-edge-to-export-search-results.md).

- Se o tamanho total estimado dos resultados retornados por uma pesquisa de conteúdo exceder 2 TB, a exportação do relatório falhará. Para exportar o relatório com êxito, tente restringir o escopo e executar novamente a pesquisa para que o tamanho estimado dos resultados seja menor que 2 TB.

- A exportação de relatórios de pesquisa de conteúdo conta com o número máximo de exportações em execução ao mesmo tempo e o número máximo de exportações que um único usuário pode executar. Para obter mais informações sobre limites de exportação, consulte [Exportar resultados de pesquisa de conteúdo](export-search-results.md#export-limits).

## <a name="generate-and-download-a-content-search-report"></a>Gerar e baixar um relatório de pesquisa de conteúdo

As etapas para gerar e baixar um relatório de pesquisa de conteúdo são semelhantes à exportação realmente dos resultados da pesquisa.
  
## <a name="step-1-generate-the-report-for-export"></a>Etapa 1: gerar o relatório para exportação

A primeira etapa é preparar o relatório para download para a exportação do seu computador. Quando você o relatório, os documentos do relatório são carregados em uma área de armazenamento do Azure na nuvem da Microsoft.
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre usando sua conta corporativa ou de estudante.
    
3. No painel esquerdo do centro de conformidade & segurança, clique em **Search** \> **pesquisa de conteúdo**de pesquisa.
    
4. Na página **pesquisa de conteúdo** , selecione uma pesquisa. 
    
5. No painel de detalhes, em **Exportar relatório para um computador**, clique em **gerar relatório**.
    
    > [!NOTE]
    > Se os resultados de uma pesquisa tiverem mais de 7 dias, você precisará atualizá-los. Se isso acontecer, cancele a exportação, clique em **Atualizar resultados da pesquisa** no painel de detalhes da pesquisa selecionada e, em seguida, inicie a exportação novamente após os resultados serem atualizados. 
  
6. Na página **exportar um relatório** , em **incluir estes itens da pesquisa**, escolha uma das seguintes opções:
    
    - Exportar somente itens indexados
    
    - Exportar itens indexados e não indexados
    
    - Exportar somente itens não indexados
    
    Para obter mais informações sobre itens não indexados, consulte [itens parcialmente indexados na pesquisa de conteúdo](partially-indexed-items-in-content-search.md).
    
7. Escolha incluir estatísticas de pesquisa para todas as versões dos documentos do SharePoint. Essa opção será exibida somente se as fontes de conteúdo da pesquisa incluírem sites do SharePoint ou do OneDrive for Business.
    
8. Clique em **gerar relatório**.
    
    O relatório de resultados de pesquisa está preparado para download, o que significa que os documentos de relatório serão carregados para a área de armazenamento do Azure na nuvem da Microsoft. Quando o relatório estiver pronto para download, o link de **relatório de download** será exibido em **Exportar relatório para um computador** no painel de detalhes. 
    
> [!NOTE]
> Você também pode exportar um relatório para uma pesquisa de conteúdo associada a uma ocorrência de descoberta eletrônica. Para fazer isso, **vá para** \> **descoberta eletrônica**eletrônica, selecione um caso e clique em **Editar** ![ícone](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)de edição. Na página **pesquisas** , selecione uma pesquisa e clique em **Exportar** ![o ícone](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> resultados da pesquisa exportar **um relatório**. 
  
## <a name="step-2-download-the-report"></a>Etapa 2: baixar o relatório

A próxima etapa é baixar o relatório da área de armazenamento do Azure para seu computador local.
  
1. No painel de detalhes da pesquisa para a qual você gerou o relatório, em **Exportar relatório para um computador**, clique em **baixar relatório**.
    
    A página de **relatório de download** é exibida e contém as seguintes informações sobre o relatório que é baixado para o seu computador. 
    
    - O número de itens que serão baixados.
    
    - O tamanho total estimado dos itens que serão baixados.
    
    - Se serão exportados itens indexados ou não indexados. Itens não indexados são itens que têm um formato reconhecido, são criptografados ou não foram indexados por outros motivos.
    
    - Se as versões dos documentos do SharePoint serão baixadas.
    
    - O status do processo de exportação de relatórios. Você pode começar a baixar o relatório mesmo se a preparação do relatório não estiver concluída.
    
2. Em **Exportar chave**, clique em **Copiar para a área de transferência**. Use essa chave na etapa 5 para baixar o relatório.
    
    > [!IMPORTANT]
    > Como qualquer pessoa pode instalar e iniciar a ferramenta de exportação de descoberta eletrônica e, em seguida, usar essa chave para baixar o relatório de pesquisa, tome precauções para proteger essa chave da mesma forma que você protegeria senhas ou outras informações relacionadas à segurança. 
  
3. Clique em **baixar relatório**.
    
4. Se você for solicitado a instalar a **ferramenta de exportação de descoberta eletrônica**, clique em **instalar**.
    
5. Na **Ferramenta de Exportação de Descoberta Eletrônica**, cole a chave de exportação que você copiou na etapa 2 na caixa apropriada.
    
6. Clique em **procurar** para especificar o local onde você deseja baixar o relatório. 
    
7. Clique em **Iniciar** para baixar os resultados da pesquisa em seu computador. 
    
    A **Ferramenta de Exportação de Descoberta Eletrônica** exibe informações de status sobre o processo de exportação, incluindo uma estimativa do número (e tamanho) dos itens restantes a serem baixados. Quando o processo de exportação estiver concluído, você poderá acessar os arquivos no local onde foram baixados. 
    
> [!NOTE]
> Você pode baixar o relatório para uma pesquisa de conteúdo associada a uma ocorrência de descoberta eletrônica. Para fazer isso, **vá para** \> **descoberta eletrônica**eletrônica, selecione um caso e clique em **Editar** ![ícone](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)de edição. Na página **Exportar** , selecione uma exportação de relatório e clique em **baixar relatório** no painel de detalhes. 
  
## <a name="whats-included-in-the-report"></a>O que está incluído no relatório

Quando você gera e exporta um relatório sobre os resultados de uma pesquisa de conteúdo, os seguintes documentos são baixados:
  
- **Resumo de exportação:** Um documento do Excel que contém um resumo da exportação. Isso inclui informações como o número de fontes de conteúdo pesquisadas, o número de resultados de pesquisa de cada local de conteúdo, o número estimado de itens, o número real de itens que serão exportados e o tamanho estimado e real dos itens que seriam exportados. 
    
    > [!NOTE]
    > Se você incluir itens não indexados ao exportar o relatório, o número de itens não indexados será incluído no número total de resultados de pesquisa estimados e no número total de resultados de pesquisa baixados (se você tiver que exportar os resultados da pesquisa) listados no relatório de Resumo de exportação. Em outras palavras, o número total de itens que seriam baixados é igual ao número total de resultados estimados e ao número total de itens não indexados. 
  
- **Manifesto:** Um arquivo de manifesto (em formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa. 
    
- **Resultados:** Um documento do Excel que contém uma linha com informações sobre cada item indexado que seria exportado com os resultados da pesquisa. Para emails, o log do resultado contém informações sobre cada mensagem, incluindo: 
    
  - O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).
    
  - A data na qual a mensagem foi enviada ou recebida.
    
  - A linha de assunto da mensagem.
    
  - O remetente e os destinatários da mensagem.
    
    Para documentos de sites do SharePoint e do OneDrive for Business, o log de resultados contém informações sobre cada documento, incluindo:
    
  - A URL para o documento.
    
  - A URL para o conjunto de sites onde o documento está localizado.
    
  - A data em que o documento foi modificado pela última vez.
    
  - O nome do documento (que está localizado na coluna Assunto no log de resultados).
    
    > [!NOTE]
    > O número de linhas no relatório de **resultados** deve ser igual ao número total de resultados de pesquisa menos o número total de itens listados no relatório de **itens não indexados** . 
  
- **Itens não indexados:** Um documento do Excel que contém informações sobre quaisquer itens não indexados incluídos nos resultados da pesquisa. Se você não incluir itens não indexados ao gerar o relatório de resultados de pesquisa, esse relatório ainda será baixado, mas estará vazio.
