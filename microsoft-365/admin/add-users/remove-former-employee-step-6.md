---
title: Etapa 6 - Remover e excluir a Microsoft 365 de um ex-funcionário
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Siga estas etapas para remover a Microsoft 365 de um ex-funcionário.
ms.openlocfilehash: ed86eb28cc6d4996f7def8cb567f0e4085e67624
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244148"
---
# <a name="step-6---remove-the-microsoft-365-license-from-a-former-employee"></a>Etapa 6 - Remover a Microsoft 365 de um ex-funcionário

Se você não quiser pagar por uma licença depois que alguém sair da sua organização, você precisará remover a licença de Microsoft 365 e excluí-la da sua assinatura. Você pode atribuir uma licença a outro usuário se não excluí-la.
  
Quando você remove a licença, todos os dados do usuário são mantidos por 30 dias. Você pode [acessar](get-access-to-and-back-up-a-former-user-s-data.md) os dados ou [restaurar](restore-user.md) a conta se o usuário retornar. Após 30 dias, todos os dados do usuário (exceto os documentos armazenados no SharePoint Online) são excluídos permanentemente do Microsoft 365 e não podem ser recuperados.

1. No centro de administração, vá para a página **Usuários** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuários ativos</a>.
2. Selecione o nome do funcionário que você deseja bloquear e selecione a guia **Licenças e Aplicativos.**
3. Des limpar as caixas de seleção para as licenças que você deseja remover e selecione **Salvar alterações**.

**Para reduzir o número de licenças** que você está pagando até contratar outra pessoa, faça as seguintes etapas:

1. No centro de administração, vá até a página **Cobrança** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Seus</a> produtos e selecione **a guia** Produtos.
2. Selecione a assinatura da qual você deseja remover licenças.
3. Na página detalhes, selecione **Remover licenças**.
4. No painel **Remover licenças,** em Nova quantidade, na caixa Total de **licenças,** insira o número total de licenças que você deseja para essa assinatura. Por exemplo, se você tiver 25 licenças e quiser remover uma delas, insira 24.
5. Selecione **Salvar**.

Ao [adicionar outra pessoa](add-users.md) à sua empresa, você será solicitado a comprar uma licença ao mesmo tempo, com apenas uma etapa!

Para obter mais informações sobre como gerenciar licenças de usuário para Microsoft 365 para empresas, consulte [Atribuir licenças a](../manage/assign-licenses-to-users.md)usuários no Microsoft 365 para empresas e [Desatribuição](../manage/remove-licenses-from-users.md)de licenças de usuários no Microsoft 365 para empresas .
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Como a conta de funcionário excluída afeta o Skype for Business

Quando você remove uma licença de usuário do Office 365, o número de chamada PSTN associado ao usuário será lançado. Você pode atribuí-la a outro usuário.
  
Se o usuário pertencer a um grupo de espera, ele não será mais um alvo viável de agentes da fila a chamada. Portanto, recomendamos remover o usuário também de grupos associados à fila de chamadas.

## <a name="set-up-call-forwarding-to-people-in-your-organization"></a>Configurar o encaminhamento de chamada para pessoas em sua organização

Se você precisar configurar o encaminhamento de chamadas para o número de telefone do funcionário encerrado, a configuração de encaminhamento de chamada em políticas de chamada pode configurar o encaminhamento para onde as chamadas de entrada podem ser encaminhadas para outros usuários ou podem tocar em outra pessoa ao mesmo tempo. Para obter mais informações, consulte [Políticas de chamada em Microsoft Teams](/microsoftteams/teams-calling-policy).
