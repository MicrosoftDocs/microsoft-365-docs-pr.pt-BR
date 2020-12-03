---
title: Configurar encaminhamento de email
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Configurar o encaminhamento de emails para uma ou mais contas de email usando o office365.
ms.openlocfilehash: c821d4363a053b432c4376d7b4fec4926df7b568
ms.sourcegitcommit: ff1f0a97e9d43bc786f04d2ea7e01695531b9f28
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49560787"
---
# <a name="configure-email-forwarding"></a>Configurar encaminhamento de email

::: moniker range="o365-21vianet"

> [!NOTE]
> O centro de administração está mudando. Se a sua experiência não corresponder aos detalhes apresentados aqui, consulte [Sobre o novo centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Como administrador de uma organização, você pode ter requisitos da empresa para configurar o encaminhamento de emails para a caixa de correio de um usuário. O encaminhamento de email permite que você encaminhe mensagens de email enviadas para a caixa de correio de um usuário para a caixa de correio de outro usuário dentro ou fora da sua organização.

> [!IMPORTANT]
> Você pode usar as políticas de filtro de spam de saída para controlar o encaminhamento automático para destinatários externos. Para obter mais informações, consulte [controlar o encaminhamento de email externo automático no Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).

  
## <a name="configure-email-forwarding"></a>Configurar encaminhamento de email

 Antes de configurar o encaminhamento de email, observe o seguinte: 

- Após configurar o encaminhamento de email **, somente os** emails enviados para a caixa  *de*  correio serão encaminhados. 
    
- O encaminhamento de email exige que a conta  *de*  tenha uma licença. Se você estiver configurando o encaminhamento de emails porque o usuário deixou sua organização, outra opção é [converter a caixa de correio em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md). Dessa forma, várias pessoas podem acessá-la. No entanto, uma caixa de correio compartilhada não pode exceder 50 GB. 
    
Você deve ser um administrador do Exchange ou administrador global no Microsoft 365 para executar estas etapas. Para obter mais informações, consulte o tópico [sobre funções de administrador](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
    
2. Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades. 
 
3. Na guia **email** , selecione **gerenciar encaminhamento de email**. 
  
4. Na página encaminhamento de email, selecione **encaminhar todos os emails enviados para esta caixa de correio**, insira o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados. Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário. Selecione **Salvar alterações**.
    
    **Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços. Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.
    
5. Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!  Se fizer isso, o encaminhamento de emails será interrompido. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuários ativos</a>. 
    
2. Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades. 

3. Expanda **configurações de email** e, na seção **encaminhamento de email** , selecione **Editar**.

4. Na página encaminhamento de email, **defina a opção Ativar, digite** o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados. Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário. Selecione **Salvar**.
    
    **Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços. Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.
    
5. Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!  Se fizer isso, o encaminhamento de emails será interrompido.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuários ativos</a>. 
    
2. Selecione o nome do usuário cujo email você deseja encaminhar para abrir a página de propriedades. 

3. Expanda **configurações de email** e, na seção **encaminhamento de email** , selecione **Editar**.

4. Na página encaminhamento de email, **defina a opção Ativar, digite** o endereço de encaminhamento e escolha se deseja manter uma cópia dos emails encaminhados. Se você não vir essa opção, certifique-se de que uma licença é atribuída à conta de usuário. Selecione **Salvar**.
    
    **Para encaminhar para vários endereços de email**, você pode solicitar ao usuário que configure uma regra no Outlook para encaminhar para os endereços. Para saber mais, confira [usar regras para encaminhar mensagens automaticamente](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746). 
    
     Ou, no centro de administração, [crie um grupo de distribuição](../setup/create-distribution-lists.md), [adicione os endereços a ele](add-user-or-contact-to-distribution-list.md)e configure o encaminhamento para apontar para a DL usando as instruções neste artigo.
    
5. Não exclua a conta do usuário que é o email que você está encaminhando ou remova sua licença!  Se fizer isso, o encaminhamento de emails será interrompido. 


::: moniker-end 
