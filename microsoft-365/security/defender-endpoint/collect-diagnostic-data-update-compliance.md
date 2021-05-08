---
title: Coletar dados de diagnóstico para Atualização de Conformidade e Windows Defender Microsoft Defender Antivírus
description: Use uma ferramenta para coletar dados para solucionar problemas de Conformidade de Atualização ao usar o Microsoft Defender Antivírus de Avaliação
keywords: solução de problemas, erro, correção, conformidade de atualização, oms, monitor, relatório, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 2aaf3d1c650713a7f6cfb7b9abb9f2232013d6db
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274791"
---
# <a name="collect-update-compliance-diagnostic-data-for-microsoft-defender-av-assessment"></a>Coletar dados de diagnóstico de Conformidade de Atualização para Avaliação do Microsoft Defender AV

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](/microsoft-365/security/defender-endpoint/)

Este artigo descreve como coletar dados de diagnóstico que podem ser usados pelas equipes de suporte e engenharia da Microsoft para ajudar a solucionar problemas que você pode encontrar ao usar a seção Avaliação do Microsoft Defender AV no complemento Conformidade de Atualização.

Antes de tentar esse processo, certifique-se de ler Solucionar problemas Microsoft Defender Antivírus [relatórios,](troubleshoot-reporting.md)todos os pré-requisitos necessários e tomar quaisquer outras etapas sugeridas de solução de problemas.

Em pelo menos dois dispositivos que não estão relatando ou aparecendo em Conformidade de Atualização, obtenha o arquivo de diagnóstico .cab, seguindo as seguintes etapas:

1. Abra uma versão no nível de administrador do prompt de comando da seguinte forma:
        
    a. Abra o menu **Iniciar.**

    b. Digite **cmd**. Clique com o botão direito do mouse **no Prompt de** Comando e clique em Executar como **administrador**.

    c. Insira credenciais de administrador ou aprove o prompt.
        
2. Navegue até o Windows Defender diretório. Por padrão, é `C:\Program Files\Windows Defender`

3. Digite o seguinte comando e pressione **Enter**
        
    ```Dos
    mpcmdrun -getfiles
    ```
    
4. Um .cab será gerado que contém vários logs de diagnóstico. O local do arquivo será especificado na saída no prompt de comando. Por padrão, o local é `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` .

5. Copie esses .cab para um local que pode ser acessado pelo suporte da Microsoft. Um exemplo pode ser uma pasta de OneDrive protegida por senha que você pode compartilhar conosco.

6. Envie um email usando o modelo de email de suporte de Conformidade <a href="mailto:ucsupport@microsoft.com?subject=WDAV assessment issue&body=I%20am%20encountering%20the%20following%20issue%20when%20using%20Windows%20Defender%20AV%20in%20Update%20Compliance%3a%20%0d%0aI%20have%20provided%20at%20least%202%20support%20.cab%20files%20at%20the%20following%20location%3a%20%3Caccessible%20share%2c%20including%20access%20details%20such%20as%20password%3E%0d%0aMy%20OMS%20workspace%20ID%20is%3a%20%0d%0aPlease%20contact%20me%20at%3a">de</a>Atualização e preencha o modelo com as seguintes informações:
  
    ```
    I am encountering the following issue when using Microsoft Defender Antivirus in Update Compliance:
    
    I have provided at least 2 support .cab files at the following location: <accessible share, including access details such as password>

    My OMS workspace ID is:

    Please contact me at:
    ```

## <a name="see-also"></a>Confira também

- [Solucionar problemas Windows Defender Microsoft Defender Antivírus relatórios](troubleshoot-reporting.md)