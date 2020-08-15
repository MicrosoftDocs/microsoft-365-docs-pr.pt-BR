---
title: 'Migração do Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) para os serviços do Office 365 nas novas regiões de datacenter alemãs '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 07/09/2020
audience: ITPro
ms.topic: hub-page
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
ms.openlocfilehash: cfbd3b7406f7c7824f736633e3a4dba6fa5c4bff
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687348"
---
# <a name="migration-from-microsoft-cloud-germany-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Migração do Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) para os serviços do Office 365 nas novas regiões de datacenter alemãs 


>[!Note]
>Esse artigo aplica-se somente aos clientes qualificados do Microsoft Cloud Alemanha/Deutschland.
>

## <a name="cloud-service-offerings-in-germany"></a>Ofertas de serviço de nuvem na Alemanha

Em agosto de 2018, anunciamos o nosso objetivo de oferecer a nuvem completa da Microsoft — Azure, Office 365, Dynamics 365 e Power Platform — das novas regiões de nuvem na Alemanha, permitindo uma melhor transformação digital de nossos clientes. Em agosto de 2019, anunciamos que estamos no processo de abertura das novas regiões de nuvem na Alemanha. Anunciamos a disponibilidade do Azure em agosto e o Office 365 a partir de dezembro.  O Dynamics 365 e o Power Platform devem estar disponíveis no primeiro trimestre de 2020.  

As novas regiões foram projetadas para atender com maior flexibilidade à evolução das necessidades dos clientes alemães, os mais recentes serviços em nuvem inteligentes e conectividade total à nossa rede global de nuvens, bem como a residência de dados dos clientes na Alemanha.

## <a name="moving-to-the-new-german-regions"></a>Migrar para as novas regiões alemãs

Os clientes existentes do Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) agora podem começar a migrar seus clientes do Office 365, Dynamics 365 Customer Engagement e Power Platform BI.  A primeira etapa é [aceitar uma migração orientada pela Microsoft](https://aka.ms/office365germanymoveoptin) para as novas regiões de datacenter alemãs. 

Para as organizações que aceitarem a abordagem orientada pela Microsoft, espera-se que as migrações ocorram em 2020. Como resultado da migração, os dados principais e assinaturas do cliente serão movidos para as novas regiões alemãs. 

Os seguintes serviços serão migrados como parte da abordagem orientada pela Microsoft:

- Azure Active Directory
- Exchange Online
- Proteção do Exchange Online
- SharePoint Online
- OneDrive for Business
- Skype for Business Online

Durante a migração do Microsoft Cloud Alemanha para as regiões de datacenter alemãs, os clientes existentes do Skype for Business Online farão a transição para o Microsoft Teams. Para saber mais, confira [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home).

- Grupos do Office 365
- Dynamics 365 / Power Platform

Os pré-requisitos e o impacto da migração para esses serviços estão descritos no artigo [Dynamics 365 Customer Engagement](https://aka.ms/d365ceoptin).

O Vídeo do Office 365 será desativado em 1 de março de 2021. Se você optar por migrar o locatário do Office 365 para as novas regiões de datacenter alemãs, o Vídeo do Office 365 não terá suporte após a migração do SharePoint Online ser concluída. [Saiba mais](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Como se preparar para a migração para os serviços do Office 365 nas novas regiões de datacenter alemãs. 

A primeira etapa consiste em notificar a Microsoft para que tenhamos permissão para migrar sua assinatura e dados dos serviços Microsoft Cloud Alemanha/Deutschland para os serviços do Office 365 nas novas regiões de datacenter alemãs.  Consulte o [processo de aceitação](ms-cloud-germany-migration-opt-in.md) para obter instruções.

- Todos os clientes em migração precisam verificar a conectividade às [URLs e endereços IP do Office 365](urls-and-ip-address-ranges.md) em todo o mundo, o que inclui as novas regiões de datacenter alemãs. 
- Analise a descrição de serviço da plataforma do Office 365 para entender quais recursos e serviços estarão disponíveis para a organização após a conclusão para a região alemã. 
- A migração fará a transição das assinaturas pagas.  Não é possível migrar assinaturas de avaliação.

As migrações de locatário são executadas como operações de serviço de back-end com a interação mínima do cliente sendo necessária.  Qualquer tarefa adicional liderada pelo cliente e o status geral da migração serão comunicados por meio do Centro de Mensagens durante o processo de migração.  Os exemplos de tarefas podem incluir atualizações DNS gerenciadas pelo cliente ou reconfiguração da instalação híbrida para clientes híbridos do Exchange.

## <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Experiência do cliente durante a migração para os serviços do Office 365 nas novas regiões de datacenter alemãs 

As migrações do locatário são projetadas para ter um impacto mínimo sobre clientes finais e administradores.  No entanto, há considerações para cada carga de trabalho.  

### <a name="azure-active-directory"></a>Azure Active Directory

As assinaturas do Office/Dynamics do Microsoft Cloud Alemanha são transferidas para a região alemã com a realocação do Azure Active Directory (Azure AD). Em seguida, a organização será então atualizada para refletir as novas assinaturas de serviços em todo o mundo. Durante o breve processo de transferência das assinaturas, as alterações nelas serão bloqueadas.

### <a name="exchange-online"></a>Exchange Online

Os clientes do Exchange Online Híbrido devem executar novamente o Assistente de Configuração Híbrida para atualizar a configuração local no Microsoft Cloud Alemanha antes da transição e executar novamente o HCW após a limpeza no serviço mundial. Atualizações DNS adicionais poderão ser necessárias para clientes com domínios personalizados.

As caixas de correio são migradas como um processo de back-end, os usuários da sua organização podem estar na Microsoft Cloud Alemanha ou na região alemã durante a transição e fazer parte da mesma organização do Exchange (GAL)

### <a name="exchange-online-protection"></a>Proteção do Exchange Online

Os recursos de Proteção Online do Exchange Back-end são copiados para a nova região da Alemanha

### <a name="sharepoint-online"></a>SharePoint Online

Após a conclusão da migração do SharePoint Online para a região alemã, os índices de dados são reconstruídos. Os recursos dependentes de índices de pesquisa podem ser afetados enquanto a reindexação é concluída.

As URLs sharepoint.de existentes são preservadas para organizações transicionadas.

### <a name="onedrive-for-business"></a>OneDrive for Business

Após a conclusão da migração do OneDrive for Business para a região alemã, os índices de dados serão reconstruídos. Os recursos dependentes de índices de pesquisa podem ser afetados enquanto a reindexação é concluída.

### <a name="skype-for-business-online"></a>Skype for Business Online

Os clientes existentes do Skype for Business Online farão a transição para o Microsoft Teams. Confira [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) para obter mais informações.

### <a name="office-365-video"></a>Vídeo do Office 365
O conteúdo do Vídeo do Office 365 será migrado como parte da migração do SharePoint Online. No entanto, o Vídeo do Office 365 será desativado e não terá mais suporte após a migração do SharePoint Online para as novas regiões de datacenter alemãs ser concluída. Os vídeos que estiverem no Vídeo do Office 365 não serão reproduzidos na interface do usuário do Vídeo do Office 365 após a migração do SharePoint.

O Microsoft Stream não será implantado no Microsoft Deutschland e, no momento, não temos um cronograma para implantar o Microsoft Stream nas novas regiões de datacenter alemãs. Como resultado, não será fornecido nesta região nenhuma ferramenta de migração do Vídeo do Office 365 para o Microsoft Stream. Para preservar seu conteúdo, você precisará baixar ou mover o conteúdo manualmente antes de 1 de março de 2021. [Saiba mais](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)


## <a name="key-differences-between-microsoft-cloud-germany-microsoft-cloud-deutschland-and-office-365-services-in-the-new-german-datacenter-regions"></a>Principais diferenças entre os serviços Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) e Office 365 nas novas regiões de datacenter alemãs 


|| Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) | Serviços do Office 365 nas novas regiões de datacenter alemãs  |
|:-------|:-----|:-----|
| Serviços disponíveis do Microsoft 365 para assinatura com apenas um locatário do Office 365 | 15 serviços (confira REF) | 29 serviços (confira REF) |
| Novos recursos | Não há novos recursos disponíveis. | Os novos recursos estarão disponíveis de forma consistente com os serviços globais do Office 365. |
| Objeto de confiança dos dados | Sim | Não |
| Colaboração entre os locatários com locatários globais do Office 365 | Não | Sim |
| Residência de dados do cliente | Os Dados do Cliente serão armazenados apenas nos Data Centers alemães. | A Microsoft armazenará os seguintes Dados do Cliente em repouso exclusivamente na Alemanha: conteúdo da caixa de correio do Exchange Online (corpo do email, entradas de calendário e o conteúdo dos anexos de email), conteúdo do site do SharePoint Online e os arquivos armazenados no site e arquivos carregados no OneDrive for Business. |
| Termos aplicáveis | [Termos dos Serviços Online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) com [suplemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Termos dos Serviços Online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="frequently-asked-questions"></a>Perguntas Frequentes

### <a name="is-migration-required"></a>A migração é necessária?

A Microsoft oferece a migração de locatário do Office 365 dos serviços Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões de datacenter alemãs, sem custo adicional.  Embora seja altamente recomendável que você migre para as novas regiões de datacenter alemãs, continuaremos fornecendo as atualizações de segurança necessárias para a região do Microsoft Cloud Alemanha.  

Os serviços do Office 365 nas novas regiões de datacenter alemãs têm benefícios adicionais:

- Ofereça preços competitivos no mercado para o [Azure](https://azure.microsoft.com/pricing/calculator/), o [Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), o [Dynamics 365 Customer Engagement](https://dynamics.microsoft.com/pricing/) e o [Power BI](https://powerbi.microsoft.com/pricing/). 
- Estão conectados à rede global da Microsoft, oferecendo centenas de sites de borda de rede, locais de emparelhamento e pontos de saída para oferecer uma experiência robusta ao usuário em qualquer lugar do mundo. 
- Ajudando você a atender aos requisitos de residência de dados do cliente local na Alemanha. 
- Forneça nossa oferta de nuvem global com todos os recursos, incluindo a versão mais recente de nossos serviços e novos recursos, incluindo o Microsoft Teams e Multi-Geo no Office 365. Compare produtos por região para o [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), o [Office 365](o365-data-locations.md) e o [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability).
- Ofereça funcionalidade completa, segurança de nível empresarial e recursos abrangentes para ajudar os clientes a atender às determinações regulamentares e de conformidade. 
- Estão acessíveis por meio de contratos de serviços online existentes.

#### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>Qual é a disponibilidade do serviço entre as diferentes ofertas de serviços em nuvem do Office 365?

Os 15 serviços a seguir estão disponíveis na oferta de serviços em nuvem do Microsoft Cloud Alemanha (Microsoft Cloud Deutschland).  Não estamos adicionando novos serviços ao Microsoft Cloud Alemanha.

1. Exchange Online
2. Sistema de Proteção de Dados do Cliente (Exchange Online)
3. Grupos (Grupos modernos)
4. Perfil do Delve
5. Proteção do Exchange Online
6. Proteção Avançada contra Ameaças (ATP)
7. Descoberta Eletrônica Avançada
8. Governança de Dados Avançada
9. SharePoint Online
10. Sistema de Proteção de Dados do Cliente (SharePoint Online)
11. OneDrive for Business
12. Skype for Business
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

Atualmente, há 29 serviços disponíveis como parte dos serviços do Office 365 nas novas regiões de datacenter alemãs.  Novos recursos e serviços estarão disponíveis de forma consistente com os serviços globais do Office 365.

1. Exchange Online
2. Sistema de Proteção de Dados do Cliente (Exchange Online)
3. Grupos (Grupos modernos)
4. Perfil do Delve
5. MyAnalytics
6. Workplace Analytics
7. Proteção do Exchange Online
8. Proteção Avançada contra Ameaças (ATP)
9. Descoberta Eletrônica Avançada
10. Gerenciamento de Segurança Avançada
11. Gerenciamento de Direitos de Informação
12. Governança de Dados Avançada
13. SharePoint Online
14. Sistema de Proteção de Dados do Cliente (SharePoint Online)
15. OneDrive for Business
16. Microsoft Stream
17. Skype for Business (fará a transição para o Microsoft Teams durante a migração)
18. Cloud PBX
19. Conferência PSTN
20. Chamada PSTN 
21. Microsoft Teams
22. Relatórios de Administrador / Relatórios de Uso
23. Word Online, Excel Online, PowerPoint, OneNote e Visio Online
24. Planner
25. Sway
26. Office 365 Pro Plus
27. Outlook Mobile
28. EMS E3 (Azure Active Directory Premium P1 + Intune + Serviço de Gerenciamento de Direitos)
29. Yammer Online

### <a name="when-will-migration-happen"></a>Quando a migração ocorrerá?

#### <a name="azure"></a>Azure 

Você pode começar hoje a [migrar](https://docs.microsoft.com/azure/germany/germany-migration-main) seus recursos do Azure para outra região. Se você tiver o Azure com o Office 365, o Dynamics 365 e/ou o Power BI, siga as etapas a seguir.

#### <a name="office-365"></a>Office 365

[Aceitar](https://aka.ms/office365germanymoveoptin) para a migração orientada pela Microsoft hoje. Quando estivermos prontos para iniciar a migração, iremos informá-lo através do [Centro de Mensagens](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) no centro de administração do Microsoft 365.

#### <a name="dynamics-365-and-power-bi"></a>Dynamics 365 e Power BI

Aceitar para a migração orientada pela Microsoft para o [Dynamics 365 Customer Engagement](https://aka.ms/D365ceOptIn) e o [Power BI hoje](https://aka.ms/PBIOptIn). Quando estivermos prontos para iniciar a migração, iremos informá-lo através do [Centro de mensagens](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) no centro de administração do Microsoft 365.

### <a name="will-the-price-change-for-the-office-services-that-i-use"></a>O preço dos serviços do Office que eu uso serão alterados?

Sim, os preços das regiões de nuvem global da Microsoft (incluindo as novas regiões de datacenter) geralmente são menores.

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>Como posso obter ajuda da Microsoft para migrar para uma nova região ou para responder a perguntas de suporte?

Se tiver dúvidas, entre em contato conosco da seguinte forma ou por meio do seu parceiro:

- Para o Azure, você pode enviar [novas solicitações de suporte](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) no portal do Azure.
- Para o Office 365, você pode enviar perguntas usando o "Precisa de Ajuda?" link do [Centro de administração do Microsoft 365](https://portal.office.de/).
- Para clientes do Dynamics 365 Customer Engagement e do Power BI que também têm o Office 365, você pode enviar perguntas usando o "Precisa de Ajuda?" link do [Centro de administração do Microsoft 365](https://portal.office.de/). As opções de suporte do Dynamics 365 Customer Engagement estão localizadas [aqui](https://docs.microsoft.com/dynamics365/get-started/support/). As opções de suporte do Power BI estão localizadas [aqui](https://powerbi.microsoft.com/support/).

## <a name="more-information"></a>Mais informações

- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](https://aka.ms/office365germanymoveoptin)
- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365endpoints)
- [Assistente de Configuração Híbrida do Office 365](https://aka.ms/HybridWizard)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
