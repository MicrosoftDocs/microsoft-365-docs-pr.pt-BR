---
title: Usando a assinatura de autoatendindo em sua organização
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: seemg, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_signup
search.appverid: MET150
description: Saiba mais sobre Microsoft 365 de autoatendados e programas de autoatendados disponíveis, como o Microsoft Power Apps, Microsoft Flow e o Dynamics 365 para Finanças.
ms.date: 03/17/2021
ms.openlocfilehash: 7aec03abce468342cfeb23da490b1f950ecd7050
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286580"
---
# <a name="using-self-service-sign-up-in-your-organization"></a>Usando a assinatura de autoatendindo em sua organização

A insinuidade de autoatendindo facilita a assinatura dos usuários em sua organização para serviços online da Microsoft. Chamamos esse processo de inscrição de "inscrição autoatendida" porque seus usuários podem se inscrever para usar os serviços pagos por sua assinatura ou usar serviços gratuitos, sem pedir que você tome medidas em nome deles.

## <a name="how-self-service-sign-up-works"></a>Como funciona a assinatura de autoatend

O exemplo a seguir descreve como a auto-assinatura funciona para uma escola. O mesmo processo funciona para qualquer organização que tenha programas de autoatendados habilitados em seu locatário.

1. Alunos e membros do corpo docente têm endereços de email escolares que indicam que estão associados à sua instituição. Por exemplo, o endereço de email jakob@uw.edu pode indicar um aluno na Universidade de Washington.
2. Os alunos e professores vão para nosso [site](https://go.microsoft.com/fwlink/p/?LinkId=536628)e usam o endereço de email para se inscrever nos serviços que sua organização oferece, como Microsoft 365 Apps para Grandes Empresas. Eles também podem se inscrever em outros serviços gratuitos que oferecemos.
3. Validamos seu endereço de email e, em seguida, eles podem começar a usar Microsoft 365, Power BI ou outros serviços imediatamente.
4. Como administrador de negócios, você pode ver quem se inscreveu  para uma assinatura selecionando a assinatura na página Licenciamento na Centro de administração do Microsoft 365. Dessa forma, você pode ver quando há licenças novas ou não reconhecedas para serviços em seu locatário. Para controlar se os usuários podem se inscrever para assinaturas de autoatendiço, use o cmdlet [Set-MsolCompanySettings](/powershell/module/msonline/set-msolcompanysettings) PowerShell com o parâmetro **AllowAdHocSubscriptions.** Para obter mais informações, consulte [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="available-self-service-programs"></a>Programas de autoatendados disponíveis

A seguir estão os programas de autoatendados disponíveis no momento. Essa lista será atualizada à medida que novos programas são adicionados.

| Programa <br/> | Descrição <br/> | Informações adicionais <br/> | Site para inscrever-se em autoatend <br/> |
|:-----|:-----|:-----|:-----|
|Office 365 A1**** <br/> |Qualquer aluno ou professor pode usar um endereço de email da escola para se inscrever gratuitamente Office 365 e obter aplicativos Office para a Web, 1 TB de armazenamento em nuvem OneDrive e SharePoint Online para sites de classe, equipe e projeto.  <br/> |[Office 365 Education Perguntas frequentes técnicas](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Office 365 A1 Plus** <br/> |Os alunos e professores qualificados podem se inscrever no Office 365 A1 Plus, que inclui tudo mencionado acima mais Microsoft 365 Apps para Grandes Empresas. Microsoft 365 Apps para Grandes Empresas é um software de produtividade, incluindo Word, PowerPoint, Excel, Outlook, OneNote, Publisher, Access e Skype for Business, que está instalado em seu computador desktop ou laptop.  <br/> |[Office 365 Education Perguntas frequentes técnicas](/microsoft-365/education/deploy/office-365-education-self-sign-up) <br/> |[Office 365 Education](https://go.microsoft.com/fwlink/p/?linkid=140841) <br/> |
|**Power BI** <br/> |Power BI permite que os usuários visualizem dados, compartilhem descobertas e colaborem de novas maneiras intuitivas. <br/> Se a sua organização já se inscrever, você poderá também ver licenças para "Power BI Pro Avaliação individual do usuário", que oferecem aos usuários acesso limitado e gratuito aos recursos avançados.  <br/> |[Power BI em sua organização](./power-bi-in-your-organization.md) <br/> |[Microsoft Power BI](https://go.microsoft.com/fwlink/p/?LinkId=536629) <br/> |
|**RmS (Rights Management Services)** <br/> |O RMS para pessoas físicas é uma assinatura de autoatendido gratuita para usuários em uma organização que foram enviados arquivos confidenciais que foram protegidos pelo Azure Rights Management (Azure RMS), mas seu departamento de IT não implementou o Azure Rights Management (Azure RMS) ou o Active Directory Rights Management Services (AD RMS).  <br/> |[RMS para pessoas físicas e gerenciamento de direitos do Azure](/azure/information-protection/rms-for-individuals) <br/> |[Portal de Gerenciamento de](https://portal.azure.com/) Direitos da Microsoft para que você possa verificar se pode abrir um determinado documento protegido por direitos.  <br/> |
|**Microsoft Power Apps** <br/> |No PowerApps, você pode gerenciar dados organizacionais executando um aplicativo que você criou ou que outra pessoa criou e compartilhou com você. Os aplicativos são executados em dispositivos móveis, como telefones, ou você pode executar em um navegador abrindo o Dynamics 365. Você pode criar uma variedade infinita de aplicativos - tudo sem aprender uma linguagem de programação como C#.  <br/> |[Inscrever-se para o PowerApps](/powerapps/maker/signup-for-powerapps) <br/> |[Microsoft Power Apps](https://go.microsoft.com/fwlink/p/?linkid=841462) <br/> |
|**Dynamics 365 para Finanças** <br/> |Obter uma solução completa de gerenciamento de negócios e financeiros para pequenas e médias empresas. O Dynamics 365 para Finanças facilita a ordenação, venda, faturamento e relatórios, começando no primeiro dia.  <br/> |[Microsoft Dynamics 365 para Finanças](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |[Microsoft Dynamics 365 para Finanças](https://go.microsoft.com/fwlink/p/?linkid=841466) <br/> |
|**Microsoft Dynamics 365 for Operations** <br/> |Aumente sua velocidade de fazer negócios. As ferramentas de ERP completas no Dynamics 365 for Operations fornecem escalabilidade global e inteligência digital para ajudá-lo a crescer em seu ritmo.  <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |[Microsoft Dynamics 365 for Operations](https://go.microsoft.com/fwlink/p/?linkid=841467) <br/> |
|**Microsoft AppSource** <br/> |O Microsoft AppSource é um destino para aplicativos de negócios de software como serviço, construídos na plataforma de nuvem da Microsoft. O AppSource apresenta centenas de aplicativos, complementos e pacotes de conteúdo que estendem a funcionalidade dos produtos Microsoft, como o Azure, o Dynamics 365, o Office 365 e o Power BI.  <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |[Microsoft AppSource](https://go.microsoft.com/fwlink/p/?linkid=841474) <br/> |
|**Incentivos do Microsoft Partner** <br/> |A Microsoft Partner Network fornece três tipos de associações. Cada tipo fornece um conjunto de benefícios para ajudar sua empresa a crescer. À medida que você atingir suas metas, participe do programa no nível que atende às suas necessidades exclusivas para acessar mais benefícios e desenvolver seu relacionamento conosco e com outros parceiros na rede.  <br/> |[Incentivos do Microsoft Partner](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |[Incentivos do Microsoft Partner](https://go.microsoft.com/fwlink/p/?linkid=841469) <br/> |
|**Microsoft Business Center** <br/> |O Microsoft Business Center é o portal para clientes que fizeram compras por meio do Contrato de Produtos e Serviços da Microsoft (MPSA). <br/> |[Início Rápido: Registre-se no Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841479) <br/> |[Microsoft Business Center](https://go.microsoft.com/fwlink/p/?linkid=841470) <br/> |
|**Centro de Serviço de Licença de Volume da Microsoft** <br/> |O Centro de Serviço de Licença de Volume da Microsoft exibe licenças adquiridas em contratos Enterprise, Select, Education (Campus ou School), Open Value, Open License e ISV Royalty agreements.  <br/> |[Recursos e treinamento do VLSC](https://www.microsoft.com/en-us/Licensing/existing-customer/vlsc-training-and-resources.aspx) <br/> |[Centro de Serviço de Licença de Volume](https://www.microsoft.com/Licensing/servicecenter/default.aspx) <br/> |
|**Minecraft Education Edition** <br/> |Usando o Minecraft como uma plataforma de aprendizagem, os educadores podem motivar e inspirar cada aluno a alcançar mais e a estimular uma paixão pelo aprendizado. Participe de uma comunidade de educadores aprendendo a usar o Minecraft para desbloquear o potencial do aluno.  <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841480) <br/> |[Minecraft Education Edition](https://go.microsoft.com/fwlink/p/?linkid=841471) <br/> |
|**Microsoft Stream** <br/> |Upload compartilhar vídeos em toda a sua organização para melhorar a comunicação, a participação e o aprendizado.  <br/> |[&amp;Inscrever-se no dia 0 experiência](https://go.microsoft.com/fwlink/p/?linkid=841472) <br/> |[Microsoft Stream](https://go.microsoft.com/fwlink/p/?linkid=841473) <br/> |
|**Power Automate** <br/> |Power Automate é um produto para ajudá-lo a configurar fluxos de trabalho automatizados entre seus aplicativos e serviços favoritos para sincronizar arquivos, receber notificações, coletar dados e muito mais.  <br/> |[Inscreva-se e entre Power Automate](/power-automate/sign-up-sign-in) <br/> |[Power Automate](https://go.microsoft.com/fwlink/p/?linkid=841465) <br/> |
|**Agentes virtuais do Power** <br/> |Power Virtual Agents capacita as equipes a criar facilmente bots poderosos usando uma interface gráfica orientada sem código sem a necessidade de desenvolvedores ou especialistas em dados. Power Virtual Agents aborda muitos dos principais problemas com a criação de bots no setor atualmente. Ele elimina o intervalo entre os especialistas no assunto e as equipes de desenvolvimento que estão criando os bots e a latência longa entre as equipes reconhecendo um problema e atualizando o bot para resolver isso.  <br/> |[Detalhes de licenciamento e acesso](/power-virtual-agents/requirements-licensing) <br/> |[Inscreva-se para Power Virtual Agents](https://aka.ms/TryPVA) <br/> |
|**Azure AD B2B** <br/> |Azure Active Directory colaboração entre empresas (B2B) (Azure AD) permite que você convide Usuários Externos (ou "usuários convidados") para usar seus serviços pagos do Azure AD. Alguns recursos são gratuitos, mas para todos os recursos pagos do Azure AD, você pode convidar até cinco usuários convidados para cada licença da edição do Azure AD que você possui para um funcionário ou um usuário não convidado em seu locatário. <br/> |[Autoatenduro para a assinatura de colaboração do Azure AD B2B](/azure/active-directory/b2b/self-service-portal) <br/> |[Azure Active Directory Diretrizes de licenciamento de colaboração B2B](/azure/active-directory/b2b/licensing-guidance) <br/> |
