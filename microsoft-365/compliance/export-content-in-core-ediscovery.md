---
title: Exportar e baixar conteúdo de um caso de Descoberta Básica
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
description: Descreve como exportar e baixar conteúdo de um caso de Descoberta Principal de Descoberta Microsoft 365.
ms.openlocfilehash: 8eb54e23369ef682e8aa1ebf7e681eb34444f1cd
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "52310831"
---
# <a name="export-content-from-a-core-ediscovery-case"></a>Exportar o conteúdo de um processo da Descoberta Eletrônica Principal

Depois que uma pesquisa associada a um caso de Descoberta Básica é executado com êxito, você pode exportar os resultados da pesquisa. Quando você exporta os resultados da pesquisa, os itens de caixa de correio são baixados em arquivos PST ou como mensagens individuais. Quando você exporta conteúdo de sites SharePoint e OneDrive for Business, cópias de documentos nativos Office documentos e outros documentos são exportados. Um Results.csv que contém informações sobre cada item exportado e um arquivo de manifesto (no formato XML) que contém informações sobre cada resultado de pesquisa também é exportado.
  
## <a name="export-search-results"></a>Exportar resultados da pesquisa

1. Acesse e entre usando as credenciais da conta de usuário que foram atribuídas às permissões [https://compliance.microsoft.com](https://compliance.microsoft.com) de Descoberta eDiscoveria apropriadas.

2. No painel de navegação esquerdo do centro de conformidade Microsoft 365, clique em **Mostrar** tudo e clique em **Descoberta > Core**.

3. Na página **Descoberta Principal da Descoberta e,** clique no nome da ocorrência em que você deseja criar a responsabilidade.

4. Na **home** page do caso, clique na **guia Pesquisas.**

5. No menu **Ações** na parte inferior da página de sobrevoo, clique em **Exportar resultados**.

   ![Opção Exportar resultados no menu Ações](../media/ActionMenuExportResults.png)

   O fluxo de trabalho para exportar os resultados de uma pesquisa associada a um caso de Descoberta Eletrônico Principal é o mesmo que exportar os resultados da pesquisa para uma pesquisa na página de pesquisa **de** conteúdo. Para obter instruções passo a passo, consulte [Exportar resultados de pesquisa de conteúdo](export-search-results.md).

   > [!NOTE]
   > Ao exportar resultados da pesquisa, você tem a opção de habilitar a de duplicação para que apenas uma cópia de uma mensagem de email seja exportada, mesmo que várias instâncias da mesma mensagem possam ter sido encontradas nas caixas de correio pesquisadas. Para obter mais informações sobre a des duplicação e como os itens duplicados são identificados, consulte [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).

   Depois de iniciar a exportação, os resultados da pesquisa são preparados para download, o que significa que eles são transferidos para um local de Armazenamento do Azure fornecido pela Microsoft na nuvem da Microsoft.
  
6. Clique na **guia Exportações** para exibir a lista de trabalhos de exportação.
  
   ![Exportar trabalhos na guia Exportar no caso de Descoberta Principal](../media/CoreeDiscoveryExport.png)

   Talvez seja preciso clicar em **Atualizar para** atualizar a lista de trabalhos de exportação para que ela mostre o trabalho de exportação criado. Os trabalhos de exportação têm o mesmo nome da pesquisa correspondente **_Export** anexado ao nome da pesquisa.

7. Clique no trabalho de exportação criado para exibir informações de status na página de sobrevoo. Essas informações incluem a porcentagem de itens que foram transferidos para o local de Armazenamento do Azure.

8. Depois que todos os itens foram transferidos, clique em **Baixar resultados** para baixar os resultados da pesquisa para o computador local. Para obter mais informações sobre como baixar resultados da pesquisa, consulte Etapa 2 em [Exportar resultados de pesquisa de conteúdo](export-search-results.md#step-2-download-the-search-results)

### <a name="more-information-about-exporting-searches-from-a-case"></a>Mais informações sobre a exportação de pesquisas de uma ocorrência

- Para obter mais informações sobre os arquivos de exportação incluídos ao exportar resultados da pesquisa, consulte [Exportar um relatório de pesquisa de conteúdo.](export-a-content-search-report.md#whats-included-in-the-report)

- Se você reiniciar a exportação, quaisquer alterações nas consultas das pesquisas que comem o trabalho de exportação não afetarão os resultados da pesquisa recuperados. Quando você reiniciar uma exportação, o mesmo trabalho de consulta de pesquisa combinado que foi executado quando o trabalho de exportação foi criado será executado novamente.

- Além disso, se você reiniciar uma exportação, os resultados da pesquisa copiados para o local de Armazenamento do Azure sobrescrevem os resultados anteriores. Os resultados anteriores copiados não estarão disponíveis para download.
