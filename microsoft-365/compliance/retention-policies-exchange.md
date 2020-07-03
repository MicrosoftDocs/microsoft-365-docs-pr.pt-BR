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
description: Saiba mais sobre o comportamento de retenção que se aplica especificamente aos emails do Exchange e às pastas públicas do Exchange.
ms.openlocfilehash: 2ecf709c8b2bdd166cd64024ef332a2e0b26b7be
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016274"
---
# <a name="learn-about-retention-policies-for-exchange"></a>Saiba mais sobre as políticas de retenção do Exchange

As informações contidas neste artigo complementam [Saiba mais sobre as políticas de retenção](retention-policies.md) porque são informações específicas para o Exchange.

## <a name="how-a-retention-policy-works-with-exchange-locations"></a>Como funciona uma política de retenção com locais do Exchange

Para os email, calendário e outros itens de um usuário, uma política de retenção é aplicada no nível de uma caixa de correio.

Para uma pasta pública, uma política de retenção é aplicada ao nível da pasta, não ao nível da caixa de correio. 

Tanto uma caixa de correio quanto uma pasta pública usam a [pasta Itens Recuperáveis](https://docs.microsoft.com/exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder) para reter itens. Somente as pessoas às quais foram atribuídas permissões de Descoberta Eletrônica podem exibir itens na pasta Itens Recuperáveis de outro usuário.
  
Quando alguém exclui uma mensagem em uma pasta diferente da pasta Itens Excluídos, por padrão, a mensagem é movida para a pasta Itens Excluídos. Quando alguém exclui um item na pasta Itens Excluídos, a mensagem é movida para a pasta Itens Recuperáveis. Entretanto, um usuário pode excluir um item de forma reversível (Shift+Delete) em qualquer pasta, o que evita que ele vá pasta Itens Excluídos e o move diretamente para a pasta Itens Recuperáveis.
  
Quando você aplica uma política de retenção a um local do Exchange, um trabalho de temporizador avalia periodicamente os itens na pasta Itens Recuperáveis. Quando um item não corresponde às regras de pelo menos uma política de retenção, ele é excluído permanentemente (chamado também de exclusão forçada) da pasta Itens Recuperáveis.

O trabalho do temporizador pode levar até sete dias para ser executado e o local da Bolsa deve conter pelo menos 10 MB
  
Quando um usuário tenta alterar propriedades de um item de caixa de correio, como assunto, corpo, anexos, remetentes e destinatários, ou a data de envio ou de recebimento de uma mensagem, uma cópia do item original é salva na pasta Itens Recuperáveis antes da confirmação da alteração. Essa ação acontecerá para todas as alterações subsequentes. No final do período de retenção, as cópias na pasta Itens Recuperáveis são excluídas permanentemente.

Depois que uma política de retenção é atribuída a uma caixa de correio ou pasta pública, os caminhos que o conteúdo assume dependem se as configurações forem para reter e excluir, somente reter ou somente excluir.

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

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a>Como excluir tipos específicos de itens do Exchange de uma política de retenção

Usando o Windows PowerShell, você pode excluir tipos específicos de itens do Exchange a partir de uma política de retenção quando as configurações de retenção são para reter somente. Por exemplo, você pode excluir mensagens de caixa postal, conversas de mensagens instantâneas e outros conteúdos do Skype for Business Online nas caixas de correio. Você também pode excluir o calendário, anotações e itens de tarefas. Esse recurso está disponível apenas no Windows PowerShell; não está disponível na interface de usuário quando você cria uma política de retenção usando o assistente no Centro de Conformidade do Microsoft 365.
  
Para excluir os tipos selecionados para itens do Exchange em uma política de retenção, use o parâmetro `ExcludedItemClasses` com os cmdlets [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/new-retentioncompliancerule) e  [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancerule).

Para usar os cmdlets de políticas de retenção, você dever primeiro [conectar-se com o Centro de Segurança e Conformidade do PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell?view=exchange-ps).

## <a name="when-a-user-leaves-the-organization"></a>Quando um usuário sair da organização 

Se um usuário deixar sua organização e a caixa de correio do usuário for incluída em uma política de retenção, ela se tornará uma caixa de correio inativa quando a conta do Microsoft 365 do usuário for excluída. O conteúdo de uma caixa de correio inativa ainda está sujeito a qualquer política de retenção que tenha sido aplicada a essa caixa antes dela se tornar inativa, e ele fica disponível para uma pesquisa de descoberta eletrônica. Para saber mais, confira [Caixas de correio inativas no Exchange Online](inactive-mailboxes-in-office-365.md). 

## <a name="how-to-configure-a-retention-policy-for-exchange"></a>Como configurar uma política de retenção para o Exchange

Siga as instruções para [Criar e configurar políticas de retenção](create-retention-policies.md) e, na página **Escolher locais** do assistente, escolha uma das seguintes opções:

- **Aplicar política apenas ao conteúdo em emails do Exchange, pastas públicas, Grupos do Office 365, documentos do OneDrive e do SharePoint**

- **Deixe-me escolher locais espec[ificos** > **E-mail do Exchange**, **Pastas públicas do Exchange**, e **Grupos do Office 365**.

Mesmo que um grupo do Microsoft 365 tenha uma caixa de correio do Exchange, uma política de retenção que inclua todo o local **E-mail do Exchange** não incluirá conteúdo nas caixas de correio de grupo do Microsoft 365. Para manter o conteúdo nessas caixas de correio, selecione o local **Grupos do Office 365**.
