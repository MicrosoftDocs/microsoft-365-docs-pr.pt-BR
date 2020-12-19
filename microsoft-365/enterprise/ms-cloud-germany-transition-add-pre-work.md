---
title: Pré-trabalho para a migração do Microsoft Cloud Alemanha
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/18/2020
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
description: 'Resumo: pré-trabalho ao migrar do Microsoft Cloud Alemanha (Microsoft Cloud Alemanha) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: 107447226b9b75f371e23f8dd06ec29860571c63
ms.sourcegitcommit: 86f75cf77a7a446a79226ca530bd7b5eb39189cb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2020
ms.locfileid: "49717026"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Pré-trabalho para a migração do Microsoft Cloud Alemanha

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Verifique a conectividade de rede para [URLs e endereços IP dos serviços do Office 365](https://aka.ms/o365urls). | Todos os clientes e serviços hospedados pelo cliente usados para acessar o serviço do Office 365 devem ser capazes de acessar os pontos de extremidade dos serviços do Office 365. | Todos os clientes em transição e clientes com acesso à rede restrito ao Microsoft Cloud Alemanha. | Ação necessária. Inaction pode resultar em falhas do software de serviço ou cliente. |
| Revisar e preparar as alterações de DNS relacionadas à migração. | O cliente prepara as entradas de DNS para o Exchange Online e o Exchange Online Protection (registro MX, etc.). | Clientes do Exchange Online | Essa é uma ação recomendada. Nenhuma ação significa que os emails de clientes migrados podem rotear através do Microsoft Cloud Alemanha até que os serviços do Microsoft Cloud Alemanha estejam desabilitados. |
| Revisar e preparar as alterações de DNS relacionadas à migração. | A zona DNS de Propriedade do cliente é alterada para o Skype for Business online. | Clientes do Skype for Business Online | – É recomendável que você atualize o tempo de vida (TTL) para qualquer registro DNS de domínio pertencente ao cliente a 5 minutos para acelerar a atualização de registros DNS. No entanto, a transferência gerenciada pela Microsoft associada a essa alteração de DNS pode ocorrer a qualquer momento dentro da janela de alteração de 24 horas fornecida. <br><br> – A interrupção do serviço é possível no futuro. Os usuários não poderão fazer logon no Skype for Business e serão redirecionados para a experiência de equipes migradas nos serviços do Office 365. |
| Preparar o usuário final e treinamento de administração e prontidão para a transição para o Microsoft Teams. | Ter êxito na transição do Skype para o Microsoft Teams, planejando a comunicação e a preparação do usuário. | Clientes do Skype for Business Online | – Os clientes precisam estar cientes dos novos serviços e como usá-los depois que os serviços são migrados para os serviços do Office 365. <br><br> – Após as alterações de DNS serem feitas para os domínios do cliente personalizado e o domínio inicial, os usuários entrarão no Skype for Business e configurariam que eles estão migrados para o Microsoft Teams. Isso também baixaria o cliente de desktop para Teams em segundo plano. |
| Prepare o treinamento de usuário final e administração sobre usuários removendo e readicionando sua conta ao Microsoft Outlook para iOS e Android. | As contas do Microsoft Outlook para iOS e Android configuradas com caixas de correio no Microsoft Cloud Alemanha podem precisar ser removidas e adicionadas novamente ao Outlook para sincronizar corretamente a nova configuração dos serviços do Office 365. | Clientes do Microsoft Outlook para iOS e Android | As caixas de correio do Outlook configuradas anteriormente para o Microsoft Cloud Alemanha podem não selecionar a nova configuração dos serviços do Office 365, levando a erros e degradados o desempenho de outras experiências do usuário. Os administradores de ti são incentivados a fornecer documentação que instrui proativamente os usuários a removerem e a adicionar novamente suas contas ao Microsoft Outlook para iOS e Android se problemas de entrada ou sincronização de email ocorrerem após a migração. |
| Prepare-se para notificar os usuários sobre a reinicialização e a entrada de seus clientes após a migração. | O licenciamento do cliente do Office passará do Microsoft Cloud Alemanha para os serviços do Office 365 na migração. Os clientes pegam uma nova licença válida após entrar e sair de clientes do Office. | Clientes do Microsoft 365 apps |  Os produtos do Office dos usuários precisam atualizar licenças dos serviços do Office 365. Se as licenças não forem atualizadas, os produtos do Office poderão ter erros de validação de licença. |
| Cancele todas as assinaturas de avaliação. | As assinaturas de avaliação não serão migradas e bloquearão a transferência de assinaturas pagas. | Todos os clientes | Os serviços de avaliação expiraram e não funcionarão se forem acessados por usuários após o cancelamento. |
| Implantar o cliente da área de trabalho do teams para usuários que acessam o Skype for Business na Alemanha. | A migração move os usuários para o Microsoft Teams para colaboração, chamada e chat. Seja, implante o cliente do teams desktop ou verifique se há um navegador compatível disponível. | Clientes do Skype for Business | Inação resultará em indisponibilidade de serviços de colaboração do teams. |
| Analisar as diferenças nos recursos de licença entre o Microsoft Cloud Alemanha e os serviços do Office 365. | Os serviços do Office 365 incluem recursos e serviços adicionais não disponíveis no Alemanha do Microsoft Cloud atual. Durante a transferência de assinatura, novos recursos estarão disponíveis para os usuários. | Todos os clientes | – Analise os diferentes recursos fornecidos pelas licenças para o Microsoft Cloud Alemanha e serviços do Office 365. Comece com a [Descrição do serviço da plataforma do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description). <br><br> – Determine se todos os novos recursos dos serviços do Office 365 devem ser inicialmente desabilitados para limitar os efeitos de usuários ou de gerenciamento de alterações do usuário e alterar as atribuições de licença do usuário conforme necessário. <br><br> – Prepare os usuários e a equipe de suporte técnico para novos serviços e recursos fornecidos pelos serviços do Office 365. |
| Criar [políticas de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention) em toda a organização para proteger contra a exclusão inadvertida de conteúdo durante a migração.  | – Para garantir que o conteúdo não seja excluído inadvertidamente por usuários finais durante a migração, os clientes podem optar por habilitar uma política de retenção em toda a organização. <br><br> -Embora a retenção não seja necessária, já que as suspensões feitas a qualquer momento durante a migração devem funcionar conforme o esperado, ter uma política de retenção é um mecanismo de segurança de backup. Ao mesmo tempo, uma política de retenção pode não ser usada por todos os clientes, especialmente aqueles que se preocupam com a preservação. | Clientes do Office | Aplique a política de retenção conforme descrito em [saiba mais sobre políticas de retenção e rótulos de retenção](https://docs.microsoft.com/microsoft-365/compliance/retention-policies). |
| [Backup do farm dos serviços de Federação do Active Directory (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) para cenários de recuperação de desastres. | Os clientes precisam fazer backup do farm do AD FS apropriadamente para garantir que as relações de confiança de terceira parte confiável para os pontos de extremidade da Alemanha & globais possam ser restauradas sem tocar no URI do emissor dos domínios. A Microsoft recomenda usar a restauração rápida do AD FS para um backup do farm e a respectiva restauração, se necessário. | Organizações de autenticação federada | Ação necessária. Inaction resultará no impacto do serviço durante a migração se o farm do AD FS do cliente falhar. |


## <a name="exchange-online"></a>Exchange Online

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Notifique os parceiros externos sobre a transição futura para os serviços do Office 365. | Configurações de espaço de endereço de disponibilidade permitem o compartilhamento de informações de disponibilidade com o Office 365. | Clientes do Exchange Online que habilitaram o compartilhamento de espaço de endereço de disponibilidade e calendário. | Ação necessária.  Se isso não for feito, poderá ocorrer uma falha de cliente ou serviço em uma fase posterior da migração do cliente. |
|||||

Se você tiver o Exchange híbrido:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Desinstalar versões anteriores do assistente de configuração híbrida (HCW) e, em seguida, instalar e executar a versão mais recente, 17.0.5378.0 do [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | A versão mais recente do HCW inclui as atualizações necessárias para dar suporte aos clientes que estão em transição do Microsoft Cloud Alemanha para os serviços do Office 365. <br><br> As atualizações incluem alterações nas configurações de certificado no local para conector de envio e conector de recebimento. | Clientes do Exchange Online executando implantação híbrida | Ação necessária. Se isso não for feito, poderão ocorrer falhas do cliente ou do serviço. |
|||||

## <a name="sharepoint-online"></a>SharePoint Online

Se você tiver o SharePoint 2013:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Limitar fluxos de trabalho do SharePoint 2013, usar durante a migração do SharePoint Online. | Reduza os fluxos de trabalho do SharePoint 2013 e complete fluxos de trabalho em trânsito antes de transições. | Clientes do SharePoint Online | Inaction pode resultar em confusão do usuário e chamadas de assistência técnica. |
|||||

## <a name="mobile"></a>Celular

Se você estiver usando uma solução de gerenciamento de dispositivo móvel (MDM) de terceiros:

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Determine se é necessário reconfigurar uma reconfiguração após a migração. | As soluções MDM podem direcionar `outlook.de` pontos de extremidade. Nesta transição para os serviços do Office 365, os perfis de cliente devem ser atualizados para a URL dos serviços do Office 365 `outlook.office365.com` . | Clientes do Exchange Online e do MDM | Os clientes podem continuar a funcionar enquanto o `outlook.de` ponto de extremidade estiver acessível, mas eles falharão se os pontos de extremidade do Microsoft Cloud Alemanha não estiverem mais disponíveis. |
|||||

## <a name="line-of-business-apps"></a>Aplicativos de linha de negócios

Se você estiver usando um serviço de terceiros ou aplicativos LOB (linha de negócios) integrados ao Office 365: 

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Determine se é necessário reconfigurar uma reconfiguração após a migração. | Os serviços e aplicativos de terceiros que se integram ao Office 365 podem ser codificados para esperar endereços IP e URLs do Microsoft Cloud Alemanha. | Todos os clientes | Ação necessária. Inaction pode resultar em falhas do software de serviço ou cliente. |
|||||

## <a name="azure"></a>Azure 

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Determine quais serviços do Azure estão em uso e prepare-se para a migração futura da Alemanha para o locatário de serviços do Office 365 trabalhando com seus parceiros. Siga as etapas descritas no [guia estratégico de migração do Azure](https://docs.microsoft.com/azure/germany/germany-migration-main). | A migração de recursos do Azure é uma responsabilidade do cliente e exige esforço manual seguindo as etapas indicadas. Entender quais serviços estão em uso na organização é fundamental para a migração bem-sucedida dos serviços do Azure. <br><br> Os clientes do Office 365 Alemanha que possuem assinaturas do Azure sob a mesma partição de identidade (organização) devem seguir a ordem prescrita pela Microsoft quando eles puderem iniciar a migração de assinatura e serviços. | Clientes do Azure | -Os clientes podem ter várias assinaturas do Azure, cada assinatura contendo infraestrutura, serviços e componentes da plataforma. <br><br> -Os administradores devem identificar assinaturas e participantes para garantir que a migração e a validação do prompt sejam possíveis como parte desse evento de migração. <br><br> A falha na conclusão da migração dessas assinaturas e dos componentes do Azure na linha do tempo prescrita afetará a conclusão da transição do Office e do Azure AD para os serviços do Office 365 e pode resultar em perda de dados.  <br><br> – Uma notificação de centro de mensagens sinalizará o ponto em que a migração de cliente pode começar. |
|||||

## <a name="dynamics-365"></a>Dynamics 365

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Para assinaturas da área restrita do Dynamics 365, certifique-se de baixar o ambiente de produção da instância do Dynamics SQL da sua assinatura do Dynamics 365 no Microsoft Cloud Alemanha. O backup de produção mais recente deve ser restaurado para a área restrita antes da migração. | A migração do Dynamics 365 exige que os clientes garantam que o ambiente de área restrita seja atualizado com o banco de dados de produção mais recente. | Clientes do Microsoft Dynamics | A equipe do FastTrack ajudará os clientes a executarem saturações para validar a atualização de versão de 8. x para 9.1. x. |
|||||

## <a name="power-bi"></a>Power BI

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Remoção de objetos das assinaturas do Power BI que não serão migradas do Power BI Microsoft Cloud Alemanha para os serviços do Office 365. | A migração de serviços do Power BI exigirá que o cliente exclua determinados artefatos, como conjuntos de DataSets e painéis. | Clientes do Power BI | Os administradores podem ter que remover os seguintes itens de sua assinatura: <br> -Real-Time DataSets (por exemplo, conjuntos de Datastream ou de transmissão de envio) <br> – Configuração e fonte de dados do data gateway local Power BI |
|||||

## <a name="dns"></a>DNS

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Revise e prepare para alteração de DNS se o DNS atual tiver uma entrada CName MSOID. | Alterações de zona DNS de Propriedade do cliente | Clientes de serviços cliente do Office | Atualize o tempo de vida (TTL) dos registros DNS de Propriedade do cliente para 5 minutos, se houver um CName MSOID. |
|||||

## <a name="federated-identity"></a>Identidade federada

| Etapa (s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Adicione um identificador de logon único (SSO) a uma confiança de terceira parte confiável existente e desabilite as atualizações automáticas de metadados do AD FS. | Uma ID deve ser adicionada ao confiança da terceira parte confiável do AD FS antes de iniciar a migração. Para evitar a remoção acidental do identificador da terceira parte confiável, desabilite a atualização automática para atualizações de metadados. <br><br> Execute este comando no servidor AD FS: <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | Organizações de autenticação federada | Ação necessária. Inaction resultará no impacto do serviço durante a migração.  |
| Gere confiança de terceira parte confiável para pontos de extremidade do Azure AD global. | Os clientes precisam criar manualmente um relatório de confiança de terceira parte confiável (RPT) para pontos de extremidade [globais](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) . Isso é feito adicionando um novo relatório via GUI, aproveitando a URL dos metadados globais de Federação e usando [as regras de declaração do Azure ad RPT](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (na ajuda do AD FS) para gerar as regras de declaração e importá-las para o relatório. | Organizações de autenticação federada | Ação necessária. Inaction resultará no impacto do serviço durante a migração. |
|||||

## <a name="more-information"></a>Mais informações

Introdução:

- [Migração do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Mover-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para o [Azure ad](ms-cloud-germany-transition-azure-ad.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
