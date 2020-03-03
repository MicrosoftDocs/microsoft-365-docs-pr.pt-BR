---
title: Criar assinaturas e isenções para toda a organização
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Saiba como adicionar assinatura de email, isenção de responsabilidade legal ou declaração de divulgação a todas as mensagens de email que entram ou saem da sua organização.
ms.openlocfilehash: a63f21dff90c70d39e3709d4c34b53d99a315a59
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2020
ms.locfileid: "42360662"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Criar assinaturas e isenções para toda a organização

 Você pode adicionar uma assinatura de email, isenção de responsabilidade ou política de divulgação às mensagens de email que entram ou saem de sua organização. É possível configurar essa mensagem para que ela se aplique a todos os emails enviados e recebidos, conforme é mostrado abaixo. Também é possível aplicá-la a determinados emails, por exemplo, aqueles que contêm palavras ou padrões de texto específicos.

 Assista a um pequeno vídeo sobre como criar uma assinatura de email em toda a empresa. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Se você achou esse vídeo útil, Confira as [ séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Criar uma assinatura que se aplica a todas as mensagens

> [!TIP]
> As assinaturas de toda a organização são chamadas de "avisos de isenção", independentemente do que incluem. Por exemplo, eles podem ser apenas uma assinatura ou incluir seu endereço, isenção de responsabilidade legal ou outras informações que você desejar.
    
::: moniker range="o365-worldwide"

Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Selecione o inicializador ![de aplicativos no ícone do inicializador](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png)de aplicativos no Office 365 e selecione **administrador**.
   
    Não consegue encontrar o aplicativo que está procurando? No inicializador de aplicativos, selecione **Todos os aplicativos** para ver uma lista em ordem alfabética dos aplicativos disponíveis do Office 365. Nesse local, você pode pesquisar um aplicativo específico. 
    
2. Selecione **centros de administração**e, em seguida, escolha **Exchange**.
    
3. Em fluxo de email, selecione **regras**.
    
4. Selecione o **+** ícone (Adicionar) e escolha **aplicar avisos de isenção de responsabilidade**.
    
5. Dê um nome à regra.
    
6. Em **aplicar esta regra**, selecione **[aplicar a todas as mensagens]**.
    
    > [!TIP]
    > [Saiba mais](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) sobre como aplicar condições se não quiser que a isenção de responsabilidade seja aplicada a todas as mensagens. (Esse artigo de escopo é para o Exchange Server, mas também se aplica ao Office 365.) 
  
7. Em Faça o seguinte, deixe **Adicionar o aviso de isenção de responsabilidade** selecionado. 
    
8.  Selecione **Inserir texto** e digite sua isenção de responsabilidade. 
    
    > [!TIP]
    > [Saiba mais](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) sobre a formatação de avisos de isenção de responsabilidade. (Este artigo de formatação é para o Exchange Server, mas também se aplica ao Office 365.) 

9. Selecione **selecionar um** e escolha **quebrar** como uma opção de fallback. Em seguida, clique em **OK**. Isso significa que, se não for possível adicionar a isenção de responsabilidade devido a criptografia ou outra configuração de email, ela será quebrada automaticamente em um envelope de mensagem.
    
10. Deixe **Auditar esta regra com o nível de severidade** selecionado. Em seguida, escolha **Baixo**, **Médio** ou **Alto** para uso no registro de mensagens. 
    
11. Escolha **Impor** para ativar a isenção de responsabilidade imediatamente, a menos que você queira testá-la primeiro. 
    
12. Escolha **Mais opções** para incluir exceções ou condições adicionais. 
    
13. Escolha **Salvar** quando terminar. 
    
## <a name="limitations-of-office-365-organization-wide-signatures"></a>Limitações das assinaturas de toda a organização do Office 365

Não é possível fazer o seguinte com as assinaturas do Office 365:
  
- Inserir a assinatura diretamente sob a última resposta de email ou encaminhar
    
- Exibir assinaturas de email do servidor em pastas de itens enviados dos usuários
    
- Inserir imagens em assinaturas de email
    
- Ignorar linhas que contêm variáveis que não puderam ser atualizadas (por exemplo, porque o valor não foi fornecido para um usuário)
    
Para obter esses e outros recursos, use uma ferramenta de terceiros. Faça uma pesquisa na Internet por **software de assinatura de email**. Vários desses provedores são parceiros Microsoft Gold e seu software fornece esses recursos. 
  
## <a name="more-resources"></a>Mais recursos

- Consulte [avisos de isenção de responsabilidade de mensagens em toda a organização, assinaturas, rodapés ou cabeçalhos no Office 365](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) para obter informações sobre como usar o PowerShell. 
    

