---
title: Ações e impactos das fases de migração
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
description: 'Resumo: entenda as ações de fases de migração e impactos da mudança do Microsoft Cloud Alemanha (Microsoft Cloud Alemanha) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: 9ffdb0bbe60bdb96d6e110ac08cba4030272c7e9
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551652"
---
# <a name="migration-phases-actions-and-impacts"></a>Ações e impactos das fases de migração

As migrações de locatário do Microsoft Cloud Alemanha para a região da Alemanha dos serviços do Office 365 da Microsoft são executadas como um conjunto de ações configuradas para cada carga de trabalho. Essas ações garantem que os dados e as experiências críticos sejam migrados para os serviços do Office 365. Após o locatário ser adicionado à fila de migração, cada carga de trabalho será concluída como um conjunto de etapas executadas no serviço de back-end. Algumas cargas de trabalho podem exigir ações pelo administrador (ou pelo usuário) ou a migração pode afetar o uso das fases executadas e discutidas em [como a migração é organizada?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

As seções a seguir contêm ações e efeitos para cargas de trabalho à medida que elas avançam em várias fases da migração. Revise as tabelas e determine quais ações ou efeitos são aplicáveis à sua organização. Verifique se você está preparado para executar as etapas nas respectivas fases, conforme necessário. A falha na conclusão das etapas necessárias pode resultar em uma interrupção de serviço e pode atrasar a conclusão da migração para os serviços do Office 365.

## <a name="exchange-online"></a>Exchange Online

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| A nova região da Alemanha é adicionada à configuração da organização existente e as caixas de correio são movidas para os serviços do Office 365. | A configuração do Exchange Online Adiciona a nova região local do alemão à organização de transição. Esta região de serviços do Office 365 é definida como padrão, o que permite que o serviço de balanceamento de carga interno Redistribua as caixas de correio para a região padrão apropriada nos serviços do Office 365. Nessa transição, os usuários do lado (serviços da Alemanha ou do Office 365) estão na mesma organização e podem usar o ponto de extremidade de URL. | Exchange Online | – Transição de usuários e serviços de URLs da Alemanha para URLs de serviços do Office 365 ( `https://outlook.office365.com` ). <br><br> -Os usuários continuarão a acessar o serviço por meio de URLs da Alemanha herdadas durante a migração. Nenhuma ação imediata necessária. <br><br> -Os usuários devem começar a usar o portal do office.com para recursos do Office Online (calendário, emails, pessoas). A navegação para serviços que ainda não foram migrados para os serviços do Office 365 não funcionará até a migração. <br><br> – O Outlook Web App não fornece a experiência de pasta pública durante a migração. |
|||||

Para saber mais sobre as diferenças de organizações em migração e depois que os recursos do Exchange Online são migrados, revise as informações na [experiência do cliente durante a migração para os serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection"></a>Proteção do Exchange Online

Os recursos de back-end do Exchange Online Protection (EOP) são copiados para a nova região da Alemanha. 

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração de detalhes de mensagens históricas e de roteamento do Exchange Online. | O Exchange Online permite o roteamento de hosts externos para o Office 365. Os registros MX externos são migrados para o roteamento para o serviço EOP. A configuração do locatário e os detalhes históricos são migrados. | Clientes do Exchange Online | – As entradas de DNS gerenciadas pela Microsoft são atualizadas do Office 365 Alemanha EOP para os serviços do Office 365. <br><br> -Os clientes devem aguardar 30 dias após a gravação dupla do EOP para a migração do EOP. Caso contrário, poderá haver perda de dados. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

<!--

| Step(s) | Description | Applies to | Impact |
|:-------|:-----|:-------|:-------|
| SharePoint and OneDrive are transitioned. | SharePoint and OneDrive are migrated from Microsoft Cloud Deutschland to Office 365 services in this phase. Existing Microsoft Cloud Deutschland URLs are preserved (for example, `contoso.sharepoint.de`). Tokens that were issued by Microsoft Cloud Deutschland or Office 365 services are valid during the transition. | SharePoint customers | - Content will be read-only for two brief periods (less than x minutes) during migration. During this time, expect a "you can't edit content" banner in SharePoint. <br><br> - The search index won't be preserved, and may take up to 10 days to be rebuilt. <br><br> - SharePoint/OneDrive content will be read-only for two brief periods (less than x minutes) during migration. Users will see a "you can't edit content" banner briefly during this time. <br><br> - The search index may be unavailable while the index is rebuilt. During this period, search queries might not return complete results. <br><br> - Existing sites are preserved. |
|||||

--> 

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| O SharePoint e o OneDrive estão em transição. | O SharePoint e o OneDrive são migrados do Microsoft Cloud Alemanha para os serviços do Office 365 nesta fase. As URLs de Alemanha do Microsoft Cloud existentes são preservadas (por exemplo, `contoso.sharepoint.de` ). Os tokens emitidos pelo Microsoft Cloud Alemanha ou os serviços do Office 365 são válidos durante a transição. | Clientes do SharePoint | -O conteúdo será somente leitura por dois curtos períodos durante a migração. Durante esse período, espere uma faixa "não é possível editar o conteúdo" no SharePoint. <br><br> – O índice de pesquisa não será preservado e pode levar até 10 dias para ser recriado. <br><br> – O conteúdo do SharePoint/OneDrive será somente leitura por dois curtos períodos durante a migração. Os usuários verão uma faixa de "não é possível editar conteúdo" durante esse tempo. <br><br> -O índice de pesquisa pode estar indisponível enquanto o índice é recriado. Durante esse período, as consultas de pesquisa podem não retornar resultados completos. <br><br> -Os sites existentes são preservados. |
|||||


## <a name="skype-for-business-online"></a>Skype for Business Online

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração do Skype for Business para o Microsoft Teams. | Os clientes existentes do Skype for Business são migrados para os serviços do Office 365 na Europa e, em seguida, transferidos para o Microsoft Teams na região da Alemanha dos serviços do Office 365. | Clientes do Skype for Business | -Os usuários não poderão entrar no Skype for Business na data de migração. Dez dias antes da migração, notificaremos os usuários finais por meio da banda no cliente Skype for Business que eles serão atualizados para o Microsoft Teams. Também postaremos no centro de administração, que essas alterações ocorrerão após os 10 dias. <br><br> -A configuração de política é migrada. <br><br> -Os usuários serão migrados para o Microsoft Teams e não terão mais o Skype for Business após a migração. <br><br> -Os usuários devem ter o cliente da área de trabalho do teams instalado. A instalação acontecerá durante os 10 dias da política da infraestrutura do Skype for Business, mas se isso falhar, os usuários ainda precisarão baixar o cliente ou se conectarem a um navegador com suporte. <br><br> -Contatos e reuniões serão migrados para o Microsoft Teams. <br><br> -Os usuários não poderão entrar no Skype for Business entre as transições de serviço de tempo para os serviços do Office 365 e não até que as entradas de DNS do cliente sejam concluídas. <br><br> -Contatos e reuniões existentes continuarão a funcionar como reuniões do Skype for Business. |
|||||
        
## <a name="subscription"></a>Assinatura

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Não podemos migrar clientes sem o consentimento. | A Microsoft Obtém o direito de migrar de duas maneiras, o que permite que a Microsoft coordene a transição de dados e serviços para a instância de serviços do Office 365. <br> O administrador opta por fazer a migração orientada pela Microsoft. <br> Os clientes renovam as assinaturas no locatário do Microsoft Cloud Alemanha após 1 de maio de 2020. Notificaremos esses clientes sobre a migração imediatamente a cada mês, espere 30 dias para que os clientes tenham uma chance de cancelar e, em seguida, aceitar diretamente, acompanhado em ICM. | Todos os clientes do Office | -O locatário está marcado como remetido para migração, e o centro de administração exibe a confirmação. <br><br> – A confirmação é lançada no locatário do centro de mensagens na nuvem da Alemanha. A configuração do serviço continua dos pontos de extremidade do Microsoft Cloud Alemanha. <br><br> – Monitorar o centro de mensagens para atualizações no status da fase de migração. |
| As assinaturas são transferidas e as licenças são reatribuídas. | Após a transição do locatário para os serviços do Office 365, as assinaturas de serviços do Office 365 correspondentes são compradas para as assinaturas do Microsoft Cloud Alemanha transferidas. Os usuários com licenças do Microsoft Cloud Alemanha atribuídas receberão licenças de serviços do Office 365. As assinaturas do Microsoft Cloud Alemanha herdadas são removidas do locatário de serviços do Office 365 na conclusão. | Todos os clientes do Office | -As alterações nas assinaturas existentes serão bloqueadas (por exemplo, nenhuma nova aquisição de assinatura ou contagem de assentos) durante esta fase. <br><br> -As alterações de atribuição de licença serão bloqueadas. <br><br> -A assinatura do Alemanha do Microsoft Cloud será migrada para a assinatura de serviços do Office 365 correspondente. A oferta de serviços do Office 365 dessa assinatura é definida pela Microsoft (também conhecida como _mapeamento de oferta_). <br><br> – O número de recursos (planos de serviço) oferecidos pelos serviços do Office 365 pode ser maior do que na oferta original do Microsoft Cloud Alemanha. As licenças de usuário nos serviços do Office 365 serão atribuídas de forma equivalente a recursos similares do Microsoft Cloud Alemanha (planos de serviço). As licenças de usuário de todos os usuários serão automaticamente atribuídas aos novos recursos. O administrador precisa executar uma ação explícita para desabilitar essas licenças, se necessário. <br><br> -Quando a migração de assinatura estiver concluída, os serviços do Office 365 e as assinaturas da Alemanha serão visíveis no portal de administração do Office 365, com o status das assinaturas da Alemanha como _desprovisionadas_. <br><br> -Os usuários receberão licenças reatribuídas que estão ligadas às novas assinaturas dos serviços do Office 365. Qualquer processo de cliente que tenha dependências nas assinaturas da Alemanha ou nos GUIDs do SKU será interrompido e precisará ser revisado com a oferta de serviços do Office 365. <br><br> -Novas assinaturas nos serviços do Office 365 serão compradas com o novo termo (mensal/trimestral/anual) e o cliente receberá um reembolso rateado para o saldo não usado da assinatura do Microsoft Cloud Alemanha. <br><br> -Partner os locatários do Microsoft Cloud Alemanha não serão migrados. Os clientes de CSP serão migrados para os serviços do Office 365 sob o novo locatário do Office 365 Services do mesmo parceiro. Após a migração do cliente, o parceiro pode gerenciar esse cliente somente a partir do locatário de serviços do Office 365. <br><br> – A funcionalidade adicional está disponível (por exemplo, Microsoft Planner e Microsoft Flow), a menos que seja desabilitada pelo administrador de locatários. Para obter informações sobre como desabilitar os planos de serviço atribuídos às licenças dos usuários, consulte [desabilitar o acesso aos serviços do Microsoft 365 enquanto atribui licenças de usuário](disable-access-to-services-while-assigning-user-licenses.md).  |
|||||

## <a name="next-step"></a>Próxima etapa

[Executar pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Mais informações

Introdução:

- [Migração do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Mover-se pela transição:

- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [Serviços](ms-cloud-germany-transition-add-general.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
