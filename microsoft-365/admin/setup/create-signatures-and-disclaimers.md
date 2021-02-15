---
title: Criar assinaturas e avisos de isenção de isenção em toda a organização
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-may2020
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Aprenda a gerenciar assinaturas de email, incluindo avisos de isenção legal ou declarações de divulgação para todas as mensagens de email que entram ou saem da sua organização.
ms.openlocfilehash: c8d63a11a75b9b53de9cabdf1f4baabc61cc3e42
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926913"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Criar assinaturas e avisos de isenção de isenção em toda a organização

 Você pode gerenciar assinaturas de email adicionando uma assinatura de email, um aviso de isenção legal ou uma declaração de divulgação às mensagens de email que entram ou saem da sua organização. É possível configurar essa mensagem para que ela se aplique a todos os emails enviados e recebidos, conforme é mostrado abaixo. Também é possível aplicá-la a determinados emails, por exemplo, aqueles que contêm palavras ou padrões de texto específicos.

 Assista a um vídeo curto sobre como criar uma assinatura de email de toda a empresa. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Se você achou esse vídeo útil, consulte as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Criar uma assinatura que se aplica a todas as mensagens

> [!TIP]
> As assinaturas de toda a organização são chamadas de "avisos de isenção", independentemente do que incluem. Por exemplo, eles podem ser apenas uma assinatura ou também incluir seu endereço, aviso de isenção legal ou outras informações que você deseja.
    
::: moniker range="o365-worldwide"

Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Selecione o iniciador de aplicativos O ícone do iniciador de ![ ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) aplicativos e, em seguida, selecione **Admin**.
   
    Não consegue encontrar o aplicativo que está procurando? No iniciador de aplicativos, selecione **Todos** os aplicativos para ver uma lista em ordem alfabética dos aplicativos disponíveis para você. Nesse local, você pode pesquisar um aplicativo específico. 
    
2. Selecione **Centros de administração** e escolha **Exchange**.
    
3. Em Fluxo de emails, selecione **Regras**.
    
4. Selecione o **+** ícone (Adicionar) e escolha **Aplicar avisos de isenção.**
    
5. Dê um nome à regra.
    
6. Em **Aplicar esta regra,** selecione **[Aplicar a todas as mensagens]**.
    
    > [!TIP]
    > [Saiba mais](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) sobre como aplicar condições se não quiser que a isenção de responsabilidade seja aplicada a todas as mensagens. (Este artigo de definição de responsabilidade é para o Exchange Server, mas também se aplica ao Microsoft 365.) 
  
7. Em Faça o seguinte, deixe **Adicionar o aviso de isenção de responsabilidade** selecionado. 
    
8.  Selecione **Enter text** e digite seu aviso de isenção de responsabilidade. 
    
    > [!TIP]
    > [Saiba mais](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) sobre a formatação de avisos de isenção de responsabilidade. (Este artigo de formatação é para o Exchange Server, mas também se aplica ao Microsoft 365.) 

9. Selecione **Selecionar um e** escolha Quebrar **como** uma opção de fallback. Em seguida, clique em **OK**. Isso significa que, se não for possível adicionar a isenção de responsabilidade devido a criptografia ou outra configuração de email, ela será quebrada automaticamente em um envelope de mensagem.
    
10. Deixe **Auditar esta regra com o nível de severidade** selecionado. Em seguida, escolha **Baixo**, **Médio** ou **Alto** para uso no registro de mensagens. 
    
11. Escolha **Impor** para ativar a isenção de responsabilidade imediatamente, a menos que você queira testá-la primeiro. 
    
12. Escolha **Mais opções** para incluir exceções ou condições adicionais. 
    
13. Escolha **Salvar** quando terminar. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Limitações de assinaturas em toda a organização

Não é possível fazer o seguinte ao gerenciar assinaturas de email no Microsoft 365:
  
- Inserir a assinatura diretamente na resposta ou encaminhamento de email mais recente
    
- Exibir assinaturas de email do lado do servidor nas pastas Itens Enviados dos usuários
    
- Incorporar imagens em assinaturas de email
    
- Ignorar linhas que contêm variáveis que não puderam ser atualizadas (por exemplo, porque o valor não foi fornecido para um usuário)
    
Para obter esses e outros recursos para gerenciar assinaturas de email, use uma ferramenta de terceiros. Faça uma pesquisa na Internet para o **software de assinatura de email.** Vários desses provedores são Parceiros Gold da Microsoft e seu software fornece esses recursos. 
  
## <a name="more-resources"></a>Mais recursos

- Consulte Avisos de isenção [de responsabilidade, assinaturas, rodapés](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) ou títulos em toda a organização no Exchange Online para obter informações sobre como usar o PowerShell.