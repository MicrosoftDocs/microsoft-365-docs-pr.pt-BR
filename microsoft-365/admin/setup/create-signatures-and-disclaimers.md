---
title: Criar assinaturas e avisos de isenção de ônus em toda a organização
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
description: Gerencie assinaturas de email, incluindo avisos de isenção de responsabilidade legal ou instruções de divulgação para todas as mensagens de email que entram ou saem da sua organização.
ms.openlocfilehash: f72d522c7dc592a7f719d716e22ecf726d00a6de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635649"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Criar assinaturas e avisos de isenção de ônus em toda a organização

 Você pode gerenciar assinaturas de email adicionando uma assinatura de email, aviso de isenção de responsabilidade legal ou declaração de divulgação às mensagens de email que entram ou saem da sua organização. É possível configurar essa mensagem para que ela se aplique a todos os emails enviados e recebidos, conforme é mostrado abaixo. Também é possível aplicá-la a determinados emails, por exemplo, aqueles que contêm palavras ou padrões de texto específicos.

## <a name="watch-create-a-company-wide-email-signature"></a>Assista: Criar uma assinatura de email em toda a empresa
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Se você achou esse vídeo útil, confira as [séries completas de treinamento para pequenas empresas e as novidades do Microsoft 365](../../business-video/index.yml).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Criar uma assinatura que se aplica a todas as mensagens

> [!TIP]
> As assinaturas em toda a organização são chamadas de "avisos de isenção de ônus", independentemente do que incluem. Por exemplo, eles podem ser apenas uma assinatura ou também incluir seu endereço, aviso de isenção de responsabilidade legal ou outras informações que você deseja.
    
::: moniker range="o365-worldwide"

Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Vá para o centro de administração do<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Selecione o launcher do aplicativo O ícone do iniciador de ![ aplicativo e selecione ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) **Admin**.
   
    Não consegue encontrar o aplicativo que está procurando? No início do aplicativo, selecione **Todos os aplicativos** para ver uma lista alfabética dos aplicativos disponíveis para você. Nesse local, você pode pesquisar um aplicativo específico. 
    
2. Selecione **Centros de administração** e escolha **Exchange**.
    
3. Em Fluxo de email, selecione **Regras**.
    
4. Selecione o **+** ícone (Adicionar) e escolha **Aplicar avisos de isenção de índole.**
    
5. Dê um nome à regra.
    
6. Em **Aplicar essa regra,** selecione **[Aplicar a todas as mensagens]**.
    
    > [!TIP]
    > [Saiba mais](/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) sobre como aplicar condições se não quiser que a isenção de responsabilidade seja aplicada a todas as mensagens. (Este artigo de scoping é para Exchange Server, mas também se aplica a Microsoft 365.) 
  
7. Em Faça o seguinte, deixe **Adicionar o aviso de isenção de responsabilidade** selecionado. 
    
8.  Selecione **Inserir texto** e digite seu aviso de isenção de responsabilidade. 
    
    > [!TIP]
    > [Saiba mais](/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) sobre a formatação de avisos de isenção de responsabilidade. (Este artigo de formatação é para Exchange Server, mas também se aplica a Microsoft 365.) 

9. Selecione **Selecionar um** e escolha **Wrap** como uma opção de fallback. Em seguida, clique em **OK**. Isso significa que, se não for possível adicionar a isenção de responsabilidade devido a criptografia ou outra configuração de email, ela será quebrada automaticamente em um envelope de mensagem.
    
10. Deixe **Auditar esta regra com o nível de severidade** selecionado. Em seguida, escolha **Baixo**, **Médio** ou **Alto** para uso no registro de mensagens. 
    
11. Escolha **Impor** para ativar a isenção de responsabilidade imediatamente, a menos que você queira testá-la primeiro. 
    
12. Escolha **Mais opções** para incluir exceções ou condições adicionais. 
    
13. Escolha **Salvar** quando terminar. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Limitações de assinaturas de toda a organização

Não é possível fazer o seguinte ao gerenciar assinaturas de email no Microsoft 365:
  
- Inserir a assinatura diretamente na resposta de email mais recente ou encaminhar
    
- Exibir assinaturas de email do lado do servidor nas pastas Itens Enviados dos usuários
    
- Inserir imagens em assinaturas de email
    
- Ignorar linhas que contêm variáveis que não puderam ser atualizadas (por exemplo, porque o valor não foi fornecido para um usuário)
    
Para obter esses e outros recursos para gerenciar assinaturas de email, use uma ferramenta de terceiros. Faça uma pesquisa na Internet para software **de assinatura de email.** Vários desses provedores são Parceiros De Ouro da Microsoft e seu software fornece esses recursos. 
  
## <a name="more-resources"></a>Mais recursos

Para obter informações sobre como usar o PowerShell, consulte Avisos de isenção de responsabilidade de mensagem em toda a [organização, assinaturas, rodapés](/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers)ou headers em Exchange Online .

## <a name="related-content"></a>Conteúdo relacionado

[Migrar emails e contatos para Microsoft 365](migrate-email-and-contacts-admin.md) (vídeo)\
[Configurações de email do usuário](../email/office-365-user-email-settings.md) (artigo)\
[Visão geral do Centro de administração do Microsoft 365](../../business-video/admin-center-overview.md) (vídeo)

