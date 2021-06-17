---
title: Atribuir dispositivos a um grupo de implantação
description: Como especificar em qual grupo de implantação você deseja que os dispositivos sejam
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985511"
---
# <a name="assign-devices-to-a-deployment-group"></a>Atribuir dispositivos a um grupo de implantação

Área de Trabalho Gerenciada da Microsoft atribuirá dispositivos aos vários grupos de implantação, mas você pode especificar ou alterar o grupo que um dispositivo é atribuído a um dispositivo usando o portal de administração. Você altera a atribuição depois que um dispositivo é registrado ou depois que um usuário se registra.

> [!IMPORTANT]
> Se você alterar a atribuição, as políticas específicas desse grupo serão aplicadas ao dispositivo. A alteração pode instalar a versão mais recente do Windows 10 (incluindo qualquer novo recurso ou atualizações de qualidade). É melhor mover apenas alguns dispositivos no início e verificar a experiência do usuário resultante. Esteja ciente de que determinadas atualizações reiniciarão o dispositivo. Verifique se você selecionou os dispositivos certos a atribuir. Pode levar até 24 horas para que a atribuição entre em vigor.

Para atribuir dispositivos a um grupo de implantação, siga estas etapas. Se você quiser mover dispositivos separados para grupos diferentes, repita estas etapas para cada grupo.

1. Em Microsoft Endpoint Manager, selecione **Dispositivos** no painel esquerdo. Na seção **Área de Trabalho Gerenciada da Microsoft,** selecione **Dispositivos**.
2. Selecione os dispositivos que você deseja atribuir. Todos os dispositivos selecionados serão atribuídos ao grupo especificado.
3. Selecione **Ações do dispositivo** no menu.
4. Selecione **Atribuir dispositivo ao grupo**. Um fly-in é aberto.
5. Use o menu suspenso para selecionar o grupo para o que mover dispositivos e, em seguida, **selecione Salvar**. O **Grupo atribuído por mudará** para **Pendente**.

Quando a atribuição for concluída, **o** Grupo atribuído por será alternada  para **Admin** (indicado que você fez a alteração) e a coluna Grupo mostrará a nova atribuição de grupo.

> [!NOTE]
> Não é possível mover dispositivos para outros grupos se eles estão no estado de registro "erro" ou "pendente".
>
>Se um dispositivo não tiver sido removido corretamente, ele poderá mostrar um status de "pronto". Se você mover esse dispositivo, é possível que a movimentação não seja concluída. Se você não  vir Grupo atribuído por alteração para **Pendente** na Etapa 5, verifique se o dispositivo está disponível pesquisando-o no Intune. Para obter mais informações, confira [Ver detalhes do dispositivo no Intune](/mem/intune/remote-actions/device-inventory).