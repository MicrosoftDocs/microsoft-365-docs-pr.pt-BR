---
title: Gerenciar a configuração da Relevância na Descoberta Eletrônica Avançada
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: fd6be6d3-2e8d-449d-9851-03ab7546e6aa
ROBOTS: NOINDEX, NOFOLLOW
description: Leia as recomendações para a configuração do treinamento em relevância na Descoberta Eletrônica Avançada para classificar arquivos por relevância e gerar resultados analíticos.
ms.openlocfilehash: 8ba09babc91f233514cd0195c3e1da08b07ccb3c
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760205"
---
# <a name="manage-relevance-setup-in-advanced-ediscovery-classic"></a>Gerenciar a configuração da Relevância na Descoberta Eletrônica Avançada (clássica)

> [!NOTE]
> A Descoberta Eletrônica Avançada exige um Office 365 E3, com um complemento de Conformidade Avançada ou uma assinatura do E5 para sua organização. Se você não tiver esse plano e quiser tentar a Descoberta Eletrônica Avançada, poderá [Inscrever-se para uma avaliação do Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
 A tecnologia de Relevância de Descoberta Eletrônica Avançada emprega software guiado por especialista para pontuar arquivos por relevância. A Relevância da Descoberta Eletrônica Avançada pode ser usada para Avaliação de Caso Antecipado (ECA), remoção e análise do arquivo de exemplo. 
  
 A Descoberta Eletrônica Avançada inclui os componentes de treinamento e marcação de Relevância de arquivos relevantes a um caso. A Descoberta Eletrônica Avançada aprende com os exemplos treinados de arquivos relevantes e não relevantes para fornecer pontuações de relevância para cada arquivo e gera resultados analíticos que podem ser usados durante e após o processo de revisão do arquivo. 
  
## <a name="guidelines-for-setting-up-relevance-training"></a>Diretrizes para configurar o treinamento de relevância

 No Advance eDiscovery, na janela **Casos**, selecione um caso e clique em **Ir para o caso**. Clique em **Relevância** \> **Configurar relevância**. Siga estas diretrizes recomendadas para configurar a Relevância. 
  
- **Marcação**: a eficácia do processo de treinamento de relevância interativa depende da capacidade de o especialista marcar os arquivos de amostra com precisão e consistência.

- **Problemas de caso**:
  
  - Para cada problema, use o mesmo especialista em todo o processo de treinamento de relevância. Não é permitido marcar simultaneamente o mesmo problema por vários especialistas.
  
  - Determine se cada grupo de arquivos é pertinente a apenas um problema específico.

  - Se um problema for definido de maneira muito genérica, o Advance eDiscovery poderá gerar arquivos demais que não são relevantes. Se um problema for definido de maneira muito estrita, o Processo de treinamento de relevância poderá levar mais tempo. 

  - Durante cada ciclo de treinamento de relevância, a Descoberta Eletrônica Avançada concentra-se em um único problema ativo e os resultados de exemplo provisórios são exibidos adequadamente.

  - Em um cenário de vários problemas, o modo de amostragem permite a seleção dos problemas a serem incluídos no processamento. Os problemas definidos como "desativados" não são tratados até o modo de amostragem ser alterado. Um problema pode estar "ocioso" ou "ativado" para apenas um especialista.

  - A Descoberta Eletrônica Avançada pode ser usada para gerar arquivos de privilégio de candidato. Configure um problema separado para privilégio. Se possível, treine e selecione primeiro para relevância e treine para privilégio no conjunto selecionado (recarregar o conjunto definido como um caso separado). 

  - O cálculo em lote pode ser realizado somente quando não houver amostras abertas (quando você clica em cálculo em lote, haverá uma lista de usuários com amostras abertas). Para "fechar" amostras de outros usuários (isso deverá ser executado somente se esses usuários não estiverem marcando essas amostras), um administrador pode usar o utilitário de "Modificar relevância" com a opção "Amostra de todos os usuários".

- **Metadados**: a Descoberta Eletrônica Avançada concentra-se no conteúdo e não considera metadados como parte dos critérios de relevância.

- **Riqueza**: se a riqueza para um problema for inferior a 3% após a avaliação, considere a propagação do treinamento em relevância com arquivos conhecidos relevantes e não relevantes.

- **Tamanho do arquivo**: Arquivos grandes (mais de 5.242.880 de caracteres de texto extraído) são ignorados em Relevância. Os arquivos não participam do processo de treinamento de relevância e não recebem uma pontuação de Relevância após o Lote de Cálculo. Os arquivos com mais de 5 MB podem ser incluídos no conjunto Avaliação.

## <a name="setting-up-case-issues"></a>Como configurar os problemas de caso

Os parâmetros descritos nesta seção estão disponíveis na Descoberta Eletrônica Avançada **Relevância** \> **Configuração de relevância**.
  
- Os problemas devem ser atribuídos a um usuário que treinará os arquivos.

- Os arquivos importados, em seguida, devem ser adicionados para o carregamento que está sendo processado.

- Defina e organize problemas com cuidado, porque isso poderá afetar os resultados de treinamento de relevância.

Após os parâmetros serem definidos, o revisor/especialista pode começar o treinamento dos arquivos na guia **Relevância**.
