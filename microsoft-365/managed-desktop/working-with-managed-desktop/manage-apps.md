---
title: Gerenciar aplicativos em Área de Trabalho Gerenciada da Microsoft
description: Informações sobre como atualizar aplicativos de linha de negócios implantados para Área de Trabalho Gerenciada da Microsoft dispositivos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: b016d8458b4b4cc9f6b684d3b8a3c0a1e1322fef
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925402"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Gerenciar aplicativos da linha empresarial na Área de Trabalho Gerenciada da Microsoft

<!--Application management -->

Há algumas maneiras de gerenciar atualizações de aplicativos para aplicativos que você Área de Trabalho Gerenciada da Microsoft e implantado em seus dispositivos Área de Trabalho Gerenciada da Microsoft. Você pode fazer atualizações de aplicativos no portal Área de Trabalho Gerenciada da Microsoft ou no Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Atualizar aplicativos de linha de negócios no Área de Trabalho Gerenciada da Microsoft

**Para atualizar seus aplicativos de linha de negócios no Área de Trabalho Gerenciada da Microsoft portal**
1. Entre no portal [Área de Trabalho Gerenciada da Microsoft Admin](https://aka.ms/mmdportal).
2. Em **Inventário,** selecione **Aplicativos**.  
3. Selecione o aplicativo que você deseja atualizar e selecione **Editar**.
4. Em **Gerenciar,** selecione **Propriedades**. 
5. Clique **em Arquivo de pacote do aplicativo** e, em seguida, navegue para carregar um novo arquivo de pacote de aplicativo.
6. Selecione **Arquivo de pacote do aplicativo**.
7. Selecione o ícone de pasta e navegue até o local do arquivo de aplicativo atualizado. Selecione **Abrir**. As informações do aplicativo são atualizadas com as informações do pacote.
8. Verifique se **a versão do aplicativo** reflete o pacote de aplicativos atualizado. 

O aplicativo atualizado será implantado nos dispositivos do usuário.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Atualizar aplicativos de linha de negócios no Intune

**Para atualizar seus aplicativos de linha de negócios no Intune**
1. Entre no [portal do Azure.](https://portal.azure.com)
2. Selecione **Todos os Serviços** do  >  **Intune**. O Intune está na **seção Monitoramento + Gerenciamento.**
3. Selecione **Aplicativos cliente > Aplicativos**.
4. Encontre e selecione seu aplicativo na lista de aplicativos.
5. Na folha **Visão geral,** selecione **Propriedades**.
6. Selecione **Arquivo de pacote do aplicativo**.
7. Selecione o ícone de pasta e navegue até o local do arquivo de aplicativo atualizado. Selecione **Abrir**. As informações do aplicativo são atualizadas com as informações do pacote.
8. Verifique se **a versão do aplicativo** reflete o pacote de aplicativos atualizado.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Reverter um aplicativo para uma versão anterior

Se houver um erro encontrado quando uma nova versão de um aplicativo for implantada, você poderá reverter para uma versão anterior. O processo descrito aqui é para aplicativos em que o tipo está listado como Windows aplicativo de linha de negócios **MSI** ou aplicativo **Windows (Win 32) - visualização**

**Para reverter um aplicativo de linha de negócios para uma versão anterior**

1. Entre no portal [Área de Trabalho Gerenciada da Microsoft Admin](https://aka.ms/mmdportal).
2. Em **Inventário,** selecione **Aplicativos**.  
3. Selecione o aplicativo que você precisa reverter e selecione **Editar**.
4. Em **Gerenciar,** selecione **Propriedades**. 
    - Para Windows aplicativos de linha de negócios **MSI,** selecione Informações do aplicativo **e,** em **Seguida,** em Ignorar versão do aplicativo, selecione **Sim**.
    - Para **Windows app (Win 32) - aplicativos** de visualização, selecione Informações do **aplicativo,** selecione **Regras** de detecção e selecione **Adicionar**. 
    Se houver uma regra MSI, verifique se a verificação da versão do produto **MSI** está definida como **Não**.
5. [Upload uma versão anterior do arquivo](../get-started/deploy-apps.md) de origem do aplicativo para Área de Trabalho Gerenciada da Microsoft portal de administração.  

