---
title: Criar rótulos de confidencialidade
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como criar e gerenciar rótulos de sensibilidade.
ms.openlocfilehash: ff3f7eb5ffddf797e254fac0ed8fc87d96940455
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701658"
---
# <a name="protect-documents-with-sensitivity-labels"></a>Proteger documentos com rótulos de confidencialidade

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3VRGT?autoplay=false]

Os rótulos de confidencialidade permitem que você classifique e proteja o conteúdo que é confidencial para sua empresa.

## <a name="try-it"></a>Experimente!

1. No [centro de administração](https://admin.microsoft.com), selecione o centro de administração de **conformidade** .
1. Selecione **classificação** e, em seguida, **Rótulos de confidencialidade**.
1. Selecione **criar um rótulo** e, quando o aviso for exibido, selecione **Sim**.
1. Insira um **nome de rótulo**, uma **dica de ferramenta** e uma **Descrição**. Selecione **Avançar**.
1. Ative a **criptografia**. Escolha quando você deseja atribuir permissões, se deseja que o acesso dos usuários ao conteúdo expire e se você deseja permitir o acesso offline.
1. **Selecione atribuir permissões** e, em seguida, **adicione esses endereços de email ou domínios**.
1. Insira um endereço de email ou nome de domínio (como Contoso.org).  Selecione **Adicionar** e repetir para cada endereço de email ou domínio que você deseja adicionar.
1. Selecione **escolher permissões de predefinidas ou personalizadas**.
1. Use a lista suspensa para selecionar permissões predefinidas, como **revisor** ou **Visualizador**, ou selecione permissões **personalizadas** . Se você escolher **personalizado**, selecione as permissões da lista. Selecione **salvar**, **salvar** e **Avançar**.
1. Ative a **marcação de conteúdo** e escolha as marcações que você deseja usar.
1. Para cada marcação escolhida, selecione **Personalizar texto**. Insira o texto que você deseja que apareça no documento e defina as opções de fonte e layout. Selecione **salvar** e, em seguida, repita para qualquer marca adicional. Selecione **Avançar**.
1. Opcionalmente, ative a **prevenção de perda de dados de pontos de extremidade**. Selecione **Avançar**.
1. Opcionalmente, ative o **rotulamento automático**. Adicione uma condição. Por exemplo, em **detectar conteúdo que contém**, selecione **Adicionar uma condição**. Insira a condição; por exemplo, adicione uma condição que se o Passport, a segurança social ou outras informações confidenciais forem detectadas, o rótulo será adicionado. Selecione **Avançar**.
1. Revise suas configurações e selecione **criar**. Seu rótulo foi criado. Repita esse processo para qualquer rótulo adicional desejado.
1. Por padrão, os rótulos aparecem em aplicativos do Office nesta ordem: **confidencial**, **interno** e **público**. Para alterar a ordem, para cada rótulo, selecione **mais ações** (reticências) e mova o rótulo para cima ou para baixo. Normalmente, as permissões são listadas do nível mais alto para o maior de permissões.
1. Para adicionar um subrótulo a um rótulo, selecione **mais ações** e, em seguida, **Adicionar subnível**.
1. Quando terminar, escolha **publicar rótulos**, **escolha rótulos para publicar** e, em seguida, **Adicionar**. Selecione os rótulos que você deseja publicar e, em seguida, selecione **Adicionar**, **concluído** e **Avançar**.
1. Por padrão, a nova política de rótulo é aplicada a todos. Se você quiser limitar a quem a política é aplicada, selecione **escolher usuários ou grupos** e **Adicionar**. Selecione a quem você deseja aplicar a política e, em seguida, selecione **Adicionar**, **concluído** e **Avançar**.
1. Se você quiser um rótulo padrão para documentos e emails, selecione o rótulo desejado na lista suspensa. Revise as configurações restantes, ajuste conforme necessário e, em seguida, selecione **Avançar**.
1. Insira um **nome** e uma **Descrição** para a política. Selecione **Avançar**.
1. Revise suas configurações e selecione **publicar**.

Para que seus rótulos funcionem, cada usuário precisa baixar o cliente de rotulação Unificação de proteção de informações do Azure. Pesquise na Web **AzinfoProtection_UL.exe**, baixe-o a partir do centro de download da Microsoft e execute-o nos computadores dos usuários.

Na próxima vez que abrir um aplicativo do Office como o Word, você verá os rótulos de sensibilidade que foram criados. Para alterar ou aplicar um rótulo, selecione sensibilidade e escolha um rótulo.

