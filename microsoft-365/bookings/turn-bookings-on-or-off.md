---
title: Ativar ou desativar o Microsoft bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Saiba como obter acesso a reservas da Microsoft no Microsoft 365.
ms.openlocfilehash: 815aa3a859db15364aa18d3550001a28d085b711
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419175"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Ativar ou desativar o Microsoft bookings

As reservas podem ser ativadas ou desativadas para toda a organização ou para usuários específicos. Quando você ativa reservas para usuários, eles podem criar uma página de reservas, criar um calendário e permitir que outras pessoas façam o horário do livro.

> [!NOTE]
> Os controles de administração descritos nessas seções não estão disponíveis para os clientes do Office 365 operado pela 21Vianet (China).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Ativar ou desativar as reservas da sua organização usando o centro de administração do Microsoft 365

1. Entre no centro de administração do Microsoft 365 como um administrador global.

2. No centro de administração, vá para **Settings**   \> **configurações** de configurações e selecione **reservas**.

3. Marque a caixa de seleção para **permitir que sua organização Use reservas** para habilitar ou desabilitar reservas para sua organização.

   > [!NOTE]
   > A desativação dos reservas desabilitará todo o acesso ao serviço, incluindo a criação e o gerenciamento de páginas de reservas.

4. Selecione **salvar alterações**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Ativar ou desativar as reservas da sua organização usando o PowerShell

Para ativar ou desativar as reservas da sua organização usando o cmdlet do PowerShell [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Conecte-se ao PowerShell do Exchange Online]() e execute o seguinte comando:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Ativar ou desativar reservas para usuários individuais

Você pode desabilitar reservas para usuários individuais.

1. Vá para o centro de administração do Microsoft 365 e, em seguida, selecione usuários ativos do **usuário** \> **Active users**.

1. Selecione o usuário desejado e, em seguida, selecione **licenças e aplicativos**.

1. Expanda **aplicativos** e desmarque a caixa de seleção de Microsoft bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Exigir aprovações de equipe antes de compartilhar informações de disponibilidade

Os administradores podem exigir que os funcionários de sua organização entrem em uma página para que as informações de disponibilidade sejam compartilhadas por meio de reservas e para poderem ser contratadas por meio de uma página de reserva. Essa configuração está disponível no centro de administração do Microsoft 365 **em reservas de configurações** \> **Settings** \> **Bookings**.

Quando essa configuração é habilitada, os funcionários adicionados como equipe em calendários de reserva irão encontrar um link aprovar/rejeitar na notificação por email que receberem.

Esse recurso está implantando gradualmente a World Wide para clientes da Microsoft 365. Se você não vir essa opção no centro de administração do Microsoft 365, verifique novamente em breve.

## <a name="block-social-sharing-options"></a>Bloquear opções de compartilhamento social

Os administradores podem controlar como as páginas de reserva são compartilhadas em redes sociais. Essa configuração está disponível no centro de administração do Microsoft 365 **em reservas de configurações** \> **Settings** \> **Bookings**.

Esse recurso está implantando gradualmente a World Wide para clientes da Microsoft 365. Se você não vir essa opção no centro de administração do Microsoft 365, verifique novamente em breve.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Permitir que somente usuários selecionados criem calendários de reservas

Usando restrições de política, você pode restringir os usuários licenciados da capacidade de criar calendários de reservas. Você deve primeiro habilitar reservas para toda a organização. Todos os usuários em sua organização terão licenças de reservas, mas apenas aquelas incluídas na política podem criar calendários de reservas e ter controle total sobre quem pode acessar os calendários criados.

Os usuários incluídos nessa política podem criar novos calendários de livros e podem ser adicionados como equipe em qualquer capacidade (incluindo a função de administrador) a calendários de livros existentes. Os usuários que não estão incluídos nesta política não poderão criar novos calendários de livros e receberão uma mensagem de erro se tentarem fazer isso.

Você precisará executar os seguintes comandos usando o PowerShell do Exchange Online. Para obter mais informações sobre a execução de cmdlets do Exchange Online, consulte [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> As etapas abaixo pressupõem que nenhuma outra política de caixa de correio do Outlook Web App (OWA) tenha sido criada em sua organização.

1. Crie uma nova política de caixa de correio para usuários que devem ter permissão para criar calendários de reservas. (A criação de calendário de livros é permitida por padrão por novas diretivas de caixa de correio).

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Para obter mais informações, consulte [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).

2. Atribua essa política aos usuários relevantes executando este comando para cada usuário que você deseja conceder permissão para criar calendários de reservas.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Para obter mais informações, consulte [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).

3. Opcional: Execute este comando se desejar desabilitar reservas para todos os outros usuários em sua organização.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Para obter mais informações, consulte [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

Para obter mais informações sobre as políticas de caixa de correio do OWA, confira os seguintes tópicos:

- [Criar uma política de caixa de correio do Outlook na Web no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Aplicar ou remover uma política de caixa de correio do Outlook na Web em uma caixa de correio no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)