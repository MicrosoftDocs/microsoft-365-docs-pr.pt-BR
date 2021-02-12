---
title: Gerenciar aplicativos na Área de Trabalho Gerenciada da Microsoft
description: Informações sobre como atualizar aplicativos de linha de negócios implantados em dispositivos da Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
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
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Gerenciar aplicativos da linha empresarial na Área de Trabalho Gerenciada da Microsoft

<!--Application management -->

Há algumas maneiras de gerenciar atualizações de aplicativos para aplicativos que você tenha integrado à Área de Trabalho Gerenciada da Microsoft e implantado em seus dispositivos da Área de Trabalho Gerenciada da Microsoft. Você pode fazer atualizações de aplicativos no portal da Área de Trabalho Gerenciada da Microsoft ou no Intune. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Atualizar aplicativos de linha de negócios na Área de Trabalho Gerenciada da Microsoft

**Para atualizar seus aplicativos de linha de negócios no portal da Área de Trabalho Gerenciada da Microsoft**
1. Entre no Portal [de Administração da Área de Trabalho Gerenciada da Microsoft.](https://aka.ms/mmdportal)
2. Em **Inventário,** selecione **Aplicativos**.  
3. Selecione o aplicativo que você deseja atualizar e, em seguida, selecione **Editar.**
4. Em **Gerenciar,** selecione **Propriedades**. 
5. Clique **no arquivo do pacote do** aplicativo e navegue para carregar um novo arquivo de pacote do aplicativo.
6. Selecione **o arquivo do pacote do aplicativo.**
7. Selecione o ícone da pasta e navegue até o local do arquivo de aplicativo atualizado. Selecione **Abrir**. As informações do aplicativo são atualizadas com as informações do pacote.
8. Verifique se **a versão do aplicativo** reflete o pacote do aplicativo atualizado. 

O aplicativo atualizado será implantado nos dispositivos do usuário.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Atualizar aplicativos de linha de negócios no Intune

**Para atualizar seus aplicativos de linha de negócios no Intune**
1. Entre no [portal do Azure.](https://portal.azure.com)
2. Selecione **Todos os Serviços** do  >  **Intune.** O Intune está na **seção Monitoramento + Gerenciamento.**
3. Selecione **Aplicativos cliente > aplicativos**.
4. Encontre e selecione seu aplicativo na lista de aplicativos.
5. Na folha **Visão geral,** selecione **Propriedades**.
6. Selecione **o arquivo do pacote do aplicativo.**
7. Selecione o ícone da pasta e navegue até o local do arquivo de aplicativo atualizado. Selecione **Abrir**. As informações do aplicativo são atualizadas com as informações do pacote.
8. Verifique se **a versão do aplicativo** reflete o pacote do aplicativo atualizado.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Reverter um aplicativo para uma versão anterior

Se houver um erro encontrado quando uma nova versão de um aplicativo for implantada, você poderá reverter para uma versão anterior. O processo descrito aqui é para aplicativos em que o tipo está listado como aplicativo de linha de **negócios MSI** do Windows ou aplicativo **do Windows (Win 32) - visualização**

**Para reverter um aplicativo de linha de negócios para uma versão anterior**

1. Entre no Portal [de Administração da Área de Trabalho Gerenciada da Microsoft.](https://aka.ms/mmdportal)
2. Em **Inventário,** selecione **Aplicativos**.  
3. Selecione o aplicativo que você precisa reverter e selecione **Editar.**
4. Em **Gerenciar,** selecione **Propriedades**. 
    - Para aplicativos de linha de negócios **MSI** do Windows, selecione Informações do aplicativo e, em  **Ignorar** versão do aplicativo, selecione **Sim.**
    - Para **o aplicativo do Windows (Win 32) -** aplicativos de visualização, selecione **Informações** do aplicativo, selecione regras de **detecção** e, em seguida, **selecione Adicionar**. 
    Se houver uma regra MSI, verifique se a verificação da versão do produto **MSI** está definida como **Não.**
5. [Carregue uma versão anterior do arquivo de origem do aplicativo no](../get-started/deploy-apps.md) portal do Administrador da Área de Trabalho Gerenciada da Microsoft.  

