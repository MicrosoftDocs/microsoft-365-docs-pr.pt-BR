---
title: Instalação rápida para Descoberta Eletrônica Avançada
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
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: d7ccd944-9698-41c7-a21b-677dc62973c4
description: Saiba como acessar a Descoberta Eletrônica Avançada no Centro de Conformidade &amp; Segurança e como analisar o fluxo de trabalho típico para usar a Descoberta Eletrônica avançada.
ms.openlocfilehash: 5bd183f0f5f1c2f091fb374aab1e54f191665ce6
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936254"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a>Configuração rápida da Descoberta Eletrônica Avançada (clássica)

> [!IMPORTANT]
> À medida que continuamos investindo em versões mais recentes da Descoberta Eletrônica Avançada, anunciamos a retirada da Descoberta Eletrônica Avançada, também conhecida como *Descoberta Eletrônica Avançada (clássica)* ou *Descoberta Eletrônica Avançada v1.0*. Se você ainda estiver usando a Descoberta Eletrônica Avançada v1.0, faça a transição para o [Descoberta Eletrônica Avançada v2.0](overview-ediscovery-20.md) (também conhecida como * solução de Descoberta Eletrônica Avançada no Microsoft 365*) o mais rápido possível. O Descoberta Eletrônica Avançada 2.0 contém funcionalidade semelhante encontrada na Descoberta Eletrônica Avançada v1.0, mas também oferece muitos recursos novos, como gerenciamento de custódia, gerenciamento de comunicações e conjuntos de revisão. Para saber mais sobre a desativação da Descoberta Eletrônica Avançada v1.0, confira [Desativação de ferramentas legadas de Descoberta Eletrônica](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 

Esta seção de configuração mostra a um gerente de Descoberta Eletrônica do Centro de Conformidade e Segurança &amp;do Microsoft 365 como começar a usar a Descoberta Eletrônica Avançada. Pressupõe-se um conhecimento prático de ambos.
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a>Como acessar um caso na Descoberta Eletrônica Avançada

You access Advanced eDiscovery from the Security &amp; Compliance Center. You have to be a member of an eDiscovery case in the Security &amp; Compliance Center to access the case in Advanced eDiscovery. For instructions about assigning eDiscovery case permissions and adding users to an eDiscovery case, see [Manage eDiscovery cases in Office 365](ediscovery-cases.md). 
  
Para ir a um caso na Descoberta Eletrônica Avançada: 
  
1. [Acesse o Centro de Conformidade &amp; Segurança](go-to-the-securitycompliance-center.md). 
    
2. No Centro de Conformidade e Segurança, clique em **Pesquisa e investigação** \> **Descoberta Eletrônica** para exibir a lista de casos na sua organização. 
    
3. Na página **Descoberta Eletrônica**, clique em **Abrir** ao lado do caso ao qual deseja ir na Descoberta Eletrônica Avançada.
    
4. Na página **Início** do caso, clique em **Alternar para Avançar o eDiscovery**.
    
    The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected, the case is opened in Advanced eDiscovery. 
    
## <a name="workflow"></a>Fluxo de trabalho

O diagrama a seguir ilustra o fluxo de trabalho comum para gerenciar e usar os casos de Descoberta Eletrônica no Centro de Conformidade e Segurança e na Descoberta Eletrônica Avançada.
  
![Diagrama que mostra o fluxo de trabalho da Descoberta Eletrônica Avançada com quatro fases de instalação, inclusive a configuração de usuários &amp; casos, identificação dos dados de caso, exportação e processamento, além das fases de análise e exportação para o computador local.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
This setup section describes the first four steps in the workflow. For a description of the other steps in the workflow, see the following.
  
## <a name="analyze"></a>Análise

[Analyzing case data](analyze-case-data-with-advanced-ediscovery.md) Identifies and organizes the files by various parameters, enables the use of Themes, and displays the results. Analyze functionality can be customized by the user in order to achieve enhanced results. 
  
## <a name="relevance-setup-and-relevance"></a>Configuração da relevância e relevância

[Relevance Setup](manage-relevance-setup-in-advanced-ediscovery.md) and [Using the Relevance module](use-relevance-in-advanced-ediscovery.md) Enables assessment and relevance training based on a random sample of files and uses them to apply decisions to the predictive coding process. Calculates and displays interim results while monitoring statistical validity of the process. Displays the results to facilitate in making review decisions. 
  
## <a name="export"></a>Exportação

[Exportar dados de casos](export-case-data-in-advanced-ediscovery.md) Permite exportar o conteúdo e os resultados da Descoberta Eletrônica Avançada para revisão externa. 
  
## <a name="report"></a>Relatório

[Execução de relatórios](run-reports-in-advanced-ediscovery.md) Habilita a geração de relatórios selecionados que estão relacionados ao processamento da Descoberta Eletrônica Avançada. 
  
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Configurar usuários e casos](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Preparação de dados](prepare-data-for-advanced-ediscovery.md)

