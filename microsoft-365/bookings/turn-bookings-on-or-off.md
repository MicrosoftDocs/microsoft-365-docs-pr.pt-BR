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
description: Saiba como acessar o Microsoft Bookings no Microsoft 365.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913761"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Ativar ou desativar o Microsoft Bookings

As reservas podem ser ativas ou desligadas para toda a organização ou para usuários específicos. Ao ativar o Bookings para usuários, eles podem criar uma página do Bookings, criar um calendário e permitir que outras pessoas reservem tempo com eles.

> [!NOTE]
> Os controles de administrador descritos nessas seções não estão disponíveis para clientes do Office 365 Operated by 21Vianet (China).

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Ativar ou desativar o Bookings para sua organização usando o Centro de administração do Microsoft 365

1. Entre no Centro de administração do Microsoft 365 como administrador global.

2. No centro de administração, vá para  **Configurações** da Organização   \> **e** selecione **Bookings**.

3. Marque a caixa de seleção Permitir **que sua organização use o Bookings** para habilitar ou desabilitar o Bookings para sua organização.

   > [!NOTE]
   > Desativar o Bookings desabilitará todo o acesso ao serviço, incluindo a criação e o gerenciamento de páginas do Bookings.

4. Selecione **Salvar Alterações**.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Ativar ou desativar o Bookings para sua organização usando o PowerShell

Para ativar ou desativar o Bookings para sua organização usando o cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)do PowerShell do PowerShell do PowerShell do [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) e executar o seguinte comando:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Ativar ou desativar o Bookings para usuários individuais

Você pode desabilitar o Bookings para usuários individuais.

1. Vá para o Centro de administração do Microsoft 365 e selecione **Usuários** \> **Usuários ativos.**

1. Selecione o usuário desejado e selecione **Licenças e Aplicativos.**

1. Expanda **Aplicativos** e limpe a caixa de seleção do Microsoft Bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Exigir aprovações da equipe antes de compartilhar informações de livre/ocupado

Os administradores podem exigir que os funcionários em sua organização se adotem antes que suas informações de disponibilidade sejam compartilhadas por meio do Bookings e antes que eles possam ser reservados por meio de uma página de reserva. Essa configuração está disponível no Centro de administração do Microsoft 365 em **Configurações** \> **Configurações** \> **Reservas**.

Quando essa configuração estiver habilitada, os funcionários adicionados como funcionários nos calendários de reserva encontrarão um link Aprovar/Rejeitar na notificação de email recebida.

Esse recurso está sendo gradualmente implantada em todo o mundo para clientes do Microsoft 365. Se você não vir essa opção no Centro de administração do Microsoft 365, volte em breve.

## <a name="block-social-sharing-options"></a>Bloquear opções de compartilhamento social

Os administradores podem controlar como as páginas de reserva são compartilhadas nas redes sociais. Essa configuração está disponível no Centro de administração do Microsoft 365 em **Configurações** \> **Configurações** \> **Reservas**.

Esse recurso está sendo gradualmente implantada em todo o mundo para clientes do Microsoft 365. Se você não vir essa opção no Centro de administração do Microsoft 365, volte em breve.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Permitir que apenas usuários selecionados criem calendários do Bookings

Usando restrições de política, você pode restringir os usuários licenciados de serem capazes de criar calendários do Bookings. Primeiro, você deve habilitar o Bookings para toda a sua organização. Todos os usuários em sua organização terão licenças do Bookings, mas somente aqueles incluídos na política podem criar calendários do Bookings e ter controle total sobre quem pode acessar os calendários que eles criam.

Os usuários incluídos nesta política podem criar novos calendários do Bookings e podem ser adicionados como funcionários em qualquer capacidade (incluindo a função de administrador) aos calendários existentes do Bookings. Os usuários que não estão incluídos nesta política não poderão criar novos calendários do Bookings e receberão uma mensagem de erro se tentarem fazer isso.

Você precisará executar os seguintes comandos usando o PowerShell do Exchange Online. Para obter mais informações sobre como executar cmdlets do Exchange Online, consulte [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> As etapas a seguir pressuem que nenhuma outra política de caixa de correio do Outlook Web App (OWA) tenha sido criada em sua organização.

1. Crie uma nova política de caixa de correio para usuários que devem ter permissão para criar calendários do Bookings. (A criação de calendário do Bookings é permitida por padrão por novas políticas de caixa de correio.)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Para obter mais informações, [consulte New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).

2. Atribua essa política aos usuários relevantes executando esse comando para cada usuário que você deseja conceder permissão para criar calendários do Bookings.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Para obter mais informações, consulte [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).

3. Opcional: execute este comando se quiser desabilitar o Bookings para todos os outros usuários em sua organização.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Para obter mais informações, consulte [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

Para obter mais informações sobre políticas de caixa de correio do OWA, confira os seguintes tópicos:

- [Criar uma política de caixa de correio do Outlook na Web no Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Aplicar ou remover uma política de caixa de correio do Outlook na Web em uma caixa de correio no Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)