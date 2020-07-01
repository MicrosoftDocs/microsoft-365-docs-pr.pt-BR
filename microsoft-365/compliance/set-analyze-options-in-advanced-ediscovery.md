---
title: Definir opções de análise na descoberta eletrônica avançada
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
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: Revise as etapas para configurar opções para o processo de análise na descoberta eletrônica avançada, incluindo duplicatas, threads de email e temas.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d622e06cdfe9a46f470be46d1a5b9df98347cc0a
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936878"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a>Definir opções de análise na descoberta eletrônica avançada (clássica)

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Em descoberta eletrônica avançada, defina as opções de análise antes de executar Analyze.
  
## <a name="set-analyze-options"></a>Definir opções de análise

Abra a configuração de ** \> análise de preparação** \> **Setup**. A janela a seguir é exibida.
  
![Definir Opções de Análise](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 **Threads quase duplicados e email** Marque esta caixa se você deseja executar a análise. Ele é selecionado por padrão. 
  
 **Similaridade de documentos** Insira o valor de limite Near-duplicates ou aceite o padrão de 65%. 
  
 **Temas** Marque esta caixa para processar todos os arquivos e atribuir temas a eles. Por padrão, essa caixa de seleção não está selecionada. Insira as opções a seguir se você deseja executar o processamento de temas.
  
- **Número máximo de temas** Insira ou selecione um valor para o número de temas a serem criados. O padrão é 200. 
    
    > [!NOTE]
    > Aumentar o número de temas afeta o desempenho, bem como a capacidade de um tema generalizar. Quanto maior o número de temas, mais granulares eles são. Por exemplo, se um conjunto de 50 temas incluir um tema como "basquete, Spurs, clipes, Lakers"; 300 temas podem incluir temas separados: "Spurs", "Clippings", "Lakers". Se você não teve conhecimento do tema "basquete" e usar esse recurso para ECA, ver o tema "basquete" pode ser útil. Mas, se o processamento tiver muitos temas, talvez você nunca veja a palavra "basquete" e talvez não saiba que Spurs e recortes são bons temas de basquete para revisar, em vez de itens que entram em inicializações e usados para cabelo. 
  
- **Temas sugeridos** Você pode sugerir palavras de tema para controlar o processamento de temas. A descoberta eletrônica avançada se concentrará nessas palavras sugeridas e tentará criar um ou mais temas relevantes, com base nas configurações de "número máximo de temas". 
    
    Por exemplo, se a palavra sugerida for "computador" e você tiver especificado "2" como o "número máximo de temas", a descoberta eletrônica avançada tentará gerar dois temas relacionados à palavra "computador". Os dois temas podem ser "software de computador" e "hardware de computador", por exemplo. 
    
    ![Adicionar tema sugerido](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. Para exibir, adicionar ou editar temas sugeridos, clique em **Modificar**.
    
2. No painel **temas sugeridos** , clique no ícone **Adicionar** ![ ícone de adição ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) para adicionar um tema. No painel **Adicionar tema sugerido** , adicione as palavras, separadas por vírgulas. 
    
3. Em **número de temas**, selecione um valor para determinar o número de temas que a descoberta eletrônica avançada tentará gerar para essas palavras (o padrão é 1 tema).
    
4. Clique em **salvar** e feche a caixa de diálogo. 
    
    > [!NOTE]
    > O número total de temas inclui temas sugeridos. O total de temas sugeridos não pode exceder o total de temas. Se houver muitos temas sugeridos em relação ao total de temas, apenas alguns temas "romance" serão detectados pelo sistema porque a maioria dos temas será dedicada aos temas sugeridos. 
  
- **Modo** Na lista suspensa, selecione uma opção de **temas** : 
    
  - **Criar e aplicar modelo**: calcula temas por modelos de um segmento dos arquivos e, em seguida, distribui arquivos entre eles.
    
  - **Criar modelo**: calcula um modelo de temas de um segmento dos arquivos. O processo de aplicação de divisão de arquivos é feito separadamente em outro momento.
    
  - **Aplicar modelo**: essa opção só será mostrada se um modelo foi criado anteriormente e ainda não foi aplicado. Isso irá dividir os arquivos com base nos temas.
    
Você também pode [definir ignorar texto](set-ignore-text-in-advanced-ediscovery.md) e [definir as configurações avançadas de análise](set-analyze-advanced-settings-in-advanced-ediscovery.md) para análise. 
  
Após definir essas opções, clique em **analisar** para executar. [Exibir resultados da análise](view-analyze-results-in-advanced-ediscovery.md) são exibidos. 
  
## <a name="related-topics"></a>Tópicos relacionados

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre a similaridade de documentos](understand-document-similarity-in-advanced-ediscovery.md)
  
[Definir o texto de ignorar](set-ignore-text-in-advanced-ediscovery.md)
  
[Definir as configurações avançadas de análise](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Exibir resultados de análise](view-analyze-results-in-advanced-ediscovery.md)

