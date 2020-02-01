---
title: Gerenciar aplicativos na área de trabalho gerenciada da Microsoft
description: Informações sobre como atualizar aplicativos de linha de negócios implantados em dispositivos de área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600678"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Gerenciar aplicativos de linha de negócios na área de trabalho gerenciada da Microsoft

<!--Application management -->

Há algumas maneiras de gerenciar as atualizações de aplicativo para aplicativos que você colocou na área de trabalho gerenciada da Microsoft e implantadas em seus dispositivos de área de trabalho gerenciada da Microsoft. Você pode fazer atualizações de aplicativos no portal de área de trabalho gerenciada da Microsoft ou no Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Atualizar aplicativos de linha de negócios na área de trabalho gerenciada da Microsoft

**Para atualizar seus aplicativos de linha de negócios no portal de área de trabalho gerenciada da Microsoft**
1. Entre no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mmdportal).
2. Em **inventário**, selecione **aplicativos**.  
3. Selecione o aplicativo que você deseja atualizar e, em seguida, selecione **Editar**.
4. Em **gerenciar**, selecione **Propriedades**. 
5. Clique em **arquivo de pacote de aplicativos**e navegue para carregar um novo arquivo de pacote de aplicativos.
6. Selecione o **arquivo do pacote de aplicativos**.
7. Selecione o ícone da pasta e navegue até o local do arquivo do aplicativo atualizado. Selecione **Abrir**. As informações do aplicativo são atualizadas com as informações do pacote.
8. Verifique se a **versão do aplicativo** reflete o pacote de aplicativos atualizado. 

O aplicativo atualizado será implantado nos dispositivos do usuário.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Atualizar aplicativos de linha de negócios no Intune

**Para atualizar seus aplicativos de linha de negócios no Intune**
1. Entre no [portal do Azure](https://portal.azure.com).
2. Selecione **todos os serviços** > do**Intune**. O Intune está na seção **monitoramento + gerenciamento** .
3. Selecione **aplicativos cliente > aplicativos**.
4. Localize e selecione seu aplicativo na lista de aplicativos.
5. Na folha **visão geral** , selecione **Propriedades**.
6. Selecione o **arquivo do pacote de aplicativos**.
7. Selecione o ícone da pasta e navegue até o local do arquivo do aplicativo atualizado. Selecione **Abrir**. As informações do aplicativo são atualizadas com as informações do pacote.
8. Verifique se a **versão do aplicativo** reflete o pacote de aplicativos atualizado.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Reverter um aplicativo para uma versão anterior

Se houver um erro encontrado quando uma nova versão de um aplicativo for implantada, você poderá reverter para uma versão anterior. O processo descrito aqui é para aplicativos onde tipo está listado como **Windows MSI linha de negócios** ou **aplicativo windows (Win 32)-Preview**

**Para reverter um aplicativo de linha de negócios para uma versão anterior**

1. Entre no [portal de administração de área de trabalho gerenciada da Microsoft](https://aka.ms/mmdportal).
2. Em **inventário**, selecione **aplicativos**.  
3. Selecione o aplicativo que você precisa reverter e, em seguida, selecione **Editar**.
4. Em **gerenciar**, selecione **Propriedades**. 
    - Para aplicativos de aplicativos **de linha de negócios do Windows MSI** , selecione **informações do aplicativo**e, em **ignorar versão do aplicativo**, selecione **Sim**.
    - Para o **aplicativo Windows (Win 32)-Visualizar** aplicativos, selecione **informações do aplicativo**, selecione regras de **detecção**e, em seguida, selecione **Adicionar**. 
    Se houver uma regra MSI, verifique se a **verificação de versão do produto MSI** está definida como **não**.
5. [Carregar uma versão anterior do arquivo de origem do aplicativo](../get-started/deploy-apps.md) no portal de administração de área de trabalho gerenciada da Microsoft.  

