---
title: Configuração rápida da Descoberta Eletrônica Avançada do Office 365
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
description: 'Saiba como acessar a Descoberta Eletrônica Avançada do Office 365 pelo Centro de Conformidade e Segurança do Office 365 e analisar o fluxo de trabalho típico para usar a Descoberta Eletrônica avançada.  '
ms.openlocfilehash: 1f434fe87fd93ebee03c4300c67214011f646134
ms.sourcegitcommit: e741930c41abcde61add22d4b773dbf171ed72ac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42557841"
---
# <a name="quick-setup-advanced-ediscovery-classic"></a>Configuração rápida da Descoberta Eletrônica Avançada (clássica)

> [!IMPORTANT]
> À medida que continuamos investindo em versões mais recentes da Descoberta Eletrônica Avançada, anunciamos a retirada da Descoberta Eletrônica Avançada do Office 365, também conhecida como *Descoberta Eletrônica Avançada (clássica)* ou *Descoberta Eletrônica Avançada v1.0*. Se você ainda estiver usando a Descoberta Eletrônica Avançada v1.0, faça a transição para o [Descoberta Eletrônica Avançada v2.0](overview-ediscovery-20.md) (também conhecida como * solução de Descoberta Eletrônica Avançada no Microsoft 365*) o mais rápido possível. O Descoberta Eletrônica Avançada 2.0 contém funcionalidade semelhante encontrada na Descoberta Eletrônica Avançada v1.0, mas também oferece muitos recursos novos, como gerenciamento de custódia, gerenciamento de comunicações e conjuntos de revisão. Para saber mais sobre a desativação da Descoberta Eletrônica Avançada v1.0, confira [Desativação de ferramentas legadas de Descoberta Eletrônica](legacy-ediscovery-retirement.md#advanced-ediscovery-v10). 

Esta seção de configuração mostra a um gerente de Descoberta Eletrônica do Centro de Conformidade e Segurança &amp;do Microsoft 365 como começar a usar a Descoberta Eletrônica Avançada. Pressupõe-se um conhecimento prático de ambos.
  
## <a name="accessing-a-case-in-advanced-ediscovery"></a>Como acessar um caso na Descoberta Eletrônica Avançada


Você acessa a Descoberta Eletrônica Avançada no Centro de Conformidade e Segurança. Você precisa ser membro de um caso de Descoberta Eletrônica no Centro de Conformidade e Segurança para acessar o caso na Descoberta Eletrônica Avançada. Confira as instruções sobre como atribuir permissões de caso de Descoberta Eletrônica e adicionar usuários a um caso de Descoberta Eletrônica em [Gerenciar casos de Descoberta Eletrônica no Office 365](ediscovery-cases.md). 
  
Para ir a um caso na Descoberta Eletrônica Avançada: 
  
1. [Vá até o Centro de Conformidade e Segurança do Office 365](go-to-the-securitycompliance-center.md). 
    
2. No Centro de Conformidade e Segurança, clique em **Pesquisa e investigação** \> **Descoberta Eletrônica** para exibir a lista de casos na sua organização. 
    
3. Na página **Descoberta Eletrônica**, clique em **Abrir** ao lado do caso ao qual deseja ir na Descoberta Eletrônica Avançada. 
    
4. Na página **Início** do caso, clique em **Descoberta Eletrônica Avançada**.
    
    A barra de progresso **Conectar-se à Descoberta Eletrônica Avançada** aparece. Quando você estiver conectado, o caso abrirá na Descoberta Eletrônica Avançada. 
    
## <a name="workflow"></a>Fluxo de trabalho

O diagrama a seguir ilustra o fluxo de trabalho comum para gerenciar e usar os casos de Descoberta Eletrônica no Centro de Conformidade e Segurança e na Descoberta Eletrônica Avançada. 
  
![Diagrama que mostra o fluxo de trabalho de Descoberta Eletrônica Avançada do Office 365 de quatro fases na instalação, inclusive a configuração de usuários e casos, identificação dos dados de caso, exportação e processamento, além das fases de análise e exportação para o computador local.](../media/76589ccc-789d-4581-b3a8-98d339b05979.png)
  
Esta seção de configuração descreve as quatro primeiras etapas do fluxo de trabalho. Confira a descrição das etapas do fluxo de trabalho a seguir.
  
## <a name="analyze"></a>Análise

[Analisar dados de casos](analyze-case-data-with-advanced-ediscovery.md) Identifica e organiza os arquivos por vários parâmetros, habilita o uso de temas e exibe os resultados. A funcionalidade de análise pode ser personalizada pelo usuário com a finalidade de obter resultados aprimorados. 
  
## <a name="relevance-setup-and-relevance"></a>Configuração da relevância e relevância

[Configuração de relevância](manage-relevance-setup-in-advanced-ediscovery.md) e [Uso do módulo de relevância](use-relevance-in-advanced-ediscovery.md) Permite avaliação e treinamento de relevância com base em uma amostra aleatória de arquivos e os usa para aplicar decisões ao processo de codificação preditiva. Calcula e exibe os resultados provisórios enquanto monitora a validade estatística do processo. Exibe os resultados para facilitar a tomada de decisões da análise. 
  
## <a name="export"></a>Exportação

[Exportar dados de casos](export-case-data-in-advanced-ediscovery.md) Permite exportar o conteúdo e os resultados da Descoberta Eletrônica Avançada para revisão externa. 
  
## <a name="report"></a>Relatório

[Execução de relatórios](run-reports-in-advanced-ediscovery.md) Habilita a geração de relatórios selecionados que estão relacionados ao processamento da Descoberta Eletrônica Avançada. 
  
## <a name="see-also"></a>Também consulte

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Configurar usuários e casos](set-up-users-and-cases-in-advanced-ediscovery.md)
  
[Preparação de dados](prepare-data-for-advanced-ediscovery.md)

