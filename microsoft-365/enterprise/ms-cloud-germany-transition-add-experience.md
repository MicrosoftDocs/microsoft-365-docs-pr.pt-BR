---
title: Ações e impactos de fases de migração para a migração do Microsoft Cloud Deutschland (avançado)
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
description: 'Resumo: Informações adicionais sobre a experiência do cliente ao mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: 8e28b9d6c8cc23e128234973039a4873b327e9fd
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476357"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-advanced"></a>Ações e impactos de fases de migração para a migração do Microsoft Cloud Deutschland (avançado)

As migrações de locatários do Microsoft Cloud Deutschland para a região da Alemanha dos serviços do Office 365 da Microsoft são executadas como um conjunto de fases e suas ações configuradas para cada carga de trabalho. Esta figura mostra as dez fases de migração para os novos datacenters alemães.

![As dez fases de migração para os novos datacenters da Alemanha](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

As seções a seguir fornecem informações adicionais sobre as experiências do cliente ao mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região do datacenter alemão.

## <a name="office-365-portal-services-between-phase-2-and-phase-3"></a>Serviços do Portal do Office 365 entre a fase 2 e a fase 3

Entre a Fase 2 e a fase 3, o Partner Portal pode não estar acessível. Durante esse tempo, o Parceiro pode não conseguir acessar as informações do locatário no Portal do Parceiro. Como cada migração é diferente, a duração da acessibilidade pode ser em horas.

### <a name="ediscovery-phase-4-to-the-end-of-phase-9"></a>EDiscovery fase 4 até o final da fase 9

**Aplica-se a:** Todos os clientes que usam a Descoberta Bancária

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Desde o início da fase 4 até a conclusão da fase 9, as pesquisas de Descoberta Virtual falharão ou retornarão 0 resultados para os locais do SharePoint Online, do OneDrive for Business e do Exchange Online que foram migrados. | Durante [a](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)migração, os clientes podem continuar a criar casos, regiões, pesquisas e exportações no Centro de Conformidade & Segurança, incluindo [Pesquisa de Conteúdo.](https://docs.microsoft.com/microsoft-365/compliance/search-for-content) No entanto, as pesquisas em locais do SharePoint Online, do OneDrive for Business e do Exchange Online migrados retornarão 0 resultados ou produzirão um erro. Para correção, consulte a _coluna Impacto._ | Caso uma pesquisa retorne zero resultados ou um erro durante a migração, faça a seguinte ação para o SharePoint Online: <ul><li>Baixe sites diretamente do site do SharePoint Online ou do OneDrive for Business seguindo as instruções em Baixar arquivos e pastas [do OneDrive ou do SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05). Este método exigirá permissões de administrador do SharePoint Online ou permissões somente leitura no site.</li><li>Se os limites são excedido, conforme explicado em Baixar arquivos e pastas do OneDrive ou [do SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), os clientes poderão usar o cliente de sincronização do OneDrive for Business seguindo as diretrizes em Sincronizar arquivos do [SharePoint](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)e do Teams com seu computador.</li><li>Para obter mais informações, consulte  [In-Place eDiscovery in-Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
||||

## <a name="exchange-online-set-userphoto-during-phase-5"></a>Exchange Online Set-UserPhoto fase 5

**Aplica-se a:** Todos os clientes que armazenaram fotos de usuário no Exchange Online e estão usando **Set-UserPhoto**:

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| A nova região "Alemanha" é adicionada a uma configuração de organização existente do Exchange Online e as caixas de correio são movidas para serviços do Office 365. | A configuração do Exchange Online adiciona a nova região go-local alemã à organização em transição. Essa região de serviços do Office 365 é definida como padrão, o que permite que o serviço interno de balanceamento de carga redistribua caixas de correio para a região padrão apropriada nos serviços do Office 365. Nesta transição, os usuários de ambos os lados (alemanha ou serviços do Office 365) estão na mesma organização e podem usar o ponto de extremidade da URL. | Se uma caixa de correio de usuário tiver sido migrada, mas uma caixa de correio de administrador não tiver sido migrada, ou vice-versa, os administradores não poderão executar **Set-UserPhoto**, um cmdlet do PowerShell. Nessa situação, um administrador deve passar uma cadeia de caracteres adicional durante a configuração da conexão `ConnectionUri` usando a seguinte sintaxe: <br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br> onde é o espaço reservado para a ID de email do usuário cuja foto precisa ser alterada usando `<user_email>` **Set-UserPhoto**. |
||||

## <a name="post-migration"></a>Pós-migração

### <a name="azure-ad-phase-9"></a>Fase 9 do Azure AD

**Aplica-se a:** Todos os clientes sincronizando identidades com a conexão do Azure AD

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Atualizar o Azure AD Connect. | Após a conclusão do corte no Azure AD, a organização está usando totalmente os serviços do Office 365 e não está mais conectada ao Microsoft Cloud Deutschland. Neste ponto, o cliente precisa garantir que o processo de sincronização delta tenha sido finalizado e, depois disso, altere o valor da cadeia de caracteres de `AzureInstance` 3 (Microsoft Cloud Deutschland) para 0 no caminho do `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` Registro. | Altere o valor `AzureInstance` de , a chave do Registro. Se não fizer isso, os objetos não serão sincronizados depois que os pontos de extremidade do Microsoft Cloud Deutschland não estiverem mais disponíveis. |
|||||

**Aplica-se a:** Todos os clientes que usam autenticação federada com a ADFS

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Remova as confianças de terceiros confiável do Microsoft Cloud Deutschland AD FS. | Após a conclusão do corte no Azure AD, a organização está usando totalmente os serviços do Office 365 e não está mais conectada ao Microsoft Cloud Deutschland. Neste ponto, o cliente precisa remover a confiança da parte confiável para os pontos de extremidade do Microsoft Cloud Deutschland. Isso só pode ser feito quando nenhum dos aplicativos do cliente aponta para os pontos de extremidade do Microsoft Cloud Deutschland quando o Azure AD é aproveitado como um Provedor de Identidade (IdP). | Organizações de Autenticação Federada | Nenhum. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Aplica-se a:** Usuários finais cujas solicitações de aprovação de grupo do Azure AD não foram aprovadas nos últimos 30 dias antes da migração 

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| As solicitações para ingressar em um grupo do Azure AD nos últimos 30 dias antes da migração precisarão ser solicitadas novamente se a solicitação original não tiver sido aprovada. | Os clientes do usuário final precisarão usar o painel do Access para enviar uma solicitação para ingressar em um grupo do Azure AD novamente se essas solicitações não foram aprovadas nos últimos 30 dias antes da migração. |  Como usuário final: <ol><li>Navegue até [o painel do Access](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Encontre um grupo do Azure AD para o qual a aprovação de associação estava pendente durante os 30 dias antes da migração.</li><li>Solicitação para ingressar no grupo do Azure AD novamente.</li></ol> As solicitações para ingressar em um grupo que estão ativos menos de 30 dias antes da migração não podem ser aprovadas, a menos que sejam solicitadas novamente após a migração. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
**Aplica-se a:**  Todos os clientes gerenciando suas próprias zonas DNS

| Step(s) | Descrição | Impacto |
|:------|:-------|:-------|
| Atualize os serviços DNS locais para os pontos de extremidade dos serviços do Office 365. | As entradas DNS gerenciadas pelo cliente que apontam para o Microsoft Cloud Deutschland precisam ser atualizadas para apontar para os pontos de extremidade dos serviços globais do Office 365. | A falha ao fazer isso pode resultar em falha do serviço ou de clientes de software. |
||||

**Aplica-se a:** Clientes que usam serviços de terceiros para pontos de extremidade de serviços do Office 365

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Atualizar parceiros e serviços de terceiros para pontos de extremidade de serviços do Office 365. | <ul><li>Os serviços e parceiros de terceiros que apontam para o Office 365 Germany precisam ser atualizados para apontar para os pontos de extremidade dos serviços do Office 365. Exemplo: registre-se de novo, em alinhamento com seus fornecedores e parceiros, a versão do aplicativo de galeria de aplicativos, se disponível. </li><li>Aponte todos os aplicativos personalizados que aproveitam a API do Graph `graph.microsoft.de` de `graph.microsoft.com` para . Outras APIs com pontos de extremidade alterados também precisam ser atualizadas, se usadas. </li><li>Altere todos os aplicativos corporativos não de primeira parte para redirecionar para os pontos de extremidade em todo o mundo. </li></ul>| Ação necessária. A falha ao fazer isso pode resultar em falha do serviço ou de clientes de software. |
||||

### <a name="sharepoint-online-post-migration"></a>Migração pós-migração do SharePoint Online

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Republicar fluxos de trabalho do SharePoint 2013. | No trabalho de pré-migração, reduzimos o número de fluxos de trabalho do SharePoint 2013. Agora, com a migração concluída, o cliente pode republicar os fluxos de trabalho. | Esta é uma ação necessária. A falha ao fazer isso pode resultar em confusão do usuário e chamadas de help desk. |
| Compartilhar itens via Outlook | O compartilhamento de itens no SharePoint Online e no OneDrive for Business via Outlook não funciona mais após a redução de locatários. |<ul><li>No SharePoint Online e no OneDrive for Business, você pode compartilhar itens por meio do Outlook. Depois de pressionar o botão do Outlook, um link compartilhável é criado e pressionado para uma nova mensagem no Outlook Web App.</li><li>Após a recorte do locatário, esse método de compartilhamento não funcionará. Reconhecemos que esse é um problema conhecido. No entanto, como esse recurso do Outlook está no caminho da precarização, a correção do problema não é planejada até que a deprecação seja aplicada. </li></ul>|
||||

### <a name="exchange-online-post-migration"></a>Migração pós-migração do Exchange Online

Se você estiver usando uma configuração híbrida do Exchange:

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Rerun Hybrid Configuration wizard (HCW) against Office 365 services. | A configuração do HCW existente deve dar suporte ao Microsoft Cloud Deutschland. Com a migração dos serviços do Exchange concluída, desaparecemos a configuração local do Microsoft Cloud Deutschland. |<ul><li>Ação necessária. A falha ao fazer isso pode resultar em falha do serviço ou de clientes de software. Antes que a migração de caixa de correio do Exchange comece (com 5 ou mais dias de aviso), notifique os clientes de que eles devem parar e excluir quaisquer movimentações de integração ou de offboard de suas caixas de correio.  Se não o fazem, eles verão erros em suas solicitações de movimentação. </li><li>Depois que a migração de caixa de correio do Exchange for concluída, notifique os clientes de que eles podem retomar as movimentações de integração e de offboard. <br> Executar **Test-MigrationServerAvailabiilty**, um cmdlet do PowerShell, durante a migração do Exchange do Microsoft Cloud Deutschland para os serviços do Office 365 pode não funcionar. No entanto, ele funcionará corretamente depois que a migração for concluída. </li><li>Se os clientes se derem com problemas com credenciais ou autorização após a migração das caixas de correio, os usuários poderão reinserer suas credenciais de administrador local no ponto de extremidade de migração executando ou definindo o mesmo usando o Painel de Controle do `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange (ECP). </li></ul>|

### <a name="ediscovery-post-migration"></a>Migração pós-descoberta e

**Aplica-se a:** Todos os clientes que usam a Descoberta E

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
|  Todos os locais do SharePoint Online, do OneDrive for Business e do Exchange Online foram migrados juntamente com o Centro de Segurança e Conformidade (SCC). | Todas as atividades de Descoberta Externa devem ser executados do locatário em todo o mundo. As pesquisas agora terão 100% de êxito.  Quaisquer falhas ou erros devem seguir os canais de suporte normais. | Nenhum |
||||

**Aplica-se a:**  Todos os clientes que aplicaram uma política de retenção como parte das etapas de pré-migração

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Remover políticas de retenção em toda a organização que foram criadas durante etapas de pré-migração | Os clientes podem remover as políticas de retenção em toda a organização que foram criadas durante o trabalho de pré-migração dos clientes. | Nenhum |
||||

## <a name="next-step"></a>Próxima etapa

[Compreender as ações e os impactos das fases de migração](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Mais informações

Como começar:

- [Migração do Microsoft Cloud Deutschland para serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
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