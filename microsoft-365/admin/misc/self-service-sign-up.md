---
title: Usando a assinatura de autoatend à sua organização
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_SMB
search.appverid:
- MET150
ms.assetid: 4f8712ff-9346-4c6c-bb63-a21ad7a62cbd
description: Saiba mais sobre a assinatura de autoatendado do Microsoft 365 e os programas de autoatenDados disponíveis, como o Microsoft Power Apps, o Microsoft Flow e o Dynamics 365 for Finance.
ms.openlocfilehash: 21e41661141a817a1751c80608035d839d2e3952
ms.sourcegitcommit: 7355cc8871cde5fac6d7d6dcecc3e41e35601623
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48906568"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Usando a assinatura de autoatend à sua organização

A assinatura self-service torna mais fácil para os usuários em sua organização se inscreverem em serviços online da Microsoft. Chamamos esse processo de inscrição de "inscrição self-service" porque seus usuários podem se inscrever para usar serviços pagos por sua assinatura ou usar serviços gratuitos, sem pedir que você tome medidas em nome deles.
  
## <a name="how-self-service-sign-up-works"></a>Como funciona a inscrever-se self-service

O exemplo a seguir descreve como a auto-assinatura funciona para uma escola. O mesmo processo funciona para qualquer organização que tenha programas de autoatendenciamento habilitados em seu locatário.
  
1. Alunos e membros do corpo docente têm endereços de email escolares que indicam que estão associados à sua instituição. Por exemplo, o endereço de email jakob@uw.edu pode indicar um aluno na University of Washington.
2. Os alunos e docentes vão para o [nosso site](https://go.microsoft.com/fwlink/p/?LinkId=536628)e usam o endereço de email deles para se inscreverem nos serviços que sua organização oferece, como o Microsoft 365 Apps para empresas. Eles também podem se inscrever para outros serviços gratuitos que oferecemos.
3. Validamos seu endereço de email e, em seguida, eles podem começar a usar o Microsoft 365, Power BI ou outros serviços imediatamente.
4. Como administrador de negócios, você pode ver quem se inscreveu  para uma assinatura selecionando a assinatura na página Licenciamento no centro de administração do Microsoft 365. Dessa forma, você pode ver quando há licenças novas ou não reconhecedas para serviços em seu locatário. Para controlar se os usuários podem se inscrever para assinaturas de autoatendente, use o cmdlet [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) PowerShell com o parâmetro **AllowAdHocSubscriptions.** Para obter mais informações, [consulte Como faço para controlar as configurações de autoatend site?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Programas de autoatend à disposição

A seguir estão os programas de autoatenDados disponíveis no momento. Essa lista será atualizada à medida que novos programas são adicionados.
  
| Programa <br/> | Descrição <br/> | Informações adicionais <br/> | Site para inscrever-se no site de autoatend à sua empresa <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |Qualquer aluno ou professor pode usar um endereço de email escolar para se inscrever gratuitamente no Office 365 e obter aplicativos do Office para a Web, 1 TB de armazenamento em nuvem do OneDrive e SharePoint Online para sites de classe, equipe e projeto.  <br/> |[Perguntas frequentes técnicas do Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |Os alunos e professores qualificados podem se inscrever no Office 365 A1 Plus, que inclui tudo mencionado acima, além do Microsoft 365 Apps para empresas. O Microsoft 365 Apps para empresas é um software de produtividade, incluindo Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access e Skype for Business, que está instalado em seu computador desktop ou laptop.  <br/> |[Perguntas frequentes técnicas do Office 365 Education](https://go.microsoft.com/fwlink/p/?LinkId=536625) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |O Power BI permite que os usuários visualizem dados, compartilhem descobertas e colaborem de novas maneiras intuitivas. <br/> Se sua organização já se inscreve, você também pode ver licenças de "Avaliação de usuário individual do Power BI Pro", que oferecem aos usuários acesso limitado e gratuito a recursos avançados.  <br/> |[Power BI em sua organização](https://go.microsoft.com/fwlink/p/?LinkId=536626) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**Rights Management Services (RMS)** <br/> |O RMS para indivíduos é uma assinatura de autoatendida gratuita para usuários em uma organização que foram enviados arquivos confidenciais protegidos pelo Azure Rights Management (Azure RMS), mas seu departamento de IT não implementou o Azure Rights Management (Azure RMS) ou o Active Directory Rights Management Services (AD RMS).  <br/> |[RMS para indivíduos e Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=536627) <br/> |[Portal do Microsoft Rights Management](https://portal.azure.com/) para que você possa verificar se pode abrir um determinado documento protegido por direitos.  <br/> |
|**Microsoft Power Apps** <br/> |No PowerApps, você pode gerenciar dados organizacionais executando um aplicativo que você criou ou que outra pessoa criou e compartilhou com você. Os aplicativos são executados em dispositivos móveis, como telefones, ou você pode executar em um navegador abrindo o Dynamics 365. Você pode criar uma variedade infinita de aplicativos, tudo isso sem aprender uma linguagem de programação como C#.  <br/> |[Inscrever-se em autoatend pois o PowerApps](https://go.microsoft.com/fwlink/p/?linkid=841461) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 for Financials** <br/> |Obter uma solução completa de gerenciamento empresarial e financeiro para pequenas e médias empresas. O Dynamics 365 for Financials facilita o pedido, a venda, o faturamento e o relatório, começando no primeiro dia.  <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 for Financials](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Aumente a velocidade de fazer negócios. As ferramentas completas de ERP no Dynamics 365 for Operations fornecem escalabilidade global e inteligência digital para ajudá-lo a crescer em seu ritmo.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |O Microsoft AppSource é um destino para aplicativos de negócios de software como serviço, construídos na plataforma de nuvem da Microsoft. O AppSource apresenta centenas de aplicativos, complementos e pacotes de conteúdo que estendem a funcionalidade de produtos da Microsoft, como Azure, Dynamics 365, Office 365 e Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Incentivos para parceiros da Microsoft** <br/> |O Microsoft Partner Network fornece três tipos de associações. Cada tipo fornece um conjunto de benefícios para ajudar seu negócio a crescer. Conforme você atingir suas metas, participe do programa no nível mais adequada às suas necessidades exclusivas para acessar mais benefícios e desenvolver seu relacionamento conosco e com outros parceiros na rede.  <br/> |[Incentivos para parceiros da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Incentivos para parceiros da Microsoft](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |O Microsoft Business Center é o portal para clientes que fizeram compras por meio do Contrato de Produtos e Serviços da Microsoft (MPSA). <br/> |[Início Rápido: registre-se no Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Centro de Serviços de Licença de Volume da Microsoft** <br/> |O Centro de Serviços de Licença por Volume da Microsoft exibe licenças adquiridas em contratos Enterprise, Select, Education (Campus ou School), Open Value, Open License e ISVTies.  <br/> |[Treinamento e recursos do VLSC](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Centro de Serviços de Licença de Volume](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Usando o Minecraft como uma plataforma de aprendizagem, os educadores podem inspirar e inspirar todos os alunos a alcançar mais e acionar um novo aprendizado. Participe de uma comunidade de educadores aprendendo a usar o Minecraft para desbloquear o potencial dos alunos.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Carregue e compartilhe vídeos em toda a organização para melhorar a comunicação, a participação e o aprendizado.  <br/> |[Inscrever-se &amp; no Dia 0](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |O Power Automate é um produto que ajuda você a configurar fluxos de trabalho automatizados entre seus aplicativos e serviços favoritos para sincronizar arquivos, receber notificações, coletar dados e muito mais.  <br/> |[Inscreva-se e entre no Power Automate](https://docs.microsoft.com/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Agentes virtuais do Power** <br/> |Os Agentes Virtuais Do Power permitem que as equipes criem facilmente bots poderosos usando uma interface gráfica guiada sem código sem a necessidade de desenvolvedores ou criadores de dados. Os Agentes Virtuais Do Power resolvem muitos dos principais problemas com a criação de bots no setor atualmente. Isso elimina a lacuna entre os especialistas no assunto e as equipes de desenvolvimento que estão criando os bots e a longa latência entre as equipes reconhecendo um problema e atualizando o bot para lidar com ele.  <br/> |[Detalhes de licenciamento e acesso](https://go.microsoft.com/fwlink/?linkid=2113708) <br/> |[Inscrever-se para Agentes Virtuais Do Power](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |A colaboração entre empresas (B2B) do Azure Active Directory (Azure AD) permite convidar usuários externos (ou "usuários convidados") para usar seus serviços pagos do Azure AD. Alguns recursos são gratuitos, mas para todos os recursos pagos do Azure AD, você pode convidar até cinco usuários convidados para cada licença da edição do Azure AD que você possui para um funcionário ou um usuário não convidado em seu locatário. <br/> |[Autoatendado para a assinatura de colaboração B2B do Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/self-service-portal) <br/> |[Diretrizes de licenciamento de colaboração B2B do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) <br/> |
