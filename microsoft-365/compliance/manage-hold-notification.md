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
description: Use o fluxo de trabalho de comunicação na Descoberta Eletrônica Avançada para controlar o status de suas notificações de responsabilidade legal e, se necessário, atualizá-las e reenvia-las.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280109"
---
# <a name="manage-hold-notifications"></a>Gerenciar as notificações de retenção

Depois de iniciar seu fluxo de trabalho de notificação de responsabilidade legal, você pode usar o fluxo de trabalho de comunicação na Descoberta Eletrônica Avançada para controlar o status de suas comunicações. A guia Comunicações contém uma lista de todas as notificações em seu caso de Descoberta Eletrônica Avançada. Você pode ver detalhes como o número de custodiantes que foram atribuídos ou reconheceram o aviso.

## <a name="monitor-acknowledgments"></a>Monitorar confirmações

Depois de selecionar uma comunicação **na** guia Comunicações, você pode exibir uma lista de custodiantes que reconheceram um aviso de espera. 

1. No centro de conformidade, vá para Descoberta > **eDiscovery Avançada.**

2. Selecione uma ocorrência e clique na guia **Comunicações.**

3. Selecione uma comunicação para exibir a **página do flyout de** comunicação custodiada.

Uma lista de custodiantes associados à comunicação selecionada é exibida na página do flyout de comunicação. Esta página também exibe informações sobre quantas confirmações foram recebidas e quantas estão pendentes. A página também mostra quais custodiantes enviaram uma confirmação de que receberam a notificação de espera.

## <a name="re-send-a-hold-notice"></a>Re-enviar um aviso de espera

Ocasionalmente, os custodiantes perdem o controle das mensagens de email no trabalho do dia a dia. Ou, para um caso de litígio de longa duração, um custodiante pode entrar em contato com você ou outras pessoas e solicitar que você envie um aviso outra vez. À medida que você gerencia o fluxo de trabalho de comunicações para avisos de responsabilidade legal, talvez seja necessário reen o envio de um aviso para que ele volte à "parte superior da caixa de correio de um usuário".

Para re-enviar um aviso de espera a um custodiatário:

1. Na Descoberta Eletrônica Avançada, selecione uma ocorrência e clique **na** guia Comunicações.

2. Selecione uma comunicação para exibir a **página do flyout de** comunicação custodiada.

3. Clique **em > Re-enviar aviso de espera.**

4. Na página **do sub-sub-aviso** de re envio de aviso, selecione os custodiantes que você quer re-enviar o aviso e digite um motivo opcional.

5. Clique **em Re-enviar** para enviar o aviso aos custodiantes selecionados.

Se um custodiante não tiver reconhecido a notificação de espera, o fluxo de trabalho de lembrete e escalonamento será reiniciado. Se um custodiante tiver reconhecido a notificação de responsabilidade, o custodiante receberá uma cópia do aviso de espera original.

> [!NOTE]
> Você só pode resendar uma notificação de espera legal para custodiantes que estão atribuídos à comunicação. 

## <a name="update-preservation-requirements"></a>Atualizar os requisitos de preservação
  
À medida que o caso progride, os custodiantes podem ser obrigados a preservar dados adicionais ou menores do que foi instruído anteriormente. Em termos de Descoberta eDiscovery, você precisa emitir o aviso de espera com conteúdo atualizado.

Para atualizar o conteúdo do aviso de espera inicial:

1. Na Descoberta Eletrônica Avançada, selecione uma ocorrência e clique **na** guia Comunicações.

2. Selecione o aviso de espera que você deseja atualizar e clique em **Editar** na página do flyout **de** comunicação custodiada.

3. No assistente **Editar Comunicação,** clique em Definir Conteúdo do **Portal** no painel esquerdo do assistente e atualize o conteúdo do aviso.

4. Clique em **Salvar**.

A notificação de reemissão será enviada a todos os responsáveis atribuídos à notificação de espera legal. Além disso, se o aviso lembrete ou escalonamento estiver habilitado, os fluxos de trabalho para esses tipos de avisos serão reiniciados.

## <a name="update-legal-hold-notifications-and-settings"></a>Atualizar notificações e configurações de espera legal

Quando você atualiza o conteúdo ou as configurações do aviso de Emissão, Lançamento, Reemissão, Lembrete ou Escalonamento, essas alterações serão aplicadas a todas as comunicações futuras geradas pelo fluxo de trabalho.

## <a name="more-information"></a>Mais informações

- [Adicionar custodiantes a uma ocorrência](add-custodians-to-case.md)

- [Criar um aviso de espera legal](create-hold-notification.md)

- [Confirmar uma notificação de retenção](acknowledge-hold-notification.md)
