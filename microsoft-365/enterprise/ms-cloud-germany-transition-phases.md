---
title: Ações e impactos de fases de migração para a migração do Microsoft Cloud Deutschland (geral)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 01/26/2021
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
description: 'Resumo: entenda as ações das fases de migração e os impactos da migração do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: 1da3ff6b3347d0e996b017aa1f6243fd724ffccd
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454402"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Ações e impactos de fases de migração para a migração do Microsoft Cloud Deutschland (geral)

As migrações de locatários do Microsoft Cloud Deutschland para a região da Alemanha dos serviços do Office 365 da Microsoft são executadas como um conjunto de fases e suas ações configuradas para cada carga de trabalho. Esta figura mostra as nove fases de migração para os novos datacenters alemães.

![As nove fases de migração para os novos datacenters da Alemanha](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

As fases e suas ações garantem que dados críticos e experiências sejam migrados para os serviços do Office 365. Depois que o locatário for adicionado à fila de migração, cada carga de trabalho será concluída como um conjunto de etapas executadas no serviço de back-end. Algumas cargas de trabalho podem exigir ações do administrador (ou do usuário) ou a migração pode afetar o uso das fases executadas e discutidas em Como a migração [é organizada?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

As seções a seguir contêm ações e efeitos para cargas de trabalho à medida que elas passam por várias fases da migração. Revise as tabelas e determine quais ações ou efeitos são aplicáveis à sua organização. Verifique se você está preparado para executar as etapas nas respectivas fases, conforme necessário. A falha na conclusão das etapas necessárias pode resultar em interrupção de serviço e pode atrasar a conclusão da migração para os serviços do Office 365.

## <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (Fase 4 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| O SharePoint e o OneDrive são transições. | O SharePoint e o OneDrive são migrados do Microsoft Cloud Deutschland para os serviços do Office 365 nesta fase. As URLs existentes do Microsoft Cloud Deutschland são preservadas (por exemplo, `contoso.sharepoint.de` ). Tokens emitidos pelos serviços do Microsoft Cloud Deutschland ou office 365 são válidos durante a transição. | Clientes do SharePoint | - O conteúdo será somente leitura por dois breves períodos durante a migração. Durante esse tempo, espere um banner "você não pode editar conteúdo" no SharePoint. <br><br> - O índice de pesquisa não será preservado e pode levar até 10 dias para ser reconstruído. <br><br> - O conteúdo do SharePoint/OneDrive será somente leitura por dois breves períodos durante a migração. Os usuários verão um banner "você não pode editar conteúdo" brevemente durante esse tempo. <br><br> - O índice de pesquisa pode ficar indisponível enquanto o índice é reconstruído. Durante esse período, as consultas de pesquisa podem não retornar resultados completos. <br><br> - Os sites existentes são preservados. |
|||||

Considerações adicionais:

- Após a conclusão da migração do SharePoint Online para a região alemã, os índices de dados são reconstruídos. Os recursos dependentes dos índices de pesquisa podem ser afetados enquanto a reindexação é concluída.

- Se sua organização ainda usa fluxos de trabalho do SharePoint 2010, eles não funcionarão mais após 31 de dezembro de 2021. Os fluxos de trabalho do SharePoint 2013 permanecerão com suporte, embora desligados por padrão para novos locatários a partir de 1º de novembro de 2020. Após a migração para o serviço do SharePoint Online ser concluída, recomendamos que você mude para o Power Automate ou outras soluções com suporte.

- Após a conclusão da migração do OneDrive para a região alemã, os índices de dados são reconstruídos. Recursos que dependem dos índices de pesquisa podem ser afetados enquanto a reindexação está em andamento.

- Os clientes do Microsoft Cloud Deutschland cuja instância do SharePoint Online ainda não foi migrada precisam permanecer no módulo do PowerShell do SharePoint Online/Microsoft.SharePointOnline.CSOM versão 16.0.20616.12000 ou abaixo. Caso contrário, as conexões com o SharePoint Online via PowerShell ou o modelo de objeto do lado do cliente falharão.

- Os clientes do Microsoft Cloud Deutschland cuja instância do SharePoint Online é migrada devem atualizar o módulo do PowerShell do SharePoint Online/Microsoft.SharePointOnline.CSOM para a versão 16.0.20717.12000 ou superior. Caso contrário, as conexões com o SharePoint Online via PowerShell ou o modelo de objeto do lado do cliente falharão.


## <a name="exchange-online-phase-5-of-9"></a>Exchange Online (Fase 5 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| A nova região da Alemanha é adicionada à configuração da organização existente e as caixas de correio são movidas para os serviços do Office 365. | A configuração do Exchange Online adiciona a nova região go-local alemã à organização em transição. Essa região de serviços do Office 365 é definida como padrão, o que permite que o serviço interno de balanceamento de carga redistribua caixas de correio para a região padrão apropriada nos serviços do Office 365. Nesta transição, os usuários de ambos os lados (alemanha ou serviços do Office 365) estão na mesma organização e podem usar o ponto de extremidade da URL. | Exchange Online | - Transições de usuários e serviços de urls (outlook.office.de) da Alemanha herdado para novas URLs de serviços do Office 365 ( `https://outlook.office365.com` ). <br><br> - Os usuários podem continuar acessando o serviço por meio de URLs herddas da Alemanha durante a migração, no entanto, eles precisam parar de usar as URLs herdas na conclusão da migração. <br><br> - Os usuários devem fazer a transição para o uso do portal do Office mundial para recursos do Office Online (Calendário, Email, Pessoas). A navegação para serviços que ainda não foram migrados para os serviços do Office 365 não funcionará até que sejam migrados. <br><br> - O Outlook Web App não fornecerá a experiência de pasta pública durante a migração. |
| Atualizar configurações de DNS personalizadas para Descoberta Automática| As configurações de DNS gerenciadas pelo cliente para Descoberta Automática que apontam para o Microsoft Cloud Deutschland precisam ser atualizadas para apontar para o Office 365 na conclusão da fase do Exchange Online (fase 5). <br> Entradas DNS existentes com CNAME apontando para autodiscover-outlook.office.de precisam ser atualizadas para apontar para autodiscover.outlook.com. | Exchange Online | Solicitações de disponibilidade e chamadas de descoberta de serviço por meio do ponto de Descoberta Automática diretamente para os serviços do Office 365. Os clientes que não executam essas atualizações DNS podem ter problemas de serviço de Descoberta Automática quando a migração for finalizada. |
|||||

Considerações adicionais:

- `myaccount.msft.com` só funcionará após a redação do Office 365. Os links produzirão mensagens de erro "algo deu errado" até esse momento.

- Os usuários do Outlook Web App que acessam uma caixa de correio compartilhada em outro ambiente (por exemplo, um usuário no ambiente alemão acessa uma caixa de correio compartilhada no ambiente global) serão solicitados a autenticar uma segunda vez. O usuário deve primeiro autenticar e acessar sua caixa de correio em , em seguida, abrir a caixa de correio `outlook.office.de` compartilhada que está em `outlook.office365.com` . Eles precisarão autenticar uma segunda vez ao acessar os recursos compartilhados hospedados no outro serviço.

- Para clientes existentes do Microsoft Cloud Deutschland ou aqueles em transição, quando uma caixa de correio compartilhada é adicionada ao Outlook usando Arquivo **> Informações > Adicionar** Conta , a exibição de permissões de calendário pode falhar (o cliente do Outlook tenta usar a API Rest `https://outlook.office.de/api/v2.0/Me/Calendars` .) Os clientes que quiserem adicionar uma conta para exibir permissões de calendário podem adicionar a chave do Registro conforme descrito em Alterações de experiência do usuário para compartilhar um calendário no [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) para garantir que essa ação seja bem-sucedida. Essa chave do Registro pode ser implantada em toda a organização usando a Política de Grupo.

- Durante a fase de migração, o uso dos cmdlets Do PowerShell **New-migrationEndpoint,** **Set-MigrationEndpoint** e **Test-MigrationsServerAvailability** pode resultar em erros (erro no proxy). Isso acontece quando a caixa de correio de arbitragem foi migrada para todo o mundo, mas a caixa de correio do administrador não foi ou vice-versa. Para resolver isso, ao criar a sessão do Locatário do PowerShell, use a caixa de correio de arbitragem como a dica de roteamento **no ConnectionUri**. Por exemplo: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Se você estiver usando o Exchange Online híbrido:

    - Os clientes híbridos do Exchange Online devem executar o assistente de Configuração Híbrida (HCW) várias vezes como parte dessa transição. Antes do início da etapa de migração **5,** qualquer cliente híbrido do Exchange Online precisa executar a versão mais recente do HCW no modo Office 365 Germany para preparar a configuração local para a migração para o Office 365 global. Após a conclusão da fase de migração **5** (quando o aviso do Centro de Mensagens é publicado), você precisa executar o HCW em relação ao uso das configurações do Office 365 Worldwide para apontar seus sistemas locais para o serviço global. Atualizações de DNS adicionais podem ser necessárias se você usar domínios personalizados.

Para saber mais sobre as diferenças para as organizações na migração e depois que os recursos do Exchange Online são migrados, revise as informações na experiência do cliente durante a migração para os serviços do [Office 365](ms-cloud-germany-transition-experience.md)nas novas regiões do datacenter alemão.

## <a name="exchange-online-protection-phase-6-of-9"></a>Proteção do Exchange Online (Fase 6 de 9)

Os recursos de Proteção do Exchange Online de back-end (EOP) são copiados para a nova região da Alemanha. 

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração do roteamento do Exchange Online e detalhes de mensagens históricas. | O Exchange Online habilita o roteamento de hosts externos para o Office 365. Os registros MX externos são transições para roteamento para o serviço EOP. A configuração do locatário e os detalhes históricos são migrados. | Clientes do Exchange Online | - As entradas DNS gerenciadas pela Microsoft são atualizadas do Office 365 Germany EOP para os serviços do Office 365. <br><br> - Os clientes devem aguardar 30 dias após a gravação dupla do EOP para migração do EOP. Caso contrário, pode haver perda de dados. |
|||||



## <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business Online (Fase 7 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração do Skype for Business para o Teams. | Os clientes existentes do Skype for Business são migrados para os serviços do Office 365 na Europa e, em seguida, fazem a transição para o Microsoft Teams na região da Alemanha dos serviços do Office 365. | Clientes do Skype for Business | - Os usuários não poderão entrar no Skype for Business na data de migração. Dez dias antes da migração, postaremos no Centro de administração para que você saiba sobre quando a migração ocorrerá e novamente quando iniciarmos a migração. <br><br> - A configuração da política é migrada. <br><br> - Os usuários serão migrados para o Teams e não terão mais o Skype for Business após a migração. <br><br> - Os usuários devem ter o cliente de área de trabalho do Teams instalado. A instalação ocorrerá durante os 10 dias por meio de política na infraestrutura do Skype for Business, mas, se isso falhar, os usuários ainda precisarão baixar o cliente ou se conectar a um navegador com suporte. <br><br> - Contatos e reuniões serão migrados para o Teams. <br><br> - Os usuários não poderão entrar no Skype for Business entre as transições de serviço de tempo para os serviços do Office 365 e não até que as entradas DNS do cliente sejam concluídas. <br><br> - Contatos e reuniões existentes continuarão a funcionar como reuniões do Skype for Business. |
|||||


## <a name="office-apps-phase-8-of-9"></a>Office Apps (Fase 8 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Clientes, Office Online durante a reposição de cliente do Office, o Azure AD finaliza o escopo do locatário para apontar para os serviços do Office 365. | Essa alteração de configuração permite que os clientes do Office atualizem e apontem para os pontos de extremidade dos serviços do Office 365. | Todos os clientes do Office | - Notifique os usuários para fechar todos os aplicativos do _Office_ e, em seguida, entrar novamente (ou forçar os clientes a reiniciar e os usuários a entrar) para permitir que os clientes do Office atendam à alteração. <br><br> - Notifique os usuários  e a equipe de atendimento técnico de que os usuários podem ver uma faixa do Office que solicita que eles reativam os aplicativos do Office em até 72 horas após a reprodover. <br><br> - Todos os aplicativos do Office em máquinas pessoais devem ser fechados e os usuários devem sair e entrar novamente. Na barra de ativação Amarela, entre para reativar em relação aos serviços do Office 365. <br><br> - As máquinas compartilhadas exigirão ações semelhantes a máquinas pessoais e não exigirão um procedimento especial. <br><br> - Em dispositivos móveis, os usuários devem sair de aplicativos, feche-os e entre novamente. |
|||||


## <a name="office-services"></a>Serviços do Office

O serviço mru (mru) usado mais recentemente no Office é uma recorte do serviço alemão para os serviços do Office 365, não uma migração. Somente os links de MRU do lado dos serviços do Office 365 estarão visíveis após a migração do portal Office.com. Os links de MRU do serviço da Alemanha não são visíveis como links MRU nos serviços do Office 365. No Office 365, os links mru são acessíveis somente depois que a migração do locatário é concluída.

## <a name="subscription"></a>Assinatura

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Não podemos migrar clientes sem consentimento. | A Microsoft obtém o direito de migrar de duas maneiras, o que permite que a Microsoft orquestrou a transição de dados e serviços para a instância de serviços do Office 365. <br> O administrador opta pela migração orientada pela Microsoft. <br> Os clientes renovam quaisquer assinaturas em seu locatário do Microsoft Cloud Deutschland após 1º de maio de 2020. Notificaremos esses clientes sobre o direito de migração todos os meses, aguardaremos 30 dias para dar aos clientes a chance de cancelar e, em seguida, optar diretamente pelo ICM. | Todos os clientes do Office | - O locatário é marcado como consentido para migração e o Centro de Administração exibe a confirmação. <br><br> - O reconhecimento é postado no Locatário do Centro de Mensagens da Cloud Germany. A configuração do serviço continua dos pontos de extremidade do Microsoft Cloud Deutschland. <br><br> - Monitore o Centro de Mensagens para atualizações sobre o status da fase de migração. |
| As assinaturas são transferidas e as licenças são reatribuídas. | Após a transição do locatário para os serviços do Office 365, as assinaturas de serviços correspondentes do Office 365 são compradas para as assinaturas transferidas do Microsoft Cloud Deutschland. Os usuários com licenças do Microsoft Cloud Deutschland atribuídas receberão licenças de serviços do Office 365. As assinaturas herdada do Microsoft Cloud Deutschland são removidas do locatário de serviços do Office 365 após a conclusão. | Todos os clientes do Office | - As alterações nas assinaturas existentes serão bloqueadas (por exemplo, nenhuma nova compra de assinatura ou alterações na contagem de assentos) durante essa fase. <br><br> - As alterações de atribuição de licença serão bloqueadas. <br><br> - A assinatura do Microsoft Cloud Deutschland será migrada para a assinatura de serviços do Office 365 correspondente. A oferta de serviços do Office 365 dessa assinatura é definida pela Microsoft (também conhecida como mapeamento _de oferta)._ <br><br> - O número de recursos (planos de serviço) oferecidos pelos serviços do Office 365 pode ser maior do que na oferta original do Microsoft Cloud Deutschland. As licenças de usuário nos serviços do Office 365 serão atribuídas equivalentemente a recursos semelhantes do Microsoft Cloud Deutschland (planos de serviço). As licenças de usuário de todos os usuários serão atribuídas automaticamente aos novos recursos. O administrador precisa tomar uma ação explícita para desabilitar essas licenças, se necessário. <br><br> - Quando a migração de assinatura for concluída, tanto os serviços do Office 365 quanto as assinaturas da Alemanha estarão visíveis no Portal de Administração do Office 365, com o status das assinaturas da Alemanha como _desprovisionadas_. <br><br> - Os usuários serão reatribuídos licenças vinculadas às novas assinaturas de serviços do Office 365. Todos os processos de clientes que tenham dependências de assinaturas da Alemanha ou GUIDs SKU serão desfeitos e precisarão ser revisados com a oferta de serviços do Office 365. <br><br> - Novas assinaturas nos serviços do Office 365 serão compradas com o novo termo (mensal/trimestral/anual) e o cliente receberá um reembolso prorável para o saldo não usado da assinatura do Microsoft Cloud Deutschland. <br><br> – Os locatários do Microsoft Cloud Deutschland parceiros não serão migrados. Os clientes CSP serão migrados para serviços do Office 365 sob o novo locatário de serviços do Office 365 do mesmo parceiro. Após a migração do cliente, o parceiro pode gerenciar esse cliente somente a partir do locatário de serviços do Office 365. <br><br> - Funcionalidade adicional está disponível (por exemplo, Microsoft Planner e Microsoft Flow), a menos que seja desabilitada pelo administrador de locatários. Para obter informações sobre como desabilitar planos de serviço atribuídos às licenças dos usuários, consulte [Disable access to Microsoft 365 services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).  |
|||||

## <a name="next-step"></a>Próxima etapa

[Executar pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Mais informações

Como começar:

- [Migração do Microsoft Cloud Deutschland para serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Movendo-se pela transição:

- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
