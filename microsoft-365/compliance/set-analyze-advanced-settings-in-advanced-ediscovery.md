---
title: Definir as configurações avançadas de análise na descoberta eletrônica avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
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
ms.assetid: a797682f-ad85-4c08-a354-3850ba2237ee
description: Saiba como definir as configurações avançadas, incluindo as duplicatas, threads de email e temas, para o processo de análise na descoberta eletrônica avançada.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac1300eb26338691722d9ccd15269ccf7f964f58
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663486"
---
# <a name="set-analyze-advanced-settings-in-advanced-ediscovery"></a>Definir as configurações avançadas de análise na descoberta eletrônica avançada

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
A descoberta eletrônica avançada fornece parâmetros avançados padrão para analisar configurações de módulo. O procedimento a seguir descreve as configurações que podem ser especificadas.
  
1. Na guia **preparar \> \> configuração de análise** , clique em **Configurações avançadas** (na parte inferior da página). O painel a seguir é exibido. 
    
    ![Definir as configurações avançadas de análise](../media/c9ea3017-e19a-456b-a742-c3d07121a3f6.png)
  
2. Em **parâmetros Near-Duplicate e threads de email**, selecione valores para os seguintes, conforme necessário:
    
  - **Número mínimo de palavras**: o número mínimo de palavras, abaixo do qual um arquivo não é enviado para análise quase duplicada. 
    
  - **Número máximo de palavras**: número máximo de palavras, acima do qual um arquivo não é enviado para análise quase duplicada.
    
  - **Similaridade de email**: nível mínimo de aparência de dois emails a serem considerados semelhantes. O valor é sempre igual ou maior que a similaridade de documentos. O padrão é 90%.
    
3. Em **parâmetros de temas**, marque a caixa de seleção **incluir números na análise de temas** para incluir números no processamento de temas durante a análise. 
    
4. Clique em **Salvar**. 
    
## <a name="related-topics"></a>Tópicos relacionados

[Descoberta Eletrônica Avançada (clássica)](office-365-advanced-ediscovery.md)
  
[Noções básicas sobre a similaridade de documentos](understand-document-similarity-in-advanced-ediscovery.md)
  
[Configuração das opções de análise](set-analyze-options-in-advanced-ediscovery.md)
  
[Configuração ignorar texto](set-ignore-text-in-advanced-ediscovery.md)
  
[Exibindo resultados de análise](view-analyze-results-in-advanced-ediscovery.md)

