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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: As caixas de correio compartilhadas são usadas quando várias pessoas precisam de acesso à mesma caixa de correio. Saiba o que você precisa saber antes de criar uma caixa de correio compartilhada.
ms.openlocfilehash: 83e779d59a8e763b3d0c0482966e75604d5f1574
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903209"
---
# <a name="about-shared-mailboxes"></a>Sobre as caixas de correio compartilhadas

As caixas de correio compartilhadas são usadas quando várias pessoas precisam acessar a mesma caixa de correio, como uma informação da empresa ou um endereço de email de suporte, para mesa de recepção ou qualquer outra função que possa ser compartilhada por várias pessoas.

Os usuários com permissões para a caixa de correio do grupo podem enviar como ou enviar em nome do endereço de email da caixa de correio, se o administrador tiver dado permissões para isso. Isso é particularmente útil para caixas de correio de ajuda e suporte, pois os usuários podem enviar emails de "Suporte da Contoso" ou "Criar uma Mesa de Recepção".

Antes de [criar uma caixa de correio compartilhada,](create-a-shared-mailbox.md)veja algumas coisas que você deve saber:

- **Licenças:** Sua caixa de correio compartilhada pode armazenar até 50 GB de dados sem atribuir uma licença a ela. Depois disso, você deve atribuir uma licença para a caixa de correio para armazenar mais dados. Para obter mais detalhes sobre o licenciamento de caixa de correio compartilhada, consulte [Limites do Exchange Online.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#StorageLimits) Quando uma caixa de correio compartilhada atingir o limite de armazenamento, você ainda poderá receber emails por um tempo, mas não poderá enviar novos emails. Depois de um tempo, você não receberá mais emails. Os remetentes que enviarem mensagens para essa caixa de correio receberão uma notificação de que a mensagem não foi entregue.

- **Permissões do usuário:** Você precisa dar aos usuários permissões (associação) para usar a caixa de correio compartilhada. Somente as pessoas de dentro da organização podem usar uma caixa de correio compartilhada.

- **Usuários externos:** Você não pode dar a pessoas de fora da sua empresa (como pessoas com uma conta do Gmail) acesso à sua caixa de correio compartilhada. Se quiser fazer isso, crie um grupo do Outlook. Para saber mais, confira [Criar um grupo do Microsoft 365 no centro de administração](../create-groups/create-groups.md).

- **Use com o Outlook:** Além de usar o Outlook na Web do navegador para acessar caixas de correio compartilhadas, você também pode usar o aplicativo outlook para iOS ou o aplicativo outlook para Android. Para saber mais, confira [Adicionar uma caixa de correio compartilhada ao Outlook mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f). Outra opção é criar um grupo para sua caixa de correio compartilhada. Para saber mais, confira [Comparar Grupos](../create-groups/compare-groups.md).

- **Criptografia:** Não é possível criptografar emails enviados de uma caixa de correio compartilhada. Isso acontece porque uma caixa de correio compartilhada não tem seu próprio contexto de segurança (nome de usuário/senha), portanto, ela não pode receber uma chave. Se mais de uma pessoa for membro e enviar/receber emails criptografados com suas próprias chaves, outros membros poderão ler o email e outras pessoas talvez não, dependendo de qual chave pública o email foi criptografado.

- **Conversão de caixa de correio:** Você pode converter caixas de correio de usuário em caixas de correio compartilhadas. Confira [Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).

- **Funções de administrador:** Os usuários com funções de administrador global ou administrador do Exchange podem criar caixas de correio compartilhadas.

- **Requisitos de assinatura:** Para criar uma caixa de correio compartilhada, você precisa assinar um plano do Microsoft 365 para empresas que inclui email (o serviço do Exchange Online). A assinatura do Microsoft 365 Apps for business não inclui email. O Microsoft 365 Business Standard inclui email.

- **Entrar:** Uma caixa de correio compartilhada não se destina a entrada direta por sua conta de usuário associada. Você sempre deve bloquear a entrada para a conta de caixa de correio compartilhada e mantê-la bloqueada.

- **Muitos usuários:** Quando há muitos usuários designados acessando simultaneamente uma caixa de correio compartilhada, eles podem não se conectar intermitentemente a essa caixa de correio. Nesse caso, você pode considerar reduzir o número de usuários ou usar uma carga de trabalho diferente, um grupo do Microsoft 365 ou uma pasta pública.

- **Exclusão de mensagem:** Infelizmente, você não pode impedir que as pessoas deletem mensagens em uma caixa de correio compartilhada. A única maneira de fazer isso é criar um grupo do Microsoft 365 em vez de uma caixa de correio compartilhada. Um grupo no Outlook é como uma caixa de correio compartilhada. Para uma comparação entre os dois, consulte [Comparar grupos](../create-groups/compare-groups.md). Para saber mais sobre grupos, consulte [Saiba mais sobre grupos](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).


> [!NOTE]
> Para acessar uma caixa de correio compartilhada, um usuário deve ter uma licença do Exchange Online, mas a caixa de correio compartilhada não exige uma licença separada. Toda caixa de correio compartilhada tem uma conta de usuário correspondente. Observe como você não foi solicitado a fornecer uma senha ao criar a caixa de correio compartilhada? A conta tem uma senha, mas é gerada pelo sistema (desconhecido). Você não deve usar a conta para fazer logoff na caixa de correio compartilhada. Sem uma licença, as caixas de correio compartilhadas são limitadas a 50 GB. Para aumentar o limite de tamanho para 100 GB, a caixa de correio compartilhada deve ser atribuída uma licença do Plano 2 do Exchange Online ou uma licença do Plano 1 do Exchange Online com uma licença complementar de Arquivamento do Exchange Online. Isso também permitirá que você habilite o arquivamento automático para uma quantidade ilimitada de capacidade de armazenamento de arquivos. Da mesma forma, se você deseja colocar uma caixa de correio compartilhada em retenção de litígio, a caixa de correio compartilhada deve ter uma licença Exchange Online Plano 2 ou uma licença Exchange Online Plano 1 com uma licença complementar de Arquivamento do Exchange Online. Se você quiser aplicar recursos avançados, como o Microsoft Defender para Office 365, a Descoberta Avançada de Descoberta Automática ou políticas de retenção automática, a caixa de correio compartilhada deve ser licenciada para esses recursos.

## <a name="related-content"></a>Conteúdo relacionado

[Criar uma caixa de correio compartilhada](create-a-shared-mailbox.md)

[Configurar uma caixa de correio compartilhada](configure-a-shared-mailbox.md)

[Converter uma caixa de correio do usuário em uma caixa de correio compartilhada](convert-user-mailbox-to-shared-mailbox.md).

[Remover uma licença de uma caixa de correio compartilhada](remove-license-from-shared-mailbox.md)

[Solucionar problemas com caixas de correio compartilhadas](resolve-issues-with-shared-mailboxes.md)