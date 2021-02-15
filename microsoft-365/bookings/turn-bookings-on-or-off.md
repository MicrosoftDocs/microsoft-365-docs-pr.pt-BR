---
title: Ativar ou desativar o Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Saiba como obter acesso ao Microsoft Bookings no Microsoft 365.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126586"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Ativar ou desativar o Microsoft Bookings

O Bookings pode ser ligado ou desligado para toda a organização ou para usuários específicos. Quando você ativar o Bookings para usuários, eles poderão criar uma página do Bookings, criar um calendário e permitir que outras pessoas reservem tempo com elas.

> [!NOTE]
> Os controles de administrador descritos nessas seções não estão disponíveis para clientes do Office 365 Operado pela 21Vianet (China).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Ativar ou desativar o Bookings para sua organização usando o Centro de administração do Microsoft 365

1. Entre no centro de administração do Microsoft 365 como um administrador global.

2. No centro de administração, vá para  **Configurações** da   \> **Organização e** selecione **Bookings.**

3. Marque a caixa de seleção Permitir **que sua organização use o Bookings** para habilitar ou desabilitar o Bookings para sua organização.

   > [!NOTE]
   > Desativar o Bookings desabilitará todo o acesso ao serviço, incluindo a criação e o gerenciamento de páginas do Bookings.

4. Selecione **Salvar Alterações**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Ativar ou desativar o Bookings para sua organização usando o PowerShell

Para ativar ou desativar o Bookings para sua organização usando o cmdlet Do PowerShell [Set-OrganizationConfig , conecte-se](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)ao [PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) do Exchange Online e execute o seguinte comando:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Ativar ou desativar o Bookings para usuários individuais

Você pode desabilitar o Bookings para usuários individuais.

1. Vá para o centro de administração do Microsoft 365 e selecione **Usuários** \> **Ativos.**

1. Selecione o usuário desejado e, em seguida, selecione **Licenças e Aplicativos.**

1. Expanda **Aplicativos** e des marque a caixa de seleção do Microsoft Bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Exigir aprovações da equipe antes de compartilhar informações de livre/ocupado

Os administradores podem exigir que os funcionários em sua organização optem antes que suas informações de disponibilidade sejam compartilhadas por meio do Bookings e antes que possam ser reservadas por meio de uma página de reserva. Essa configuração está disponível no Centro de administração do Microsoft 365 em **Configurações** \> **do** \> **Bookings.**

Quando essa configuração estiver habilitada, os funcionários adicionados como funcionários nos calendários de reserva encontrarão um link Aprovar/Rejeitar na notificação por email recebida.

Esse recurso está sendo gradualmente implantando em todo o mundo para clientes do Microsoft 365. Se você não vir essa opção no centro de administração do Microsoft 365, verifique novamente em breve.

## <a name="block-social-sharing-options"></a>Bloquear opções de compartilhamento social

Os administradores podem controlar como as páginas de reserva são compartilhadas em redes sociais. Essa configuração está disponível no Centro de administração do Microsoft 365 em **Configurações** \> **do** \> **Bookings.**

Esse recurso está sendo gradualmente implantando em todo o mundo para clientes do Microsoft 365. Se você não vir essa opção no centro de administração do Microsoft 365, verifique novamente em breve.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Permitir que apenas usuários selecionados criem calendários do Bookings

Usando restrições de política, você pode restringir os usuários licenciados de serem capazes de criar calendários do Bookings. Primeiro, você deve habilitar o Bookings para toda a organização. Todos os usuários em sua organização terão licenças do Bookings, mas somente aqueles incluídos na política poderão criar calendários do Bookings e ter controle total sobre quem pode acessar os calendários que criarem.

Os usuários incluídos nesta política podem criar novos calendários do Bookings e podem ser adicionados como funcionários em qualquer capacidade (incluindo a função de administrador) aos calendários existentes do Bookings. Os usuários que não estão incluídos nesta política não poderão criar novos calendários do Bookings e receberão uma mensagem de erro se tentarem fazer isso.

Você precisará executar os seguintes comandos usando o PowerShell do Exchange Online. Para obter mais informações sobre como executar cmdlets do Exchange Online, consulte [Conectar-se ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

> [!IMPORTANT]
> As etapas a seguir presumem que nenhuma outra política de caixa de correio do Outlook Web App (OWA) tenha sido criada em sua organização.

1. Crie uma nova política de caixa de correio para os usuários que devem ter permissão para criar calendários do Bookings. (A criação de calendário do Bookings é permitida por padrão por novas políticas de caixa de correio.)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Para obter mais informações, [consulte New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).

2. Atribua essa política aos usuários relevantes executando este comando para cada usuário que você deseja conceder permissão para criar calendários do Bookings.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Para obter mais informações, [consulte Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).

3. Opcional: Execute este comando se quiser desabilitar o Bookings para todos os outros usuários em sua organização.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Para obter mais informações, [consulte Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

Para obter mais informações sobre políticas de caixa de correio do OWA, confira os seguintes tópicos:

- [Criar uma política de caixa de correio do Outlook na Web no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Aplicar ou remover uma política de caixa de correio do Outlook na Web em uma caixa de correio no Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
