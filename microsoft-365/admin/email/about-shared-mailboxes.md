---
title: Sobre as caixas de correio compartilhadas
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
description: Caixas de correio compartilhadas são usadas quando várias pessoas precisam acessar a mesma caixa de correio. Saiba o que você precisa saber antes de criar uma caixa de correio compartilhada.
ms.openlocfilehash: d0e0888a71e2a017b3934caa67f8d53ffb787fe7
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445694"
---
# <a name="about-shared-mailboxes"></a>Sobre as caixas de correio compartilhadas

As caixas de correio compartilhadas são usadas quando várias pessoas precisam acessar a mesma caixa de correio, como uma informação da empresa ou um endereço de email de suporte, para mesa de recepção ou qualquer outra função que possa ser compartilhada por várias pessoas.

Os usuários com permissões para a caixa de correio do grupo podem enviar como ou enviar em nome do endereço de email da caixa de correio, se o administrador tiver dado permissões para isso. Isso é particularmente útil para caixas de correio de ajuda e suporte, pois os usuários podem enviar emails de "Suporte da Contoso" ou "Criar uma Mesa de Recepção".

Antes [de criar uma caixa de correio compartilhada](create-a-shared-mailbox.md), aqui estão algumas coisas que você deve saber:

- **Licenças:** Sua caixa de correio compartilhada pode armazenar até 50 GB de dados sem atribuir uma licença a ele. Depois disso, você deve atribuir uma licença para a caixa de correio para armazenar mais dados. Para obter mais detalhes sobre licenciamento de caixa de correio compartilhada, confira [limites do Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits). Quando uma caixa de correio compartilhada atingir o limite de armazenamento, você ainda poderá receber emails por um tempo, mas não poderá enviar novos emails. Depois de um tempo, você não receberá mais emails. Os remetentes que enviarem mensagens para essa caixa de correio receberão uma notificação de que a mensagem não foi entregue.

- **Permissões de usuário:** Você precisa conceder permissões aos usuários (Associação) para usar a caixa de correio compartilhada. Somente as pessoas de dentro da organização podem usar uma caixa de correio compartilhada.

- **Usuários externos:** Você não pode permitir que pessoas de fora da sua empresa (como pessoas com uma conta do Gmail) acessem sua caixa de correio compartilhada. Se quiser fazer isso, crie um grupo do Outlook. Para saber mais, confira [criar um grupo do Microsoft 365 no centro de administração](../create-groups/create-groups.md).

-  **Use com o Outlook:** Além de usar o Outlook na Web do seu navegador para acessar caixas de correio compartilhadas, você também pode usar o aplicativo Outlook para iOS ou o aplicativo Outlook para Android. Para saber mais, confira <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Adicionar uma caixa de correio compartilhada ao Outlook Mobile</a>. Outra opção é criar um grupo para sua caixa de correio compartilhada. Para saber mais, confira [comparar grupos](../create-groups/compare-groups.md).  

- **Criptografia:** Você não pode criptografar emails enviados de uma caixa de correio compartilhada. Isso ocorre porque uma caixa de correio compartilhada não tem seu próprio contexto de segurança (nome de usuário/senha), portanto, não pode ser atribuída a uma chave. Se mais de uma pessoa for um membro e elas enviarem/receberem emails criptografados com suas próprias chaves, outros membros poderão ler o email e outras podem não, dependendo de qual chave pública o email foi criptografado.

- **Conversão de caixa de correio:** Você pode converter caixas de correio de usuário em caixas de correio compartilhadas. Confira [Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).

- **Funções de administrador:** Usuários com funções de administrador global ou administrador do Exchange podem criar caixas de correio compartilhadas.

- **Requisitos de assinatura:** Para criar uma caixa de correio compartilhada, você precisa se inscrever em um plano do Microsoft 365 para empresas que inclui emails (o serviço do Exchange Online). A assinatura do Microsoft 365 Apps for Business não inclui email. O Microsoft 365 Business Standard inclui email.

- **Entrar:** Uma caixa de correio compartilhada não se destina ao logon direto por sua conta de usuário associada. Você deve sempre bloquear o logon para a conta de caixa de correio compartilhada e mantê-lo bloqueado.

- **Muitos usuários:** Quando há muitos usuários designados acessando simultaneamente uma caixa de correio compartilhada, eles podem falhar intermitentemente para se conectar a essa caixa de correio. Nesse caso, você pode considerar reduzir o número de usuários ou usar uma carga de trabalho diferente, como um grupo do Microsoft 365 ou uma pasta pública.

- **Exclusão de mensagens:** Infelizmente, não é possível impedir que as pessoas excluam mensagens em uma caixa de correio compartilhada. A única maneira de contornar isso é criar um grupo do Microsoft 365 em vez de uma caixa de correio compartilhada. Um grupo no Outlook é como uma caixa de correio compartilhada. Para uma comparação dos dois, consulte [Compare groups](../create-groups/compare-groups.md). Para saber mais sobre grupos, consulte [saiba mais sobre grupos](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

## <a name="related-articles"></a>Artigos relacionados

[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md)

[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md)

[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).

[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md)

[Solucionar problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md)
