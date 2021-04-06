---
title: Atividades pós-migração para a migração do Microsoft Cloud Deutschland
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
description: 'Resumo: atividades pós-migração após a migração do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: 745589c1c997540094fc4a770e437de89015f88a
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591751"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Atividades pós-migração para a migração do Microsoft Cloud Deutschland

As seções a seguir fornecem atividades pós-migração para vários serviços depois de migrar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região do datacenter alemão.

## <a name="azure-ad"></a>Azure Active Directory

### <a name="azure-ad-connect"></a>Azure AD Connect
**Aplica-se a:** Todos os clientes sincronizando identidades com a conexão do Azure AD

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Atualizar o Azure AD Connect. | Após a conclusão do corte no Azure AD, a organização está usando totalmente os serviços do Office 365 e não está mais conectada ao Microsoft Cloud Deutschland. Neste ponto, o cliente precisa garantir que o processo de sincronização delta tenha sido finalizado e, depois disso, altere o valor da cadeia de caracteres de `AzureInstance` 3 (Microsoft Cloud Deutschland) para 0 no caminho do `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` Registro. | Altere o valor `AzureInstance` de , a chave do Registro. Se não fizer isso, os objetos não serão sincronizados depois que os pontos de extremidade do Microsoft Cloud Deutschland não estiverem mais disponíveis. |
|||||

### <a name="azure-ad-federated-authentication-with-ad-fs"></a>Autenticação federada do Azure AD com o AD FS
**Aplica-se a:** Todos os clientes que usam autenticação federada com o AD FS

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Remova as confianças de terceiros confiável do Microsoft Cloud Deutschland AD FS. | Após a conclusão do corte no Azure AD, a organização está usando totalmente os serviços do Office 365 e não está mais conectada ao Microsoft Cloud Deutschland. Neste ponto, o cliente precisa remover a confiança da parte confiável para os pontos de extremidade do Microsoft Cloud Deutschland. Isso só pode ser feito quando nenhum dos aplicativos do cliente aponta para os pontos de extremidade do Microsoft Cloud Deutschland quando o Azure AD é aproveitado como um Provedor de Identidade (IdP). | Organizações de Autenticação Federada | Nenhum. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a>Aprovações de grupo
**Aplica-se a:** Usuários finais cujas solicitações de aprovação de grupo do Azure AD não foram aprovadas nos últimos 30 dias antes da migração 

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| As solicitações para ingressar em um grupo do Azure AD nos últimos 30 dias antes da migração precisarão ser solicitadas novamente se a solicitação original não tiver sido aprovada. | Os clientes do usuário final precisarão usar o painel do Access para enviar uma solicitação para ingressar em um grupo do Azure AD novamente se essas solicitações não foram aprovadas nos últimos 30 dias antes da migração. |  Como usuário final: <ol><li>Navegue até [o painel do Access](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Encontre um grupo do Azure AD para o qual a aprovação de associação estava pendente durante os 30 dias antes da migração.</li><li>Solicitação para ingressar no grupo do Azure AD novamente.</li></ol> As solicitações para ingressar em um grupo que estão ativos menos de 30 dias antes da migração não podem ser aprovadas, a menos que sejam solicitadas novamente após a migração. |
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
## <a name="custom-dns-updates"></a>Atualizações DNS personalizadas
**Aplica-se a:**  Todos os clientes gerenciando suas próprias zonas DNS

| Step(s) | Descrição | Impacto |
|:------|:-------|:-------|
| Atualize os serviços DNS locais para os pontos de extremidade dos serviços do Office 365. | As entradas DNS gerenciadas pelo cliente que apontam para o Microsoft Cloud Deutschland precisam ser atualizadas para apontar para os pontos de extremidade dos serviços globais do Office 365. | A falha ao fazer isso pode resultar em falha do serviço ou de clientes de software. |
||||

## <a name="third-party-services"></a>Serviços de terceiros
**Aplica-se a:** Clientes que usam serviços de terceiros para pontos de extremidade de serviços do Office 365

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Atualizar parceiros e serviços de terceiros para pontos de extremidade de serviços do Office 365. | <ul><li>Os serviços e parceiros de terceiros que apontam para o Office 365 Germany precisam ser atualizados para apontar para os pontos de extremidade dos serviços do Office 365. Exemplo: registre-se de novo, em alinhamento com seus fornecedores e parceiros, a versão do aplicativo de galeria de aplicativos, se disponível. </li><li>Aponte todos os aplicativos personalizados que aproveitam a API do Graph `graph.microsoft.de` de `graph.microsoft.com` para . Outras APIs com pontos de extremidade alterados também precisam ser atualizadas, se usadas. </li><li>Altere todos os aplicativos corporativos não de primeira parte para redirecionar para os pontos de extremidade em todo o mundo. </li></ul>| Ação necessária. A falha ao fazer isso pode resultar em falha do serviço ou de clientes de software. |
||||

## <a name="sharepoint-online"></a>SharePoint Online
**Aplica-se a**: clientes que usam fluxos de trabalho do SharePoint 2013

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Republicar fluxos de trabalho do SharePoint 2013. | No trabalho de pré-migração, reduzimos o número de fluxos de trabalho do SharePoint 2013. Agora, com a migração concluída, o cliente pode republicar os fluxos de trabalho. | Esta é uma ação necessária. A falha ao fazer isso pode resultar em confusão do usuário e chamadas de help desk. |
| Compartilhar itens via Outlook | O compartilhamento de itens no SharePoint Online e no OneDrive for Business via Outlook não funciona mais após a redução de locatários. |<ul><li>No SharePoint Online e no OneDrive for Business, você pode compartilhar itens por meio do Outlook. Depois de pressionar o botão do Outlook, um link compartilhável é criado e pressionado para uma nova mensagem no Outlook Web App.</li><li>Após a recorte do locatário, esse método de compartilhamento não funcionará. Reconhecemos que esse é um problema conhecido. No entanto, como esse recurso do Outlook está no caminho da precarização, a correção do problema não é planejada até que a deprecação seja aplicada. </li></ul>|
||||

## <a name="exchange-online"></a>Exchange Online
**Aplica-se a**: clientes que usam uma configuração híbrida do Exchange

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Rerun Hybrid Configuration wizard (HCW) against Office 365 services. | A configuração do HCW existente deve dar suporte ao Microsoft Cloud Deutschland. Com a migração dos serviços do Exchange concluída, desaparecemos a configuração local do Microsoft Cloud Deutschland. |<ul><li>Ação necessária. A falha ao fazer isso pode resultar em falha do serviço ou de clientes de software. Antes que a migração de caixa de correio do Exchange comece (com 5 ou mais dias de aviso), notifique os clientes de que eles devem parar e excluir quaisquer movimentações de integração ou de offboard de suas caixas de correio.  Se não o fazem, eles verão erros em suas solicitações de movimentação. </li><li>Depois que a migração de caixa de correio do Exchange for concluída, notifique os clientes de que eles podem retomar as movimentações de integração e de offboard. <br> Executar **Test-MigrationServerAvailabiilty**, um cmdlet do PowerShell, durante a migração do Exchange do Microsoft Cloud Deutschland para os serviços do Office 365 pode não funcionar. No entanto, ele funcionará corretamente depois que a migração for concluída. </li><li>Se os clientes se derem com problemas com credenciais ou autorização após a migração das caixas de correio, os usuários poderão reinserer suas credenciais de administrador local no ponto de extremidade de migração executando ou definindo o mesmo usando o Painel de Controle do `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` Exchange (ECP). </li></ul>|
