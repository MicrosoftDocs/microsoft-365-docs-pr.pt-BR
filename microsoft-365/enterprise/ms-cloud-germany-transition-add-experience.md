---
title: Ações e impactos das fases de migração para a migração do Microsoft Cloud Deutschland (avançado)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: 'Resumo: informações adicionais sobre a experiência do cliente ao mudar do Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região de datacenter alemã.'
ms.openlocfilehash: 717978d69c9f87855967c474f29216f6db8d3ce9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242849"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Ações e impactos das fases de migração para a migração do Microsoft Cloud Deutschland (avançado) 

As migrações de locatário do Microsoft Cloud Deutschland para a região Alemanha dos serviços do Office 365 da Microsoft são executadas como um conjunto de fases e suas ações configuradas para cada carga de trabalho. Esta figura mostra as nove fases da migração para os novos datacenters alemães.

![As nove fases da migração para os novos datacenters da Alemanha](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

As seções a seguir fornecem informações adicionais sobre experiências do cliente ao mudar do Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região de datacenter alemã.

## <a name="services"></a>Serviços

### <a name="azure-ad-phase-2-of-9"></a>Azure AD (Fase 2 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Locatário do Azure AD no Microsoft Cloud Deutschland copiado para os Serviços do Office 365. | O Azure AD copia o locatário para os serviços do Office 365. Os identificadores de locatário e usuário são preservados. As chamadas de serviço do Azure AD são redirecionadas do Microsoft Cloud Deutschland para os serviços do Office 365 e são transparentes para os serviços. | Todos os clientes do Office | – As Solicitações gerais de DSRs (Regulamentação Geral de Proteção de Dados) sobre a Proteção de Dados (RGPD) são executadas no portal de administração do Azure para solicitações futuras. Todos os dados de diagnóstico herdados ou que não são do cliente residentes no Microsoft Cloud Deutschland são excluídos em ou antes de 30 dias. <br><br> - Os clientes que usam autenticações federadas com os Serviços de Federação do Active Directory (AD FS) não devem fazer alterações nos URIs do emissor que são usados para todas as autenticações com o Active Directory local durante a migração. Alterar URIs de emissores levará a falhas de autenticação para usuários no domínio. Os URIs do emissor podem ser alterados diretamente no  AD FS ou quando um domínio é convertido de gerenciado para _federado_ e vice-versa. Recomendamos que os clientes não adicionem, removam ou convertam um domínio federado no locatário do Azure AD que foi migrado. Os URIs do emissor podem ser alterados após a conclusão completa da migração. <br><br> - As solicitações de autenticação multifatório (MFA) que usam o Microsoft Authenticator são exibidas como o usuário ObjectID (um GUID) enquanto o locatário é copiado para os serviços do Office 365. As solicitações de MFA terão o desempenho esperado apesar desse comportamento de exibição.  As contas do Microsoft Authenticator que foram ativadas usando os pontos de extremidade de serviços do Office 365 exibirão o nome UPN.  As contas adicionadas usando os pontos de extremidade do Microsoft Cloud Deutschland exibirão a ObjectID do usuário, mas funcionarão com os pontos de extremidade de serviços do Microsoft Cloud Deutschland e do Office 365.  |
| Estabeleça o AuthServer local apontando para o serviço STS global. | Isso garante que as solicitações de usuários que migram para o Microsoft Cloud Deutschland para solicitações de disponibilidade do Exchange que visam o ambiente local híbrido sejam autenticadas para acessar o serviço local. Da mesma forma, isso garantirá a autenticação de solicitações de pontos de extremidade de serviços locais para os serviços do Office 365. | Clientes do Exchange Online com implantações híbridas (locais) | Depois que a migração do Azure AD for concluída, o administrador da topologia local do Exchange (híbrido) deverá adicionar um novo ponto de extremidade do serviço de autenticação para os serviços do Office 365. Com este comando do Exchange PowerShell, substitua pela ID de locatário da sua organização (encontrada no portal do `<TenantID>` Azure no **Azure Active Directory).** <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> Se essa tarefa não for concluída, as solicitações híbridas de livre-ocupado não fornecerão informações para usuários de caixa de correio que foram migrados do Microsoft Cloud Deutschland para os serviços do Office 365.  |
| Migração de recursos do Azure. | Os clientes que usam recursos do Office 365 e do Azure (por exemplo, rede, computação e armazenamento) realizarão a migração de recursos para a instância de serviços do Office 365. Essa migração é uma responsabilidade dos clientes. As postagens do Centro de Mensagens sinalizam o início. A migração deve ser concluída antes da finalização da organização do Azure AD no ambiente de serviços do Office 365. | Clientes do Azure | Para migrações do Azure, confira o manual de migração do Azure, visão geral das diretrizes de migração do [Azure Alemanha.](https://docs.microsoft.com/azure/germany/germany-migration-main) |
|||||

### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (Fase 5 de 9)

Se você estiver usando **Set-UserPhoto**:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| A nova região Da Alemanha é adicionada a uma configuração de organização existente, e as caixas de correio são movidas para os serviços do Office 365. | A configuração do Exchange Online adiciona a nova região alemã go-local à organização de transição. Essa região de serviços do Office 365 é definida como padrão, o que permite que o serviço de balanceamento de carga interno redistribua caixas de correio para a região padrão apropriada nos serviços do Office 365. Nesta transição, os usuários de ambos os lados (serviços da Alemanha ou do Office 365) estão na mesma organização e podem usar qualquer ponto de extremidade de URL. |  Exchange Online | Se uma caixa de correio de usuário tiver sido migrada, mas uma caixa de correio de administrador não tiver sido migrada, ou vice-versa, os administradores não poderão executar **Set-UserPhoto**, um cmdlet do PowerShell. Nessa situação, um administrador deve passar uma cadeia de caracteres adicional durante a configuração da `ConnectionUri` conexão usando a seguinte sintaxe: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> onde está o espaço reservado para o email-ID do usuário cuja foto precisa ser alterada `<user_email>` usando **Set-UserPhoto**. |
|||||

Se você estiver usando uma implantação híbrida local:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
|Pare ou exclua qualquer movimentação de integração ou exclusão de caixas de correio.  | Isso garante que as solicitações de movimentação não falhem com um erro. | Clientes do Exchange Online com implantações híbridas (locais) | Ação necessária. Não fazer isso pode resultar em falha do serviço ou de clientes de software. |
|||||

### <a name="dynamics-phase-8-of-9"></a>Dynamics (Fase 8 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Recursos do Microsoft Dynamics | Os clientes com o Microsoft Dynamics serão envolvidos pela Engenharia ou FastTrack para fazer a transição do Dynamics para a instância de serviços do Office 365.* | Clientes do Microsoft Dynamics 365 | - Após a migração, o administrador valida a organização. <br><br> - O administrador modifica os fluxos de trabalho, conforme necessário. <br><br> - O administrador limpa o modo AdminOnly conforme apropriado. <br><br> - O administrador altera o tipo de organização da _Área Des sandbox,_ conforme apropriado <br><br> - Notifique os usuários finais sobre a nova URL para acessar a instância (org). <br><br> - Atualize todas as conexões de entrada para a nova URL do ponto de extremidade. <br><br> - O serviço do Dynamics ficará indisponível para os usuários durante a transição. <br><br> - Os usuários são obrigados a validar a saúde e os recursos da organização após a migração de cada organização.  |
|||||

\* (i) Os clientes com o Microsoft Dynamics 365 devem tomar medidas nesse cenário de migração, conforme definido pelo processo de migração fornecido. (ii) Se o cliente não tomar uma ação, isso significa que a Microsoft não poderá concluir a migração. (iii) Quando a Microsoft não puder concluir a migração devido à inação do cliente, a assinatura do cliente expirará em 29 de outubro de 2021. 


### <a name="power-bi-phase-8-of-9"></a>Power BI (Fase 8 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração de recursos do Power BI | Os clientes com o Microsoft Power BI serão envolvidos pela Engenharia ou FastTrack depois de disparar manualmente uma ferramenta de migração PBI existente para fazer a transição do Power BI para a instância de serviços do Office 365.\*\* | Clientes do Microsoft Power BI | - Os seguintes itens do Power BI _não serão_ transitivos e precisarão ser re-criados: <br><br> - Conjuntos de dados em tempo real (por exemplo, conjuntos de dados de streaming ou push). <br> - Fonte de dados e configuração do gateway de dados local do Power BI. <br> - Os relatórios construídos com base nos conjuntos de dados em tempo real não estarão disponíveis após a migração e precisarão ser recriados. <br><br> - Os serviços do Power BI estarão indisponíveis para os usuários durante a transição. A indisponibilidade do serviço não deve ser superior a 24 horas. <br><br> - Os usuários precisarão reconfigurar as fontes de dados e seus gateways de dados locais com o serviço do Power BI após a migração.  Até que isso seja feito, os usuários não poderão usar essas fontes de dados para executar consultas agendadas de atualização e/ou diretas com essas fontes de dados. <br><br> - Capacidades e espaços de trabalho premium não podem ser migrados. Os clientes precisam excluir todas as capacidades antes da migração e re-crie-as após a migração. Mova os espaços de trabalho de volta para as capacidades conforme desejado.  |
|||||

\*\* (i) Os clientes com o Microsoft Power BI devem tomar medidas nesse cenário de migração, conforme definido pelo processo de migração fornecido. (ii) Se o cliente não tomar uma ação, isso significa que a Microsoft não poderá concluir a migração. (iii) Quando a Microsoft não puder concluir a migração devido à inação do cliente, a assinatura do cliente expirará em 29 de outubro de 2021. 



## <a name="during-migration"></a>Durante a migração

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (Fase 4 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| O SharePoint e o OneDrive são transições. | O SharePoint e o OneDrive são migrados do Microsoft Cloud Deutschland para os serviços do Office 365 nesta fase. As URLs existentes do Microsoft Cloud Deutschland são preservadas ( `contoso.sharepoint.de` ). Os tokens emitidos pelos serviços do Microsoft Cloud Deutschland ou do Office 365 são válidos durante a transição. | Clientes do SharePoint | Os fluxos de trabalho do SharePoint 2013 de inflight serão interrompidos durante a migração e devem ser republicados após a migração. |
|||||


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (Fase 5 de 9)

Para Descoberta eDiscovery:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Durante a migração, as pesquisas de Descoberta eDiscovery falharão ou retornarão resultados 0 para locais do SharePoint Online, OneDrive for Business e Exchange Online que foram migrados. | Durante a migração, os clientes podem continuar a criar casos, regiões, pesquisas e [&](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)exportações no Centro de Conformidade e Segurança, incluindo [a Pesquisa de Conteúdo.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)  No entanto, pesquisas em locais do SharePoint Online, OneDrive for Business e Exchange Online que foram migrados retornarão 0 resultados ou produzirão um erro. Para correção, consulte a coluna _Impacto._ | Todos os clientes que usam a Descoberta eDiscovery |  Caso uma pesquisa retorne 0 resultados ou um erro durante a migração, faça o seguinte para o SharePoint Online: <br><br>  Baixe sites diretamente do site do SharePoint Online/OneDrive for Business seguindo as instruções em Baixar arquivos e pastas do [OneDrive ou do SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05) Esse método exigirá permissões de administrador do SharePoint Online ou permissões somente leitura no site. <br><br> Se os limites são excedido, conforme explicado em Baixar arquivos e pastas do OneDrive ou [do SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)os clientes podem usar o cliente de sincronização do OneDrive for Business seguindo as orientações em Sincronizar arquivos do [SharePoint](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)e do Teams com seu computador. <br><br> - Exchange Online <br><br> - [Descoberta In-place no Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||


### <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business Online (Fase 7 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração do Skype for Business para o Teams. | Os clientes existentes do Skype for Business são migrados para os serviços do Office 365 na Europa e, em seguida, migrados para o Microsoft Teams na região alemã dos serviços do Office 365. | Clientes do Skype for Business |  O PowerShell usará para administrar configurações e políticas para seu locatário e usuários. Ao se conectar a uma sessão do PowerShell, adicione o seguinte: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||


## <a name="post-migration"></a>Pós-migração

### <a name="azure-ad-phase-9-of-9"></a>Azure AD (Fase 9 de 9)

Para híbrido:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Atualize o Azure AD Connect. | Após a conclusão do corte para o Azure AD, a organização está usando totalmente os serviços do Office 365 e não está mais conectada ao Microsoft Cloud Deutschland. Neste ponto, o cliente precisa garantir que o processo de sincronização delta tenha sido finalizado e, depois disso, alterar o valor da cadeia de caracteres de `AzureInstance` 3 (Microsoft Cloud Deutschland) para 0 no caminho do `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` Registro. | Organizações conectadas híbridas do Azure AD | Altere o valor `AzureInstance` de , a chave do Registro. Se isso não for feito, os objetos não serão sincronizados depois que os pontos de extremidade do Microsoft Cloud Deutschland não estiverem mais disponíveis. |
|||||

Para autenticação federada:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Remover confianças de terceiros confiável do Microsoft Cloud Deutschland AD FS. | Após a conclusão do corte para o Azure AD, a organização está usando totalmente os serviços do Office 365 e não está mais conectada ao Microsoft Cloud Deutschland. Neste ponto, o cliente precisa remover a confiança de terceiros confiável para os pontos de extremidade do Microsoft Cloud Deutschland. Isso só pode ser feito quando nenhum aplicativo do cliente aponta para os pontos de extremidade do Microsoft Cloud Deutschland quando o Azure AD é aproveitado como um Provedor de Identidade (IdP). | Organizações de Autenticação Federada | Nenhum. |
|||||

Para o Azure AD:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| As solicitações para ingressar em um grupo do Azure AD nos últimos 30 dias antes da migração precisarão ser solicitadas novamente se a solicitação original não tiver sido aprovada. | Os clientes do usuário final precisarão usar o painel do Access para enviar a solicitação para ingressar em um grupo do Azure AD novamente se essas solicitações não foram aprovadas nos últimos 30 dias antes da migração. | Usuários finais cujas solicitações de aprovação de grupo do Azure AD não foram aprovadas nos últimos 30 dias antes da migração |  Como usuário final: <ol><li>Navegue até [o painel de acesso.](https://account.activedirectory.windowsazure.com/r#/joinGroups)</li><li>Encontre um grupo do Azure AD para o qual a aprovação de associação estava pendente em 30 dias antes da migração.</li><li>Solicitação para ingressar no grupo do Azure AD novamente.</li></ol> As solicitações para ingressar em um grupo que estão ativos menos de 30 dias antes da migração não podem ser aprovadas, a menos que sejam solicitadas após a migração. |
|||||

Para DNS:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Atualizar serviços DNS locais para pontos de extremidade de serviços do Office 365. | As entradas DNS gerenciadas pelo cliente que apontam para o Office 365 Germany precisam ser atualizadas para apontar para os pontos de extremidade de serviços do Office 365. | Todos os clientes do Office | Ação necessária. Não fazer isso pode resultar em falha do serviço ou de clientes de software. |
|||||

Para serviços de terceiros para pontos de extremidade de serviços do Office 365:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Atualizar parceiros e serviços de terceiros para pontos de extremidade de serviços do Office 365. | – Serviços e parceiros de terceiros que apontam para o Office 365 Germany precisam ser atualizados para apontar para os pontos de extremidade de serviços do Office 365. Exemplo: Registre-se de novo, em alinhamento com seus fornecedores e parceiros, a versão do aplicativo da galeria de aplicativos, se disponível. <br><br> - Aponte todos os aplicativos personalizados que aproveitam a API do Graph `graph.microsoft.de` de para `graph.microsoft.com` . Outras APIs com pontos de extremidade alterados também precisam ser atualizadas, se aproveitadas. <br><br> - Altere todos os aplicativos corporativos não terceirizados para redirecionar para os pontos de extremidade em todo o mundo.  | Todos os clientes do Office | Ação necessária. Não fazer isso pode resultar em falha do serviço ou de clientes de software. |
|||||

### <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (Fase 4 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Republicar fluxos de trabalho do SharePoint 2013. | No trabalho de pré-migração, reduzimos o número de fluxos de trabalho do SharePoint 2013. Agora, com a migração concluída, o cliente pode republicar os fluxos de trabalho. | Todos os clientes do Office | Esta é uma ação necessária. Não fazer isso pode resultar em confusão para o usuário e chamadas de help desk. |
| Compartilhar itens por meio do Outlook | O compartilhamento de itens pelo Outlook não funciona mais após a transferência do locatário. | SharePoint Online e OneDrive for Business | – No SharePoint Online e no OneDrive for Business, você pode compartilhar itens por meio do Outlook. Depois de pressionar o botão do Outlook, um link compartilhável é criado e pressionado para uma nova mensagem no Outlook Web App. <br><br> - Após a mudança de locatário, esse método de compartilhamento não funcionará. Reconhecemos que esse é um problema conhecido. No entanto, como esse recurso do Outlook está no caminho de preterido, a correção do problema não é planejada até que a preterida seja aplicada. |


### <a name="exchange-online-phase-5-of-9"></a>Exchange Online (Fase 5 de 9)

Se você estiver usando uma configuração híbrida do Exchange:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Rerun Hybrid Configuration wizard (HCW) against Office 365 services. | A configuração existente do HCW tem como objetivo dar suporte ao Microsoft Cloud Deutschland. Com a migração dos serviços do Exchange concluída, desaquecemos a configuração local do Microsoft Cloud Deutschland. | Clientes do Exchange Online que estão executando uma implantação híbrida | - Ação necessária. Não fazer isso pode resultar em falha do serviço ou de clientes de software. Antes que a migração de caixa de correio do Exchange comece (com cinco ou mais dias de aviso prévio), notifique os clientes de que eles devem parar e excluir qualquer movimentação de integração ou exclusão de suas caixas de correio.  Se não o fazem, eles verão erros em suas solicitações de movimentação. <br><br> - Após a conclusão da migração da caixa de correio do Exchange, notifique os clientes de que eles podem retomar as movimentações de integração e re transferência. <br> Executar **Test-MigrationServerAvailabiilty**, um cmdlet do PowerShell, durante a migração do Exchange do Microsoft Cloud Deutschland para os serviços do Office 365 pode não funcionar. No entanto, ele funcionará corretamente após a conclusão da migração. <br><br> Se os clientes têm problemas com credenciais ou autorização após a migração das caixas de correio, os usuários podem reinserirem suas credenciais de administrador local no ponto de extremidade de migração executando ou definindo o mesmo usando o Painel de Controle do `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange (ECP).  |

Para Descoberta eDiscovery:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
|  Todos os locais do SharePoint Online, oneDrive for Business e Exchange Online foram migrados junto com o Centro de Conformidade e Segurança (SCC). | Todas as atividades de DescobertaScoberta devem ser realizadas a partir do locatário em todo o mundo. As pesquisas agora serão 100% bem-sucedidas.  Quaisquer falhas ou erros devem seguir canais de suporte normais. | Todos os clientes que usam o eDiscovery | Nenhum. |
| Remover políticas de retenção para toda a organização que foram criadas durante as etapas de pré-migração | Os clientes podem remover as políticas de retenção de toda a organização que foram criadas durante o trabalho de pré-migração dos clientes. | Todos os clientes que aplicaram uma política de retenção como parte das etapas de pré-migração. | Nenhum. |
|||||



## <a name="next-step"></a>Próxima etapa

[Compreender as ações e os impactos das fases de migração](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Mais informações

Iniciando:

- [Migração do Microsoft Cloud Deutschland para os serviços do Office 365 nas novas regiões de datacenter alemãs](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Passando pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD](ms-cloud-germany-transition-azure-ad.md), [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos em nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
