---
title: Exportar e baixar conteúdo de uma ocorrência principal de Descoberta eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como exportar e baixar conteúdo de um caso de Descoberta e Principal.
ms.openlocfilehash: 30fc30943bd570cf4d79ce88b5bef5836b3dfe14
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760295"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Exportar conteúdo de um caso de Descoberta e Principal

Depois que uma pesquisa for realizada com êxito, você poderá exportar os resultados da pesquisa. Quando você exporta os resultados da pesquisa, os itens da caixa de correio são baixados em arquivos PST ou como mensagens individuais. Quando você exporta conteúdo de sites do SharePoint e do OneDrive for Business, cópias de documentos nativos do Office e outros documentos são exportados. Um Results.csv que contém informações sobre cada item exportado e um arquivo de manifesto (em formato XML) que contém informações sobre cada resultado de pesquisa também é exportado.
  
Você pode exportar os resultados de uma única pesquisa associada [a](#export-the-results-of-a-single-search) uma ocorrência ou pode exportar os resultados de várias pesquisas [associadas a uma ocorrência.](#export-the-results-of-multiple-searches)
  
## <a name="export-the-results-of-a-single-search"></a>Exportar os resultados de uma única pesquisa

1. Acesse e entre usando as credenciais da conta de usuário que recebeu as permissões [https://compliance.microsoft.com](https://compliance.microsoft.com) apropriadas de Descoberta.

2. No painel de navegação esquerdo do centro de conformidade do Microsoft 365, clique em Mostrar tudo e clique em **eDiscovery > Core.**

3. Na página **Descoberta eDiscovery** Principal, selecione a ocorrência da onde você deseja exportar os resultados da pesquisa e clique em **Abrir caso.**

4. Na **home** page do caso, clique na **guia** Pesquisas.

5. Na lista de pesquisas do caso, clique na pesquisa da onde você  deseja exportar os resultados da pesquisa e clique em Exportar resultados no flyout.

    A **página Exportar resultados** é exibida. 

    ![Exportar página de resultados](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    O fluxo de trabalho para exportar os resultados de uma pesquisa associada a um caso de Descoberta Eletrônico Principal é o mesmo que exportar os resultados da pesquisa para uma pesquisa na página **pesquisa de** conteúdo. Para obter instruções passo a passo, consulte [Exportar resultados de pesquisa de conteúdo.](export-search-results.md)

    > [!NOTE]
    > Ao exportar os resultados da pesquisa, você tem a opção de habilitar a des duplicação para que apenas uma cópia de uma mensagem de email seja exportada, mesmo que várias instâncias da mesma mensagem possam ter sido encontradas nas caixas de correio pesquisadas. Para obter mais informações sobre a des duplicação e como os itens duplicados são identificados, consulte Des duplicação nos resultados da pesquisa [de DescobertaScoberta.](de-duplication-in-ediscovery-search-results.md)

    Depois de iniciar a exportação, os resultados da pesquisa são preparados para download, o que significa que eles são carregados para um local de armazenamento do Azure fornecido pela Microsoft na nuvem da Microsoft.
  
6. Clique na **guia Exportar** para exibir a lista de trabalhos de exportação da ocorrência.
  
    Talvez seja preciso clicar em **Atualizar para** atualizar a lista de trabalhos de exportação para que ela mostre o trabalho de exportação que você criou. Os trabalhos de exportação têm o mesmo nome da pesquisa correspondente **_Export** anexados ao nome da pesquisa.

7. Clique no trabalho de exportação criado para exibir informações de status na página do flyout. Essas informações incluem a porcentagem de itens que foram transferidos para o local de armazenamento do Azure.

8. Depois que todos os itens foram transferidos, clique **em Baixar resultados** para baixar os resultados da pesquisa para o computador local. Para obter mais informações sobre como baixar resultados de pesquisa, consulte a Etapa 2 em [Exportar resultados de pesquisa de conteúdo](export-search-results.md#step-2-download-the-search-results)

## <a name="export-the-results-of-multiple-searches"></a>Exportar os resultados de várias pesquisas

Como alternativa à exportação dos resultados de uma única pesquisa associada a uma ocorrência, você pode exportar os resultados de várias pesquisas do mesmo caso em um único trabalho de exportação. Exportar os resultados de várias pesquisas é mais rápido e fácil do que exportar os resultados uma pesquisa por vez.
  
> [!NOTE]
> Não é possível exportar os resultados de várias pesquisas se uma dessas pesquisas foi configurada para locais de pesquisa em espera.

1. Acesse e entre usando as credenciais da conta de usuário que recebeu as permissões [https://compliance.microsoft.com](https://compliance.microsoft.com) apropriadas de Descoberta.

2. No painel de navegação esquerdo do centro de conformidade do Microsoft 365, clique em Mostrar tudo e clique em **eDiscovery > Core.**

3. Na página **Descoberta eDiscovery** Principal, selecione a ocorrência da onde você deseja exportar os resultados da pesquisa e clique em **Abrir caso.**

4. Na **home** page do caso, clique na **guia** Pesquisas.
    
5. Na lista de pesquisas da ocorrência, marque a caixa de seleção ao lado de duas ou mais pesquisas das quais você deseja exportar resultados de pesquisa. 

   A **página do flyout** ações em massa é exibida. 

    ![Na página Ações em Massa, clique em Exportar resultados](../media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
6. Clique **em Exportar resultados.**

   A **página Exportar resultados** é exibida. 

    ![Exportar página de resultados](../media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    Neste ponto, o fluxo de trabalho para exportar os resultados de várias pesquisas associadas a um caso de Descoberta Eletrônico Principal é o mesmo que exportar os resultados da pesquisa para uma única pesquisa. Confira a etapa 5 na seção anterior.

### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>Mais informações sobre como exportar os resultados de várias pesquisas

- Quando você exporta os resultados de várias pesquisas, as consultas de pesquisa de todas as pesquisas são combinadas usando operadores **OR** e, em seguida, a pesquisa combinada é iniciada. Os resultados estimados da pesquisa combinada são exibidos na página do flyout do trabalho de exportação selecionado. Os resultados da pesquisa são copiados para o local de armazenamento do Azure na nuvem da Microsoft. O status do trabalho de cópia também é exibido na página do flyout. Conforme mencionado anteriormente, depois que todos os resultados da pesquisa foram copiados, você pode baixá-los para um computador local.

- O número máximo de palavras-chave de consultas para todas as pesquisas que você deseja exportar é 500. Esse é o mesmo limite para uma única pesquisa. Isso porque o trabalho de exportação combina todas as consultas de pesquisa usando o **operador OR.** Se você exceder esse limite, um erro será retornado. Nesse caso, você precisa exportar os resultados de menos pesquisas ou simplificar as consultas de pesquisa das pesquisas originais que você deseja exportar.

- Os resultados da pesquisa exportados são organizados pelo local de conteúdo em que o item foi encontrado. Isso significa que um local de conteúdo nos resultados da exportação pode ter itens retornados por pesquisas diferentes. Por exemplo, se você optar por exportar mensagens de email em um arquivo PST para cada caixa de correio, o arquivo PST poderá ter resultados de várias pesquisas.

- Se o mesmo item de email ou documento do mesmo local de conteúdo for retornado por mais de uma das pesquisas que você exportar, apenas uma cópia do item será exportada.

- Você não pode editar uma exportação para várias pesquisas depois de criar. Por exemplo, você não pode adicionar ou remover pesquisas do trabalho de exportação. Você precisa criar um trabalho de exportação para alterar quais resultados de pesquisa são exportados. Depois que um trabalho de exportação é criado, você só pode baixar os resultados em um computador, reiniciar a exportação ou excluir o trabalho de exportação.

- Se você reiniciar a exportação, quaisquer alterações nas consultas das pesquisas que comportam o trabalho de exportação não afetarão os resultados da pesquisa recuperados. Quando você reiniciar uma exportação, o mesmo trabalho de consulta de pesquisa combinado executado quando o trabalho de exportação foi criado será executado novamente.

- Além disso, se você reiniciar uma exportação, os resultados da pesquisa copiados para o local de Armazenamento do Azure substituirão os resultados anteriores. Os resultados anteriores que foram copiados não estarão disponíveis para download.
