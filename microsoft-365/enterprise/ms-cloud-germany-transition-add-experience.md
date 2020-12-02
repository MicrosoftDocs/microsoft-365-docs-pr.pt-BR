---
title: Informações adicionais sobre a experiência da migração do Microsoft Cloud Alemanha
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
description: 'Resumo: informações adicionais sobre a experiência do cliente ao migrar do Microsoft Cloud Alemanha (Microsoft Cloud Alemanha) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: b282a12966e7a6dc8a1a331409834322c5087a10
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551870"
---
# <a name="additional-experience-information-for-the-migration-from-microsoft-cloud-deutschland"></a>Informações adicionais sobre a experiência da migração do Microsoft Cloud Alemanha 

As seções a seguir fornecem informações adicionais sobre as experiências dos clientes.

## <a name="services"></a>Serviços

### <a name="azure-ad"></a>Azure AD

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Locatário do Azure AD no Microsoft Cloud Alemanha copiado para os serviços do Office 365. | O Azure AD copia o locatário para os serviços do Office 365. Os identificadores de locatário e de usuário são preservados. As chamadas do serviço do Azure AD são redirecionadas do Microsoft Cloud Alemanha para os serviços do Office 365 e são transparentes para os serviços. | Todos os clientes do Office | – RGPD (regulamentação geral de proteção de dados) as solicitações de entidades de dados (DSRs) são executadas do portal de administração do Azure para futuras solicitações. Quaisquer dados de diagnóstico herdados ou não clientes residentes no Microsoft Cloud Alemanha são excluídos em ou antes de 30 dias decorridos. <br><br> – Os clientes que usam autenticações federadas com o AD FS (serviços de Federação do Active Directory) não devem fazer alterações nos URIs de emissor usados para todas as autenticações com o Active Directory local durante a migração. Alterar URIs de emissor levará a falhas de autenticação para usuários no domínio. URIs de emissor podem ser alterados diretamente no AD FS ou quando um domínio é convertido de _gerenciado_ para _federado_ e vice-versa. Recomendamos que os clientes não adicionem, removam ou convertam um domínio federado no locatário do Azure AD que tenha sido migrado. Os URIs de emissor podem ser alterados após a conclusão da migração. <br><br> -Solicitações de autenticação multifator (MFA) que usam o Microsoft Authenticator exibir como o ObjectID do usuário (um GUID) enquanto o locatário é copiado para os serviços do Office 365. As solicitações da MFA serão realizadas conforme o esperado, apesar desse comportamento de exibição.  As contas do Microsoft Authenticator que foram ativadas usando os pontos de extremidade dos serviços do Office 365 exibirão o nome principal do usuário (UPN).  As contas adicionadas usando os pontos de extremidade do Microsoft Cloud Alemanha exibirão o ObjectID do usuário, mas funcionarão com os pontos de extremidade do Microsoft Cloud Alemanha e dos serviços do Office 365.  |
| Estabeleça um AuthServer local apontando para o serviço global STS. | Isso garante que as solicitações de usuários que migrarem para o Microsoft Cloud Alemanha para as solicitações de disponibilidade do Exchange que direcionam o ambiente local híbrido sejam autenticadas para acessar o serviço local. Da mesma forma, isso garantirá a autenticação de solicitações de pontos de extremidade de serviços no local para o Office 365. | Clientes do Exchange Online com implantações híbridas (locais) | Depois que a migração do Azure AD estiver concluída, o administrador da topologia do Exchange local (híbrido) deve adicionar um novo ponto de extremidade de serviço de autenticação para os serviços do Office 365. Com este comando do Exchange PowerShell, substitua `<TenantID>` pela ID de locatário da sua organização (encontrada no portal do Azure no **Azure Active Directory**). <br><br> - `New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1` <br> <br> A conclusão dessa tarefa pode resultar em solicitações de disponibilidade híbrida que não fornecem informações para usuários de caixa de correio que foram migrados do Microsoft Cloud Alemanha para os serviços do Office 365.  |
| Migração de recursos do Azure. | Os clientes que usam os recursos do Office 365 e do Azure (por exemplo, rede, computação e armazenamento) realizarão a migração de recursos para a instância dos serviços do Office 365. Essa migração é uma responsabilidade para os clientes. As postagens do centro de mensagens sinalizarão o início. A migração deve ser concluída antes da finalização da organização do Azure AD no ambiente de serviços do Office 365. | Clientes do Azure | Para migrações do Azure, consulte o guia de migração do Azure, [visão geral da guia de migração para a Alemanha do Azure](https://docs.microsoft.com/azure/germany/germany-migration-main). |
|||||

<!--
[Reference: Experience][Data Protection] Experience][
[Reference: Experience][Federation] 
[Reference: Experience][MFA]  


[Reference: Experience – Post Migration][Hybrid]    
        

[Reference: Experience – During Migration] [Azure] 
-->

### <a name="exchange-online"></a>Exchange Online

Se você estiver usando o **set-UserPhoto**:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| A nova região da Alemanha é adicionada a uma configuração de organização existente, e as caixas de correio são movidas para os serviços do Office 365. | A configuração do Exchange Online Adiciona a nova região local do alemão à organização de transição. Esta região de serviços do Office 365 é definida como padrão, o que permite que o serviço de balanceamento de carga interno Redistribua as caixas de correio para a região padrão apropriada nos serviços do Office 365. Nessa transição, os usuários do lado (serviços da Alemanha ou do Office 365) estão na mesma organização e podem usar o ponto de extremidade de URL. |  Exchange Online | Se uma caixa de correio de usuário tiver sido migrada, mas uma caixa de correio de administrador não tiver sido migrada ou vice-versa, os administradores não poderão executar **set-UserPhoto**, um cmdlet do PowerShell. Nessa situação, um administrador deve passar uma cadeia de caracteres adicional no `ConnectionUri` durante a configuração da conexão usando a seguinte sintaxe: <br><br> `https://outlook.office.de/PowerShell-LiveID?email=<user_email>` <br><br> em que `<user_email>` é o espaço reservado para o email-ID do usuário cuja foto precisa ser alterada usando **set-UserPhoto**. |
|||||

<!--
[Reference: Experience][Exchange Online]  [if using Set-UserPhoto] 
-->  

Se você estiver usando uma implantação híbrida local:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
|Parar ou excluir qualquer movimento de integração ou remoção de caixas de correio.  | Isso garante que as solicitações de movimentação não falhem com um erro. | Clientes do Exchange Online com implantações híbridas (locais) | Ação necessária. Se isso não for feito, poderão ocorrer falhas do serviço ou de clientes de software. |
|||||

<!--
[Reference: Experience][Hybrid] 
--> 


### <a name="dynamics"></a>Dynamics

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Recursos do Microsoft Dynamics | Os clientes com o Microsoft Dynamics serão contratados pela engenharia ou pelo FastTrack para fazer a transição do Dynamics para a instância dos serviços do Office 365. * | Clientes do Microsoft Dynamics 365 | – Após a migração, o administrador valida a organização. <br><br> – O administrador modifica os fluxos de trabalho, conforme necessário. <br><br> – O administrador limpa o modo AdminOnly, conforme apropriado. <br><br> -O administrador altera o tipo de organização da _área restrita_, conforme apropriado <br><br> – Notifique os usuários finais da nova URL para acessar a instância (org). <br><br> – Atualizar conexões de entrada para a nova URL de ponto de extremidade. <br><br> – O serviço do Dynamics ficará indisponível para os usuários durante a transição. <br><br> -Os usuários precisam validar a integridade e os recursos da organização após a migração de cada organização.  |
|||||

\* (i) clientes com Microsoft Dynamics 365 devem tomar medidas neste cenário de migração, conforme definido pelo processo de migração fornecido. (II) a falha pelo cliente para tomar providências significa que a Microsoft não poderá concluir a migração. (III) quando a Microsoft não consegue concluir a migração devido à inacção do cliente, a assinatura do cliente expirará em 29 de outubro de 2021. 


### <a name="power-bi"></a>Power BI

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração de recursos do Power BI | Os clientes com o Microsoft Power BI serão contratados pelo engenharia ou pelo FastTrack após o disparo manual de uma ferramenta de migração do PBI existente para fazer a transição do Power BI para a instância dos serviços do Office 365.\*\* | Clientes do Microsoft Power BI | -Os seguintes itens do Power BI _não_ serão transicionados e terão que ser recriados: <br><br> – DataSets em tempo real (por exemplo, conjuntos de datastreams ou de envio por push). <br> – Configuração e fonte de dados do gateway de dados do Power BI local. <br> -Os relatórios criados na parte superior dos conjuntos de valores em tempo real não estarão disponíveis após a migração e precisam ser recriados. <br><br> -Os serviços do Power BI não estarão disponíveis para os usuários durante a transição. A indisponibilidade do serviço não deve ser maior que 24 horas. <br><br> -Os usuários serão solicitados a reconfigurar as fontes de dados e seus gateways de dados locais com o serviço do Power BI após a migração.  Até que isso ocorra, os usuários não poderão usar essas fontes de dados para executar atualizações agendadas e/ou consultas diretas contra essas fontes de dados. <br><br> – As capacidades e espaços de trabalho Premium não podem ser migrados. Os clientes precisam excluir todas as capacidades antes da migração e recriá-las após a migração. Mova os espaços de trabalho de volta às capacidades conforme desejado.  |
|||||

\*\* (i) clientes com o Microsoft Power BI devem executar ações neste cenário de migração, conforme definido pelo processo de migração fornecido. (II) a falha pelo cliente para tomar providências significa que a Microsoft não poderá concluir a migração. (III) quando a Microsoft não consegue concluir a migração devido à inacção do cliente, a assinatura do cliente expirará em 29 de outubro de 2021. 


### <a name="office-apps"></a>Aplicativos do Office

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Clientes, Office Online durante a substituição do cliente do Office, o Azure AD finaliza o escopo do locatário para apontar para os serviços do Office 365.<!--v-gmoor: What?--> | Essa alteração de configuração permite que os clientes do Office atualizem e apontem para os pontos de extremidade dos serviços do Office 365. | Todos os clientes do Office | -Remove MSOID CName de DNS de Propriedade do cliente, se existir. <br><br> – Notifique os usuários para fechar _todos os_ aplicativos do Office e entre novamente (ou Force os clientes a reiniciar e que os usuários façam logon) para permitir que os clientes do Office escolham a alteração. <br><br> -Notificar os usuários e a equipe de suporte técnico de que os usuários *podem* ver uma faixa do Office que solicita a reativação de aplicativos do office em 72 horas após a substituição. <br><br> – Todos os aplicativos do Office em máquinas pessoais devem ser fechados e os usuários devem sair e entrar novamente. Na barra de ativação amarela, entre para reativar para os serviços do Office 365. <br><br> -As máquinas compartilhadas exigirão ações similares às máquinas pessoais e não exigirão um procedimento especial. <br><br> -Em dispositivos móveis, os usuários devem sair de aplicativos, fechá-los e entrar novamente. |
|||||

<!--
[Reference: Experience][Office Apps]
--> 

## <a name="during-migration"></a>Durante a migração


### <a name="exchange-online"></a>Exchange Online

Para descoberta eletrônica:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Durante a migração, as pesquisas de descoberta eletrônica falharão ou retornarão 0 resultados para os locais do SharePoint Online, do OneDrive for Business e do Exchange Online que foram migrados. | Durante a migração, os clientes podem continuar a criar casos, isenções, pesquisas e exportações no centro de conformidade & segurança, incluindo pesquisa de conteúdo.  No entanto, as pesquisas nos locais do SharePoint Online, do OneDrive for Business e do Exchange Online que foram migradas retornarão 0 resultados ou produzirão um erro. Para correção, confira a coluna _impacto_ . | Todos os clientes que usam o eDiscovery |  No caso de uma pesquisa retornar 0 resultados ou um erro durante a migração, execute a seguinte ação para o SharePoint Online: <br><br>  Baixe sites diretamente do site do SharePoint Online/OneDrive for Business seguindo as instruções em [baixar arquivos e pastas do onedrive ou do SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05). Esse método exigirá permissões de administrador do SharePoint Online ou permissões somente leitura no site. <br><br> Se os limites forem excedidos, conforme explicado em [baixar arquivos e pastas do onedrive ou do SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), os clientes podem usar o cliente de sincronização do onedrive for Business seguindo as orientações em [sincronizar arquivos do SharePoint e do teams com o seu computador](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88). <br><br> -Exchange Online <br><br> - [Descoberta eletrônica in-loco no Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/ediscovery/ediscovery) |
|||||

<!--
[Reference: Experience – During Migration][ [eDiscovery]
-->          


### <a name="sharepoint-online"></a>SharePoint Online

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| O SharePoint e o OneDrive estão em transição. | O SharePoint e o OneDrive são migrados do Microsoft Cloud Alemanha para os serviços do Office 365 nesta fase. As URLs de Alemanha do Microsoft Cloud existentes são preservadas ( `contoso.sharepoint.de` ). Tokens emitidos pelo Microsoft Cloud Alemanha ou os serviços do Office 365 são válidos durante a transição. | Clientes do SharePoint | Os fluxos de trabalho do Inflight SharePoint 2013 serão desfeitos durante a migração e deverão ser publicados novamente após a migração. |
|||||

<!--
[Reference: Experience – During Migration][ [SPO]
-->  

### <a name="skype-for-business-online"></a>Skype for Business Online

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração do Skype for Business para o Microsoft Teams. | Os clientes existentes do Skype for Business são migrados para os serviços do Office 365 na Europa e, em seguida, transferidos para o Microsoft Teams na região da Alemanha dos serviços do Office 365. | Clientes do Skype for Business |  O PowerShell usará para administrar as configurações e políticas para seus locatários e usuários. Ao se conectar a uma sessão do PowerShell, adicione o seguinte: <br><br> `-OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"` |
|||||

<!--
[Reference: Experience – During Migration][ [SfBO]
-->  


## <a name="post-migration"></a>Pós-migração

### <a name="azure-ad"></a>Azure AD

Para o híbrido:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Atualize o Azure AD Connect. | Depois que o recorte para o Azure AD estiver concluído, a organização estará totalmente usando os serviços do Office 365 e não estará mais conectado ao Microsoft Cloud Alemanha. Neste ponto, o cliente precisa garantir que o processo de sincronização Delta tenha sido finalizado e depois disso, altere o valor da cadeia de caracteres de `AzureInstance` 3 (Microsoft Cloud Alemanha) para 0 no caminho do registro `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` . | Organizações híbridas conectadas ao Azure AD | Altere o valor de `AzureInstance` , a chave do registro. Se isso não for feito, o levará a objetos que não estão sendo sincronizados depois que os pontos de extremidade do Microsoft Cloud Alemanha não estão mais disponíveis. |
|||||

<!--
[Reference: Experience – Post Migration][Hybrid]
--> 

Para autenticação federada:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Remover as relações de confiança de terceira parte confiável do Microsoft Cloud Alemanha AD FS. | Depois que o recorte para o Azure AD estiver concluído, a organização estará totalmente usando os serviços do Office 365 e não estará mais conectado ao Microsoft Cloud Alemanha. Neste ponto, o cliente precisa remover o confiança da terceira parte confiável para os pontos de extremidade do Microsoft Cloud Alemanha. Isso só pode ser feito quando nenhum aplicativo do cliente aponta para pontos de extremidade do Microsoft Cloud Alemanha quando o Azure AD é aproveitado como um provedor de identidade (IdP). | Organizações de autenticação federada | Nenhum |
|||||

<!--
[Reference: Experience – Post Migration][Federated]
-->             

Para o Azure AD:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| As solicitações para ingressar em um grupo do Azure AD nos últimos 30 dias antes da migração precisarão ser solicitadas novamente se a solicitação original não for aprovada. | Os clientes de usuário final precisarão usar o painel de acesso para enviar solicitação para ingressar em um grupo do Azure AD novamente se essas solicitações não foram aprovadas nos últimos 30 dias antes da migração. | Usuários finais cujas solicitações de aprovação de grupo do Azure AD não foram aprovadas nos últimos 30 dias antes da migração |  Como usuário final: <ol><li>Navegue até o [painel de acesso](https://account.activedirectory.windowsazure.com/r#/joinGroups).</li><li>Encontre um grupo do Azure AD para o qual a aprovação de associação estava pendente em 30 dias antes da migração.</li><li>Solicite o ingresso no grupo do Azure AD novamente.</li></ol> As solicitações para ingressar em um grupo que estão ativos menos de 30 dias antes da migração não podem ser aprovadas, a menos que sejam resolicitadas após a migração. |
|||||

<!--
[Reference: Experience – Post Migration][Azure AD]
--> 

Para DNS:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Atualize os serviços DNS locais para pontos de extremidade de serviços do Office 365. | As entradas DNS gerenciadas pelo cliente que apontam para o Office 365 Alemanha precisam ser atualizadas para apontar para os pontos de extremidade dos serviços do Office 365. | Todos os clientes do Office | Ação necessária. Se isso não for feito, poderão ocorrer falhas do serviço ou de clientes de software. |
|||||

<!--
 [Reference: Experience – Post Migration][DNS]
-->

Para serviços de terceiros para pontos de extremidade de serviços do Office 365:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Atualizar parceiros e serviços de terceiros para pontos de extremidade de serviços do Office 365. | -Os serviços e parceiros de terceiros que apontam para o Office 365 Alemanha precisam ser atualizados para apontar para os pontos de extremidade dos serviços do Office 365. Exemplo: registrar novamente, em alinhamento com seus fornecedores e parceiros, a versão do aplicativo da Galeria de aplicativos, se disponível. <br><br> -Aponte todos os aplicativos personalizados que utilizam a API do Graph de `graph.microsoft.de` para o `graph.microsoft.com` . Outras APIs com pontos de extremidade alterados também precisam ser atualizadas, se forem aproveitadas. <br><br> -Altere todos os aplicativos corporativos que não são de terceiros para redirecionar para os pontos de extremidade mundiais.  | Todos os clientes do Office | Ação necessária. Se isso não for feito, poderão ocorrer falhas do serviço ou de clientes de software. |
|||||

<!--
 [Reference: Experience – Post Migration][]
--> 

### <a name="exchange-online"></a>Exchange Online

Se você estiver usando uma configuração híbrida do Exchange:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Execute o assistente de configuração híbrida (HCW) em serviços do Office 365. | A configuração do HCW existente é destinada a oferecer suporte ao Microsoft Cloud Alemanha. Com a migração dos serviços do Exchange concluída, desassociamos a configuração local do Microsoft Cloud Alemanha. | Clientes do Exchange Online que estão executando uma implantação híbrida | -Ação necessária. Se isso não for feito, poderão ocorrer falhas do serviço ou de clientes de software. Antes do início da migração de caixa de correio do Exchange (com 5 ou mais dias de aviso), notifique os clientes de que eles devem interromper e excluir as movimentações de integração ou remoção de suas caixas de correio.  Caso contrário, eles verão os erros em suas solicitações de movimentação. <br><br> – Após a conclusão da migração de caixa de correio do Exchange, notifique os clientes de que eles podem retomar a integração e a remoção de remoções. <br> Executar **Test-MigrationServerAvailabiilty**, um cmdlet do PowerShell, durante a migração do Exchange do Microsoft Cloud Alemanha para os serviços do Office 365 pode não funcionar. No entanto, ele funcionará corretamente após a conclusão da migração. <br><br> Se os clientes estiverem em problemas com credenciais ou autorização após a migração das caixas de correio, os usuários poderão inserir novamente as credenciais de administrador local no ponto de extremidade de migração executando `Set-MigrationEndpoint endpointName -Credential $(Get-Credential)` o ou definindo o mesmo usando o painel de controle do Exchange (ECP).  |

<!--
[Reference: Experience – Post Migration][Hybrid]  
[Reference: Experience – Post Migration][Exchange Online]
--> 

Para descoberta eletrônica:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
|  Todos os locais do SharePoint Online, do OneDrive for Business e do Exchange Online foram migrados junto com o centro de segurança e conformidade (SCC). | Todas as atividades de descoberta eletrônica devem ser executadas do locatário mundial. As pesquisas agora terão 100% bem-sucedidas.  Qualquer falha ou erro deve seguir os canais de suporte normais. | Todos os clientes que usam eDiscovery | Nenhum |
| Remover políticas de retenção em toda a organização que foram criadas durante as etapas de pré-migração | Os clientes podem remover as políticas de retenção em toda a organização que foram criadas durante o trabalho de pré-migração dos clientes. | Todos os clientes que aplicaram uma política de retenção como parte das etapas de pré-migração. | Nenhum |
|||||

<!--
 [Reference: Experience – Post Migration][ [eDiscovery]             

[Reference: Experience – Post Migration][ [eDiscovery]
-->             

### <a name="sharepoint-online"></a>SharePoint Online

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Republicar fluxos de trabalho do SharePoint 2013. | No trabalho anterior à migração, reduzimos o número de fluxos de trabalho do SharePoint 2013. Agora, com a migração concluída, o cliente pode republicar os fluxos de trabalho. | Todos os clientes do Office | Essa é uma ação obrigatória. Se isso não for feito, poderá resultar em uma confusão do usuário e em chamadas de suporte técnico. |
| Compartilhar itens via Outlook | O compartilhamento de itens via Outlook não funciona mais após a substituição do locatário. | SharePoint Online e OneDrive for Business | -No SharePoint Online e no OneDrive for Business, você pode compartilhar itens através do Outlook. Após pressionar o botão do Outlook, um link compartilhável é criado e enviado para uma nova mensagem no Outlook Web App. <br><br> – Após a transferência de locatário, esse método de compartilhamento não funcionará. Reconhecemos que esse é um problema conhecido. No entanto, como esse recurso do Outlook está no caminho da substituição, a correção do problema não é planejada até que a substituição seja distribuída. |

<!--
 [Reference: Experience – Post Migration][ [SPO]
-->

## <a name="next-step"></a>Próxima etapa

[Entender ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Mais informações

Introdução:

- [Migração do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Mover-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [Serviços](ms-cloud-germany-transition-add-general.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
