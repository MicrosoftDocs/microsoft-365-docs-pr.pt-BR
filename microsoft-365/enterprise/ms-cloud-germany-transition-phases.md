---
title: Ações e impactos de fases de migração para a migração do Microsoft Cloud Deutschland)
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
ms.openlocfilehash: 8e3e6fb228445823481b52d27e5a7b6c623349e2
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995016"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland"></a>Ações e impactos de fases de migração para a migração do Microsoft Cloud Deutschland

As migrações de locatários do Microsoft Cloud Deutschland (MCD) para a região "Alemanha" dos serviços Globais do Office 365 da Microsoft são executadas como um conjunto de fases e suas ações configuradas para cada carga de trabalho. Esta figura mostra as dez fases de migração para os novos datacenters alemães.

![As dez fases de migração para os novos datacenters da Alemanha](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

O processo de migração será concluído ao longo de muitas semanas, dependendo do tamanho geral e da complexidade da organização. Enquanto a migração está em andamento, os usuários e administradores podem continuar utilizando os serviços com alterações notáveis detalhadas nesta documentação. O gráfico e a tabela definem fases e etapas durante a migração.

|Etapa|Duration|Responsável|Descrição|
|:--------|:--------|:--------|:--------|
|Opt-In|Horas|Cliente|Opte pela sua organização na migração.|
|Pré-trabalho|Days|Cliente|Conclua o trabalho necessário para preparar usuários, estações de trabalho e rede para migração.|
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
|Pontos de extremidade desabilitados|30 dias|Microsoft|30 dias após a finalização do Azure AD, o serviço do Microsoft Cloud Deutschland Azure AD interromperá o acesso ao ponto de extremidade para a organização em transição. As solicitações de ponto de extremidade, como Autenticação, falharão deste ponto em diante em relação ao serviço Microsoft Cloud Deutschland. |


As fases e suas ações garantem que dados críticos e experiências sejam migrados para os serviços Globais do Office 365. Depois que o locatário for adicionado à fila de migração, cada carga de trabalho será concluída como um conjunto de etapas executadas no serviço de back-end. Algumas cargas de trabalho podem exigir ações do administrador (ou do usuário) ou a migração pode afetar o uso das fases executadas e discutidas em Como a migração [é organizada?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

As seções a seguir contêm ações e efeitos para cargas de trabalho à medida que elas passam por várias fases da migração. Revise as tabelas e determine quais ações ou efeitos são aplicáveis à sua organização. Verifique se você está preparado para executar as etapas nas respectivas fases, conforme necessário. A falha na conclusão das etapas necessárias pode resultar em interrupção de serviço e pode atrasar a conclusão da migração para os serviços do Office 365.

## <a name="phase-opt-in"></a>Fase: Opt-In

**Aplica-se** a : Todos os clientes com um locatário do Office 365 hospedado no Microsoft Cloud Deutschland (MCD) A Microsoft não pode migrar locatários do Office 365 hospedados no MCD sem consentimento.

| Step(s) | Descrição | Impacto |
|:-------|:-----|:-------|
|**Tarefa do cliente**: conceder consentimento para migração| O cliente concede consentimento para a migração para que a Microsoft obtém o direito de migrar e de orquestrar a transição de dados e serviços para a instância dos serviços Globais do Office 365. Há duas maneiras <ol><li>O administrador de locatários do Office 365 opta pela migração orientada pela Microsoft. </li><li> Os clientes renovaram quaisquer assinaturas em seu locatário do MCD Office 365 após 1º de maio de 2020. A Microsoft notifica esses clientes sobre o direito de migração a cada mês, espera 30 dias para dar aos clientes a chance de cancelar e, em seguida, optar diretamente.</li></ol> | <ul><li>O locatário é marcado como consentido para migração, e o Centro de Administração exibe a confirmação. </li><li>O reconhecimento é postado no Centro de Mensagens do locatário do Office 365. A configuração do serviço continua dos pontos de extremidade do Microsoft Cloud Deutschland. </li><li> </li></ul>
|**Administrador de Locatários**: Monitorar mensagens|O administrador de locatários deve monitorar o Centro de Mensagens do Office 365 para atualizações sobre o status da fase de migração a partir deste momento.|O cliente pode executar as tarefas necessárias a tempo.
||||

## <a name="phase-1-before-the-migration-starts"></a>Fase 1: antes da migração começar

Certifique-se de que você está familiarizado com as etapas de preparação de [migração que se aplicam a todos os clientes](ms-cloud-germany-transition-add-pre-work.md).

Caso você tenha definido um CNAME DNS chamado _msoid_ em um ou muitos namespaces DNS que você possui, você precisa remover o CNAME até o final da fase 8 no máximo. Você pode remover o _msoid_ CNAME a qualquer momento antes do final da fase 8. Consulte o [pré-trabalho para DNS](ms-cloud-germany-transition-add-pre-work.md#dns-entries-for-custom-domains).

Caso você use o login único para o Office 365 e o Azure na instância do Microsoft Cloud Deutschland, você deve preparar e agendar a migração de assinatura do Azure de acordo. Certifique-se de entender o [pré-trabalho do Microsoft Azure](ms-cloud-germany-transition-add-pre-work.md#microsoft-azure).

### <a name="azure-ad-connect-with-ad-fs-federation"></a>Azure AD Connect com federação do AD FS
**Aplica-se a**: Clientes com federação do AD FS

**Quando aplicado:** antes da fase 2 ser iniciada

Se você estiver usando os Serviços de Federação do Active Directory (AD FS), certifique-se de fazer o back  up da configuração do [ADFS](ms-cloud-germany-transition-azure-ad.md) antes e depois de adicionar a confiança de parte confiável para o serviço Global do Office 365 antes do início da fase 2.

## <a name="phase-2-azure-ad-migration"></a>Fase 2: Migração do Azure AD
Nesta fase, o Azure Active Directory será migrado para a nova região do datacenter e se tornará ativo. Os pontos de extremidade antigos do Azure AD ainda estarão disponíveis.

### <a name="exchange-online-hybrid---modify-authserver-on-premises"></a>Exchange Online Híbrido - Modificar o AuthServer local
**Aplica-se a:** Todos os clientes que usam uma configuração híbrida ativa do Exchange com servidores Exchange locais

**Quando aplicado :** após o final da fase 2

O AuthServer local deve estar apontando para STS (Serviço de Token de Segurança) global para autenticação após a conclusão da migração do Azure AD.
Isso garante que as solicitações de autenticação para solicitações de disponibilidade do Exchange de usuários em estado de migração destinados ao ambiente local híbrido sejam autenticadas para acessar o serviço local. Da mesma forma, isso garantirá a autenticação de solicitações do local para os pontos de extremidade dos serviços globais do Office 365. Depois que a migração do Azure AD (fase 2) for concluída, o administrador da topologia local do Exchange (híbrido) deverá adicionar um novo ponto de extremidade do serviço de autenticação para os serviços Globais do Office 365. Com este comando do Exchange PowerShell, substitua pela ID de locatário da sua organização encontrada no portal do `<TenantID>` Azure no Azure Active Directory.

```powershell
New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantID>/metadata/json/1
```

A falha na conclusão dessa tarefa pode resultar em solicitações híbridas de ocupado livre que não fornecem informações para usuários de caixa de correio que foram migrados do Microsoft Cloud Deutschland para os serviços do Office 365.

## <a name="phase-3-subscription-transfer"></a>Fase 3: Transferência de assinatura

**Aplica-se a**: Todos os clientes com um locatário do Office 365 hospedado no Microsoft Cloud Deutschland (MCD)

Os locatários do Microsoft Cloud Deutschland parceiros não serão migrados. Os clientes CSP serão migrados para serviços do Office 365 sob o novo locatário de serviços do Office 365 do mesmo parceiro. Após a migração do cliente, o parceiro pode gerenciar esse cliente somente a partir do locatário de serviços do Office 365.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Assinaturas são transferidas| A assinatura do Microsoft Cloud Deutschland será migrada para a assinatura correspondente dos serviços globais do Office 365. <ul><li>A oferta de serviços globais do Office 365 dessa assinatura é definida pela Microsoft (também conhecida como mapeamento _de oferta)._</li><li> As assinaturas correspondentes dos serviços globais do Office 365 são compradas na instância Global do Office 365 para as assinaturas transferidas do Microsoft Cloud Deutschland.</li><li>As assinaturas herdada do Microsoft Cloud Deutschland são removidas do locatário de serviços do Office 365 após a conclusão.</li></ul>| <ul><li>As alterações nas assinaturas existentes serão bloqueadas (por exemplo, nenhuma nova compra de assinatura ou alterações na contagem de assentos) durante essa fase.</li><li>As alterações de atribuição de licença serão bloqueadas.</li><li>Quando a migração de assinatura for concluída, tanto os serviços do Office 365 quanto as assinaturas do Microsoft Cloud Deutschland estarão visíveis no Portal de Administração do Office 365, com o status das assinaturas do Microsoft Cloud Deutschland _como desprovisionadas_. </li><li>Todos os processos do cliente que tenham dependências de assinaturas do Microsoft Cloud Deutschland ou GUIDs SKU serão desfeitos e precisarão ser revisados com a oferta de serviços do Office 365. </li><li>Novas assinaturas nos serviços do Office 365 serão compradas com o novo termo (mensal/trimestral/anual) e o cliente receberá um reembolso prorável para o saldo não usado da assinatura do Microsoft Cloud Deutschland. </li></ul> |
|As licenças são reatribuídas|Os usuários com licenças do Microsoft Cloud Deutschland atribuídas receberão licenças na instância Global do Office 365.|<ul><li>Os usuários serão reatribuídos licenças vinculadas às novas assinaturas de serviços do Office 365. As licenças de usuário de todos os usuários serão atribuídas automaticamente aos novos recursos.</li><li>O número de recursos (planos de serviço) oferecidos pelos serviços do Office 365 pode ser maior do que na oferta original do Microsoft Cloud Deutschland. As licenças de usuário nos serviços do Office 365 serão atribuídas equivalentemente a recursos semelhantes do Microsoft Cloud Deutschland (planos de serviço). </li></ul> 
|**Tarefa de administrador** Desabilitar recursos|O administrador precisa tomar uma ação explícita para desabilitar esses recursos, se necessário. |<ul><li>Os usuários veem novos serviços desconhecidos no portal</li><li>A funcionalidade adicional está disponível (por exemplo, Microsoft Planner e Microsoft Flow), a menos que seja desabilitada pelo administrador de locatários. Para obter informações sobre como desabilitar planos de serviço atribuídos às licenças dos usuários, consulte [Disable access to Microsoft 365 services while assigning user licenses](disable-access-to-services-while-assigning-user-licenses.md).</li></ul>
|**Tarefa de administrador**|Revise todos os processos do cliente que tenham dependências de assinaturas do Microsoft Cloud Deutschland ou guids SKU com a oferta de serviços do Office 365|Os processos do cliente continuam a funcionar.
||||

**Aplica-se a**: Parceiros da Microsoft que estão usando o Portal de Parceiros do Office 365

Entre a Fase 2 e a fase 3, o Partner Portal pode não estar acessível. Durante esse tempo, o Parceiro pode não conseguir acessar as informações do locatário no Portal do Parceiro. Como cada migração é diferente, a duração da acessibilidade pode ser em horas.


## <a name="phase-4-sharepoint-online"></a>Fase 4: SharePoint Online

**Aplica-se a**: todos os clientes que usam o SharePoint Online

Caso você ainda esteja usando fluxos de trabalho do SharePoint 2013, limite o uso de fluxos de trabalho do SharePoint 2013 durante a migração do SharePoint Online.

| Step(s) | Descrição | Impacto |
|:-------|:-----|:-------|
| SharePoint e OneDrive são transições | O SharePoint Online e o OneDrive for Business são migrados do Microsoft Cloud Deutschland para os serviços globais do Office 365 nesta fase.<br><ul><li>As URLs existentes do Microsoft Cloud Deutschland são preservadas (por exemplo, `contoso.sharepoint.de` ).</li><li>Os sites existentes são preservados.</li><li>Os tokens de autenticação do lado do cliente que foram emitidos pelo Serviço de Token de Segurança (STS) na instância de serviços Globais do Microsoft Cloud Deutschland ou office 365 são válidos durante a transição.</li></ul>|<ul><li>O conteúdo será somente leitura por dois breves períodos durante a migração. Durante esse tempo, espere um banner "você não pode editar conteúdo" no SharePoint.</li><li>O índice de pesquisa não será preservado e pode levar até 10 dias para ser reconstruído.</li><li>O conteúdo do SharePoint Online e do OneDrive for Business será somente leitura por dois breves períodos durante a migração. Os usuários verão um banner "você não pode editar conteúdo" brevemente durante esse tempo.</li><li>Após a conclusão da migração do SharePoint Online, os resultados da pesquisa para o conteúdo do SharePoint Online e do OneDrive for Business podem ficar indisponíveis enquanto o índice é reconstruído. Durante esse período, as consultas de pesquisa podem não retornar resultados completos. Recursos que dependem dos índices de pesquisa, como o SharePoint Online News, podem ser afetados enquanto a reindexação é concluída.</li><li>Os fluxos de trabalho do SharePoint 2013 serão interrompidos durante a migração e devem ser republicados após a migração.</li></ul>
|**Administrador de SPO**: Republicar fluxos de trabalho do SharePoint 2013| Um administrador do SharePoint Online republica os fluxos de trabalho do SharePoint 2013 após a migração.|Os fluxos de trabalho do SharePoint 2013 estão disponíveis.
|**Usuário do PowerShell**: atualizar para novo módulo| Todos os usuários do módulo do Powershell do SharePoint Online precisam atualizar o módulo/Microsoft.SharePointOnline.CSOM para a versão 16.0.20717.12000 ou superior após a conclusão da migração do SharePoint Online. A conclusão é comunicada no centro de mensagens.| O SharePoint Online via PowerShell ou o modelo de objeto do lado do cliente não falhará mais.
||||

Considerações adicionais:

- Se sua organização ainda usa fluxos de trabalho do SharePoint 2010, eles não funcionarão mais após 31 de dezembro de 2021. Os fluxos de trabalho do SharePoint 2013 permanecerão com suporte, embora desligados por padrão para novos locatários a partir de 1º de novembro de 2020. Após a migração para o serviço do SharePoint Online ser concluída, recomendamos que você mude para o Power Automate ou outras soluções com suporte.
 - Os clientes do Microsoft Cloud Deutschland cuja instância do SharePoint Online ainda não foi migrada precisam permanecer no módulo do PowerShell do SharePoint Online/Microsoft.SharePointOnline.CSOM versão 16.0.20616.12000 ou abaixo. Caso contrário, as conexões com o SharePoint Online via PowerShell ou o modelo de objeto do lado do cliente falharão.
- Durante essa fase, os endereços IP por trás das URLs do SharePoint mudarão. Após a transição para os serviços Globais do Office 365, os endereços para as URLs de locatário preservadas (por exemplo, e ) serão alterados para as URLs e intervalos de endereço IP do Microsoft 365 em todo o mundo `contoso.sharepoint.de` `contoso-my.sharepoint.de` [(SharePoint Online e OneDrive for Business)](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide#sharepoint-online-and-onedrive-for-business).

> [!NOTE]
> Caso esteja usando a Descoberta eDiscovery, certifique-se de estar ciente da experiência de [migração de Descoberta e.](ms-cloud-germany-transition-add-scc.md)

## <a name="phase-5-exchange-online"></a>Fase 5: Exchange Online 
A partir da fase 5, as caixas de correio do Exchange Online são movidas do Microsoft Cloud Deutschland para os serviços Globais do Office 365.

A região de serviços globais do Office 365 é definida como padrão, o que permite que o serviço de balanceamento de carga interno redistribua caixas de correio para a região padrão apropriada nos serviços do Office 365. Nesta transição, os usuários de ambos os lados (mcd ou serviços globais) estão na mesma organização e podem usar o ponto de extremidade da URL.

A nova região "Alemanha" é adicionada à configuração da organização. A configuração do Exchange Online adiciona a nova região go-local alemã à organização em transição.

- Transições de usuários e serviços de suas URLs MCD herdados ( ) para novas URLs de serviços do `https://outlook.office.de` Office 365 ( `https://outlook.office365.com` ).
-  Os serviços do Exchange Online (Outlook Web Access e Centro de Administração do Exchange) para a nova região do datacenter alemão estarão disponíveis nesta fase, eles não estarão disponíveis antes.
- Os usuários podem continuar a acessar o serviço por meio de URLs MCD herdados durante a migração, no entanto, eles precisam parar de usar as URLs herdados na conclusão da migração.
- Os usuários devem fazer a transição para o uso do portal do Office mundial para recursos do Office Online (Calendário, Email, Pessoas). A navegação para serviços que ainda não foram migrados para os serviços do Office 365 não funcionará até que sejam migrados. 
- Essa limitação também se aplica a serviços em segundo plano, como "Minha Conta". Minha conta para serviços globais ficará disponível após a conclusão da fase 9. Até isso, os usuários devem usar o portal MCD para gerenciar suas configurações de conta.
- O Outlook Web App não fornecerá a experiência de pasta pública durante a migração.

Se você deseja modificar as fotos do usuário durante a fase 5, consulte Exchange Online PowerShell - Set-UserPhoto [durante a fase 5](#exchange-online-powershell).

### <a name="dns-record-for-autodiscover-in-exchange-online"></a>Registro DNS para Descoberta Automática no Exchange Online
**Aplica-se a:** Clientes que usam o Exchange Online com um domínio personalizado

As configurações de DNS gerenciadas pelo cliente para Descoberta Automática que apontam para o Microsoft Cloud Deutschland precisam ser atualizadas para se referir ao ponto de extremidade Global do Office 365 na conclusão da fase do Exchange Online (fase 5). <br> Entradas DNS existentes com CNAME apontando para autodiscover-outlook.office.de precisam ser atualizadas para apontar para **autodiscover.outlook.com**.

Os clientes que não realizarem essas atualizações DNS após a conclusão da fase de migração **9** podem ter problemas de serviço quando a migração for finalizada.

> [!NOTE]
> Erros de validação no Centro de Administração para domínios personalizados para a entrada descoberta automática podem ser ignorados. Os serviços funcionarão corretamente somente quando o registro CNAME tiver sido alterado para autodiscover.outlook.com.

### <a name="exchange-online-powershell"></a>PowerShell do Exchange Online
**Aplica-se a:** Administradores do Exchange Online usando o PowerShell do Exchange Online

Durante a fase de migração, o uso dos cmdlets Do PowerShell **New-MigrationEndpoint,** **Set-MigrationEndpoint** e **Test-MigrationsServerAvailability** pode resultar em erros (erro no proxy). Isso acontece quando a caixa de correio de arbitragem foi migrada para todo o mundo, mas a caixa de correio do administrador não foi ou vice-versa. Para resolver isso, ao criar a sessão do Locatário do PowerShell, use a caixa de correio de arbitragem como a dica de roteamento **no ConnectionUri**. Por exemplo:

```powershell
New-PSSession 
    -ConfigurationName Microsoft.Exchange 
    -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@<tenant>.onmicrosoft.de"
    -Credential $UserCredential
    -Authentication Basic
    -AllowRedirection
```
O uso do cmdlet **Set-UserPhoto** do PowerShell resulta em um erro se uma caixa de correio de usuário foi migrada, mas uma caixa de correio de administrador não foi migrada ou vice-versa. Nessa situação, um administrador deve passar a ID de email do usuário cuja foto precisa ser alterada durante a criação da sessão `ConnectionUri` do PowerShell de locatário: 
```powershell
-ConnectionUri "https://outlook.office.de/powershell-liveid?email=<user_email>" 
```
 onde `<user_email>` é o espaço reservado para a ID de email da caixa de correio do usuário. 

Considerações adicionais:
- Os usuários do Outlook Web App que acessam uma caixa de correio compartilhada em outro ambiente (por exemplo, um usuário no ambiente MCD acessa uma caixa de correio compartilhada no ambiente Global) serão solicitados a autenticar uma segunda vez. O usuário deve primeiro autenticar e acessar sua caixa de correio em , em seguida, abrir a caixa de correio `outlook.office.de` compartilhada que está em `outlook.office365.com` . Eles precisarão autenticar uma segunda vez ao acessar os recursos compartilhados hospedados no outro serviço.
- Para clientes existentes do Microsoft Cloud Deutschland ou aqueles em transição, quando uma caixa de correio compartilhada é adicionada ao Outlook usando Arquivo **> Informações > Adicionar** Conta , a exibição de permissões de calendário pode falhar (o cliente do Outlook tenta usar a API Rest `https://outlook.office.de/api/v2.0/Me/Calendars` ). Os clientes que quiserem adicionar uma conta para exibir permissões de calendário podem adicionar a chave do Registro conforme descrito em Alterações de experiência do usuário para compartilhar um calendário no [Outlook](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) para garantir que essa ação seja bem-sucedida. Essa chave do Registro pode ser implantada em toda a organização usando a Política de Grupo.
- Todos os clientes que usam uma Configuração Híbrida ativa do Exchange não são capazes de mover caixas de correio do Exchange Server local para o Exchange Online, nem para o Microsoft Cloud Deutschland, nem para a nova região do datacenter na Alemanha. Os clientes precisam garantir que as movimentações de caixa de correio em andamento tenham sido concluídas antes da fase 5 e serão retomadas após a conclusão desta fase.
- Certifique-se de que todos os usuários que usam protocolos herdados (POP3/IMAP4/SMTP) para seus dispositivos estão preparados para alterar os pontos de extremidade em seu cliente depois que a caixa de correio do Exchange for movida para a nova região do datacenter alemão, conforme descrito nas etapas de [pré-migração](ms-cloud-germany-transition-add-pre-work.md#exchange-online)do Exchange Online.
- O agendamento de reuniões do Skype for Business no Outlook Web App não está mais disponível após a migração da caixa de correio. Se necessário, os usuários terão que usar o Outlook.

Para saber mais sobre as diferenças para as organizações na migração e depois que os recursos do Exchange Online são migrados, revise as informações na experiência do cliente durante a migração para os serviços do [Office 365](ms-cloud-germany-transition-experience.md)nas novas regiões do datacenter alemão.

## <a name="phase-6-exchange-online-protection--security-and-compliance"></a>Fase 6: Proteção do Exchange Online / Segurança e Conformidade

**Aplica-se a:** Todos os clientes que usam o Exchange Online<br>

Os recursos de Proteção do Exchange Online de back-end (EOP) são copiados para a nova região "Alemanha". O Exchange Online habilita o roteamento de hosts externos para o Office 365 e detalhes históricos do locatário estão sendo migrados, o que também inclui serviços back-end para recursos de Segurança e Conformidade.

Os clientes que usam apenas recursos do Exchange Online (não híbridos) não precisam prestar atenção neste estágio.

### <a name="exchange-online-hybrid-deployments"></a>Implantações híbridas do Exchange Online
**Aplica-se a:** Todos os clientes que usam uma configuração híbrida ativa do Exchange com servidores Exchange locais

Certifique-se [de que o pré-trabalho](ms-cloud-germany-transition-add-pre-work.md#exchange-online-hybrid-customers) do Exchange tenha sido aplicado antes do início da etapa de migração **5**. Os clientes híbridos do Exchange Online devem executar a versão mais recente do Assistente de Configuração Híbrida do Exchange (HCW) no modo "Office 365 Germany" para preparar a configuração local para a migração para os serviços globais do Office 365.

**Ações de administrador:**
- Entre o início da fase de migração 6 e a conclusão da fase de migração 9 (quando o aviso do Centro de Mensagens é publicado), você precisa executar o HCW novamente usando as configurações do Office 365 Worldwide para apontar seus sistemas locais para os serviços Globais do Office 365. A falha na conclusão dessa tarefa antes da fase 9 [Conclusão da Migração] pode resultar em NDRs para emails roteados entre sua implantação local do Exchange e o Office 365.
- Pare ou exclua qualquer movimentação de caixa de correio de integração ou de offboard, ou seja, não mova caixas de correio entre o Exchange local e o Exchange Online.  Isso garante que as solicitações de movimentação de caixa de correio não falhem com um erro. A falha ao fazer isso pode resultar em falha do serviço ou dos clientes do Office.
- Os Send-Connectors que foram criados além do conector criado pelo HCW e que estão direcionando para o Exchange Online devem ser atualizados nesta fase imediatamente após a execução do HCW ter sido executado, caso contrário, eles param de funcionar. O domínio TLS deve ser atualizado para esses Conectores de Envio. <br> Para atualizar o domínio TLS, use o seguinte comando do PowerShell em seu Exchange Server ambiente:
```powershell
Set-SendConnector -Identity <SendConnectorName> -TlsDomain "mail.protection.outlook.com"
```

## <a name="phase-7-skype-for-business-online"></a>Fase 7: Skype for Business Online

**Aplica-se a:** Todos os clientes que usam o Skype for Business Online

Revise as [etapas de pré-migração para a](ms-cloud-germany-transition-add-pre-work.md#skype-for-business-online) migração do Skype for Business Online e certifique-se de concluir todas as etapas.
Nesta fase, o Skype for Business será migrado para o Microsoft Teams. Os clientes existentes do Skype for Business são migrados para os serviços Globais do Office 365 na Europa e, em seguida, fazem a transição para o Microsoft Teams na região "Alemanha" dos serviços do Office 365.

- Os usuários não poderão entrar no Skype for Business na data de migração. Dez dias antes da migração, o cliente receberá uma mensagem no Centro de Administração que anuncia quando a migração ocorrerá e novamente quando a migração começar.
- A configuração da política é migrada.
- Os usuários serão migrados para o Teams e não terão mais acesso ao Skype for Business após a migração.
- Os usuários devem ter o cliente da área de trabalho do Microsoft Teams instalado. A instalação ocorrerá durante os 10 dias por meio de política na infraestrutura do Skype for Business, mas, se isso falhar, os usuários ainda precisarão baixar o cliente ou se conectar a um navegador com suporte.
- Contatos e reuniões serão migrados para o Microsoft Teams.
- Os usuários não poderão entrar no Skype for Business entre as transições de serviço de tempo para os serviços do Office 365 e não até que as entradas DNS do cliente sejam concluídas.
- Contatos e reuniões existentes continuarão a funcionar como reuniões do Skype for Business.
- A versão do navegador da Web do Microsoft Teams não funcionará após a conclusão da fase 9.

Se você tiver que se conectar ao Skype for Business Online com o PowerShell após a conclusão da fase de migração 9, use o seguinte código do PowerShell para se conectar:

```powershell
Import-Module MicrosoftTeams
$userCredential = Get-Credential
Connect-MicrosoftTeams -Credential $userCredential -OverridePowershellUri "https://admin4E.online.lync.com/OcsPowershellOAuth"
```

## <a name="phase-8-dynamics-365"></a>Fase 8: Dynamics 365

**Aplica-se a:** Todos os clientes que usam o Microsoft Dynamics 365

Certifique-se de que você está familiarizado com o pré-trabalho do procedimento de instalação do [Microsoft Dynamics 365.](ms-cloud-germany-transition-add-pre-work.md#dynamics365)

Os clientes com o Dynamics 365 exigem envolvimento adicional para migrar as organizações do Dynamics da organização de forma independente.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Recursos do Microsoft Dynamics | Os clientes com o Microsoft Dynamics serão contratados pela Microsoft Engineering ou pelo Microsoft FastTrack para fazer a transição do Microsoft Dynamics 365 para a instância dos serviços globais do Office 365.* |<ul><li>Após a migração, o administrador valida a organização. <</li><li>O administrador modifica fluxos de trabalho, conforme necessário. </li><li>O administrador limpa o modo AdminOnly conforme apropriado.</li><li>O administrador altera o tipo de organização do _Sandbox_, conforme apropriado</li><li>Notifique os usuários finais da nova URL para acessar a instância (org).</li><li>Atualize quaisquer conexões de entrada para a nova URL do ponto de extremidade. </li><li>O serviço dynamics ficará indisponível para os usuários durante a transição. </li><li>Os usuários são obrigados a validar a saúde e os recursos da organização após a migração de cada organização.</li></ul>|
||||

\* (i) Os clientes com o Microsoft Dynamics 365 devem tomar medidas nesse cenário de migração conforme definido pelo processo de migração fornecido. (ii) A falha da ação do cliente significa que a Microsoft não poderá concluir a migração. (iii) Quando a Microsoft não conseguir concluir a migração devido à inação do cliente, a assinatura do cliente expirará em 29 de outubro de 2021.

## <a name="phase-8-power-bi"></a>Fase 8: Power BI

**Aplica-se a:** Todos os clientes que usam o Microsoft Power BI (PBI)

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Migração de recursos do Power BI | Os clientes com o Microsoft Power BI (PBI) serão contratados pela Microsoft Engineering ou pelo Microsoft FastTrack depois de disparar manualmente uma ferramenta de migração PBI existente para fazer a transição do Power BI para a instância de serviços Globais do Office 365.\*\* |<ul><li>Os seguintes itens do Power BI não _serão_ transitivos, e eles terão que ser re-criados: <</li><li>Conjuntos de dados em tempo real (por exemplo, conjuntos de dados de streaming ou push). </li><li>Configuração e fonte de dados do gateway de dados local do Power BI. </li><li>Os relatórios construídos sobre os conjuntos de dados em tempo real não estarão disponíveis após a migração e serão necessários para serem recriados. </li><li>Os serviços do Power BI não estarão disponíveis para os usuários durante a transição. A indisponibilidade do serviço não deve ser superior a 24 horas.</li><li>Os usuários serão obrigados a reconfigurar fontes de dados e seus gateways de dados locais com o serviço Power BI após a migração.  Até que isso seja feito, os usuários não poderão usar essas fontes de dados para executar consultas agendadas de atualização e/ou diretas em relação a essas fontes de dados. </li><li>Capacidades e espaços de trabalho premium não podem ser migrados. Os clientes precisam excluir todas as capacidades antes da migração e re-criar após a migração. Mova os espaços de trabalho de volta para as capacidades conforme desejado.</li></ul>  |
||||

\*\* (i) Os clientes com o Microsoft Power BI devem tomar medidas nesse cenário de migração conforme definido pelo processo de migração fornecido. (ii) A falha da ação do cliente significa que a Microsoft não poderá concluir a migração. (iii) Quando a Microsoft não conseguir concluir a migração devido à inação do cliente, a assinatura do cliente expirará em 29 de outubro de 2021.

## <a name="phase-9-office-apps"></a>Fase 9: Office Apps

**Aplica-se a:** Todos os clientes que usam aplicativos da área de trabalho do Office (Word, Excel, PowerPoint, Outlook, ...)

Os locatários do Office 365 que fazem a transição para a região "Alemanha" exigem que todos os usuários fechem, saia do Office 365 e volte para todos os aplicativos de área de trabalho do Office (Word, Excel, PowerPoint, Outlook etc.) e cliente do OneDrive for Business depois que a migração do locatário atingir a fase 9. Entrar e entrar, permite que os serviços do Office obtenham novos tokens de autenticação do serviço global do Azure AD.

A melhor experiência do usuário pode ser assegurada usando aplicativos do Office mais recentes. As empresas devem considerar o uso do Canal Empresarial Mensal.

Certifique-se de ter concluído o [procedimento de pré-trabalho para dispositivos móveis.](ms-cloud-germany-transition-add-pre-work.md#mobile-device-management)

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Clientes, Office Online durante a reposição de cliente do Office, o Azure AD finaliza o escopo do locatário para apontar para os serviços do Office 365. | Essa alteração de configuração permite que os clientes do Office atualizem e apontem para os pontos de extremidade dos serviços do Office 365. | <ul><li>Notifique os usuários para fechar todos os aplicativos do _Office_ e, em seguida, entrar novamente (ou forçar os clientes a reiniciar e os usuários a entrar) para permitir que os clientes do Office atendam à alteração. </li><li>Notifique os usuários  e a equipe de atendimento técnico de que os usuários podem ver um banner do Office que solicita que eles reativam os aplicativos do Office em até 72 horas após a recortação. </li><li>Todos os aplicativos do Office em máquinas pessoais devem ser fechados e os usuários devem sair e entrar novamente. Na barra de ativação Amarela, entre para reativar em relação aos serviços do Office 365.</li><li>As máquinas compartilhadas exigirão ações semelhantes a máquinas pessoais e não exigirão um procedimento especial. </li><li>Em dispositivos móveis, os usuários devem sair de aplicativos, fechar e entrar novamente.</li></ul>|
||||

## <a name="phase-9-line-of-business-apps"></a>Fase 9: aplicativos de linha de negócios

**Aplica-se a:** Todos os clientes que usam aplicativos de linha de negócios conectados ao Office 365

Caso você tenha aplicativos de linha de negócios, certifique-se de ter concluído o [pré-trabalho](ms-cloud-germany-transition-add-pre-work.md#line-of-business-apps) para o procedimento de aplicativos de linha de negócios.

## <a name="phase-9--10-azure-ad-finalization"></a>Fase 9 & 10: Finalização do Azure AD

**Aplica-se a:** Todos os clientes

Quando o locatário do Office 365 conclui a etapa final da migração (Finalização do Azure AD (Fase 9)) todos os serviços são transições para todo o mundo. Nenhum aplicativo ou usuário deve estar acessando recursos para o locatário em qualquer um dos pontos de extremidade do Microsoft Cloud Deutschland. Automaticamente, 30 dias após a conclusão da finalização, o serviço do Microsoft Cloud Deutschland Azure AD interromperá o acesso ao ponto de extremidade para o locatário em transição. As solicitações de ponto de extremidade, como Autenticação, falharão deste ponto em diante em relação ao serviço Microsoft Cloud Deutschland. 

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Atualizar pontos de extremidade do usuário | Garantir que todos os usuários acessem o serviço usando os pontos de extremidade do mundo inteiro da Microsoft apropriados |30 dias após a finalização da migração, os pontos de extremidade do Microsoft Cloud Deutschland param de receber solicitações; o tráfego de cliente ou aplicativo falhará.  |
| Atualizar pontos de extremidade do aplicativo do Azure AD | Você deve atualizar a Autenticação, o Azure Active Directory (Azure AD) Graph e os pontos de extremidade do MS Graph para seus aplicativos para os do serviço Microsoft Worldwide. | 30 dias após a finalização da migração, os pontos de extremidade do Microsoft Cloud Deutschland param de receber solicitações; o tráfego de cliente ou aplicativo falhará. |
||||

### <a name="azure-ad-connect"></a>Azure AD Connect
**Aplica-se a:** Todos os clientes sincronizando identidades com a conexão do Azure AD

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Atualizar o Azure AD Connect. | Após a conclusão do corte no Azure AD, a organização está usando totalmente os serviços do Office 365 e não está mais conectada ao Microsoft Cloud Deutschland. Neste ponto, o cliente precisa garantir que o processo de sincronização delta tenha sido finalizado e, depois disso, altere o valor da cadeia de caracteres de `AzureInstance` 3 (Microsoft Cloud Deutschland) para 0 no caminho do `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Azure AD Connect` Registro. | Altere o valor `AzureInstance` de , a chave do Registro. Se não fizer isso, os objetos não serão sincronizados depois que os pontos de extremidade do Microsoft Cloud Deutschland não estiverem mais disponíveis. |
|||||

## <a name="post-migration"></a>Pós-migração

Leia o artigo de atividades [de pós-migração](ms-cloud-germany-transition-add-experience.md) e execute-os de acordo.
