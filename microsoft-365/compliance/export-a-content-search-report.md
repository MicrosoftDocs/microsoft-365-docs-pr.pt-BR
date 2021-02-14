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
description: Em vez & de exportar os resultados reais de uma Pesquisa de Conteúdo no Centro de Conformidade e Segurança do Office 365, você pode exportar um relatório de resultados de pesquisa. O relatório contém um resumo dos resultados da pesquisa e um documento com informações detalhadas sobre cada item que seria exportado.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de27e25945f14f6a6119b4c1776eebca5e84d8ce
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358297"
---
# <a name="export-a-content-search-report"></a>Exportar um relatório de Pesquisa de Conteúdo

Em vez de exportar o conjunto completo de resultados de pesquisa de uma Pesquisa de Conteúdo no Centro de Conformidade e Segurança (e de uma Pesquisa de Conteúdo associada a um caso de Descoberta eDiscovery), você pode exportar os mesmos relatórios gerados quando você exporta os resultados da pesquisa. &
  
Quando você exporta um relatório, ele é baixado para uma pasta que tem o mesmo nome da Pesquisa de Conteúdo, mas que é anexado _ReportsOnly *.* Por exemplo, se a Pesquisa de Conteúdo se chamar  *ContosoCase0815,* o relatório será baixado para uma pasta chamada *ContosoCase0815_ReportsOnly*. Para uma lista de documentos incluídos no relatório, consulte [o que está incluído no relatório.](#whats-included-in-the-report)

## <a name="assign-roles-and-check-system-requirements"></a>Atribuir funções e verificar os requisitos do sistema

- Para exportar um relatório de Pesquisa de Conteúdo, você precisa ter a função de gerenciamento de Pesquisa de Conformidade no Centro de Conformidade & Segurança. Essa função é atribuída por padrão aos grupos de funções de Gerenciamento da Organização e Gerente de Descobertas e Descobertas.. Para obter mais informações, confira [Atribuir permissões de descoberta eletrônica](assign-ediscovery-permissions.md).

- Quando você exporta um relatório, os dados são temporariamente armazenados em uma área exclusiva de Armazenamento do Azure na nuvem da Microsoft antes de ser baixado para o computador local. Certifique-se de que sua organização possa se conectar ao ponto de extremidade no Azure, que é **\* .blob.core.windows.net** (o caractere curinga representa um identificador exclusivo para a exportação). Os dados dos resultados da pesquisa são excluídos da área de Armazenamento do Azure duas semanas após sua criação. 
    
- O computador que você usa para exportar os resultados da pesquisa devem atender aos seguintes requisitos de sistema:
    
  - Versões de 32 bits ou 64 bits do Windows 7 e versões posteriores
    
  - Microsoft .NET Framework 4.7
    
- Você precisa usar um dos seguintes navegadores com suporte para executar a Ferramenta de Exportação de Descobertas e<sup>1:</sup>

  - Microsoft Edge <sup>2</sup>

    OU

  - Microsoft Internet Explorer 10 e versões posteriores

  > [!NOTE]
  > <sup>1</sup> A Microsoft não fabrica extensões ou complementos de terceiros para aplicativos ClickOnce. Não há suporte para a exportação de resultados de pesquisa usando um navegador sem suporte com extensões ou complementos de terceiros.<br/>
  > <sup>2</sup> Como resultado de alterações recentes no Microsoft Edge, o suporte ao ClickOnce não está mais habilitado por padrão. Para obter instruções sobre como habilitr o suporte ao ClickOnce no Edge, consulte Usar a Ferramenta de Exportação de [Descobertas No Microsoft Edge.](configure-edge-to-export-search-results.md)

- Se o tamanho total estimado dos resultados retornados por uma Pesquisa de Conteúdo exceder 2 TB, a exportação do relatório falhará. Para exportar o relatório com êxito, tente restringir o escopo e realizar novamente a pesquisa para que o tamanho estimado dos resultados seja inferior a 2 TB.

- Exportar relatórios de Pesquisa de Conteúdo conta com o número máximo de exportações em execução ao mesmo tempo e o número máximo de exportações que um único usuário pode executar. Para obter mais informações sobre limites de exportação, consulte [Exportar resultados da Pesquisa de Conteúdo.](export-search-results.md#export-limits)

## <a name="generate-and-download-a-content-search-report"></a>Gerar e baixar um relatório de Pesquisa de Conteúdo

As etapas para gerar e baixar um relatório de Pesquisa de Conteúdo são semelhantes à exportação de resultados de pesquisa.
  
## <a name="step-1-generate-the-report-for-export"></a>Etapa 1: Gerar o relatório para exportação

A primeira etapa é preparar o relatório para baixar para o computador que está exportando. Quando você faz o relatório, os documentos do relatório são carregados para uma área de Armazenamento do Azure na nuvem da Microsoft.
  
1. Acesse [https://protection.office.com](https://protection.office.com).
    
2. Entre usando sua conta de trabalho ou da escola.
    
3. No painel esquerdo do Centro de Conformidade e Segurança &, clique em **Pesquisar** \> **Conteúdo.**
    
4. Na página **Pesquisa de** conteúdo, selecione uma pesquisa. 
    
5. No painel de detalhes, em **Exportar relatório para um computador,** clique em Gerar **relatório**.
    
    > [!NOTE]
    > Se os resultados de uma pesquisa tiverem mais de 7 dias, você precisará atualizá-los. Se isso acontecer, cancele  a exportação, clique em Atualizar resultados da pesquisa no painel de detalhes da pesquisa selecionada e inicie a exportação de relatório novamente depois que os resultados forem atualizados. 
  
6. Na página **Exportar um relatório,** em Incluir esses itens da **pesquisa,** escolha uma das seguintes opções:
    
    - Exportar somente itens indexados
    
    - Exportar itens indexados e não indexados
    
    - Exportar somente itens não indexados
    
    Para obter mais informações sobre itens não indexados, consulte [Itens parcialmente indexados na Pesquisa de Conteúdo.](partially-indexed-items-in-content-search.md)
    
7. Opte por incluir estatísticas de pesquisa para todas as versões de documentos do SharePoint. Essa opção só será exibida se as fontes de conteúdo da pesquisa incluír sites do SharePoint ou do OneDrive for Business.
    
8. Clique **em Gerar relatório**.
    
    O relatório de resultados da pesquisa está preparado para download, o que significa que os documentos do relatório serão carregados para a área de Armazenamento do Azure na nuvem da Microsoft. Quando o relatório estiver pronto para download, o link **Baixar** relatório será exibido em **Exportar relatório para** um computador no painel de detalhes. 
    
> [!NOTE]
> Você também pode exportar um relatório para uma Pesquisa de Conteúdo que está associada a um caso de Descoberta eDiscovery. Para fazer isso, vá para Descoberta e **Descoberta** \> **eDiscovery,** selecione uma ocorrência e clique em **Editar** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ícone. Na página **Pesquisas,** selecione uma pesquisa  e clique em Exportar o ícone Exportar resultados da pesquisa ![ Exportar um ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \> **relatório.** 
  
## <a name="step-2-download-the-report"></a>Etapa 2: Baixar o relatório

A próxima etapa é baixar o relatório da área de Armazenamento do Azure para o computador local.
  
1. No painel de detalhes da pesquisa para a que você gerou o relatório, em **Exportar relatório para um** computador, clique em Baixar **relatório**.
    
    A **página Baixar relatório** é exibida e contém as seguintes informações sobre o relatório que é baixado para seu computador. 
    
    - O número de itens que serão baixados.
    
    - O tamanho total estimado dos itens que serão baixados.
    
    - Se serão exportados itens indexados ou não indexados. Itens não indexados são itens que têm um formato reconhecido, são criptografados ou não foram indexados por outros motivos.
    
    - Se as versões dos documentos do SharePoint serão baixadas.
    
    - O status do processo de exportação de relatório. Você pode começar a baixar o relatório mesmo se a preparação do relatório não estiver concluída.
    
2. Em **Exportar chave**, clique em **Copiar para a área de transferência**. Use essa chave na etapa 5 para baixar o relatório.
    
    > [!IMPORTANT]
    > Como qualquer pessoa pode instalar e iniciar a ferramenta Exportação de Descobertas e, em seguida, usar essa chave para baixar o relatório de pesquisa, certifique-se de tomar precauções para proteger essa chave da mesma forma que protegeria senhas ou outras informações relacionadas à segurança. 
  
3. Clique **em Baixar relatório**.
    
4. If you're prompted to install the **eDiscovery Export Tool**, click **Install**.
    
5. Na **Ferramenta de Exportação de Descoberta Eletrônica**, cole a chave de exportação que você copiou na etapa 2 na caixa apropriada.
    
6. Clique **em** Procurar para especificar o local onde deseja baixar o relatório. 
    
7. Clique em **Iniciar** para baixar os resultados da pesquisa em seu computador. 
    
    A **Ferramenta de Exportação de Descoberta Eletrônica** exibe informações de status sobre o processo de exportação, incluindo uma estimativa do número (e tamanho) dos itens restantes a serem baixados. Quando o processo de exportação estiver concluído, você poderá acessar os arquivos no local onde eles foram baixados. 
    
> [!NOTE]
> Você pode baixar o relatório para uma Pesquisa de Conteúdo associada a um caso de Descoberta eDiscovery. Para fazer isso, vá para Descoberta e **Descoberta** \> **eDiscovery,** selecione uma ocorrência e clique em **Editar** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ícone. Na página **Exportações,** selecione uma exportação de relatório e clique em **Baixar relatório** no painel de detalhes. 
  
## <a name="whats-included-in-the-report"></a>O que está incluído no relatório

Quando você gera e exporta um relatório sobre os resultados de uma Pesquisa de Conteúdo, os seguintes documentos são baixados:
  
- **Resumo da exportação:** Um documento do Excel que contém um resumo da exportação. Isso inclui informações como o número de fontes de conteúdo pesquisadas, o número de resultados de pesquisa de cada local de conteúdo, o número estimado de itens, o número real de itens que seriam exportados e o tamanho estimado e real dos itens que seriam exportados. 
    
    > [!NOTE]
    > Se você incluir itens não índicedos ao exportar o relatório, o número de itens não índicedos será incluído no número total de resultados estimados da pesquisa e no número total de resultados de pesquisa baixados (se você fosse exportar os resultados da pesquisa) listados no relatório resumo de exportação. Em outras palavras, o número total de itens que seriam baixados é igual ao número total de resultados estimados e ao número total de itens não índicedos. 
  
- **Manifesto:** Um arquivo de manifesto (no formato XML) que contém informações sobre cada item incluído nos resultados da pesquisa. 
    
- **Resultados:** Um documento do Excel que contém uma linha com informações sobre cada item indexado que seria exportado com os resultados da pesquisa. Para emails, o log do resultado contém informações sobre cada mensagem, incluindo: 
    
  - O local da mensagem na caixa de correio de origem (inclusive se a mensagem está na caixa de correio principal ou de arquivo morto).
    
  - A data na qual a mensagem foi enviada ou recebida.
    
  - A linha de assunto da mensagem.
    
  - O remetente e os destinatários da mensagem.
    
    Para documentos de sites do SharePoint e do OneDrive for Business, o log de Resultados contém informações sobre cada documento, incluindo:
    
  - A URL para o documento.
    
  - A URL para o conjunto de sites onde o documento está localizado.
    
  - A data em que o documento foi modificado pela última vez.
    
  - O nome do documento (que está localizado na coluna Assunto no log de resultados).
    
    > [!NOTE]
    > O número de linhas  no relatório de Resultados deve ser igual ao número total de resultados da pesquisa menos o número total de itens listados no relatório de Itens Não **Índicedos.** 
  
- **Itens não índicedos:** Um documento do Excel que contém informações sobre todos os itens não índicedos incluídos nos resultados da pesquisa. Se você não incluir itens não índicedos ao gerar o relatório de resultados da pesquisa, esse relatório ainda será baixado, mas estará vazio.
