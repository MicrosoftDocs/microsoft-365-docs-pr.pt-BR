---
title: Pré-trabalho para a migração do Microsoft Cloud Deutschland
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
description: 'Resumo: pré-trabalho ao mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: 085630c498cebfea26fb3de975740af17cb73921
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454414"
---
# <a name="pre-work-for-the-migration-from-microsoft-cloud-deutschland"></a>Pré-trabalho para a migração do Microsoft Cloud Deutschland


Use esses links para chegar às etapas de pré-trabalho relevantes para sua organização:

- Para todas as assinaturas, faça [estas etapas.](#applies-to-everyone)
- Se você estiver usando o Exchange Online ou o Exchange híbrido, [faça esta etapa](#exchange-online).
- Se você estiver usando o SharePoint Online, faça [esta etapa](#sharepoint-online).
- Se você estiver usando uma solução de gerenciamento de dispositivo móvel (MDM) de terceiros, [faça esta etapa.](#mobile)
- Se você estiver usando aplicativos lob (serviço de terceiros) ou linha de negócios integrados ao Office 365, [faça esta etapa.](#line-of-business-apps)
- Se você também estiver usando serviços do Azure além daqueles incluídos com sua assinatura do Office 365, [faça esta etapa](#azure).
- Se você também estiver usando o Dynamics 365, faça [esta etapa](#dynamics365).
- Se você também estiver usando o Power BI, faça [esta etapa](#power-bi).
- Para alterações de DNS, [faça esta etapa](#dns).
- Se você estiver usando a identidade federada, faça [estas etapas.](#federated-identity)

## <a name="applies-to-everyone"></a>Aplica-se a todos

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Certifique-se de conectividade de rede com URLs e endereços IP de serviços do [Office 365.](https://aka.ms/o365urls) | Todos os clientes e serviços hospedados pelo cliente que são usados para acessar o serviço do Office 365 devem ser capazes de acessar os pontos de extremidade dos serviços do Office 365. | Todos os clientes em transição e clientes com acesso à rede restrito ao Microsoft Cloud Deutschland. | Ação necessária. Falhas do serviço ou do software cliente podem ocorrer se isso não for feito antes da Fase 4 de 9. |
| Revise e prepare-se para alterações de DNS relacionadas à migração. | Alterações na zona DNS de propriedade do cliente para o Skype for Business Online. | Clientes do Skype For Business Online | - Recomendamos que você atualize o TTL (Time-to-Live) para quaisquer registros DNS de domínio de propriedade do cliente para 5 minutos para acelerar a atualização de registros DNS. No entanto, a transferência gerenciada pela Microsoft associada a essa alteração DNS pode ocorrer a qualquer momento dentro da janela de alteração de 24 horas fornecida. <br><br> - A interrupção do serviço é possível no futuro. Os usuários não poderão fazer logoff no Skype for Business e serão redirecionados para a experiência migrada do Teams nos serviços do Office 365. |
| Preparar treinamento e preparação do Usuário Final e administração para a transição para o Microsoft Teams. | Seja bem-sucedido em sua transição do Skype para o Teams planejando a comunicação e a prontidão do usuário. | Clientes do Skype For Business Online | - Os clientes precisam estar cientes dos novos serviços e como usar depois que seus serviços são transitivos para os serviços do Office 365. <br><br> - Depois que as alterações de DNS são feitas para os domínios de cliente e para o domínio inicial, os usuários entrariam no Skype for Business e veriam que eles agora são migrados para o Teams. Isso também baixaria o cliente da área de trabalho para o Teams em segundo plano. |
| Prepare o treinamento de administração e usuário final sobre os usuários removendo e adicionando sua conta ao Microsoft Outlook para iOS e Android. | As contas do Microsoft Outlook para iOS e Android configuradas com caixas de correio no Microsoft Cloud Deutschland podem ter que ser removidas e adicionadas novamente ao Outlook para sincronizar corretamente a nova configuração de serviços do Office 365. | Microsoft Outlook para clientes iOS e Android | As caixas de correio do Outlook configuradas anteriormente para o Microsoft Cloud Deutschland podem não escolher a nova configuração dos Serviços do Office 365, levando a erros e ao desempenho degradado de outras experiências de usuário. Os administradores de IT são incentivados a fornecer documentação que instrui proativamente os usuários a remover e adicionar suas contas ao Microsoft Outlook para iOS e Android se ocorrerem problemas com a entrada ou sincronização de emails após a migração. |
| Prepare-se para notificar os usuários sobre como reiniciar e entrar e sair de seus clientes após a migração. | O licenciamento do cliente do Office fará a transição do Microsoft Cloud Deutschland para os serviços do Office 365 na migração. Os clientes escolhem uma nova licença válida depois de entrar e sair para clientes do Office. | Clientes do Microsoft 365 Apps |  Os produtos do Office dos usuários precisam atualizar licenças dos serviços do Office 365. Se as licenças não são atualizadas, os produtos do Office podem ter erros de validação de licença. |
| Cancele assinaturas de avaliação. | As assinaturas de avaliação não serão migradas e bloquearão a transferência de assinaturas pagas. | Todos os clientes | Os serviços de avaliação expiram e não funcionam se acessados pelos usuários após o cancelamento. |
| Implantar o cliente de área de trabalho do Teams para usuários que acessam o Skype for Business na Alemanha. | A migração move os usuários para o Teams para colaboração, chamada e chat. Implante o cliente da área de trabalho do Teams ou verifique se um navegador com suporte está disponível. | Clientes do Skype for Business | A inação resultará na indisponibilidade dos serviços de colaboração do Teams. |
| Analise as diferenças nos recursos de licença entre o Microsoft Cloud Deutschland e o Office 365 Services. | Os serviços do Office 365 incluem recursos e serviços adicionais não disponíveis no Microsoft Cloud Deutschland atual. Durante a transferência de assinatura, novos recursos estarão disponíveis para os usuários. | Todos os clientes | - Analise os diferentes recursos fornecidos pelas licenças do Microsoft Cloud Deutschland e do Office 365 Services. Comece com a descrição do [serviço da plataforma do Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) <br><br> - Determine se os novos recursos dos serviços do Office 365 devem ser desabilitados inicialmente para limitar os efeitos nos usuários ou no gerenciamento de alterações do usuário e alterar as atribuições de licença do usuário conforme necessário. <br><br> - Preparar usuários e equipe de help desk para novos serviços e recursos fornecidos pelos serviços do Office 365. |
| Crie políticas de [retenção em](https://docs.microsoft.com/microsoft-365/compliance/retention) toda a organização para proteger contra exclusão inadvertida de conteúdo durante a migração.  | - Para garantir que o conteúdo não seja excluído inadvertidamente pelos usuários finais durante a migração, os clientes podem optar por habilitar uma política de retenção em toda a organização. <br><br> - Embora a retenção não seja necessária, já que as retenções colocadas a qualquer momento durante a migração devem funcionar conforme o esperado, ter uma política de retenção é um mecanismo de segurança de back-up. Ao mesmo tempo, uma política de retenção pode não ser usada por todos os clientes, especialmente aqueles que estão preocupados com a preservação. | Clientes do Office | Aplicar política de retenção conforme descrito em [Saiba mais sobre políticas de retenção e rótulos de retenção.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Falhas do serviço ou do software cliente podem ocorrer se isso não for feito antes da Fase 4 de 9.  |
| [Backup do farm dos Serviços de Federação do Active Directory (AD FS)](ms-cloud-germany-transition-add-adfs.md#backup) para cenários de recuperação de desastres. | Os clientes precisam fazer o back up do farm do AD FS adequadamente para garantir que as confianças da parte confiável nos pontos de extremidade globais & Alemanha possam ser restauradas sem tocar no URI do emissor dos domínios. A Microsoft recomenda usar a Restauração Rápida do AD FS para um backup do farm e a respectiva restauração, se necessário. | Organizações de Autenticação Federada | Ação Necessária. A inação resultará em impacto no serviço durante a migração se o farm do AD FS do cliente falhar. Para obter mais informações, consulte [Etapas de Migração do ADFS] (https://docs.microsoft.com/microsoft-365/enterprise/ms-cloud-germany-transition-add-adfs) |


## <a name="exchange-online"></a>Exchange Online

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Notifique parceiros externos sobre a próxima transição para os serviços do Office 365. | As configurações de espaço de endereço de disponibilidade permitem o compartilhamento de informações de disponibilidade com o Office 365. | Clientes do Exchange Online que habilitaram o compartilhamento de calendário e espaço de endereço de disponibilidade. | Ação necessária.  A falha ao fazer isso pode resultar em falha no serviço ou no cliente em uma fase posterior da migração do cliente. |
|||||

<!--
Reworked as text:

**Step:** Notify external partners of the upcoming transition to Office 365 services.

**Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

**Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

**Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

- **Step:** Notify external partners of the upcoming transition to Office 365 services.

- **Description:** Availability address space configurations allow sharing of free/busy information with Office 365. | Exchange Online customers who have enabled sharing calendar and availability address space.

- **Applies to:** Exchange Online customers who have enabled sharing calendar and availability address space.

- **Impact:** Required action.  Failure to do so may result in service or client failure at a later phase of customer migration.

--> 


### <a name="for-hybrid-exchange"></a>Para o Exchange híbrido

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Atualize para a versão mais recente do Assistente de Configuração Híbrida (HCW) antes da migração. <br><br> Os clientes do Exchange Online híbridos do Microsoft Cloud Deutschland devem desinstalar versões anteriores do HCW e instalar e executar a versão mais recente (17.0.5378.0 ou superior) de [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) . | A versão mais recente do HCW inclui atualizações necessárias para dar suporte aos clientes que estão fazendo a transição do Microsoft Cloud Deutschland para o Office 365 Services. <br><br> As atualizações incluem alterações nas configurações de certificado local para o conector de Envio e o conector de Recebimento. <br><br> Os clientes devem re-instalar usando as configurações do Office 365 Germany antes do início da Fase 5 de 9 (migração do Exchange). <br><br> OBSERVAÇÃO: após a conclusão da migração para serviços do Office 365, você removerá e instalará novamente o HCW, desta vez usando as configurações do Office 365 Worldwide para concluir sua configuração híbrida com o serviço global. | Clientes do Exchange Online executando a implantação híbrida | Ação necessária. A falha ao fazer isso antes da Fase 5 de 9 (migração do Exchange) pode resultar em falha no serviço ou no cliente. |
|||||

<!--
Reworked as text:

**Step:** Uninstall previous versions of Hybrid Configuration wizard (HCW), and then install and execute the latest version, 17.0.5378.0, from [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard).

**Description:** The latest version of the HCW includes necessary updates to support customers who are transitioning from Microsoft Cloud Deutschland to Office 365 Services. <br><br> Updates include changes to on-premises certificate settings for Send connector and Receive connector.

**Applies to:** Exchange Online customers running Hybrid deployment

**Impact:** Required action. Failure to do so may result in service or client failure.
-->


## <a name="sharepoint-online"></a>SharePoint Online

Se você tiver o SharePoint 2013:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Limite os fluxos de trabalho do SharePoint 2013, use durante a migração do SharePoint Online. | Reduza os fluxos de trabalho do SharePoint 2013 e conclua fluxos de trabalho de pré-voo antes das transições. | Clientes do SharePoint Online | A inação pode resultar em confusão do usuário e chamadas de help desk. |
|||||

## <a name="mobile"></a>Celular

Se você estiver usando uma solução de gerenciamento de dispositivo móvel (MDM) de terceiros:

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Determine se qualquer reconfiguração é necessária após a migração. | As soluções MDM podem direcionar `outlook.de` pontos de extremidade. Nesta transição para o Office 365 Services, os perfis de cliente devem ser atualizados para a URL dos serviços do Office 365, `outlook.office365.com` . | Clientes do Exchange Online e MDM | Os clientes podem continuar a funcionar enquanto o ponto de extremidade estiver acessível, mas falharão se os pontos de extremidade do `outlook.de` Microsoft Cloud Deutschland não estão mais disponíveis. |
|||||

## <a name="line-of-business-apps"></a>Aplicativos de linha de negócios

Se você estiver usando um serviço de terceiros ou aplicativos de linha de negócios (LOB) integrados ao Office 365: 

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Determine se qualquer reconfiguração é necessária após a migração. | Serviços e aplicativos de terceiros que se integram ao Office 365 podem ser codificados para esperar endereços IP e URLs do Microsoft Cloud Deutschland. | Todos os clientes | Ação necessária. A inação pode resultar em falhas do serviço ou do software cliente. |
|||||

## <a name="azure"></a>Azure 

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Determine quais serviços do Azure estão em uso e prepare-se para a migração futura da Alemanha para o locatário de serviços do Office 365 trabalhando com seus parceiros. Siga as etapas descritas no playbook de migração [do Azure](https://docs.microsoft.com/azure/germany/germany-migration-main). | A migração de recursos do Azure é uma responsabilidade do cliente e requer esforço manual seguindo as etapas prescritas. Entender quais serviços estão em uso na organização é fundamental para a migração bem-sucedida dos serviços do Azure. <br><br> Os clientes do Office 365 Germany que têm assinaturas do Azure sob a mesma partição de identidade (organização) devem seguir a ordem prescrita pela Microsoft quando podem iniciar a migração de assinatura e serviços. | Clientes do Azure | - Os clientes podem ter várias assinaturas do Azure, cada assinatura contendo infraestrutura, serviços e componentes de plataforma. <br><br> - Os administradores devem identificar assinaturas e partes interessadas para garantir que a migração e a validação de prompts seja possível como parte desse evento de migração. <br><br> A falha na conclusão da migração dessas assinaturas e componentes do Azure dentro da linha do tempo prescrita afetará a conclusão da transição do Office e do Azure AD para os serviços do Office 365 e poderá resultar em perda de dados.  <br><br> - Uma notificação do Centro de Mensagens sinaliza o ponto no qual a migração liderada pelo cliente pode começar. |
|||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](https://docs.microsoft.com/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

## <a name="dynamics-365"></a>Dynamics 365

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Para assinaturas de área de segurança do Dynamics 365, baixe o ambiente de produção da instância SQL Dynamics da sua assinatura do Dynamics 365 no Microsoft Cloud Deutschland. O backup de produção mais recente deve ser restaurado para a área de segurança antes da migração da área de segurança. | A migração do Dynamics 365 exige que os clientes assegurem que o ambiente de Área Desarmada seja atualizado com o banco de dados de produção mais recente. | Clientes do Microsoft Dynamics | A equipe do FastTrack ajudará os clientes na execução de execução de execução a seco para validar a atualização de versão de 8.x para 9.1.x. |
|||||

## <a name="power-bi"></a>Power BI

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Remoção de objetos de assinaturas do Power BI que não serão migrados do Power BI Microsoft Cloud Deutschland para serviços do Office 365. | A migração dos serviços do Power BI exigirá a ação do cliente para excluir determinados artefatos, como conjuntos de dados e painéis. | Clientes do Power BI | Os administradores podem ter que remover os seguintes itens de sua assinatura: <br> - Real-Time dados (por exemplo, conjuntos de dados de streaming ou push) <br> - Configuração e fonte de dados do Power BI local |
|||||

## <a name="dns"></a>DNS

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Remova MSOID, CName do DNS de propriedade do cliente se existir a qualquer momento antes do recorte do Azure AD. Um TTL de 5 minutos pode ser definido para que a alteração possa ter efeito rapidamente. | Alterações na zona DNS de propriedade do cliente | Clientes de serviços cliente do Office | 
|||||

## <a name="federated-identity"></a>Identidade federada

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Adicione um identificador para SSO (login único) a uma confiança de parte confiável existente e desabilite as atualizações automáticas de metadados do AD FS. | Uma ID deve ser adicionada à confiança da parte confiável do AD FS antes de iniciar a migração. Para evitar a remoção acidental do identificador de terceiros de confiança, desabilite a atualização automática para atualizações de metadados. <br><br> Execute este comando no servidor do AD FS: <br> `Set-AdfsRelyingPartyTrust -TargetIdentifier urn:federation:microsoftonline.de -Identifier @('urn:federation:microsoftonline.de','https://login.microsoftonline.de/extSTS.srf','https://login.microsoftonline.de') -AutoUpdate $False` | Organizações de autenticação federadas | Ação Necessária. A inação antes da Fase 4 de 9 (SharePoint) resultará em impacto no serviço durante a migração.  |
| Gere confiança de terceiros confiável para pontos de extremidade globais do Azure AD. | Os clientes precisam criar manualmente um RPT (confiança de parte confiável) para pontos de extremidade [globais.](https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml) Isso é feito adicionando um novo RPT via GUI aproveitando a URL de metadados de federação global e usando as Regras de Declaração RPT do [Azure AD](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator#:~:text=%20Azure%20AD%20RPT%20Claim%20Rules%20%201,Azure%20AD.%20This%20will%20be%20what...%20More%20) (na Ajuda do AD FS) para gerar as regras de declaração e importá-las para o RPT. | Organizações de autenticação federadas | Ação Necessária. A inação resultará em impacto no serviço durante a migração. |
|||||

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

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
