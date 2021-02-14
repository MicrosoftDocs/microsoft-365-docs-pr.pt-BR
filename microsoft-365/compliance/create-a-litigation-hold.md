---
title: Criar uma Retenção de Litígio
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Saiba como colocar uma caixa de correio em Retenção de Litígio, retendo todo o conteúdo da caixa de correio durante uma investigação.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 4bcb857095a63c06caa6e9762496ca74afeead04
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546983"
---
# <a name="create-a-litigation-hold"></a>Criar uma Retenção de Litígio

Você pode colocar uma caixa de correio em Retenção de Litígio para reter todo o conteúdo da caixa de correio, incluindo itens excluídos e as versões originais de itens modificados. Quando você coloca uma caixa de correio de usuário em Litígio, o conteúdo na caixa de correio de arquivo morto do usuário (se estiver habilitado) também é retido. Ao criar uma espera, você pode especificar uma duração de espera (também chamada de espera baseada em *tempo)* para que os itens excluídos e modificados sejam mantidos por um período especificado e, em seguida, excluídos permanentemente da caixa de correio. Ou você pode simplesmente reter o conteúdo indefinidamente (chamado de retenção *infinita)* ou até que a Retenção de Litígio seja removida. Se você especificar um período de duração de espera, ele é calculado a partir da data em que uma mensagem é recebida ou um item de caixa de correio é criado. 
  
Veja o que acontece quando você cria uma Responsabilidade de Litígio.
  
- Os itens excluídos permanentemente pelo usuário são mantidos na pasta Itens Recuperáveis na caixa de correio do usuário pela duração da espera.
    
- Os itens que são limpos da pasta Itens Recuperáveis pelo usuário são mantidos pela duração da espera.
    
- A cota de armazenamento da pasta Itens Recuperáveis aumentou de 30 GB para 110 GB.
    
- Itens nas caixas de correio principal e de arquivo morto do usuário são mantidos
    
## <a name="assign-an-exchange-online-plan-2-license"></a>Atribuir uma licença do Plano 2 do Exchange Online

- Para colocar uma caixa de correio do Exchange Online em Litígio, ela deve receber uma licença do Plano 2 do Exchange Online. Se uma caixa de correio receber uma licença do Exchange Online Plano 1, você terá que atribuir uma licença separada do Arquivamento do Exchange Online para coloca-la em espera.
    

## <a name="place-a-mailbox-on-litigation-hold"></a>Colocar uma caixa de correio em Retenção de Litígio

Aqui estão as etapas para colocar uma caixa de correio em Responsabilidade de Litígio usando o Centro de administração do Exchange.

1. Acesse e [https://outlook.office.com/ecp](https://outlook.office.com/ecp) entre usando sua conta de administrador global.

2. Clique **em Destinatários > Caixas de** Correio no painel de navegação esquerdo.

3. Selecione a caixa de correio que você deseja colocar em Litígio e clique em **Editar**.

4. Na página de propriedades da caixa de correio, clique em **Recursos da Caixa de Correio**.
    
5. Em **Retenção de Litígio: Desativado**, clique em **Habilitar** para colocar a caixa de correio em Retenção de Litígio.
    
6. Na página **Litígio, insira** as seguintes informações opcionais: 
    
    - **Duração da espera de litígio (dias)** - Use essa caixa para criar uma espera baseada em tempo e especificar por quanto tempo os itens da caixa de correio serão mantidos quando a caixa de correio for colocada em Litígio. A duração é calculada a partir da data em que um item de caixa de correio é recebido ou criado. Quando a duração da espera expirar para um item específico, esse item não será mais preservado. Se você deixar essa caixa em branco, os itens serão preservados indefinidamente ou até que a espera seja removida. Use dias para especificar a duração.
    
    - **Observação:** use esta caixa para informar ao usuário que sua caixa de correio está em Espera de Litígio. A observação aparecerá na página Informações da Conta na caixa de correio do usuário se ele estiver usando o Outlook 2010 ou posterior. Para acessar esta página, os usuários podem clicar **em Arquivo** no Outlook.
    
    - **URL** - Use essa caixa para direcionar o usuário a um site para obter mais informações sobre a Responsabilidade de Litígio. Essa URL aparece na página Informações da Conta na caixa de correio do usuário se ele estiver usando o Outlook 2010 ou posterior. Para acessar esta página, os usuários podem clicar **em Arquivo** no Outlook.

7. Clique **em Salvar** na página De espera **de** litígio e, em seguida, clique em **Salvar** na página de propriedades da caixa de correio.

### <a name="create-a-litigation-hold-using-powershell"></a>Criar uma Espera de Litígio usando o PowerShell

Você também pode criar uma Espera de Litígio executando o seguinte comando no [PowerShell do Exchange Online:](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

O comando anterior preserva itens indefinidamente porque a duração da espera não é especificada. Para criar uma espera baseada em tempo, usando o seguinte comando:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

Para obter mais informações, consulte [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).

## <a name="how-does-litigation-hold-work"></a>Como funciona a retenção de litígio?

No fluxo de trabalho normal de item excluído, um item de caixa de correio é movido para a subpasta Exclusões na pasta Itens recuperáveis quando um usuário o excluir permanentemente (Shift + Delete) ou o excluir da pasta Itens excluídos. Uma política de exclusão (que é uma marca de retenção configurada com uma ação de retenção de exclusão) também move itens para a subpasta Exclusões quando o período de retenção expira. Quando um usuário descarta um item da pasta Itens recuperáveis ou quando o período de retenção do item excluído expira para um item, ele é movido para a subpasta Exclusões na pasta Itens recuperáveis e marcado para exclusão permanente. Ele será excluído do Exchange na próxima vez em que a caixa de correio for processada pelo Assistente de Pasta Gerenciada (MFA).

Quando uma caixa de correio é colocada em retenção de litígio, os itens na subpasta Exclusões são preservados durante o período especificado pela retenção de litígio. A duração da retenção é calculada a partir da data original em que um item foi recebido ou criado e define por quanto tempo os itens na subpasta Exclusões são retidos. Quando expira o período de retenção de um item na subpasta Exclusões, o item é marcado para exclusão permanente e é excluído da Exchange na próxima vez em que a caixa de correio for processada pelo MFA. Se uma caixa de correio for colocada em retenção indefinida, os itens nunca serão excluídos da subpasta Exclusões.

A imagem a seguir mostra as subpastas nas pastas Itens Recuperáveis e o processo de fluxo de trabalho de retenção.

![Ciclo de vida de Espera de Litígio](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Se uma isenção associada a uma ocorrência de Descoberta Eletrônico for colocada em uma caixa de correio, os itens excluídos serão movidos da subpasta Exclusões para a subpasta DiscoveryHolds e serão preservados até que a caixa de correio seja liberada da isenção de Descoberta Eletrônico.
  
