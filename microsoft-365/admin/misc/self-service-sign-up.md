---
title: Usando a inscrição de autoatendimento em sua organização
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Saiba mais sobre os programas de autoatendimento do Office 365 e recursos disponíveis como o Microsoft Power apps, Microsoft Flow e Dynamics 365 para finanças.
ms.custom: okr_SMB
ms.openlocfilehash: fa7e6dcb4c40a7a41599b7c1a81fa596868d8e2d
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106107"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Usando a inscrição de autoatendimento em sua organização

Vamos ouvir seus comentários e tornar mais fácil para os usuários em sua organização inscrever-se nos serviços online da Microsoft. Chamamos esse novo processo de inscrição de "inscrição de autoatendimento", pois seus usuários podem se inscrever para usar os serviços pagos pela sua assinatura ou usar serviços gratuitos, sem pedir que você execute a ação em seu nome.
  
## <a name="how-self-service-sign-up-works"></a>Como funciona a inscrição de autoatendimento

O exemplo a seguir descreve como o auto-inscrição funciona para uma escola. O mesmo processo funciona para qualquer organização que tenha programas de autoatendimento habilitados no locatário.
  
1. Estudantes e professores têm endereços de email escolares que indicam que estão associados à sua instituição. Por exemplo, o endereço de email jakob@uw.edu pode indicar um aluno da Universidade de Washington.

2. Estudantes e professores vão para o [nosso site](https://go.microsoft.com/fwlink/p/?LinkId=536628)e usar o endereço de email para se inscrever nos serviços que sua organização oferece, como o Office 365 ProPlus. Eles também podem se inscrever em outros serviços gratuitos que oferecemos.

3. Validamos o endereço de email e, em seguida, eles podem começar a usar o Office 365, Power BI ou outros serviços imediatamente.

4. Como administrador de negócios, você vê quem se inscreveu para uma assinatura, exibindo a página **produtos & Services** no centro de administração. Dessa forma, você pode ver quando há licenças novas ou não reconhecidas para serviços em seu locatário. Para controlar se os usuários podem se inscrever em subscrições de autoatendimento, use o cmdlet do PowerShell [set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) com o parâmetro **AllowAdHocSubscriptions** . Para obter mais informações, consulte [como controlar as configurações de autoatendimento?](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq?view=o365-worldwide)

## <a name="available-self-service-programs"></a>Programas de autoatendimento disponíveis

A seguir estão os programas autoatendimento disponíveis atualmente. Essa lista será atualizada à medida que novos programas forem adicionados.
  
|||||
|:-----|:-----|:-----|:-----|
|**Programa** <br/> |**Descrição** <br/> |**Informações adicionais** <br/> |Site para inscrição de autoatendimento * * * * <br/> |
|Office 365 a1 * * * * <br/> |Qualquer aluno ou professor pode usar um endereço de email escolar para se inscrever no Office 365 gratuito e obter aplicativos do Office para a Web, 1TB de armazenamento em nuvem do OneDrive e SharePoint Online para sites de classe, equipe e projeto.  <br/> |[Perguntas técnicas frequentes sobre o Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 a1 Plus** <br/> |Estudantes e professores qualificados podem se inscrever no Office 365 a1 Plus, que inclui tudo mencionado acima, além do Office 365 ProPlus. O Office 365 ProPlus é um software de produtividade, incluindo Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access e Skype for Business, que é instalado no computador desktop ou notebook.  <br/> |[Perguntas técnicas frequentes sobre o Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |O Power BI permite que os usuários visualizem dados, compartilhem descobertas e colabore de novas maneiras intuitivas. <br/> Se sua organização já estiver inscrita no Office 365, você poderá ver as licenças da "avaliação de usuário individual do Power BI pro", que oferece aos usuários acesso gratuito e limitado aos recursos avançados.  <br/> |[Power BI em sua organização](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rights Management Services (RMS)** <br/> |O RMS para pessoas é uma assinatura de autoatendimento gratuito para usuários em uma organização que tenham enviado arquivos confidenciais que foram protegidos pelo Azure Rights Management (Azure RMS), mas seu departamento de ti não implementou o Azure Rights Management (Azure RMS) ou Active Directory Rights Management Services (AD RMS).  <br/> |[RMS para indivíduos e o Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Portal de gerenciamento de direitos da Microsoft](https://portal.azure.com/) para que você possa verificar se pode abrir um determinado documento protegido por direitos.  <br/> |
|**Aplicativos de alimentação da Microsoft** <br/> |No PowerApps, você pode gerenciar dados organizacionais executando um aplicativo que você criou ou que outra pessoa criou e compartilhou com você. Os aplicativos são executados em dispositivos móveis, como telefones, ou podem ser executados em um navegador abrindo o Dynamics 365. Você pode criar uma variedade infinita de aplicativos, sem aprender uma linguagem de programação como C#.  <br/> |[Inscrição de autoatendimento para PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Aplicativos de alimentação da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 para finanças** <br/> |Obtenha uma solução completa de gerenciamento de negócios e financeiro para pequenas e médias empresas. O Dynamics 365 para finanças facilita o pedido, a venda, o faturamento e o relatório, começando no dia um.  <br/> |[Microsoft Dynamics 365 para finanças](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 para finanças](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 para operações** <br/> |Aumente sua velocidade de fazer negócios. As ferramentas ERP completas do Dynamics 365 for Operations fornecem escalabilidade global e inteligência digital para ajudá-lo a crescer em seu ritmo.  <br/> |[Microsoft Dynamics 365 para operações](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 para operações](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |O Microsoft AppSource é um destino para aplicativos de negócios de software como serviço criados na plataforma de nuvem da Microsoft. AppSource oferece centenas de aplicativos, Complementos e pacotes de conteúdo que estendem a funcionalidade de produtos da Microsoft, como Azure, Dynamics 365, Office 365 e Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Incentivos de parceiros da Microsoft** <br/> |O Microsoft Partner Network fornece três tipos de associações. Cada tipo fornece um conjunto de benefícios para ajudar sua empresa a crescer. À medida que atingir suas metas, participe do programa no nível que atenda às suas necessidades exclusivas para acessar mais benefícios e desenvolver sua relação com a empresa e outros parceiros na rede.  <br/> |[Incentivos de parceiros da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Incentivos de parceiros da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Centro de negócios da Microsoft** <br/> |O Microsoft Business Center é o portal para clientes que fizeram compras por meio do contrato de produtos e serviços da Microsoft (MPSA). <br/> |[Início rápido: Registre-se no Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Centro de negócios da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Centro de serviços de licença por volume da Microsoft** <br/> |O centro de serviços de licença de volume da Microsoft exibe licenças adquiridas sob Enterprise, Select, Education (campus ou School), Open Value, Open License, and ISV Royalty Agreements.  <br/> |[Treinamento e recursos do VLSC](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Centro de serviços de licença de volume](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Usando o Minecraft como uma plataforma para o aprendizado, os educadores podem motivar e inspirar cada aluno a alcançar mais e Ignite uma paixão para o aprendizado. Ingresse em uma comunidade de educadores aprendendo a usar o Minecraft para desbloquear o potencial do aluno.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Carregue e compartilhe vídeos em sua organização para melhorar a comunicação, a participação e o aprendizado.  <br/> |[Experiência do &amp; dia de inscrição 0](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Automatização de energia** <br/> |A automatização de energia é um produto para ajudá-lo a configurar fluxos de trabalho automatizados entre seus aplicativos e serviços favoritos para sincronizar arquivos, obter notificações, coletar dados e muito mais.  <br/> |[Inscreva-se e entre para automatizar a alimentação](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Automatização de energia](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Agentes virtuais de alimentação** <br/> |Os agentes virtuais de alimentação capacitam o Teams a criar facilmente bots poderosos usando uma interface gráfica orientada e sem código, sem a necessidade de cientistas ou desenvolvedores de dados. Os agentes virtuais de alimentação resolvem muitos dos principais problemas com a criação de bot no setor atualmente. Ele elimina a lacuna entre os especialistas no assunto e as equipes de desenvolvimento que montam os bots, e a longa latência entre as equipes que reconhecem um problema e a atualização do bot para o endereçamento.  <br/> |[Detalhes de licenciamento e acesso](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Inscrever-se para agentes virtuais de alimentação](https://aka.ms/TryPVA) <br/> |