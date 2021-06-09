---
title: Conectar seu domínio ao Microsoft 365
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como conectar seu domínio ao Microsoft 365.
ms.openlocfilehash: 1bec66a43026321ddf1979c73902a533bee3a07b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925105"
---
# <a name="connect-your-domain-to-microsoft-365-for-business"></a>Conexão seu domínio para Microsoft 365 para empresas

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LFpy?autoplay=false]

Depois de configurar o Microsoft 365 e mover seus dados de email do Google Workspace, você poderá conectar seu domínio ao Microsoft 365. 

Primeiro, você precisará excluir registros DNS existentes do Google e, em seguida, podemos adicionar novos registros DNS Microsoft 365.

## <a name="try-it"></a>Experimente!

1. Entre no console de administração do Google Workspace em [admin.google.com](https://admin.google.com).
1. Selecione **Domínios,** **Gerenciar domínios,** **Exibir detalhes,** **Gerenciar domínio** e **DNS** na nav esquerda.
1. Role para baixo até **Registros sintéticos,** abra **o Espaço de Trabalho do Google,** selecione **Excluir** e **Excluir** novamente.
1. Role para baixo até **Registros de** recursos personalizados e exclua quaisquer registros DNS existentes que apareçam, incluindo qualquer um que você possa ter criado anteriormente para Microsoft 365.
1. Vá para o centro [de administração Microsoft 365.](https://admin.microsoft.com)
1. Na nav esquerda, escolha, **Mostrar tudo** **,** Configurações , **Domínios**.
1. Em seguida, escolha seu domínio padrão.
1. Selecione **Continuar a** instalação , em seguida, para conectar seu domínio, escolha  **Continuar**.
1. Role para baixo para exibir os registros DNS que precisam ser copiados para o Google.
1. Abra **registros MX** e, em **Pontos para resolver ou valor,** copie o registro.
1. Retorne ao Google e, na **seção** Registros de recursos personalizados, abra o menu suspenso tipo de registro e selecione **MX**.
1. No campo **Dados,** colar o registro copiado.
1. Em seguida, selecione **OK**.
1. Repita o processo para registros CNAME e TXT e adicione os valores na página de gerenciamento DNS do Google.
1. Retorne ao centro de administração Microsoft 365 e selecione **Continuar**.

    Sua configuração de domínio está concluída.