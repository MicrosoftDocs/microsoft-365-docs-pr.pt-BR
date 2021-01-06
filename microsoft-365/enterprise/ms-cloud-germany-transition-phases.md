---
title: Ações de fases de migração e impactos da migração do Microsoft Cloud Alemanha (geral)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/15/2020
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
ms.openlocfilehash: 940ad0799aca7ead20d226cfcf3cc4b7b21c6cdb
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760193"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Ações de fases de migração e impactos da migração do Microsoft Cloud Alemanha (geral)

As migrações de locatário do Microsoft Cloud Alemanha para a região da Alemanha dos serviços do Office 365 da Microsoft são executadas como um conjunto de ações configuradas para cada carga de trabalho. Essas ações garantem que os dados e as experiências críticos sejam migrados para os serviços do Office 365. Após o locatário ser adicionado à fila de migração, cada carga de trabalho será concluída como um conjunto de etapas executadas no serviço de back-end. Algumas cargas de trabalho podem exigir ações pelo administrador (ou pelo usuário) ou a migração pode afetar o uso das fases executadas e discutidas em [como a migração é organizada?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

As seções a seguir contêm ações e efeitos para cargas de trabalho à medida que elas avançam em várias fases da migração. Revise as tabelas e determine quais ações ou efeitos são aplicáveis à sua organização. Verifique se você está preparado para executar as etapas nas respectivas fases, conforme necessário. A falha na conclusão das etapas necessárias pode resultar em uma interrupção de serviço e pode atrasar a conclusão da migração para os serviços do Office 365.

## <a name="exchange-online"></a>Exchange Online

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| A nova região da Alemanha é adicionada à configuração da organização existente e as caixas de correio são movidas para os serviços do Office 365. | A configuração do Exchange Online Adiciona a nova região local do alemão à organização de transição. Esta região de serviços do Office 365 é definida como padrão, o que permite que o serviço de balanceamento de carga interno Redistribua as caixas de correio para a região padrão apropriada nos serviços do Office 365. Nessa transição, os usuários do lado (serviços da Alemanha ou do Office 365) estão na mesma organização e podem usar o ponto de extremidade de URL. | Exchange Online | – Transição de usuários e serviços de URLs da Alemanha para URLs de serviços do Office 365 ( `https://outlook.office365.com` ). <br><br> -Os usuários continuarão a acessar o serviço por meio de URLs da Alemanha herdadas durante a migração. Nenhuma ação imediata necessária. <br><br> -Os usuários devem começar a usar o portal do office.com para recursos do Office Online (calendário, emails, pessoas). A navegação para serviços que ainda não foram migrados para os serviços do Office 365 não funcionará até a migração. <br><br> – O Outlook Web App não fornece a experiência de pasta pública durante a migração. |
|||||

Considerações adicionais:

- `myaccount.msft.com` funcionará apenas após a transferência do Office 365. Os links produzirão mensagens de erro "algo deu errado" até esse momento.

- Os usuários do Outlook Web App que acessam uma caixa de correio compartilhada no outro ambiente (por exemplo, um usuário no ambiente da Alemanha acessa uma caixa de correio compartilhada no ambiente global) serão solicitados a autenticar uma segunda vez. O usuário deve primeiro autenticar e acessar sua caixa de correio no `outlook.office.de` e, em seguida, abrir a caixa de correio compartilhada em `outlook.office365.com` . Eles precisarão autenticar uma segunda vez ao acessar os recursos compartilhados hospedados no outro serviço.

- Para os clientes existentes do Microsoft Cloud Alemanha ou aqueles em transição, quando uma caixa de correio compartilhada é adicionada ao Outlook usando as **informações de > de arquivo > adicionar conta**, as permissões de calendário podem falhar (o cliente do Outlook tenta usar a API REST `https://outlook.office.de/api/v2.0/Me/Calendars` ). Os clientes que desejam adicionar uma conta para exibir permissões de calendário podem adicionar a chave do registro, conforme descrito em [alterações de experiência do usuário para compartilhar um calendário no Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) para garantir que essa ação seja bem-sucedida. Essa chave do registro pode ser implantada em toda a organização usando a política de grupo.

- Durante a fase de migração, usar os cmdlets do PowerShell **New-migrationEndpoint**, **set-migrationEndpoint** e **Test-MigrationsServerAvailability** pode resultar em erros (erro no proxy). Isso acontece quando a caixa de correio de arbitragem foi migrada para o mundo inteiro, mas a caixa de correio de administrador não é ou vice-versa. Para resolver isso, ao criar a sessão do PowerShell do locatário, use a caixa de correio de arbitragem como a dica de roteamento no **ConnectionURI**. Por exemplo: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Se você estiver usando o Exchange Online híbrido:

    - Você deve executar novamente o assistente de configuração híbrida (HCW) para atualizar a configuração local no Microsoft Cloud Alemanha antes da transição e executar novamente o HCW após a limpeza nos serviços do Office 365. Outras atualizações DNS poderão ser necessárias se você usar domínios personalizados.

Para saber mais sobre as diferenças de organizações em migração e depois que os recursos do Exchange Online são migrados, revise as informações na [experiência do cliente durante a migração para os serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition-experience.md).

## <a name="exchange-online-protection"></a>Proteção do Exchange Online

Os recursos de back-end do Exchange Online Protection (EOP) são copiados para a nova região da Alemanha. 

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração de detalhes de mensagens históricas e de roteamento do Exchange Online. | O Exchange Online permite o roteamento de hosts externos para o Office 365. Os registros MX externos são migrados para o roteamento para o serviço EOP. A configuração do locatário e os detalhes históricos são migrados. | Clientes do Exchange Online | – As entradas de DNS gerenciadas pela Microsoft são atualizadas do Office 365 Alemanha EOP para os serviços do Office 365. <br><br> -Os clientes devem aguardar 30 dias após a gravação dupla do EOP para a migração do EOP. Caso contrário, poderá haver perda de dados. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| O SharePoint e o OneDrive estão em transição. | O SharePoint e o OneDrive são migrados do Microsoft Cloud Alemanha para os serviços do Office 365 nesta fase. As URLs de Alemanha do Microsoft Cloud existentes são preservadas (por exemplo, `contoso.sharepoint.de` ). Os tokens emitidos pelo Microsoft Cloud Alemanha ou os serviços do Office 365 são válidos durante a transição. | Clientes do SharePoint | -O conteúdo será somente leitura por dois curtos períodos durante a migração. Durante esse período, espere uma faixa "não é possível editar o conteúdo" no SharePoint. <br><br> – O índice de pesquisa não será preservado e pode levar até 10 dias para ser recriado. <br><br> – O conteúdo do SharePoint/OneDrive será somente leitura por dois curtos períodos durante a migração. Os usuários verão uma faixa de "não é possível editar conteúdo" durante esse tempo. <br><br> -O índice de pesquisa pode estar indisponível enquanto o índice é recriado. Durante esse período, as consultas de pesquisa podem não retornar resultados completos. <br><br> -Os sites existentes são preservados. |
|||||

Considerações adicionais:

- Após a conclusão da migração do SharePoint Online para a região alemã, os índices de dados são reconstruídos. Os recursos que dependem dos índices de pesquisa podem ser afetados durante a conclusão da reindexação.

- Se sua organização ainda usar fluxos de trabalho do SharePoint 2010, eles não funcionarão mais após 31 de dezembro de 2021. Os fluxos de trabalho do SharePoint 2013 permanecerão compatíveis, embora estejam desativados por padrão para novos locatários a partir de 1º de novembro de 2020. Depois que a migração para o serviço do SharePoint Online estiver concluída, recomendamos que você vá para automatização de energia ou outras soluções suportadas.

- Após a conclusão da migração do OneDrive para a região do alemão, os índices de dados são recriados. Os recursos que dependem de índices de pesquisa podem ser afetados enquanto a reindexação está em andamento.

- Microsoft Cloud Alemanha os clientes cuja instância do SharePoint Online ainda não foi migrada precisam permanecer no módulo do PowerShell do SharePoint Online/Microsoft. SharePointOnline. CSOM versão 16.0.20616.12000 ou abaixo. Caso contrário, as conexões com o SharePoint Online por meio do PowerShell ou do modelo de objeto do lado do cliente falharão.

- Microsoft Cloud Alemanha os clientes cuja instância do SharePoint Online é migrada devem atualizar o módulo do PowerShell do SharePoint Online/Microsoft. SharePointOnline. CSOM para a versão 16.0.20717.12000 ou superior. Caso contrário, as conexões com o SharePoint Online por meio do PowerShell ou do modelo de objeto do lado do cliente falharão.


## <a name="skype-for-business-online"></a>Skype for Business Online

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração do Skype for Business para o Microsoft Teams. | Os clientes existentes do Skype for Business são migrados para os serviços do Office 365 na Europa e, em seguida, transferidos para o Microsoft Teams na região da Alemanha dos serviços do Office 365. | Clientes do Skype for Business | -Os usuários não poderão entrar no Skype for Business na data de migração. Dez dias antes da migração, postaremos no centro de administração para permitir que você saiba quando ocorrerá a migração e, novamente, quando começarmos a migração. <br><br> -A configuração de política é migrada. <br><br> -Os usuários serão migrados para o Microsoft Teams e não terão mais o Skype for Business após a migração. <br><br> -Os usuários devem ter o cliente da área de trabalho do teams instalado. A instalação acontecerá durante os 10 dias da política da infraestrutura do Skype for Business, mas se isso falhar, os usuários ainda precisarão baixar o cliente ou se conectarem a um navegador com suporte. <br><br> -Contatos e reuniões serão migrados para o Microsoft Teams. <br><br> -Os usuários não poderão entrar no Skype for Business entre as transições de serviço de tempo para os serviços do Office 365 e não até que as entradas de DNS do cliente sejam concluídas. <br><br> -Contatos e reuniões existentes continuarão a funcionar como reuniões do Skype for Business. |
|||||

## <a name="office-services"></a>Serviços do Office

O serviço mais recentemente usado (MRU) no Office é uma substituição do serviço da Alemanha para os serviços do Office 365, não uma migração. Somente os links MRU do lado dos serviços do Office 365 serão visíveis após a migração do portal do Office.com. Os links MRU do serviço da Alemanha não são visíveis como links MRU nos serviços do Office 365. No Office 365, os links MRU são acessíveis somente após a conclusão da migração do locatário.

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
- Informações adicionais para o [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
