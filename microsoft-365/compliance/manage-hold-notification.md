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
description: Use o fluxo de trabalho de comunicações Advanced eDiscovery para rastrear o status de suas notificações de espera legal e, se necessário, atualizá-las e reendá-las.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280109"
---
# <a name="manage-hold-notifications"></a>Gerenciar as notificações de retenção

Depois de iniciar o fluxo de trabalho de notificação de espera legal, você poderá usar o fluxo de trabalho de comunicações Advanced eDiscovery controlar o status de suas comunicações. A guia Comunicações contém uma lista de todas as notificações em seu Advanced eDiscovery caso. Você pode ver detalhes como o número de custodiantes que foram atribuídos ou reconheceram o aviso.

## <a name="monitor-acknowledgments"></a>Monitorar confirmações

Depois de selecionar uma comunicação na guia **Comunicações,** você pode exibir uma lista de custodiantes que reconheceram um aviso de responsabilidade. 

1. No centro de conformidade, vá para **Descoberta > Advanced eDiscovery**.

2. Selecione uma ocorrência e clique na guia **Comunicações.**

3. Selecione uma comunicação para exibir a **página de sobrevoo** de comunicação custodiada.

Uma lista de custodiantes associados à comunicação selecionada é exibida na página de sobrevoo de comunicação. Esta página também exibe informações e sobre quantos reconhecimentos foram recebidos e quantos são pendentes. A página também mostra quais custodiantes enviaram um reconhecimento de que receberam a notificação de responsabilidade.

## <a name="re-send-a-hold-notice"></a>Re-enviar um aviso de espera

Ocasionalmente, os custodiantes perdem o controle das mensagens de email no trabalho do dia a dia. Ou para um caso de litígio de longa duração, um custodiante pode entrar em contato com você ou outras pessoas e solicitar que você envie um aviso. Ao gerenciar o fluxo de trabalho de comunicações para avisos de responsabilidade legal, talvez seja necessário enviar novamente um aviso para trazê-lo de volta para a "parte superior da caixa de correio de um usuário".

Para re-enviar um aviso de espera a um custodiado:

1. Em Advanced eDiscovery, selecione uma ocorrência e clique na guia **Comunicações.**

2. Selecione uma comunicação para exibir a **página de sobrevoo** de comunicação custodiada.

3. Clique **em Mais > aviso de re-envio de espera.**

4. Na página **Sub-aviso** de espera de re envio, selecione os custodiantes que você deve enviar o aviso e digite um motivo opcional.

5. Clique **em Re-enviar** para enviar o aviso aos custodiantes selecionados.

Se um custodiante não tiver reconhecido a notificação de espera, o fluxo de trabalho de lembrete e escalonamento será reiniciado. Se um custodiante tiver reconhecido o aviso de responsabilidade, o custodiante receberá uma cópia do aviso de responsabilidade original.

> [!NOTE]
> Você só pode rescreviar uma notificação de espera legal aos custodiantes atribuídos à comunicação. 

## <a name="update-preservation-requirements"></a>Atualizar requisitos de preservação
  
À medida que o caso avança, os custodiantes podem ser necessários para preservar dados adicionais ou menores do que os instruídos anteriormente. Em termos de Descoberta e, você precisa emitir o aviso de responsabilidade com o conteúdo atualizado.

Para atualizar o conteúdo do aviso de espera inicial:

1. Em Advanced eDiscovery, selecione uma ocorrência e clique na guia **Comunicações.**

2. Selecione o aviso de espera que você deseja atualizar e clique em **Editar** na **página** sobrevoo de comunicação custodiada.

3. No assistente **Editar Comunicação,** clique em **Definir Conteúdo** do Portal no painel esquerdo do assistente e atualize o conteúdo do aviso.

4. Clique em **Salvar**.

O aviso de remissão será enviado a todos os custodiantes atribuídos à notificação de missão legal. Além disso, se o aviso Lembrete ou Escalonamento estiver habilitado, os fluxos de trabalho para esses tipos de avisos serão reiniciados.

## <a name="update-legal-hold-notifications-and-settings"></a>Atualizar notificações e configurações de espera legal

Quando você atualiza o conteúdo ou as configurações do aviso de Emissão, Lançamento, Reemissão, Lembrete ou Escalonamento, essas alterações se aplicarão a todas as comunicações futuras geradas pelo fluxo de trabalho.

## <a name="more-information"></a>Mais informações

- [Adicionar custodiantes a uma ocorrência](add-custodians-to-case.md)

- [Criar um aviso de espera legal](create-hold-notification.md)

- [Confirmar uma notificação de retenção](acknowledge-hold-notification.md)
