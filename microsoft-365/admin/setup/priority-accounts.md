---
title: Gerenciar e monitorar contas prioritárias
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Monitorar mensagens enviadas por email com falha e atraso enviadas para ou de contas com alto impacto comercial.
ms.openlocfilehash: b31cbf79b5b1b8f882c4c7bc8926779410baefe3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914049"
---
# <a name="manage-and-monitor-priority-accounts"></a>Gerenciar e monitorar contas prioritárias

Em cada organização do Microsoft 365, há pessoas essenciais, como executivos, líderes, gerentes ou outros usuários que têm acesso a informações confidenciais, proprietárias ou de alta prioridade.

Para ajudar sua organização a proteger essas contas, agora você pode designar usuários específicos como contas prioritárias e aproveitar recursos específicos do aplicativo que oferecem a eles proteção extra. No futuro, mais aplicativos e recursos darão suporte a contas de prioridade e, para começar, anunciamos dois **recursos:** proteção de conta de prioridade e monitoramento de fluxo de **emails premium.**

- Proteção de conta de prioridade **–** o Microsoft Defender para Office 365 (anteriormente a Proteção Avançada contra Ameaças do Office 365) dá suporte a contas prioritárias como marcas que podem ser usadas em filtros em alertas, relatórios e investigações. Para obter mais informações, confira [Marcas de usuário no Microsoft Defender para Office 365](../../security/office-365-security/user-tags.md).
- **Monitoramento de Fluxo de Email Premium** - O fluxo de emails saudável pode ser fundamental para o sucesso dos negócios, e atrasos ou falhas de entrega podem ter um impacto negativo sobre a empresa. Você pode escolher um limite para emails com falha ou atraso, receber alertas quando esse limite for excedido e exibir um relatório de problemas de email para contas de prioridade. Para obter mais informações, confira Problemas de email para o relatório de contas [de prioridade no EAC moderno](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

Para práticas recomendadas de segurança para contas prioritárias, consulte [Recomendações de segurança para contas prioritárias.](../../security/office-365-security/security-recommendations-for-priority-accounts.md)

## <a name="before-you-begin"></a>Antes de começar

O **recurso de proteção** de conta de prioridade descrito neste tópico está disponível apenas para organizações que atendem aos seguintes requisitos:

- Microsoft Defender para Office 365 Plano 2, incluindo aqueles com Office 365 E3, Office 365 E5, Microsoft 365 E5 ou Microsoft 365 E5 Security.

O recurso Monitoramento de **Fluxo de** Email Premium descrito neste tópico está disponível apenas para organizações que atendem aos seguintes requisitos:

- Sua organização precisa ter uma contagem de licenças de pelo menos 10.000, de um ou uma combinação dos seguintes produtos: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Por exemplo, sua organização pode ter 3.000 licenças do Office 365 E3 e 8500 Microsoft 365 E5, para um total de 11.500 licenças dos produtos qualificados.
- A organização precisa ter pelo menos 50 usuários ativos mensais do Exchange Online.

> [!NOTE]
> Você pode monitorar até 250 contas de prioridade.

### <a name="add-priority-accounts-from-the-setup-page"></a>Adicionar contas de prioridade da página De instalação

Adicione contas de prioridade da página **De instalação**.

1. Vá para o Centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vá para **Configurar**  >  **Conhecimento organizacional** e escolha **Exibir** em Monitorar suas contas **mais importantes.**

3. Selecione **Iniciar ou** **Gerenciar**.

4. Na página **Adicionar contas de** prioridade, no campo de pesquisa, digite o nome ou o endereço de email da pessoa que você deseja adicionar à lista de contas de prioridade. Você também pode definir o limite de email para emails com falha ou atraso e obter um relatório semanal de problemas para contas prioritárias.

5. Selecione o usuário e escolha **Salvar**.

Você também pode adicionar contas de prioridade da página Usuários ativos.

### <a name="add-priority-accounts-from-active-users-page"></a>Adicionar contas de prioridade da página Usuários ativos

Adicione contas de prioridade da página Usuários ativos.

1. Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Vá para **Usuários**  >  **Usuários ativos** e escolha **...** na parte superior da página. Selecione **Gerenciar contas de prioridade**.

3. Selecione **Adicionar contas** e, na página Adicionar contas **de** prioridade, no campo de pesquisa, digite o nome da pessoa que você deseja adicionar à lista de contas de prioridade.

4. Selecione o usuário e escolha **Salvar**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Remover um usuário da lista de contas de prioridade

1. Vá para o Centro de administração do Microsoft 365 em <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Vá para **Configurar**  >  **Conhecimento organizacional** e escolha **Exibir** em Monitorar suas contas **mais importantes.**

3. Na página **Monitorar a maioria das contas,** escolha Contas de **prioridade** em Gerenciar **esse recurso**.

4. Na página **Contas de prioridade,** selecione o usuário ou os usuários que você deseja remover da lista e escolha, **Remover contas**.

## <a name="related-topics"></a>Tópicos relacionados

[Usando contas prioritárias no Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)