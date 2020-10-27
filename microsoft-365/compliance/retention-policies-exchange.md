---
title: Saiba mais sobre a retenção do Exchange
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Saiba como a retenção funciona para o Exchange.
ms.openlocfilehash: 4e8a536aaa81b0117f40b0ce330491fa8430f97c
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754431"
---
# <a name="learn-about-retention-for-exchange"></a>Saiba mais sobre a retenção para o Exchange

As informações contidas neste artigo complementam [Saiba mais sobre retenção](retention.md) porque são informações específicas para o Exchange.  Para outras cargas de trabalho, confira:

- [Saiba mais sobre retenção para o Microsoft Office SharePoint Online e o OneDrive](retention-policies-sharepoint.md)
- [Saiba mais sobre retenção para o Microsoft Teams](retention-policies-teams.md)
- [Saiba mais sobre retenção no Yammer](retention-policies-yammer.md)

## <a name="whats-included-for-retention-and-deletion"></a>O que está incluído para retenção e exclusão

Os seguintes itens do Exchange podem ser retidos e excluídos usando políticas de retenção e rótulos de retenção: Email do Outlook (inclui rascunhos) com quaisquer anexos, tarefas quando eles têm uma data de término e notas. 

Os itens de Calendário do Outlook com data de término têm suporte para políticas de retenção, mas não para rótulos de retenção.

Contatos e quaisquer tarefas e itens de calendário que não tenham uma data de término não são suportados.

Outros itens armazenados em uma caixa de correio, como mensagens do Skype e Teams, não são incluídos nas políticas de retenção ou rótulos do Exchange. Esses itens têm suas próprias políticas de retenção.

## <a name="how-retention-works-for-exchange"></a>Saiba como a retenção funciona para o Exchange.

Tanto uma caixa de correio quanto uma pasta pública usam a [pasta Itens Recuperáveis](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) para reter itens. Somente as pessoas às quais foram atribuídas permissões de Descoberta Eletrônica podem exibir itens na pasta Itens Recuperáveis de outro usuário.
  
Quando alguém exclui uma mensagem em uma pasta diferente da pasta Itens Excluídos, por padrão, a mensagem é movida para a pasta Itens Excluídos. Quando alguém exclui um item na pasta Itens Excluídos, a mensagem é movida para a pasta Itens Recuperáveis. Entretanto, um usuário pode excluir um item de forma reversível (Shift+Delete) em qualquer pasta, o que evita que ele vá pasta Itens Excluídos e o move diretamente para a pasta Itens Recuperáveis.
  
Quando você aplica configurações de retenção a um dado do Exchange, um trabalho do temporizador avalia periodicamente os itens na pasta Itens Recuperáveis. Quando um item não corresponde às regras de pelo menos uma política de retenção ou rótulo de retenção, ele é excluído permanentemente (chamado também de exclusão forçada) da pasta Itens Recuperáveis.

O trabalho do temporizador pode levar até sete dias para ser executado e o local da Bolsa deve conter pelo menos 10 MB
  
Quando um usuário tenta alterar propriedades de um item de caixa de correio, como assunto, corpo, anexos, remetentes e destinatários, ou a data de envio ou de recebimento de uma mensagem, uma cópia do item original é salva na pasta Itens Recuperáveis antes da confirmação da alteração. Essa ação acontecerá para todas as alterações subsequentes. No final do período de retenção, as cópias na pasta Itens Recuperáveis são excluídas permanentemente.

Depois que configurações de retenção são atribuídas ao conteúdo do Exchange, os caminhos que o conteúdo assume dependem se as configurações forem para reter e excluir, somente reter ou somente excluir.

Quando as configurações de retenção são reter e excluir:

![Diagrama de fluxo de retenção em emails e pastas públicas](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Se o item for modificado ou excluído permanentemente** pelo usuário (usando SHIFT+DELETE ou excluído de Itens Excluídos) durante o período de retenção: ele será movido (ou copiado, no caso de uma edição) para a pasta Itens Recuperáveis. Lá, um trabalho de temporizador é executado periodicamente e identifica itens cujo período de retenção expirou, que então são permanentemente excluídos em até 14 dias após o fim do período de retenção. Observe que 14 dias é a configuração padrão, podendo ser estendida para até 30 dias.

2. **Se o item não for modificado ou excluído** durante o período de retenção: o mesmo processo será executado periodicamente em todas as pastas na caixa de correio, identificando itens cujo período de retenção expirou. Esses itens são então permanentemente excluídos em até 14 dias após o fim do período de retenção. Observe que 14 dias é a configuração padrão, podendo ser estendida para até 30 dias. 

Quando as configurações forem reter somente ou excluir somente, os caminhos de conteúdo serão variações de reter e excluir:

### <a name="content-paths-for-retain-only-retention-settings"></a>Caminhos de conteúdo para as configurações de reter somente

1. **Se o item for modificado ou excluído** durante o período de retenção: uma cópia do item original será criada na pasta Itens Recuperáveis e retida até o fim do período de retenção, quando a cópia na pasta Itens Recuperáveis será excluída permanentemente dentro de 14 dias após o item expirar. 

2. **Se o item não for modificado ou excluído** durante o período de retenção: nada acontece antes e depois do período de retenção; o item permanecerá no local original.

### <a name="content-paths-for-delete-only-retention-settings"></a>Caminhos de conteúdo para as configurações de excluir somente

1. **Se o item não for excluído** durante o período configurado: no final do período configurado na política de retenção, o item será movido para a pasta Itens Recuperáveis. 

2. **Se o item for excluído** durante o período configurado: o item será movido imediatamente para a pasta Itens Recuperáveis. Se um usuário excluir o item da pasta Itens Recuperáveis ou esvaziá-la, o item será excluído permanentemente. Caso contrário, o item será excluído permanentemente depois de ficar na pasta Itens Recuperáveis por 14 dias. 

## <a name="when-a-user-leaves-the-organization"></a>Quando um usuário sair da organização 

Se um usuário deixar sua organização e a caixa de correio do usuário for incluída em uma política de retenção, ela se tornará uma caixa de correio inativa quando a conta do Microsoft 365 do usuário for excluída. O conteúdo de uma caixa de correio inativa ainda está sujeito a qualquer política de retenção que tenha sido aplicada a essa caixa antes dela se tornar inativa, e ele fica disponível para uma pesquisa de descoberta eletrônica. Para obter mais informações, consulte [Caixas de correio inativas no Exchange Online](inactive-mailboxes-in-office-365.md).

## <a name="configuration-guidance"></a>Instruções de configuração

Se você é novo na configuração de retenção no Microsoft 365, consulte [Começar com políticas e rótulos de retenção](get-started-with-retention.md).

Se você estiver pronto para configurar uma política de retenção ou rótulo de retenção do Exchange, consulte as instruções a seguir:
- [Criar e configurar políticas de retenção](create-retention-policies.md)
- [Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)
- [Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)