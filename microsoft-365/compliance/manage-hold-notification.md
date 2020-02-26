---
title: Gerenciar as notificações de retenção
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Use o fluxo de trabalho de comunicações em descoberta eletrônica avançada para acompanhar o status de suas notificações de retenção legal e, se necessário, atualize e reenvie-as.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280109"
---
# <a name="manage-hold-notifications"></a>Gerenciar as notificações de retenção

Depois de iniciar seu fluxo de trabalho de notificação de retenção legal, você pode usar o fluxo de trabalho de comunicações em descoberta eletrônica avançada para acompanhar o status de suas comunicações. A guia comunicações contém uma lista de todas as notificações dentro da caixa de descoberta eletrônica avançada. Você pode ver detalhes como o número de responsáveis que foram atribuídos ou que confirmaram o aviso.

## <a name="monitor-acknowledgments"></a>Monitorar confirmações

Depois de selecionar uma comunicação na guia **comunicações** , você pode exibir uma lista de responsáveis que reconheceram um aviso de isenção. 

1. No centro de conformidade, acesse **ediscovery > descoberta eletrônica avançada**.

2. Selecione uma ocorrência e, em seguida, clique na guia **comunicações** .

3. Selecione uma comunicação para exibir a página do submenu de **comunicação do responsáveis** .

Uma lista de responsáveis associados à comunicação selecionada é exibida na página de submenu de comunicação. Esta página também exibe informações sobre quantas confirmações foram recebidas e quantas estão pendentes. A página também mostra quais responsáveis enviaram uma confirmação de que receberam a notificação de espera.

## <a name="re-send-a-hold-notice"></a>Enviar novamente um aviso de isenção

Ocasionalmente, os responsáveis perderão o controle das mensagens de email em seu trabalho diário. Ou para um caso de litígio de longa duração, um membro pode entrar em contato com você ou outras pessoas e solicitar que você envie novamente um aviso. Ao gerenciar o fluxo de trabalho de comunicações para notificações de retenção legal, talvez seja necessário enviar novamente um aviso para trazê-lo de volta à "parte superior da caixa de correio de um usuário".

Para reenviar um aviso de retenção para um bloqueador:

1. Em descoberta eletrônica avançada, selecione uma ocorrência e, em seguida, clique na guia **comunicações** .

2. Selecione uma comunicação para exibir a página do submenu de **comunicação do responsáveis** .

3. Clique em **mais > aviso de reenvio de bloqueio**.

4. Na página do submenu de **aviso de espera de reenvio** , selecione os responsáveis que você deseja enviar o aviso novamente e digite um motivo opcional.

5. Clique em **reenviar** para enviar o aviso para os responsáveis selecionados.

Se um funcionário não tiver confirmado a notificação de espera, o lembrete e o fluxo de trabalho de escalonamento serão reiniciados. Se um reconheceu o aviso de espera, o responsáveis receberá uma cópia do aviso de isenção original.

> [!NOTE]
> Você só pode reenviar uma notificação de retenção legal para os responsáveis que são atribuídos à comunicação. 

## <a name="update-preservation-requirements"></a>Requisitos de preservação da atualização
  
Como o caso progride, os responsáveis podem ser necessários para preservar dados adicionais ou menos do que foram instruídos anteriormente. Em termos de descoberta eletrônica, você precisa emitir novamente o aviso de retenção com conteúdo atualizado.

Para atualizar o conteúdo do aviso de bloqueio inicial:

1. Em descoberta eletrônica avançada, selecione uma ocorrência e, em seguida, clique na guia **comunicações** .

2. Selecione o aviso de isenção que você deseja atualizar e clique em **Editar** na página do submenu de **comunicação do responsáveis** .

3. No Assistente para **Editar comunicação** , clique em **definir conteúdo do portal** no painel esquerdo do assistente e atualize o conteúdo do aviso.

4. Clique em **Salvar**.

O aviso de reemissão será enviado a todos os responsáveis atribuídos à notificação de retenção legal. Além disso, se o lembrete ou o aviso de escalonamento estiver habilitado, os fluxos de trabalho desses tipos de aviso serão reiniciados.

## <a name="update-legal-hold-notifications-and-settings"></a>Atualizar notificações e configurações de retenção legal

Ao atualizar o conteúdo ou as configurações do aviso de emissão, lançamento, reemissão, lembrete ou escalonamento, essas alterações serão aplicadas a todas as comunicações futuras geradas pelo fluxo de trabalho.

## <a name="more-information"></a>Mais informações

- [Adicionar custodiantes a uma ocorrência](add-custodians-to-case.md)

- [Criar um aviso de retenção legal](create-hold-notification.md)

- [Confirmar uma notificação de retenção](acknowledge-hold-notification.md)
