---
title: Segurança ampliada do Office 365 para seu ambiente de teste do Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use este guia de laboratório de teste para habilitar configurações de segurança adicionais do Office 365 seu ambiente de teste do Microsoft 365 Enterprise.
ms.openlocfilehash: 18e7b682d20c2212ae73783d668250d28b04075f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864946"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a>Segurança ampliada do Office 365 para seu ambiente de teste do Microsoft 365 Enterprise

Com as instruções deste artigo, você deve configurar as configurações adicionais do Office 365 para aumentar a segurança em seu ambiente de teste do Microsoft 365 Enterprise.

![Guias de Laboratório de Teste do Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Clique [aqui](https://aka.ms/m365etlgstack) para ver um mapa visual de todos os artigos da pilha do Guia de Laboratório de Teste do Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Criar o seu ambiente de teste do Microsoft 365 Enterprise

Se você deseja configurar maior segurança do Office 365 de forma leve com os requisitos mínimos, siga as instruções na [configuração base leve](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se você deseja configurar maior segurança do Office 365 em uma empresa simulada, siga as instruções na [autenticação de passagem](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testar maior segurança do Office 365 não requer que o ambiente de teste de simulado empresarial, que inclui uma intranet simulada conectada à Internet e a sincronização de diretório para uma floresta do Windows Server AD. Ele é fornecido aqui como uma opção para que você possa testar automatizada de licenciamento e a associação ao grupo e experimentar em um ambiente que representa uma organização típica. 


## <a name="phase-2-configure-increased-office-365-security"></a>Fase 2: Configurar maior segurança do Office 365

Nesta fase, você pode habilitar maior segurança do Office 365 para seu ambiente de teste do Microsoft 365 Enterprise. Para obter detalhes adicionais e configurações, consulte [Configure seu locatário do Office 365 para aumentar a segurança](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>Configurar o SharePoint Online para bloquear os aplicativos que não há suporte para autenticação moderna

Aplicativos que não têm suporte para autenticação moderna não podem ter a [identidade e dispositivo acessam as configurações](microsoft-365-policies-configurations.md) aplicadas a eles, que é um elemento importante de proteger sua assinatura do Microsoft 365 e seus ativos digitais. 

1. Vá para o portal do Office 365 ([https://portal.office.com](https://portal.office.com)) e se conectar à sua assinatura de avaliação do Office 365 com sua conta de administrador global.
    
  - Se você estiver usando o ambiente de teste do Microsoft 365 leve, entre do computador local.
    
  - Se você estiver usando o ambiente de teste do enterprise simulado 365 da Microsoft, use o [portal Azure](https://portal.azure.com) para conectar a máquina virtual CLIENT1 e entrar em CLIENT1.
 
2. A partir da guia do **Centro de administração do Microsoft 365** , clique em **Admin**.
3. Na guia do **Centro de administração do Microsoft 365** nova, clique em **centrais de Admin > SharePoint**.
4. Na guia nova **Centro de administração do SharePoint** , clique em **controle de acesso**.
5. Em **aplicativos que não há suporte para autenticação moderna**, clique em **bloco > Okey**.


### <a name="enable-advanced-threat-protection-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Habilitar o Advanced proteção contra ameaças (ATP) para SharePoint, OneDrive e equipes da Microsoft

O Office 365 avançadas ameaça proteção (ATP) é um recurso do Exchange Online Protection (EOP) que ajuda a manter o malware fora do seu email. Com ATP, criar políticas no Centro de administração do Exchange (EAC) ou a segurança & Centro de conformidade que ajudam a garantir a seus usuários acessar apenas links ou anexos em emails que são identificadas como não mal-intencionado. Para obter mais informações, consulte [proteção contra ameaças avançadas para anexos seguros e links de seguros](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).

1. Na guia **Centro de administração do Microsoft 365** do navegador, clique em **centrais de Admin > segurança e conformidade**.
2. Na guia **segurança e conformidade** nova, clique em **gerenciamento de ameaças > política**.
3. Clique em **anexos de ATP seguros**.
4. No painel **anexos seguros** , selecione **Ativar ATP para SharePoint, OneDrive e as equipes da Microsoft**e clique em **Salvar**.

### <a name="enable-anti-malware"></a>Habilitar antimalware

Malware é composto de vírus e spyware. Os vírus infectar outros programas e dados e eles espalham em todo o seu computador procurando programas infectar. Spyware se refere ao malware que coletam suas informações pessoais, como informações de entrada e de dados pessoais e enviá-la de volta para o autor de malware. 

O Office 365 tem recursos que ajudam a proteger mensagens de entrada e saídas de software mal-intencionado e ajudam a proteger contra spam de filtragem de spam e malware interno. Para obter mais informações, consulte [proteção antispam e antimalware no Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)

Para garantir que o processamento de antimalware estiver sendo executado no arquivos com tipos de arquivo de anexo comuns:

1. Clique no botão Voltar no navegador para voltar à página de **política** .
2. Clique em **Anti-malware**.
3. Clique duas vezes a política de chamada **padrão**.
4. Na janela **política antimalware** , clique em **configurações**.
4. Em **tipos de anexo comuns de filtro**, clique em **em > Salvar**.


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a>Fase 3: Examinar os logs e ferramentas de segurança do Office 365

Nesta fase, você observar serviços internos que informam sobre eventos de segurança e medem sua postura geral de segurança.

### <a name="threat-management-dashboard"></a>Painel de gerenciamento de ameaça

Gerenciamento de ameaça do Office 365 pode ajudá-lo a controlar e gerenciar o acesso de dispositivo móvel aos dados da sua organização, ajudar a proteger sua organização contra perda de dados e ajudar a proteger mensagens de entrada e saídas contra spam e softwares mal-intencionados. Você também pode usar threat management para proteger a reputação do seu domínio e para determinar se ou não os remetentes são falsificação de modo mal-intencionado contas do seu domínio. Para obter mais informações, consulte [gerenciamento de ameaça na segurança do Office 365 & Centro de conformidade](https://docs.microsoft.com/office365/securitycompliance/threat-management).

Use estas etapas para exibir o painel de gerenciamento do Office 365 ameaça:

1. Na guia **Centro de administração do Microsoft 365** do navegador, clique em **centrais de Admin > segurança e conformidade**.
2. Na guia **segurança e conformidade** nova, clique em **gerenciamento de ameaças > Painel**.
3. Na guia nova **painel** no seu navegador, observe as tendências de malware, ideias e outras seções do painel de controle.

### <a name="office-365-cloud-app-security-dashboard"></a>Painel de segurança de aplicativo de nuvem do Office 365

Segurança de aplicativo do Office 365 nuvem, anteriormente conhecido como o Office 365 gerenciamento avançado de segurança, permite que você crie diretivas que monitoram e informam atividades suspeitas em sua assinatura do Office 365, para que você possa investigar e levar possíveis ação de remediação. Para obter mais informações, consulte [Visão geral do Office 365 App segurança na nuvem](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

1. Na guia **Centro de administração do Microsoft 365** do navegador, clique em **centrais de Admin > segurança e conformidade**.
2. Na guia **segurança e conformidade** nova, clique em **alertas > Gerenciar alertas de Avançado > Ir para segurança de aplicativo de nuvem do Office 365**.
3. Na guia **Segurança de aplicativo de nuvem** nova, observe o modo de exibição do painel e a lista de políticas padrão que monitorar para várias atividades em sua assinatura do Office 365.
4. Clique no ícone de painel para ver um resumo das atividades de segurança de aplicativo de nuvem que estão sendo rastreadas.
5. Clique em **investigar** (o ícone de óculos) e, em seguida, **o log de atividade** para ver a lista de entradas recentes e outras atividades.

### <a name="secure-score"></a>Pontuação de segura

1. Criar uma nova guia no seu navegador e vá para **securescore.office.com**.
2. Na **Guia do painel**, observe sua pontuação de seguro atual e a lista de ações na fila para aumentar a pontuação.

Consulte a etapa [Configure maior segurança para o Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) na fase de **proteção de informações** para obter informações e links para definir essas configurações em produção.

## <a name="next-step"></a>Próxima etapa

Explore recursos adicionais de [proteção de informações](m365-enterprise-test-lab-guides.md#information-protection) e recursos no seu ambiente de teste.

## <a name="see-also"></a>Confira também

[Guias do Laboratório de Teste do Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implantar o Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentação do Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

