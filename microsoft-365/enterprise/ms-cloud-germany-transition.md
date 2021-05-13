---
title: Migração do Microsoft Cloud Deutschland para serviços Office 365 nas novas regiões do datacenter alemão
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Resumo: Entenda a migração dos serviços do Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) para o Office 365 na nova região de datacenter alemã.'
ms.openlocfilehash: ad6c81f04b9e8551ad6eeb6521f7562243df53e9
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346299"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migração do Microsoft Cloud Deutschland para serviços Office 365 nas novas regiões do datacenter alemão

> [!NOTE]
> Este artigo só se aplica a clientes qualificados do Microsoft Cloud Deutschland.

Em agosto de 2018, a Microsoft anuncia nossa intenção de fornecer a nuvem completa da Microsoft – Azure, Office 365, Dynamics 365 e Power Platform – de novas regiões de nuvem na Alemanha para habilitar melhor a transformação digital de nossos clientes. Em agosto de 2019, anunciamos que estamos no processo de abertura das novas regiões de nuvem na Alemanha. Desde então, anunciamos a disponibilidade do Azure, Office 365, Dynamics 365 e Plataforma Power.

As novas regiões foram projetadas para atender às necessidades em evolução dos clientes alemães com maior flexibilidade, os serviços de nuvem inteligentes mais recentes e conectividade total com a nossa rede de nuvem de serviços Microsoft 365, bem como a residência de dados do cliente na Alemanha.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>Como migrar para as novas regiões do datacenter alemão

Os clientes existentes do Microsoft Cloud Deutschland agora podem começar a migrar seus clientes Office 365, o Envolvimento do Cliente do Dynamics 365 e a Plataforma Power. A primeira etapa é [aceitar uma migração orientada pela Microsoft](./ms-cloud-germany-migration-opt-in.md) para as novas regiões de datacenter alemãs. 

Para organizações que optam pela abordagem orientada pela Microsoft, as migrações devem começar no início de 2021 e serão concluídas até 29 de outubro de 2021. Como resultado da migração, os dados principais e assinaturas do cliente serão movidos para as novas regiões alemãs.

Este artigo fornece uma visão geral da abordagem orientada pela Microsoft para a migração, clareza sobre as experiências para usuários e administradores durante e após a migração e ações que podem ser necessárias para clientes com base em quais cargas de trabalho você utiliza.

Os seguintes serviços serão migrados como parte da abordagem orientada pela Microsoft:

- Azure Active Directory (Azure AD)
- Exchange Online
- Proteção do Exchange Online
- SharePoint Online
- OneDrive for Business
- Skype for Business Online\*\*
- Grupos do Office 365
- Dynamics 365 / Power Platform\*\*\*

\*\*Durante a migração do Microsoft Cloud Deutschland para as regiões do datacenter alemão, os clientes Skype for Business Online existentes vão fazer a transição para Microsoft Teams. Para saber mais, confira [Introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here).

\*\*\*Os pré-requisitos e o impacto da migração para esses serviços são descritos no artigo de envolvimento do [cliente do Dynamics 365.](/dynamics365/get-started/migrate-data-german-region)

O Vídeo do Office 365 será desativado em 1 de março de 2021. Se você optar por migrar o locatário do Office 365 para as novas regiões de datacenter alemãs, o Vídeo do Office 365 não terá suporte após a migração do SharePoint Online ser concluída. Para obter mais informações, consulte Linha do tempo [do Microsoft Cloud Deutschland](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="how-is-the-migration-organized"></a>Como a migração é organizada?

Esta figura mostra as dez fases de migração para os novos datacenters alemães.

![As dez fases de migração para os novos datacenters da Alemanha](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

Essas fases começam quando [você opta pela migração](./ms-cloud-germany-migration-opt-in.md). A maioria das fases de migração são executadas como operações de serviço back-end com a interação mínima necessária para o cliente e são executadas uma fase após a outra. O início de tarefas adicionais lideradas pelo cliente e o status de migração geral serão comunicados por meio do centro de mensagens do centro de administração Microsoft 365 durante o processo de migração. Exemplo de tarefas pode incluir atualizações de DNS gerenciadas pelo cliente, reconfiguração da configuração híbrida para clientes Exchange híbridos ou migração do Azure.

A migração não começa imediatamente quando ocorre a aceitação. Sua organização é adicionada à lista de locatários agendados para a migração posterior. Você pode começar as fases de pré-trabalho agora, pois elas são fundamentais para garantir a migração e o uso bem-sucedidos após a conclusão:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)

Uma semana antes do início da migração do locatário, você receberá um aviso no serviço central de mensagens como um aviso final de que todos os pré-requisitos devem estar concluídos.

A migração moverá seu locatário do Azure AD do serviço do Azure AD da Alemanha soberana para a instância de serviços Office 365 do Azure AD na região da UE.

A próxima fase é a migração de assinaturas e licenças de&#39;locatários de produtos específicos da Alemanha para produtos globais.

Depois que todas as etapas são concluídas, incluindo a migração do cliente do Azure, seu locatário é finalizado no serviço de serviços Office 365 e a migração é marcada como concluída. Neste ponto, a atualização final para o Centro de Mensagens é fornecida para você. O locatário agora é uma organização de Office 365 global.

Você é notificado sobre o progresso da migração com postagens do Centro de Mensagens. As postagens ocorrerão em etapas específicas e fornecerão orientações sobre o andamento de uma etapa, bem como informações importantes para os clientes agirem com base nos requisitos do processo. As notificações do centro de mensagens são fornecidas nos seguintes marcos:

- Início da migração (5 dias úteis antes do início da migração do Azure AD)
- Migração do Azure AD concluída
- Assinatura e migração de licença concluída
- SharePoint migração concluída
- Exchange migração concluída
- Skype for Business concluído
- Dynamics concluído
- Power BI concluído
- A recorte final dos serviços está concluída

Após a redução final do Azure AD para o serviço mundial, espera-se que todos os clientes e aplicativos sejam totalmente transitivos para usar os pontos de extremidade corretos. Há uma janela de 30 dias após a reposição final, onde pode ser possível continuar a obter tokens do Azure AD do serviço Microsoft Cloud Deutschland. Quando a janela de 30 dias expirar, clientes e aplicativos não poderão mais acessar os pontos de extremidade do Azure AD do Microsoft Cloud Deutschland. Aplicativos ou acesso ao usuário falharão a partir deste ponto. Você deve garantir que todos os usuários e aplicativos sejam migrados para os pontos de extremidade corretos antes que essa janela de tempo feche. 

## <a name="moving-to-the-new-german-datacenter-regions"></a>Movendo-se para as novas regiões do datacenter alemão

Os clientes existentes do Microsoft Cloud Deutschland agora podem começar a migrar seus Office 365, o Envolvimento do Cliente do Dynamics 365 e os serviços da Plataforma Power. A primeira etapa é [aceitar uma migração orientada pela Microsoft](./ms-cloud-germany-migration-opt-in.md) para as novas regiões de datacenter alemãs.  Ao renovar sua assinatura, você automaticamente opta por uma migração assistida pela Microsoft. A Microsoft notificará os administradores de locatários do cliente com email e no centro de mensagens do Microsoft 365 de administração quando isso acontecer. No entanto, se você preferir iniciar [](./ms-cloud-germany-migration-opt-in.md) o processo agora, poderá optar diretamente Microsoft 365 centro de administração. As migrações devem começar no início de 2021 e serão concluídas até 29 de outubro de 2021. 

Como resultado da migração, os dados principais do cliente e assinaturas são movidos para as novas regiões do datacenter alemão.

> [!NOTE]
> Este artigo inclui diretrizes para a migração de serviços Office 365 somente. Se você estiver executando cargas de trabalho adicionais do Azure no Microsoft Cloud Deutschland, consulte as diretrizes de [migração para o Azure Germany](/azure/germany/germany-migration-main).

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Como se preparar para a migração para os serviços do Office 365 nas novas regiões de datacenter alemãs. 

A primeira etapa é notificar a Microsoft para que nós temos sua permissão para migrar sua assinatura e dados do Microsoft Cloud Deutschland para Office 365 serviços nas novas regiões do datacenter alemão. Consulte o processo [de aceitação para](./ms-cloud-germany-migration-opt-in.md) obter instruções e observe que:

- Todos os clientes migradores precisam verificar a conectividade com as [URLs](urls-and-ip-address-ranges.md)e endereços IP do Office 365 Services Office 365 , que incluem as novas regiões do datacenter alemão. A inação pode resultar em falha no serviço e no cliente.
- Revise a lista de [atividades de pré-trabalho](ms-cloud-germany-transition-add-pre-work.md) para garantir que sua organização esteja informada e preparada para as alterações.
- Você deve revisar Office 365 descrição do serviço de plataforma de Office 365 para entender quais recursos e serviços estarão disponíveis para sua organização após a migração para a região alemã.
- As assinaturas de avaliação não serão migradas e bloquearão a migração de todas as assinaturas pagas. Você deve cancelar qualquer avaliação ou converter em assinaturas pagas antes do início da migração.

## <a name="where-do-i-go-from-here"></a>Para onde eu vou daqui?

Revise a seção Perguntas Frequentes a seguir.

## <a name="frequently-asked-questions"></a>Perguntas Frequentes

### <a name="is-migration-required"></a>A migração é necessária?

A Microsoft Office 365 migração de locatários do Microsoft Cloud Deutschland para Office 365 serviços nas novas regiões do datacenter alemão sem custo adicional. Embora seja recomendável que você opte por migrar para as novas regiões do datacenter alemão, continuaremos fornecendo as atualizações de segurança necessárias para a região do Microsoft Cloud Deutschland.

Office 365 serviços nas novas regiões do datacenter alemão:

- Ofereça preços competitivos no mercado para o [Azure](https://azure.microsoft.com/pricing/calculator/), o [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), o [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) e o [Power BI](https://powerbi.microsoft.com/pricing/).
- Estão conectados à rede global da Microsoft&#39;, oferecendo centenas de sites de borda de rede, locais de paração e pontos de saída para oferecer uma experiência de usuário robusta em qualquer lugar do mundo.
- Ajudando você a atender aos requisitos de residência de dados do cliente local na Alemanha.
- Entregue nossa oferta de nuvem global com recursos completos com as versões mais recentes de nossos serviços e novos recursos, incluindo Microsoft Teams e Multi-Geo no Office 365. Compare produtos por região para o [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), o [Office 365](o365-data-locations.md) e o [Dynamics 365](/dynamics365/get-started/availability).
- Ofereça funcionalidade completa, segurança de nível empresarial e recursos abrangentes para ajudar os clientes a atender às determinações regulamentares e de conformidade.
- Estão acessíveis por meio de contratos de serviços online existentes.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Qual é a disponibilidade do serviço entre as diferentes ofertas de serviços em nuvem do Office 365?
<h2 id="serv-avail"></h2>

Os 15 serviços a seguir estão disponíveis na oferta de serviço de nuvem do Microsoft Cloud Deutschland. Não estamos adicionando novos serviços ao Microsoft Cloud Deutschland.

1. Exchange Online
2. Sistema de Proteção de Dados do Cliente (Exchange Online)
3. Grupos (Grupos modernos)
4. Perfil do Delve
5. Proteção do Exchange Online
6. O que é o Defender para Office 365?
7. Descoberta Eletrônica Avançada
8. Governança de Dados Avançada
9. SharePoint Online
10. Sistema de Proteção de Dados do Cliente (SharePoint Online)
11. OneDrive for Business
12. Skype for Business Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

Atualmente, há 39 serviços disponíveis como parte dos serviços Office 365 nas novas regiões do datacenter alemão. Novos recursos e serviços estarão disponíveis de forma consistente com os serviços globais do Office 365.

1. Exchange Online
2. Customer Lockbox for Exchange Online
3. Grupos do Microsoft 365
4. Perfil do Delve
5. MyAnalytics
6. Workplace Analytics
7. Proteção do Exchange Online
8. O que é o Defender para Office 365?
9. Descoberta Eletrônica Avançada
10. Gerenciamento de Segurança Avançada
11. Proteção de Informações para o Office 365 
12. Governança de Dados Avançada
13. SharePoint Online
14. Customer Lockbox for SharePoint Online
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (migrará para Microsoft Teams durante a migração)
18. Cloud PBX
19. Conferência PSTN
20. Chamada PSTN 
21. Microsoft Teams
22. Relatórios de Administrador / Relatórios de Uso
23. Office na Web
24. Planner
25. Sway
26. Microsoft 365 Apps
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune e Serviço de Gerenciamento de Direitos)
29. Yammer Enterprise
30. Microsoft Forms
31. Power Automate para Office 365
32. Power Virtual Agents para Office 365
33. PowerApps para o Office 365
34. Microsoft Bookings
35. Tarefas pendentes
36. Quadro de comunicações
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. Listas

### <a name="when-will-migration-happen"></a>Quando a migração ocorrerá?

**Azure**

Se você for apenas um cliente do Azure, poderá começar a [migrar](/azure/germany/germany-migration-main) seus recursos do Azure para outra região hoje. 

Se você tiver o Azure com Office 365, Dynamics 365 ou Power BI, deverá seguir o processo de migração para garantir a migração bem-sucedida do AzureAD antes de iniciar a migração auto-direcionada do Azure. Você deve concluir a migração do Azure antes do encerramento do serviço para manter suas cargas de trabalho do Azure com o AzureAD e Office 365 organização.

**Office 365**

[Aceitar](./ms-cloud-germany-migration-opt-in.md) para a migração orientada pela Microsoft hoje. Quando estiver pronto para iniciar sua migração, informaremos você por meio do Centro de Mensagens no Microsoft 365 de administração.

**Dynamics 365 e Power BI**

Opt-in to the Microsoft-driven migration for [Dynamics 365 Customer Engagement](/dynamics365/get-started/migrate-data-german-region) and [Power BI](/power-bi/admin/service-admin-migrate-data-germany) today. Quando estivermos prontos para iniciar a migração, iremos informá-lo através do Centro de mensagens no centro de administração do Microsoft 365.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>O preço mudará para os serviços Office 365 que eu uso?

Sim. Os preços nas regiões de nuvem globais da Microsoft&#39;(incluindo as novas regiões do datacenter) geralmente são mais baixos.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Durante a migração de assinatura, quais SKUs e Licenças serão aplicadas à minha organização e aos usuários?

Durante a migração do Microsoft Cloud Deutschland para os serviços Office 365, os SKUs específicos do serviço da Alemanha são substituídos por versões globais do mesmo SKU ou semelhantes. Para a maioria dos casos, o SKU nos serviços Office 365 é o mesmo, no entanto, há poucas substituições em que o SKU na Alemanha não está mais disponível nos serviços Office 365. Se você deseja atualizar o SKU atribuído à sua organização após a conclusão da migração, contate o vendedor para adicionar ou modificar os serviços atribuídos.

| Microsoft Cloud Deutschland - SKU do produto (DE) | Microsoft Cloud Global - SKU do produto (WW) |
| --- | --- |
| DE de lockbox do \_ cliente (LOCKBOX \_ DE) | Lockbox do cliente (LOCKBOX) |
| Dynamics 365 Edição Enterprise - Banco de Dados adicional Armazenamento \_ DE (CRMSTORAGE \_ DE) | Dynamics 365 Edição Enterprise - Banco de Dados adicional Armazenamento (CRMSTORAGE) |
| Dynamics 365 Edição Enterprise - DE instância adicional de não produção \_ (CRMTESTINSTANCE \_ DE) | Dynamics 365 Edição Enterprise - Instância adicional de não produção (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service Edição Enterprise \_ DE (DYN365 \_ ENTERPRISE CUSTOMER SERVICE \_ \_ \_ DE) | Dynamics 365 for Customer Service Edição Enterprise (DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Edição Enterprise \_ DE (DYN365 \_ ENTERPRISE SALES \_ \_ DE) | Dynamics 365 for Sales Edição Enterprise (DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 para membros da equipe Edição Enterprise \_ DE (DYN365 \_ ENTERPRISE TEAM MEMBERS \_ \_ \_ DE) | Dynamics 365 para membros da equipe Edição Enterprise (MEMBROS DA EQUIPE CORPORATIVA DYN365) \_ \_ \_ |
| Dynamics 365 Plan 1 Edição Enterprise \_ DE (DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Plano 1 Edição Enterprise (DYN365 \_ ENTERPRISE \_ PLAN1) |
| \_Serviços da ECAL (EOA, EOP, DLP) DE (ECAL \_ SERVICES \_ DE) | Serviços da ECAL (EOA, EOP, DLP) (SERVIÇOS \_ ECAL) |
| \_Enterprise Mobility + Security E3 DE (EMS \_ DE) | Enterprise Mobility + Security E3 (EMS) |
| \_Exchange Online (Plano 1) DE (EXCHANGESTANDARD \_ DE) | Exchange Online (Plano 1) (EXCHANGESTANDARD) |
| \_Exchange Online (Plano 2) DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online (Plano 2) (EXCHANGEENTERPRISE) |
| \_Arquivamento do Exchange Online para Exchange Online DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Arquivamento do Exchange Online para Exchange Online (ADDON EXCHANGEARCHIVE) \_ |
| \_Arquivamento do Exchange Online para Exchange Server DE (EXCHANGEARCHIVE \_ DE) | Arquivamento do Exchange Online para Exchange Server (EXCHANGEARCHIVE) |
| \_Exchange Online Essentials DE (EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials (EXCHANGE \_ S \_ ESSENTIALS) |
| \_Exchange Online Kiosk DE (EXCHANGEDESKLESS \_ DE) | Exchange Online Kiosk (EXCHANGEDESKLESS) |
| \_Proteção do Exchange Online DE (EOP \_ ENTERPRISE \_ DE) | Proteção do Exchange Online (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Online Instância \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online Instância (CRMINSTANCE) |
| Office 365 A1 professores \_ DE (STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1 para professores (STANDARDWOFFPACK \_ FACULTY) |
| Office 365 A1 para alunos \_ DE (STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1 para alunos (ALUNO \_ STANDARDWOFFPACK) |
| \_Conformidade Avançada do Office 365 DE (EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 Compliance (CONFORMIDADE \_ COM A PROTEÇÃO DE \_ INFORMAÇÕES) |
|Microsoft Defender para Office 365 (Plano 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender para Office 365 (Plano 1) (ATP \_ ENTERPRISE) |
| \_Office 365 Business Essentials DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic (O365 \_ BUSINESS \_ ESSENTIALS) |
| \_Office 365 Business Premium DE (O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard (O365 \_ BUSINESS \_ PREMIUM) |
| \_Office 365 Business DE (O365 \_ BUSINESS \_ DE) | Microsoft 365 Apps para Pequenos e Médios negócios (O365 \_ BUSINESS) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 sem ProPlus \_ DE (ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 sem ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ DE) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE (ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| \_Office 365 com Espaço de Armazenamento Adicional DE (SHAREPOINTSTORAGE \_ DE) | Office 365 com Espaço de Armazenamento Adicional (SHAREPOINTSTORAGE) |
| \_Office 365 F1 DE (DESKLESSPACK \_ DE) | Office 365 F1 (DESKLESSPACK) |
| Office 365 ProPlus para Docente \_ DE (OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus para Professores (CORPO DOCENTE DO OFFICESUBSCRIPTION) \_ |
| Office 365 ProPlus para Alunos \_ DE (DE DO ALUNO DO OFFICESUBSCRIPTION) \_ \_ | Office 365 ProPlus para alunos (ESTUDANTE DO \_ OFFICESUBSCRIPTION) |
| \_Office 365 ProPlus DE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| \_OneDrive for Business (Plano 1) DE (WACONEDRIVESTANDARD \_ DE) | OneDrive for Business (Plano 1) (WACONEDRIVESTANDARD) |
| \_OneDrive for Business (Plano 2) DE (WACONEDRIVEENTERPRISE \_ DE) | OneDrive for Business (Plano 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro para professores \_ DE (POWER \_ BI \_ PRO \_ FACULTY \_ DE) | Power BI Pro para professores (POWER \_ BI \_ PRO \_ FACULTY) |
| \_Power BI Pro DE (POWER \_ BI \_ PRO \_ DE) | Power BI Pro (POWER \_ BI \_ PRO) |
| Project Online Essentials \_ DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium DE \_ (PROJECTPREMIUM \_ DE) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ DE (PROJECTPROFESSIONAL \_ DE) | Project Online Professional (PROJECTPROFESSIONAL) |
| \_Project Plano 3 DE (PROJECTPROFESSIONAL \_ DE) | Project Plano 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| \_SharePoint Online (Plano 1) DE (SHAREPOINTSTANDARD \_ DE) | SharePoint Online (Plano 1) (SHAREPOINTSTANDARD) |
| \_SharePoint Online (Plano 2) DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online (Plano 2) (SHAREPOINTENTERPRISE) |
| Skype for Business Online (Plano 1) \_ DE (MCOIMP \_ DE) | Office 365 E1 (STANDARDPACK) |
| Skype for Business Online (Plano 1) \_ DE (MCOIMP \_ DE) | Skype for Business Online (Plano 1) (MCOIMP) |
| Skype for Business Online (Plano 2) \_ DE (MCOSTANDARD \_ DE) | Skype for Business Online (Plano 2) (MCOSTANDARD) |
| Skype for Business Mais CAL \_ DE (MCOPLUSCAL \_ DE) | Skype for Business Mais CAL (MCOPLUSCAL) |
| Visio Plano Online 1 para professores \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio Plano Online 1 para professores (VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Plano Online 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Plano Online 1 (VISIOONLINE \_ PLAN1) |
| Visio Plano Online 2 para professores \_ DE (VISIOCLIENT \_ FACULTY \_ DE) | Visio Plano Online 2 para professores (PROFESSORES VISIOCLIENT) \_ |
| Visio Plano Online 2 \_ DE (VISIOCLIENT \_ DE) | Visio Plano Online 2 (VISIOCLIENT) |
| \_Visio Plano 1 DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Plano 1 (VISIOONLINE \_ PLAN1) |
| \_Visio Plano 2 DE (VISIOCLIENT \_ DE) | Visio Plano 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Como posso obter ajuda da Microsoft para migrar para uma nova região ou para responder a perguntas de suporte?

Se você tiver dúvidas, entre em contato conosco ou com seu parceiro:

- Para o Azure, você pode enviar [novas solicitações de suporte](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) no portal do Azure.
- Para Office 365, você pode enviar perguntas usando o link Precisar de Ajuda? do centro de administração &quot; &quot; [Microsoft 365.](https://portal.office.de/)
- Se você for cliente do Dynamics 365 Customer Engagement e Power BI e também tiver Office 365, poderá enviar perguntas usando o link Precisa de Ajuda? do centro de administração Microsoft 365 &quot; &quot; . [](https://portal.office.de/) As opções de suporte do Dynamics 365 Customer Engagement estão localizadas [aqui](/dynamics365/get-started/support/). As opções de suporte do Power BI estão localizadas [aqui](https://powerbi.microsoft.com/support/).

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>Meu cliente já tem um locatário M365 na nuvem global da Microsoft, além de um locatário do Microsoft Cloud Deutschland. Esses dois locatários podem ser mesclados em um como parte da migração?

Não, não há nenhum recurso de mesclagem de locatários. Os locatários permanecerão separados e exclusivos, pois cada locatário tem seu próprio namespace e ID exclusivo. A Microsoft migrará um locatário do Microsoft Cloud Deutschland para a nuvem global, se desejar, ou então o cliente poderá cancelá-la e abandoná-la.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>Quais ações devem ser feitas pela maioria dos usuários finais como parte da migração?
A migração foi projetada para ter impacto mínimo para usuários/clientes finais.
- Verifique se Office aplicativos estão executando versões disponíveis mais recentes. 
- Os clientes Skype for Business fazer a transição para Teams como parte da migração e podem precisar [baixar](/deployoffice/teams-install) e instalar Teams em dispositivos.
- Os usuários finais podem precisar fazer logoff dos aplicativos Office e fazer logoff de volta depois que a migração for concluída. 
- Os clientes que executam o cliente OneDrive Sync precisam sair de sua estação de trabalho e fazer logoff novamente para permitir que OneDrive cliente Sync faça logoff no serviço de Azure Active Directory global.
- Esteja ciente das novas URLs globais depois que a migração for concluída, notadamente Outlook Web Access (exemplo: use outlook.office365.com). SharePoint Os clientes online continuarão a se conectar com êxito ao namespace MCD usando a URL existente (exemplo: contoso.sharepoint.de).


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>Quais clientes são afetados pela Azure Active Directory migração? 

Todos os clientes do Office365 dependem da Azure Active Directory autenticar e armazenar componentes de serviço críticos necessários para a operação de serviços hospedados pela Microsoft. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Quais são os impactos da migração Azure Active Directory migração?

A migração inicial de Azure Active Directory na fase inicial não afeta a experiência do cliente. Após o estágio final de migração, todos os serviços para o locatário do cliente estão totalmente no serviço global. Após esse estágio final, o serviço Azure Active Directory no Microsoft Cloud Deutschland pode não aceitar mais solicitações de autorização ou fornecer tokens de acesso para Office serviços.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>O que significa garantir a conectividade de rede com [urls Office 365 serviços e endereços IP?](./urls-and-ip-address-ranges.md)

Este artigo descreve as URLs e endereços IP necessários para a função adequada do serviço global para garantir uma boa experiência do cliente. Em casos relativamente raros, alguns clientes tentam configurar a segurança de perímetro de rede de forma a minimizar os fluxos de tráfego e restringir o acesso aos serviços para aqueles apenas como parte dos intervalos IP do serviço Microsoft Cloud Deutschland.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>Como faço para gerenciar as alterações dns para Exchange Online para que o email continue a fluir?

Os intervalos de IP gerenciados pela Microsoft e zonas DNS são transições durante e como parte da migração para o serviço global. 

Zonas DNS gerenciadas pelo cliente, como registros MX de domínio personalizado, são de responsabilidade do cliente, no entanto, simplificar essa migração que o registro MX gerenciado do cliente aponta para um ponto de extremidade de serviço do Office 365 na zona office.de e a Microsoft gerencia a migração desse ponto de extremidade de serviço automaticamente.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>Como faço para gerenciar as alterações dns para Skype for Business? 
 
Todos os Skype clientes para Empresas entrarão em transição para Microsoft Teams. A transição das zonas Skype DNS do cliente não é necessária na migração para Teams. Os clientes poderão entrar no Teams imediatamente com todas as funcionalidades após a migração.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>O Outlook para iOS e Android funcionará após a migração? 

Sim. A recomendação da Microsoft é que todos os clientes executem as versões mais recentes disponíveis de clientes Office, incluindo Outlook para clientes iOS e Android. Após a conclusão da migração para o serviço global Office 365, todos os clientes Office precisarão fazer logoff e fazer logoff novamente para obter um novo token de Azure Active Directory de acesso do serviço global. 



## <a name="next-step"></a>Próxima etapa

[Consentimento para migração](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Mais informações

Como começar:

- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Movendo-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Informações do programa de migração do Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here)
