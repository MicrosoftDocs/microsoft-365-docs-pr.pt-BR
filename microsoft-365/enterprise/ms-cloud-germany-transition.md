---
title: Migração do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
ms.openlocfilehash: 16e57eff5556d31d2d13ab6ce0d284719d63c44c
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688636"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migração do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão

> [!NOTE]
> Este artigo aplica-se apenas aos clientes do Microsoft Cloud Alemanha qualificados.

Em agosto de 2018, a Microsoft anunciou nossa intenção de fornecer a implantação completa da Microsoft Cloud – Azure, Office 365, Dynamics 365 e Power Platform – a partir de novas regiões de nuvem na Alemanha para permitir melhor a transformação digital de nossos clientes. Em agosto de 2019, anunciamos que estamos no processo de abertura das novas regiões de nuvem na Alemanha. Já anunciamos a disponibilidade do Azure, Office 365, Dynamics 365 e a plataforma de energia.

As novas regiões são projetadas para atender às necessidades em evolução dos clientes de alemão com maior flexibilidade, dos serviços de nuvem inteligente mais recentes e conectividade completa com a nossa rede de nuvem de serviços da Microsoft 365, bem como residências de dados do cliente na Alemanha.

## <a name="how-to-migrate-to-the-new-german-regions"></a>Como migrar para as novas regiões do alemão

Os clientes do Microsoft Cloud Alemanha existentes agora podem começar a migrar seus clientes do Office 365, Dynamics 365 e do cliente da plataforma de energia. A primeira etapa é [aceitar uma migração orientada pela Microsoft](https://aka.ms/office365germanymoveoptin) para as novas regiões de datacenter alemãs. 

Para organizações que optam pela abordagem orientada pela Microsoft, as migrações devem começar no início de 2021 e serão concluídas em 29 de outubro de 2021. Como resultado da migração, os dados principais e assinaturas do cliente serão movidos para as novas regiões alemãs.

Este artigo fornece uma visão geral da abordagem orientada pela Microsoft para a migração, clareza sobre as experiências para usuários e administradores durante e após a migração, e ações que podem ser necessárias para clientes com base nas cargas de trabalho que você utiliza.

Os seguintes serviços serão migrados como parte da abordagem orientada pela Microsoft:

- Azure Active Directory (Azure AD)
- Exchange Online
- Proteção do Exchange Online
- SharePoint Online
- OneDrive for Business

- Skype for Business Online\*\*
- Grupos do Office 365
- Dynamics 365/Power Platform\*\*\*

\*\*Durante a migração do Microsoft Cloud Alemanha para as regiões do datacenter alemão, os clientes existentes do Skype for Business online farão a transição para o Microsoft Teams. Para saber mais, confira [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home).

\*\*\*Os pré-requisitos e o impacto da migração desses serviços são descritos no artigo do [contrato do cliente do Dynamics 365](https://aka.ms/d365ceoptin) .

O Vídeo do Office 365 será desativado em 1 de março de 2021. Se você optar por migrar o locatário do Office 365 para as novas regiões de datacenter alemãs, o Vídeo do Office 365 não terá suporte após a migração do SharePoint Online ser concluída. Para obter mais informações, consulte [Microsoft Cloud Alemanha Timeline](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="how-is-the-migration-organized"></a>Como a migração é organizada?

Esta figura representa os vários componentes do Office 365 e do Dynamics 365 na migração para os novos datacenters alemão.

![Componentes do Office 365 e Dynamics 365 na migração para os novos datacenters da Alemanha](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

A migração é executada em fases que começam quando você [opta por migração](https://aka.ms/office365germanymoveoptin). A maioria das fases de migração é executada como operações de serviço de back-end com interação mínima do cliente e é executada uma fase após a outra. O início para tarefas adicionais e o status de migração geral do cliente serão comunicados no centro de mensagens do centro de administração do Microsoft 365 durante o processo de migração. Exemplo de tarefas podem incluir atualizações DNS gerenciadas pelo cliente, reconfiguração da configuração híbrida para clientes híbridos do Exchange ou migração do Azure.

A migração não é iniciada imediatamente quando o consentimento ocorre. Sua organização é adicionada à lista de locatários agendados para migração posterior. Você pode começar as fases de trabalho agora que são fundamentais para garantir a migração e o uso bem-sucedido após a conclusão:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)

Uma semana antes do início da migração do locatário, você receberá um aviso no serviço do centro de mensagens como um aviso final de que todos os pré-requisitos devem ser concluídos.

A migração passará do locatário do Azure AD do soberana da Alemanha do Azure ad para a instância dos serviços do Office 365 do Azure AD na região da UE.

A próxima fase é a migração de suas assinaturas de locatário&#39;s e licenças de usuário dos produtos específicos da Alemanha.

Após a conclusão de todas as etapas, incluindo a migração de cliente do Azure, seu locatário é finalizado no serviço serviços do Office 365 e a migração é marcada como concluída. Neste ponto, a atualização final da central de mensagens é fornecida para você. O locatário agora não é uma organização totalmente global do Office 365.

Você é notificado do progresso da migração com as postagens do centro de mensagens. As postagens ocorrerão em etapas específicas e fornecerão orientações sobre o andamento de uma etapa, bem como informações importantes para os clientes agirem com base nos requisitos de processo. As notificações do centro de mensagens são fornecidas nas seguintes etapas:

- Início da migração (5 dias úteis antes do início da migração do Azure Active Directory)
- Migração do Azure AD concluída
- Migração de assinatura e licença concluída
- Migração do SharePoint concluída
- Migração do Exchange concluída
- Skype for Business concluído
- Dynamics concluída
- Power BI concluído
- Término da transferência final de serviços

## <a name="moving-to-the-new-german-regions"></a>Migrar para as novas regiões alemãs

Os clientes do Microsoft Cloud Alemanha (Microsoft Cloud Alemanha) já podem começar a migrar seus clientes do Office 365, Dynamics 365 e da plataforma de energia. A primeira etapa é [aceitar uma migração orientada pela Microsoft](https://aka.ms/office365germanymoveoptin) para as novas regiões de datacenter alemãs.  Ao renovar sua assinatura, você aceita automaticamente uma migração assistida pela Microsoft. A Microsoft notificará os administradores de locatários do cliente com o email e o centro de mensagens do centro de administração do Microsoft 365, quando isso acontecer. No entanto, se você preferir iniciar o processo agora, você pode [optar](https://aka.ms/office365germanymoveoptin) diretamente no centro de administração do Microsoft 365 hoje. Espera-se que as migrações comecem no início de 2021 e sejam concluídas em 29 de outubro de 2021. 

Como resultado da migração, os dados principais e assinaturas do cliente serão movidos para as novas regiões alemãs.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Como se preparar para a migração para os serviços do Office 365 nas novas regiões de datacenter alemãs. 

A primeira etapa é notificar a Microsoft para que temos sua permissão para migrar sua assinatura e seus dados do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão. Consulte o processo de [consentimento](https://aka.ms/office365germanymoveoptin) para obter instruções e observe que:

- Todos os clientes de migração precisam verificar a conectividade com as [URLs e os endereços IP](urls-and-ip-address-ranges.md)do Office 365 Services do Office 365, que incluem as novas regiões do datacenter alemão. Inaction pode resultar em falha de serviço e cliente.
- Revise a lista de atividades de [pré-trabalho](ms-cloud-germany-transition-add-pre-work.md) para garantir que sua organização seja informada e preparada para as alterações.
- Você deve consultar a descrição do serviço da plataforma do Office 365 para entender quais recursos e serviços estarão disponíveis para sua organização seguindo a migração para a região do alemão.
- As assinaturas de avaliação não serão migradas e bloquearão a migração de todas as assinaturas pagas. Você deve cancelar qualquer avaliação ou converter para assinaturas pagas antes do início da migração.

## <a name="where-do-i-go-from-here"></a>De onde eu passo aqui?

Examine a seção perguntas frequentes a seguir.

## <a name="frequently-asked-questions"></a>Perguntas Frequentes

### <a name="is-migration-required"></a>A migração é necessária?

A Microsoft oferece a migração de locatário do Office 365 do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão sem custo adicional. Embora seja altamente recomendável que você opte por migrar para as novas regiões do datacenter alemão, continuaremos a fornecer as atualizações de segurança necessárias para a região do Microsoft Cloud Alemanha.

Serviços do Office 365 nas novas regiões do datacenter alemão:

- Ofereça preços competitivos no mercado para o [Azure](https://azure.microsoft.com/pricing/calculator/), o [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), o [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) e o [Power BI](https://powerbi.microsoft.com/pricing/).
- Estão conectados à rede global do Microsoft&#39;s, oferecendo centenas de sites de borda de rede, locais de emparelhamento e pontos de egresso para fornecer uma experiência de usuário robusta em qualquer lugar do mundo.
- Ajudando você a atender aos requisitos de residência de dados do cliente local na Alemanha.
- Forneça nossa oferta completa de nuvem global com as versões mais recentes dos nossos serviços e novos recursos, incluindo o Microsoft Teams e o multigeográfico no Office 365. Compare produtos por região para o [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), o [Office 365](o365-data-locations.md) e o [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Ofereça funcionalidade completa, segurança de nível empresarial e recursos abrangentes para ajudar os clientes a atender às determinações regulamentares e de conformidade.
- Estão acessíveis por meio de contratos de serviços online existentes.

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Qual é a disponibilidade do serviço entre as diferentes ofertas de serviços em nuvem do Office 365?
<h2 id="serv-avail"></h2>

Os 15 serviços a seguir estão disponíveis na oferta de serviço de nuvem do Microsoft Cloud Alemanha. Não estamos adicionando novos serviços ao Microsoft Cloud Alemanha.

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

Atualmente, há 29 serviços disponíveis como parte dos serviços do Office 365 nas novas regiões de datacenter alemãs. Novos recursos e serviços estarão disponíveis de forma consistente com os serviços globais do Office 365.

1. Exchange Online
2. Lockbox de cliente para o Exchange Online
3. Grupos do Microsoft 365
4. Perfil do Delve
5. MyAnalytics
6. Workplace Analytics
7. Proteção do Exchange Online
8. O que é o Defender para Office 365?
9. Descoberta Eletrônica Avançada
10. Gerenciamento de Segurança Avançada
11. Gerenciamento de Direitos de Informação
12. Governança de Dados Avançada
13. SharePoint Online
14. Lockbox de cliente para o SharePoint Online
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (migrará para o Microsoft Teams durante a migração)
18. Cloud PBX
19. Conferência PSTN
20. Chamada PSTN 
21. Microsoft Teams
22. Relatórios de Administrador / Relatórios de Uso
23. Word Online, Excel Online, PowerPoint, OneNote e Visio Online
24. Planner
25. Sway
26. Aplicativos do Microsoft 365
27. Outlook Mobile
28. Enterprise Mobility + Security (EMS) E3 (Azure AD Premium P1, Intune e serviço de gerenciamento de direitos)
29. Yammer Online

### <a name="when-will-migration-happen"></a>Quando a migração ocorrerá?

**Azure**

Se você for um cliente do Azure apenas, poderá começar a [migrar](https://docs.microsoft.com/azure/germany/germany-migration-main) seus recursos do Azure para outra região hoje. 

Se você tiver o Azure com o Office 365, o Dynamics 365 ou o Power BI, deverá seguir o processo de migração para garantir o êxito da migração do AzureAD antes de iniciar a migração autodirigida do Azure. Você deve concluir a migração do Azure antes do encerramento do serviço a fim de manter suas cargas de trabalho do Azure com seu AzureAD e a organização do Office 365.

**Office 365**

[Aceitar](https://aka.ms/office365germanymoveoptin) para a migração orientada pela Microsoft hoje. Quando estivermos pronto para iniciar sua migração, vamos informá-lo no centro de mensagens no centro de administração do Microsoft 365.

**Dynamics 365 e Power BI**

Aceitar a migração orientada pela Microsoft para o [cliente do Dynamics 365](https://aka.ms/D365ceOptIn) e o [Power bi](https://aka.ms/PBIOptIn) atualmente. Quando estivermos prontos para iniciar a migração, iremos informá-lo através do Centro de mensagens no centro de administração do Microsoft 365.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>O preço será alterado para os serviços do Office 365 que eu uso?

Sim. O preço nas regiões de nuvem global do Microsoft&#39;s (incluindo as novas regiões de Datacenter) geralmente é menor.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>Durante a migração da assinatura, quais SKUs e licenças serão aplicadas à minha organização e aos usuários?

Durante a migração do Microsoft Cloud Alemanha para os serviços do Office 365, os SKUs específicos do serviço da Alemanha são substituídos por versões globais do mesmo SKU ou semelhante. Para a maioria dos casos, a SKU nos serviços do Office 365 é a mesma no entanto, há poucas substituições em que a SKU na Alemanha não está mais disponível nos serviços do Office 365. Se você quiser atualizar a SKU atribuída à sua organização após a conclusão da migração, entre em contato com seu vendedor para adicionar ou modificar os serviços atribuídos.

| Microsoft Cloud Alemanha-SKU do produto (DE) | Microsoft Cloud global-SKU do produto (WW) |
| --- | --- |
| Lockbox \_ de cliente (Lockbox \_ de) | Lockbox de cliente (LOCKBOX) |
| Dynamics 365 Enterprise Edition-armazenamento de banco \_ de dados adicional (CRMSTORAGE \_ de) | Dynamics 365 Enterprise Edition-armazenamento de banco de dados adicional (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition – instância de não produção adicional \_ de (CRMTESTINSTANCE \_ de) | Dynamics 365 Enterprise Edition – instância de não produção adicional (CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service for Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Customer \_ Service \_ ) | Dynamics 365 for Customer Service Enterprise Edition (DYN365 \_ Enterprise \_ Customer \_ Service) |
| Dynamics 365 para sales Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Sales \_ de) | Dynamics 365 para sales Enterprise Edition (DYN365 \_ Enterprise \_ Sales) |
| Dynamics 365 para membros da equipe Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Team Teams \_ \_ de) | Dynamics 365 para membros da equipe Enterprise Edition ( \_ membros da equipe corporativa do DYN365 \_ \_ ) |
| Dynamics 365 plano 1 Enterprise Edition \_ de (DYN365 \_ Enterprise \_ Plan1 \_ de) | Dynamics 365 plano 1 Enterprise Edition (DYN365 \_ Enterprise \_ Plan1) |
| ECAL Services (EOA, EOP, DLP) \_ de (ECAL \_ Services \_ de) | ECAL Services (EOA, EOP, DLP) (serviços do ECAL \_ ) |
| Enterprise Mobility + Security E3 \_ de (EMS \_ de) | Enterprise Mobility + Security E3 (EMS) |
| Exchange Online (plano 1) \_ de (EXCHANGESTANDARD \_ de) | Exchange Online (plano 1) (EXCHANGESTANDARD) |
| Exchange Online (plano 2) \_ de (EXCHANGEENTERPRISE \_ de) | Exchange Online (plano 2) (EXCHANGEENTERPRISE) |
| Arquivamento do Exchange Online para Exchange Online \_ de (EXCHANGEARCHIVE \_ addon \_ de) | Arquivamento do Exchange Online para o Exchange Online (EXCHANGEARCHIVE \_ addon) |
| Arquivamento do Exchange Online para o Exchange Server \_ de (EXCHANGEARCHIVE \_ de) | Arquivamento do Exchange Online para Exchange Server (EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ de (Exchange \_ S \_ Essentials \_ de) | Exchange Online Essentials (EXCHANGE \_ S \_ Essentials) |
| Exchange Online quiosque \_ de (EXCHANGEDESKLESS \_ de) | Quiosque do Exchange Online (EXCHANGEDESKLESS) |
| Proteção do Exchange Online \_ de (EOP \_ Enterprise \_ de) | Proteção do Exchange Online (EOP \_ Enterprise) |
| Microsoft 365 Business Standard (O365 \_ Business \_ Premium) | Microsoft 365 Business Standard (O365 \_ Business \_ Premium) |
| Instância \_ de (CRMINSTANCE de) do Microsoft Dynamics CRM \_ | Instância do Microsoft Dynamics CRM Online (CRMINSTANCE) |
| Office 365 a1 para docentes \_ (STANDARDWOFFPACK \_ professores \_ de) | Office 365 a1 para docentes ( \_ docentes STANDARDWOFFPACK) |
| Office 365 a1 para estudantes \_ de (STANDARDWOFFPACK \_ \_ de aluno) | Office 365 a1 para estudantes (STANDARDWOFFPACK \_ Student) |
| Office 365 Advanced Compliance \_ de (EQUIVIO \_ Analytics \_ de) | Conformidade com a Microsoft 365 E5 (conformidade com proteção de informações \_ \_ ) |
|Microsoft defender para Office 365 (plano 1) \_ de (ATP \_ Enterprise \_ de) |Microsoft defender para Office 365 (plano 1) ( \_ empresa ATP) |
| Office 365 Business Essentials \_ de (O365 \_ Business \_ Essentials \_ de) | Microsoft 365 Business Basic (O365 \_ Business \_ Essentials) |
| Office 365 Business Premium \_ de (O365 \_ Business \_ Premium \_ de) | Microsoft 365 Business Standard (O365 \_ Business \_ Premium) |
| Office 365 Business \_ de (O365 \_ Business \_ de) | Microsoft 365 Apps for Business (O365 \_ Business) |
| Office 365 E1 \_ de (STANDARDPACK \_ de) | Office 365 E1 (STANDARDPACK) |
| Office 365 E3 sem ProPlus \_ de (ENTERPRISEPACKWITHOUTPROPLUS \_ de) | Office 365 E3 sem ProPlus (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ de (STANDARDPACK \_ de) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Armazenamento de arquivos extra do Office 365 \_ de (SHAREPOINTSTORAGE \_ de) | Armazenamento de arquivos extra do Office 365 (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ de (DESKLESSPACK \_ de) | Office 365 F1 (DESKLESSPACK) |
| Office 365 PROPLUS para docentes \_ (OFFICESUBSCRIPTION \_ professores \_ de) | Office 365 PROPLUS para docentes ( \_ docentes OFFICESUBSCRIPTION) |
| Office 365 PROPLUS para alunos \_ de ( \_ OFFICESUBSCRIPTION \_ de aluno) | Office 365 PROPLUS para estudantes (OFFICESUBSCRIPTION \_ Student) |
| Office 365 ProPlus \_ de (OFFICESUBSCRIPTION \_ de) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| OneDrive for Business (plano 1) \_ de (WACONEDRIVESTANDARD \_ de) | OneDrive for Business (plano 1) (WACONEDRIVESTANDARD) |
| OneDrive for Business (plano 2) \_ de (WACONEDRIVEENTERPRISE \_ de) | OneDrive for Business (plano 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro for docent \_ (Power \_ bi \_ pro \_ \_ ) | Power BI pro para docentes ( \_ docentes do Power bi \_ pro \_ ) |
| Power BI pro \_ de (Power \_ bi \_ pro \_ de) | Power BI pro (POWER \_ bi \_ pro) |
| Project online Essentials \_ de (PROJECTESSENTIALS \_ de) | Project online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ de (PROJECTPREMIUM \_ de) | Project Online Premium (PROJECTPREMIUM) |
| Project online Professional \_ de (PROJECTPROFESSIONAL \_ de) | Project online Professional (PROJECTPROFESSIONAL) |
| Plano de projeto 3 \_ de (PROJECTPROFESSIONAL \_ de) | Plano de projeto 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ de (ENTERPRISEWITHSCAL \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (plano 1) \_ de (SHAREPOINTSTANDARD \_ de) | SharePoint Online (plano 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (plano 2) \_ de (SHAREPOINTENTERPRISE \_ de) | SharePoint Online (plano 2) (SHAREPOINTENTERPRISE) |
| Skype for Business online (plano 1) \_ de (MCOIMP \_ de) | Office 365 E1 (STANDARDPACK) |
| Skype for Business online (plano 1) \_ de (MCOIMP \_ de) | Skype for Business online (plano 1) (MCOIMP) |
| Skype for Business online (plano 2) \_ de (MCOSTANDARD \_ de) | Skype for Business online (plano 2) (MCOSTANDARD) |
| Skype for Business Plus CAL \_ de (MCOPLUSCAL \_ de) | Skype for Business Plus CAL (MCOPLUSCAL) |
| Visio online plano 1 para professores \_ de (VISIOONLINE \_ Plan1 \_ fac \_ de) | Visio online plano 1 para docentes (VISIOONLINE \_ Plan1 \_ fac) |
| Visio online plano 1 \_ de (VISIOONLINE \_ Plan1 \_ de) | Visio online plano 1 (VISIOONLINE \_ Plan1) |
| Visio online plano 2 para docentes \_ (VISIOCLIENT \_ professores \_ de) | Visio online plano 2 para docentes ( \_ docentes VISIOCLIENT) |
| Visio online plano 2 \_ de (VISIOCLIENT \_ de) | Visio online plano 2 (VISIOCLIENT) |
| Visio Plan 1 \_ de (VISIOONLINE \_ Plan1 \_ de) | Visio Plan 1 (VISIOONLINE \_ Plan1) |
| Visio Plan 2 \_ de (VISIOCLIENT \_ de) | Visio Plan 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Como posso obter ajuda da Microsoft para migrar para uma nova região ou para responder a perguntas de suporte?

Se você tiver dúvidas, entre em contato conosco ou seu parceiro:

- Para o Azure, você pode enviar [novas solicitações de suporte](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) no portal do Azure.
- Para o Office 365, você pode enviar perguntas usando a &quot; ajuda necessária? &quot; link do [centro de administração do Microsoft 365](https://portal.office.de/).
- Se você estiver usando o contrato de cliente do Dynamics 365 e o cliente do Power BI e também tiver o Office 365, você poderá enviar perguntas usando a &quot; ajuda necessária? &quot; link do [centro de administração do Microsoft 365](https://portal.office.de/). As opções de suporte do Dynamics 365 Customer Engagement estão localizadas [aqui](https://docs.microsoft.com/dynamics365/get-started/support/). As opções de suporte do Power BI estão localizadas [aqui](https://powerbi.microsoft.com/support/).


## <a name="next-step"></a>Próxima etapa

[Consentimento para migração](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>Mais informações

Introdução:

- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Mover-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para o [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
