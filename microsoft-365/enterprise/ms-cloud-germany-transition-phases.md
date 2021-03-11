---
title: Ações e impactos de fases de migração para a migração do Microsoft Cloud Deutschland (geral)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/05/2021
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
ms.openlocfilehash: 98a547a9af772e880465f75d9a3b01b1795639e1
ms.sourcegitcommit: 88ab08c0fa1acbc9e066009e131b9f2b0d506c64
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711947"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Ações e impactos de fases de migração para a migração do Microsoft Cloud Deutschland (geral)

As migrações de locatários do Microsoft Cloud Deutschland (MCD) para a região "Alemanha" dos serviços Globais do Office 365 da Microsoft são executadas como um conjunto de fases e suas ações configuradas para cada carga de trabalho. Esta figura mostra as nove fases de migração para os novos datacenters alemães.

![As nove fases de migração para os novos datacenters da Alemanha](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

O processo de migração será concluído ao longo de muitas semanas, dependendo do tamanho geral e da complexidade da organização. Enquanto a migração está em andamento, os usuários e administradores podem continuar utilizando os serviços com alterações notáveis detalhadas nesta documentação. O gráfico e a tabela definem fases e etapas durante a migração.

|Etapa|Duration|Responsável|Descrição|
|:--------|:--------|:--------|:--------|
|Opt-In|Horas|Cliente|Opte pela sua organização na migração.|
|Pré-trabalho|Dias|Cliente|Conclua o trabalho necessário para preparar usuários, estações de trabalho e rede para migração.|
|Azure Active Directory (Azure AD)|1 a 2 dias|Microsoft|Migrar a organização do Azure AD para todo o mundo.|
|Azure|Semanas|Cliente|Criar novas assinaturas do Azure em todo o mundo e fazer a transição dos serviços do Azure.|
|Transição de licença & assinatura|1 a 2 dias|Microsoft|Compre assinaturas em todo o mundo, cancele assinaturas do Microsoft Cloud Deutschland e licenças de usuário de transição.|
|SharePoint e OneDrive|Mais de 15 dias|Microsoft|Migre o conteúdo do SharePoint e do OneDrive for Business, sharepoint.de URLs.|
|Exchange Online|Mais de 15 dias|Microsoft|Migrar conteúdo do Exchange Online e fazer a transição para URLs em todo o mundo.|
|Conformidade e Segurança|1 a 2 dias|Microsoft|Transição de & de conformidade e conteúdo.|
|Skype for Business|1 a 2 dias|Microsoft|Transição do Skype for Business para o Microsoft Teams.|
|Power BI & Dynamics 365|Mais de 15 dias|Microsoft|Migrar conteúdo do Power BI e do Dynamics 365.|
|Finalizar o Azure AD|1 a 2 dias|Microsoft|Concluir a recortamento de locatários para todo o mundo.|
|Clean-Up|1 a 2 dias|Cliente|Limpe as conexões herdadas com o Microsoft Cloud Deutschland, como reinicializações dos Serviços de Federação do Active Directory (AD FS), Confiança de Parte Confiável do Azure AD Connect e cliente do Office.|

As fases e suas ações garantem que dados críticos e experiências sejam migrados para os serviços Globais do Office 365. Depois que o locatário for adicionado à fila de migração, cada carga de trabalho será concluída como um conjunto de etapas executadas no serviço de back-end. Algumas cargas de trabalho podem exigir ações do administrador (ou do usuário) ou a migração pode afetar o uso das fases executadas e discutidas em Como a migração [é organizada?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

As seções a seguir contêm ações e efeitos para cargas de trabalho à medida que elas passam por várias fases da migração. Revise as tabelas e determine quais ações ou efeitos são aplicáveis à sua organização. Verifique se você está preparado para executar as etapas nas respectivas fases, conforme necessário. A falha na conclusão das etapas necessárias pode resultar em interrupção de serviço e pode atrasar a conclusão da migração para os serviços do Office 365.

## <a name="opt-in"></a>Opt-In

**Aplica-se a**: Todos os clientes com um locatário do Office 365 hospedado no Microsoft Cloud Deutschland (MCD)

| Step(s) | Descrição | Impacto |
|:-------|:-----|:-------|
| Não é possível migrar locatários do Office 365 hospedados no MCD sem consentimento. | A Microsoft obtém o direito de migrar de duas maneiras, o que permite à Microsoft orquestrar a transição de dados e serviços para a instância de serviços Globais do Office 365. <ol><li>O administrador de locatários do Office 365 opta pela migração orientada pela Microsoft. </li><li> Os clientes renovam qualquer assinatura em seu locatário do MCD Office 365 após 1º de maio de 2020. Notificaremos esses clientes sobre o direito de migração todos os meses, aguardaremos 30 dias para dar aos clientes a chance de cancelar e, em seguida, optar diretamente.</li></ol> | <ul><li>O locatário é marcado como consentido para migração, e o Centro de Administração exibe a confirmação. </li><li>O reconhecimento é postado no Centro de Mensagens do locatário do Office 365. A configuração do serviço continua dos pontos de extremidade do Microsoft Cloud Deutschland. </li><li>O administrador de locatários deve monitorar o Centro de Mensagens do Office 365 para atualizações sobre o status da fase de migração. </li></ul>|

## <a name="subscription-phase-3"></a>Assinatura (Fase 3)

**Aplica-se a**: Todos os clientes com um locatário do Office 365 hospedado no Microsoft Cloud Deutschland (MCD)

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| As assinaturas são transferidas e as licenças são reatribuídas. | As assinaturas correspondentes dos serviços globais do Office 365 são compradas na instância Global do Office 365 para as assinaturas transferidas do Microsoft Cloud Deutschland. Os usuários com licenças do Microsoft Cloud Deutschland atribuídas receberão licenças na instância Global do Office 365. As assinaturas herdada do Microsoft Cloud Deutschland são removidas do locatário de serviços do Office 365 após a conclusão.| <ul><li>As alterações nas assinaturas existentes serão bloqueadas (por exemplo, nenhuma nova compra de assinatura ou alterações na contagem de assentos) durante essa fase.</li><li>As alterações de atribuição de licença serão bloqueadas.</li><li>A assinatura do Microsoft Cloud Deutschland será migrada para a assinatura correspondente dos serviços globais do Office 365. A oferta de serviços globais do Office 365 dessa assinatura é definida pela Microsoft (também conhecida como mapeamento _de oferta)._</li><li>O número de recursos (planos de serviço) oferecidos pelos serviços do Office 365 pode ser maior do que na oferta original do Microsoft Cloud Deutschland. As licenças de usuário nos serviços do Office 365 serão atribuídas equivalentemente a recursos semelhantes do Microsoft Cloud Deutschland (planos de serviço). As licenças de usuário de todos os usuários serão atribuídas automaticamente aos novos recursos. O administrador precisa tomar uma ação explícita para desabilitar essas licenças, se necessário. </li><li>Quando a migração de assinatura for concluída, tanto os serviços do Office 365 quanto as assinaturas do Microsoft Cloud Deutschland estarão visíveis no Portal de Administração do Office 365, com o status das assinaturas do Microsoft Cloud Deutschland _como desprovisionadas_. </li><li>Os usuários serão reatribuídos licenças vinculadas às novas assinaturas de serviços do Office 365. Todos os processos do cliente que tenham dependências de assinaturas MCD ou GUIDs SKU serão desfeitos e precisarão ser revisados com a oferta de serviços do Office 365. </li><li>Novas assinaturas nos serviços do Office 365 serão compradas com o novo termo (mensal/trimestral/anual) e o cliente receberá um reembolso prorável para o saldo não usado da assinatura do Microsoft Cloud Deutschland. </li><li>Os locatários do Microsoft Cloud Deutschland parceiros não serão migrados. Os clientes CSP serão migrados para serviços do Office 365 sob o novo locatário de serviços do Office 365 do mesmo parceiro. Após a migração do cliente, o parceiro pode gerenciar esse cliente somente a partir do locatário de serviços do Office 365. </li><li>A funcionalidade adicional está disponível (por exemplo, Microsoft Planner e Microsoft Flow), a menos que seja desabilitada pelo administrador de locatários. Para obter informações sobre como desabilitar planos de serviço atribuídos às licenças dos usuários, consulte [Disable access to Microsoft 365 services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</li></ul> |
||||

## <a name="sharepoint-online-phase-4"></a>SharePoint Online (Fase 4)

**Aplica-se a**: todos os clientes que usam o SharePoint Online

| Step(s) | Descrição | Impacto |
|:-------|:-----|:-------|
| SharePoint e OneDrive são transições | O SharePoint Online e o OneDrive for Business são migrados do Microsoft Cloud Deutschland para os serviços globais do Office 365 nesta fase.<br><ul><li>As URLs existentes do Microsoft Cloud Deutschland são preservadas (por exemplo, `contoso.sharepoint.de` ).</li><li>Os sites existentes são preservados.</li><li>Os tokens de autenticação do lado do cliente que foram emitidos pelo Serviço de Token de Segurança (STS) na instância de serviços Globais do Microsoft Cloud Deutschland ou office 365 são válidos durante a transição.</li></ul>|<ul><li>O conteúdo será somente leitura por dois breves períodos durante a migração. Durante esse tempo, espere um banner "você não pode editar conteúdo" no SharePoint.</li><li>O índice de pesquisa não será preservado e pode levar até 10 dias para ser reconstruído.</li><li>O conteúdo do SharePoint Online e do OneDrive for Business será somente leitura por dois breves períodos durante a migração. Os usuários verão um banner "você não pode editar conteúdo" brevemente durante esse tempo.</li><li>Após a conclusão da migração do SharePoint Online, os resultados da pesquisa para o conteúdo do SharePoint Online e do OneDrive for Business podem ficar indisponíveis enquanto o índice é reconstruído. Durante esse período, as consultas de pesquisa podem não retornar resultados completos. Recursos que dependem dos índices de pesquisa, como o SharePoint Online News, podem ser afetados enquanto a reindexação é concluída.</li></ul>|
||||

Considerações adicionais:

- Se sua organização ainda usa fluxos de trabalho do SharePoint 2010, eles não funcionarão mais após 31 de dezembro de 2021. Os fluxos de trabalho do SharePoint 2013 permanecerão com suporte, embora desligados por padrão para novos locatários a partir de 1º de novembro de 2020. Após a migração para o serviço do SharePoint Online ser concluída, recomendamos que você mude para o Power Automate ou outras soluções com suporte.

- Os clientes do Microsoft Cloud Deutschland cuja instância do SharePoint Online ainda não foi migrada precisam permanecer no módulo do PowerShell do SharePoint Online/Microsoft.SharePointOnline.CSOM versão 16.0.20616.12000 ou abaixo. Caso contrário, as conexões com o SharePoint Online via PowerShell ou o modelo de objeto do lado do cliente falharão.

- Os clientes do Microsoft Cloud Deutschland cuja instância do SharePoint Online é migrada devem atualizar o módulo do PowerShell do SharePoint Online/Microsoft.SharePointOnline.CSOM para a versão 16.0.20717.12000 ou superior. Caso contrário, as conexões com o SharePoint Online via PowerShell ou o modelo de objeto do lado do cliente falharão.

## <a name="exchange-online-phase-5"></a>Exchange Online (Fase 5)

**Aplica-se a:** Todos os clientes que usam o Exchange Online

Se você estiver usando o Exchange Online híbrido: os administradores híbridos do Exchange Online devem executar o assistente de Configuração Híbrida  **(HCW)** várias vezes como parte dessa transição. Consulte as etapas [de migração avançadas de pré-trabalho para o Exchange](ms-cloud-germany-transition-add-experience.md#exchange-online-before-phase-5)

Conforme descrito no pré-trabalho de migração [,](ms-cloud-germany-transition-add-pre-work.md#exchange-online)antes do início da etapa de migração **5,** os clientes híbridos do Exchange Online precisam executar a versão mais recente do Assistente de Configuração Híbrida do Exchange (HCW) no modo "Office 365 Germany" para preparar a configuração local para a migração para os serviços globais do Office 365.

Após a conclusão da fase de migração **5** (quando o aviso do Centro de Mensagens é publicado), você precisa executar o HCW novamente usando as configurações do Office 365 Worldwide para apontar seus sistemas locais para os serviços Globais do Office 365. Atualizações de DNS adicionais podem ser necessárias se você usar domínios personalizados.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| As caixas de correio do Exchange Online são movidas do Microsoft Cloud Deutschland para os serviços Globais do Office 365.| A configuração do Exchange Online adiciona a nova região go-local alemã à organização em transição. A região de serviços globais do Office 365 é definida como padrão, o que permite que o serviço de balanceamento de carga interno redistribua caixas de correio para a região padrão apropriada nos serviços do Office 365. Nesta transição, os usuários de ambos os lados (mcd ou serviços globais) estão na mesma organização e podem usar o ponto de extremidade da URL. |<ul><li>Transições de usuários e serviços de urls mcd herdados (outlook.office.de) para novas URLs de serviços do Office 365 ( `https://outlook.office365.com` ).</li><li>Os usuários podem continuar a acessar o serviço por meio de URLs MCD herdados durante a migração, no entanto, eles precisam parar de usar as URLs herdados na conclusão da migração.</li><li>Os usuários devem fazer a transição para o uso do portal do Office mundial para recursos do Office Online (Calendário, Email, Pessoas). A navegação para serviços que ainda não foram migrados para os serviços do Office 365 não funcionará até que sejam migrados. </li><li>O Outlook Web App não fornecerá a experiência de pasta pública durante a migração. </li></ul>|
| Atualizar configurações de DNS personalizadas para Descoberta Automática| As configurações de DNS gerenciadas pelo cliente para Descoberta Automática que apontam para o Microsoft Cloud Deutschland precisam ser atualizadas para se referir ao ponto de extremidade global do Office 365 na conclusão da fase do Exchange Online (fase 5). <br> Entradas DNS existentes com CNAME apontando para autodiscover-outlook.office.de precisam ser atualizadas para apontar para autodiscover.outlook.com. |  Solicitações de disponibilidade e chamadas de descoberta de serviço por meio do ponto de Descoberta Automática diretamente para os serviços do Office 365. Os clientes que não executam essas atualizações DNS podem ter problemas de serviço de Descoberta Automática quando a migração for finalizada. |
||||

Considerações adicionais:
<!--
    The statement below is not clear. What does myaccount.microsoft.com mean?
-->

- `myaccount.microsoft.com` só funcionará após a recorta do locatário na fase 9. Os links produzirão mensagens de erro "algo deu errado" até esse momento.

- Os usuários do Outlook Web App que acessam uma caixa de correio compartilhada em outro ambiente (por exemplo, um usuário no ambiente MCD acessa uma caixa de correio compartilhada no ambiente Global) serão solicitados a autenticar uma segunda vez. O usuário deve primeiro autenticar e acessar sua caixa de correio em , em seguida, abrir a caixa de correio `outlook.office.de` compartilhada que está em `outlook.office365.com` . Eles precisarão autenticar uma segunda vez ao acessar os recursos compartilhados hospedados no outro serviço.

- Para clientes existentes do Microsoft Cloud Deutschland ou aqueles em transição, quando uma caixa de correio compartilhada é adicionada ao Outlook usando Arquivo **> Informações > Adicionar** Conta , a exibição de permissões de calendário pode falhar (o cliente do Outlook tenta usar a API Rest `https://outlook.office.de/api/v2.0/Me/Calendars` .) Os clientes que quiserem adicionar uma conta para exibir permissões de calendário podem adicionar a chave do Registro conforme descrito em Alterações de experiência do usuário para compartilhar um calendário no [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) para garantir que essa ação seja bem-sucedida. Essa chave do Registro pode ser implantada em toda a organização usando a Política de Grupo.

- Durante a fase de migração, o uso dos cmdlets Do PowerShell **New-migrationEndpoint,** **Set-MigrationEndpoint** e **Test-MigrationsServerAvailability** pode resultar em erros (erro no proxy). Isso acontece quando a caixa de correio de arbitragem foi migrada para todo o mundo, mas a caixa de correio do administrador não foi ou vice-versa. Para resolver isso, ao criar a sessão do Locatário do PowerShell, use a caixa de correio de arbitragem como a dica de roteamento **no ConnectionUri**. Por exemplo:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```

Para saber mais sobre as diferenças para as organizações na migração e depois que os recursos do Exchange Online são migrados, revise as informações na experiência do cliente durante a migração para os serviços do [Office 365](ms-cloud-germany-transition-experience.md)nas novas regiões do datacenter alemão.

## <a name="exchange-online-protection--security-and-compliance-phase-6"></a>Proteção do Exchange Online / Segurança e Conformidade (Fase 6)

**Aplica-se a:** Todos os clientes que usam o Exchange Online<br>

Os recursos de Proteção do Exchange Online de back-end (EOP) são copiados para a nova região "Alemanha".

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Migração do roteamento do Exchange Online e detalhes de mensagens históricas. | O Exchange Online habilita o roteamento de hosts externos para o Office 365. Os registros MX externos são transições para roteamento para o serviço EOP. A configuração do locatário e os detalhes históricos são migrados. |<ul><li>As entradas DNS gerenciadas pela Microsoft são atualizadas do Office 365 Germany EOP para os serviços do Office 365.</li><li>Os clientes devem aguardar 30 dias após a gravação dupla do EOP para migração do EOP. Caso contrário, pode haver perda de dados.</li></ul>|
||||

## <a name="skype-for-business-online-phase-7"></a>Skype for Business Online (Fase 7)

**Aplica-se a:** Todos os clientes que usam o SharePoint Online

<!--
    Question from ckinder
    the PowerShell command seems to be incomplete
-->
| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Migração do Skype for Business para o Teams. | Os clientes existentes do Skype for Business são migrados para os serviços Globais do Office 365 na Europa e, em seguida, fazem a transição para o Microsoft Teams na região "Alemanha" dos serviços do Office 365. |<ul><li>Os usuários não poderão entrar no Skype for Business na data de migração. Dez dias antes da migração, postaremos no Centro de administração para que você saiba sobre quando a migração ocorrerá e novamente quando iniciarmos a migração.</li><li> A configuração da política é migrada. </li><li>Os usuários serão migrados para o Teams e não terão mais o Skype for Business após a migração. </li><li>Os usuários devem ter o cliente da área de trabalho do Teams instalado. A instalação ocorrerá durante os 10 dias por meio de política na infraestrutura do Skype for Business, mas, se isso falhar, os usuários ainda precisarão baixar o cliente ou se conectar a um navegador com suporte. </li><li>Contatos e reuniões serão migrados para o Teams.</li><li>Os usuários não poderão entrar no Skype for Business entre as transições de serviço de tempo para os serviços do Office 365 e não até que as entradas DNS do cliente sejam concluídas. </li><li>Contatos e reuniões existentes continuarão a funcionar como reuniões do Skype for Business. </li><li>O PowerShell usará para administrar configurações e políticas para seu locatário e usuários. Ao se conectar a uma sessão do PowerShell, adicione o seguinte: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"`</li></ul>|
||||

## <a name="dynamics-365-phase-8"></a>Dynamics 365 (Fase 8)

**Aplica-se a:** Todos os clientes que usam o Microsoft Dynamics 365

Os clientes com o Dynamics 365 exigem envolvimento adicional para migrar as organizações do Dynamics da organização de forma independente.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Recursos do Microsoft Dynamics | Os clientes com o Microsoft Dynamics serão contratados pela Microsoft Engineering ou pelo Microsoft FastTrack para fazer a transição do Microsoft Dynamics 365 para a instância dos serviços globais do Office 365.* |<ul><li>Após a migração, o administrador valida a organização. <</li><li>O administrador modifica fluxos de trabalho, conforme necessário. </li><li>O administrador limpa o modo AdminOnly conforme apropriado.</li><li>O administrador altera o tipo de organização do _Sandbox_, conforme apropriado</li><li>Notifique os usuários finais da nova URL para acessar a instância (org).</li><li>Atualize quaisquer conexões de entrada para a nova URL do ponto de extremidade. </li><li>O serviço dynamics ficará indisponível para os usuários durante a transição. </li><li>Os usuários são obrigados a validar a saúde e os recursos da organização após a migração de cada organização.</li></ul>|
|||||

\* (i) Os clientes com o Microsoft Dynamics 365 devem tomar medidas nesse cenário de migração conforme definido pelo processo de migração fornecido. (ii) A falha da ação do cliente significa que a Microsoft não poderá concluir a migração. (iii) Quando a Microsoft não conseguir concluir a migração devido à inação do cliente, a assinatura do cliente expirará em 29 de outubro de 2021.

## <a name="power-bi-phase-8-of-9"></a>Power BI (Fase 8 de 9)

**Aplica-se a:** Todos os clientes que usam o Microsoft Power BI (PBI)

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Migração de recursos do Power BI | Os clientes com o Microsoft Power BI (PBI) serão contratados pela Microsoft Engineering ou pelo Microsoft FastTrack depois de disparar manualmente uma ferramenta de migração PBI existente para fazer a transição do Power BI para a instância de serviços Globais do Office 365.\*\* |<ul><li>Os seguintes itens do Power BI não _serão_ transitivos, e eles terão que ser re-criados: <</li><li>Conjuntos de dados em tempo real (por exemplo, conjuntos de dados de streaming ou push). </li><li>Configuração e fonte de dados do gateway de dados local do Power BI. </li><li>Os relatórios construídos sobre os conjuntos de dados em tempo real não estarão disponíveis após a migração e serão necessários para serem recriados. </li><li>Os serviços do Power BI não estarão disponíveis para os usuários durante a transição. A indisponibilidade do serviço não deve ser superior a 24 horas.</li><li>Os usuários serão obrigados a reconfigurar fontes de dados e seus gateways de dados locais com o serviço Power BI após a migração.  Até que isso seja feito, os usuários não poderão usar essas fontes de dados para executar consultas agendadas de atualização e/ou diretas em relação a essas fontes de dados. </li><li>Capacidades e espaços de trabalho premium não podem ser migrados. Os clientes precisam excluir todas as capacidades antes da migração e re-criar após a migração. Mova os espaços de trabalho de volta para as capacidades conforme desejado.</li></ul>  |
||||

\*\* (i) Os clientes com o Microsoft Power BI devem tomar medidas nesse cenário de migração conforme definido pelo processo de migração fornecido. (ii) A falha da ação do cliente significa que a Microsoft não poderá concluir a migração. (iii) Quando a Microsoft não conseguir concluir a migração devido à inação do cliente, a assinatura do cliente expirará em 29 de outubro de 2021.

## <a name="office-apps"></a>Office Apps

**Aplica-se a:** Todos os clientes que usam aplicativos da área de trabalho do Office (Word, Excel, PowerPoint, Outlook, ...)

Os locatários do Office 365 que fazem a transição para a região "Alemanha" exigem que todos os usuários fechem, saia do Office 365 e volte para todos os aplicativos de área de trabalho do Office (Word, Excel, PowerPoint, Outlook etc.) e cliente do OneDrive for Business depois que a migração do locatário atingir a fase 9. Entrar e entrar, permite que os serviços do Office obtenham novos tokens de autenticação do serviço global do Azure AD.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Clientes, Office Online durante a reposição de cliente do Office, o Azure AD finaliza o escopo do locatário para apontar para os serviços do Office 365. | Essa alteração de configuração permite que os clientes do Office atualizem e apontem para os pontos de extremidade dos serviços do Office 365. | <ul><li>Notifique os usuários para fechar todos os aplicativos do _Office_ e, em seguida, entrar novamente (ou forçar os clientes a reiniciar e os usuários a entrar) para permitir que os clientes do Office atendam à alteração. </li><li>Notifique os usuários  e a equipe de atendimento técnico de que os usuários podem ver um banner do Office que solicita que eles reativam os aplicativos do Office em até 72 horas após a recortação. </li><li>Todos os aplicativos do Office em máquinas pessoais devem ser fechados e os usuários devem sair e entrar novamente. Na barra de ativação Amarela, entre para reativar em relação aos serviços do Office 365.</li><li>As máquinas compartilhadas exigirão ações semelhantes a máquinas pessoais e não exigirão um procedimento especial. </li><li>Em dispositivos móveis, os usuários devem sair de aplicativos, fechar e entrar novamente. </li></ul>|
||||

## <a name="office-services"></a>Serviços do Office

O serviço mru (mru) usado mais recentemente no Office é um recorte do MCD para os serviços Globais do Office 365, não uma migração. Somente os links de MRU do lado dos serviços globais do Office 365 estarão visíveis após a migração do portal Office.com. Os links de MRU do MCD não são visíveis como links MRU nos serviços Globais do Office 365. Nos serviços globais do Office 365, os links de MRU só podem ser acessados depois que a migração de locatários atingir a fase 9.

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
