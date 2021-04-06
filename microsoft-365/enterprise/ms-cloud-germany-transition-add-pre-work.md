---
title: Atividades de pré-migração para a migração do Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 03/09/2021
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
ms.openlocfilehash: e04246626088d9fca653c98246fd4a5b81bc1d30
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591869"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Atividades de pré-migração para a migração do Microsoft Cloud Deutschland

Use esses links para chegar às etapas de pré-migração relevantes para sua organização.

Se você estiver usando

- **Office 365 no Microsoft Cloud Deutschland**, faça [estas etapas](#general-tenant-migration-considerations).
- **Domínios personalizados**, [faça esta etapa](#dns-entries-for-custom-domains).

- **SharePoint Online**, faça [esta etapa](#sharepoint-online).
- **Exchange Online** ou **Exchange Híbrido**, faça [esta etapa](#exchange-online).
- **Skype for Business Online**, [faça esta etapa](#skype-for-business-online).
- **Dynamics 365**, faça [esta etapa.](#dynamics365)
- **Power BI**, faça [esta etapa](#power-bi).

- **Serviços de Federação do Active Directory** para o Azure AD Connect, faça estas [etapas.](#active-directory-federation-services-ad-fs)
- **Serviços de terceiros ou** aplicativos de linha de **negócios (LOB)** integrados ao Office 365, [faça esta etapa](#line-of-business-apps).
- Uma solução de gerenciamento de dispositivo móvel (MDM) de terceiros, [faça esta etapa](#mobile-device-management).
- **Serviços do Azure** com sua assinatura do Office 365, faça [esta etapa](#microsoft-azure).

## <a name="general-tenant-migration-considerations"></a>Considerações gerais sobre migração de locatários

**Aplica-se a:** Todos os clientes que usam o Office 365 na instância do Microsoft Deutschland Cloud

Os identificadores de usuário e locatário do Office 365 são preservados durante a migração. As chamadas de serviço do Azure AD são redirecionadas do Microsoft Cloud Deutschland para os serviços Globais do Office 365 e são transparentes para os serviços do Office 365.

- As Solicitações gerais de Assunto de Proteção de Dados (RGPD) são executadas a partir do portal de administração do Azure para solicitações futuras. Quaisquer dados de diagnóstico herdados ou não do cliente residentes no Microsoft Cloud Deutschland são excluídos em ou antes de 30 dias.
- Solicitações de autenticação multifatória (MFA) que usam a exibição do Microsoft Authenticator como objectID do usuário (um GUID) enquanto o locatário é copiado para serviços do Office 365. As solicitações de MFA terão o desempenho esperado apesar desse comportamento de exibição.  As contas do Microsoft Authenticator que foram ativadas usando pontos de extremidade dos serviços do Office 365 exibirão o nome principal do usuário (UPN).  Contas adicionadas usando pontos de extremidade do Microsoft Cloud Deutschland exibirão o ObjectID do usuário, mas funcionarão com pontos de extremidade do Microsoft Cloud Deutschland e do Office 365.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Prepare-se para notificar os usuários sobre como reiniciar e entrar e sair de seus clientes após a migração. | O licenciamento do cliente do Office fará a transição do Microsoft Cloud Deutschland para os serviços do Office 365 na migração. Os clientes escolhem uma nova licença válida depois de entrar e sair para clientes do Office. | Os produtos do Office dos usuários precisam atualizar licenças dos serviços do Office 365. Se as licenças não são atualizadas, os produtos do Office podem ter erros de validação de licença. |
| Certifique-se de conectividade de rede com URLs e endereços IP de serviços do [Office 365.](https://aka.ms/o365urls) | Todos os clientes e serviços hospedados pelo cliente que são usados para acessar o serviço do Office 365 devem ser capazes de acessar os pontos de extremidade dos serviços globais do Office 365. <br>Caso você ou seus parceiros de colaboração tenham regras de firewall em vigor que impediriam o acesso às URLs e endereços IP listados em URLs e endereços IP de serviços do [Office 365](https://aka.ms/o365urls) devem alterar as regras de firewall para permitir o acesso aos pontos de extremidade do serviço Global do Office 365| Falhas do serviço ou do software cliente podem ocorrer se isso não for feito antes da Fase 4  |
| Cancele assinaturas de avaliação. | As assinaturas de avaliação não serão migradas e bloquearão a transferência de assinaturas pagas. | Os serviços de avaliação expiram e não funcionam se acessados pelos usuários após o cancelamento. |
| Analise as diferenças nos recursos de licença entre o Microsoft Cloud Deutschland e os Serviços Globais do Office 365. | Os serviços do Office 365 incluem recursos e serviços adicionais não disponíveis no Microsoft Cloud Deutschland atual. Durante a transferência de assinatura, novos recursos estarão disponíveis para os usuários. | <ul><li> Analise os diferentes recursos fornecidos pelas licenças do Microsoft Cloud Deutschland e do Office 365 Global Services. Comece com a descrição do [serviço da plataforma do Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Determine se os novos recursos dos serviços do Office 365 devem ser desabilitados inicialmente para limitar os efeitos nos usuários ou no gerenciamento de alterações do usuário e alterar as atribuições de licença do usuário conforme necessário. </li><li>Preparar usuários e equipe de help desk para novos serviços e recursos fornecidos pelos serviços do Office 365. |
| Crie políticas de [retenção em](https://docs.microsoft.com/microsoft-365/compliance/retention) toda a organização para proteger contra exclusão inadvertida de conteúdo durante a migração.  |<ul><li>Para garantir que o conteúdo não seja excluído inadvertidamente pelos usuários finais durante a migração, os clientes podem optar por habilitar uma política de retenção em toda a organização. </li><li>Embora a retenção não seja necessária, já que as retenções colocadas a qualquer momento durante a migração devem funcionar conforme o esperado, ter uma política de retenção é um mecanismo de segurança de back-up. Ao mesmo tempo, uma política de retenção pode não ser usada por todos os clientes, especialmente aqueles que estão preocupados com a preservação.</li></ul>| Aplicar política de retenção conforme descrito em [Saiba mais sobre políticas de retenção e rótulos de retenção.](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) Falhas do serviço ou do software cliente podem ocorrer se isso não for feito antes da Fase 4 de 9. </li></ul>|
|||||

## <a name="dns-entries-for-custom-domains"></a>Entradas DNS para domínios personalizados

<!-- before phase 9 -->

**Aplica-se** a : clientes que definiram um CNAME _msoid_ personalizado em seu próprio domínio DNS

Se configurado, o CNAME _msoid_ afetará apenas clientes usando o cliente da Área de Trabalho do Office (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...).

Caso você tenha definido um CNAME DNS chamado _msoid_ em um ou muitos namespaces DNS que você possui, você precisa remover o CNAME até o final da fase 8 no máximo. Você pode remover o _msoid_ CNAME a qualquer momento antes do final da fase 8.

Para verificar se você definiu um CNAME em seu namespace DNS, siga as etapas abaixo e substitua contoso.com _pelo_ seu próprio nome de domínio:

```console
nslookup -querytype=CNAME msoid.contoso.com
```

Se a linha de comando retornar um registro DNS, remova o CNAME _msoid_ do seu domínio.

## <a name="active-directory-federation-services-ad-fs"></a>Serviços de Federação do Active Directory (AD FS)

<!-- before phase 4 -->

**Aplica-se** a : clientes que usam o AD FS no local para autenticar usuários que se conectam ao Microsoft Office 365<br>
**Quando aplicado:** a qualquer momento antes do início da fase 4

Ler e aplicar as etapas [de Migração do ADFS](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

<!-- before phase 4 -->

**Aplica-se a**: clientes que usam o SharePoint 2013 local<br>
**Quando aplicado:** a qualquer momento antes do início da fase 4

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Limite os fluxos de trabalho do SharePoint 2013, use durante a migração do SharePoint Online. | Reduza os fluxos de trabalho do SharePoint 2013 e conclua fluxos de trabalho de pré-voo antes das transições. | A inação pode resultar em confusão do usuário e chamadas de help desk. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Aplica-se a**: clientes do Exchange Online<br>
**Quando aplicado:** a qualquer momento antes do final da fase 9

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Notifique parceiros externos sobre a próxima transição para os serviços do Office 365. |  Os clientes devem notificar seus parceiros com os quais eles habilitaram a configuração do calendário de compartilhamento e do espaço de endereço de disponibilidade (permitir o compartilhamento de informações de disponibilidade com o Office 365). A configuração de disponibilidade precisa fazer a transição para usar os pontos de extremidade do [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) em todo o mundo quando a migração do Exchange Online for concluída. | A falha ao fazer isso pode resultar em falha no serviço ou no cliente em uma fase posterior da migração do cliente. |
| Notifique os usuários das alterações de cliente IMAP4/POP3/SMTP necessárias. | Os usuários que têm conexões de dispositivo com pontos de extremidade do Microsoft Cloud Deutschland para protocolos cliente IMAP4, POP3, SMTP são necessários para atualizar manualmente seus dispositivos cliente para alternar para os pontos de extremidade do [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide)em todo o mundo. | Pré-comunicar essa dependência aos usuários desses protocolos e garantir que eles alternem para usar o Outlook mobile ou o Outlook na Web durante essa migração. A falha na atualização dos pontos de extremidade do cliente resultará em falhas de conexão do cliente em relação ao Microsoft Cloud Deutschland quando as caixas de correio de usuário são migradas. |
||||

### <a name="exchange-online-hybrid-configuration"></a>Configuração híbrida do Exchange Online

**Aplica-se a:** Todos os clientes que usam uma configuração híbrida ativa do Exchange com servidores Exchange locais<br>
**Quando aplicado:** a qualquer momento antes do início da Fase 5

Clientes corporativos com uma implantação híbrida do Exchange Online e um serviço local Exchange Server executar o Assistente de Configuração Híbrida (HCW) para manter e estabelecer a instalação híbrida. Ao fazer a transição do Microsoft Cloud Deutschland para a região do Office 365 Germany, o administrador deve executar a versão mais recente do HCW no modo "Office 365 Germany" antes do início da migração do Exchange (Fase 5). Em seguida, execute o HCW novamente no modo "Office 365 Worldwide" na conclusão da Fase 5 para finalizar a implantação local com as configurações da região do Office 365 Germany.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| (Pré-Estágio 5) - Executar o HCW usando configurações do Office 365 Germany <br><br> <i>Você pode iniciar essa atividade imediatamente após receber a notificação da central de mensagens de que a migração de locatários do Office 365 começou (fase 1).</i>| Desinstalar e executar novamente o HCW (17.0.5378.0 ou superior) antes do Estágio 5 garantirá que sua configuração local esteja preparada para enviar e receber emails com usuários do Microsoft Cloud Deutschland e usuários migrados para a região do [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) Office 365 Germany. <p><li> No HCW, para a caixa de listagem abaixo da organização do **Meu Office 365** é hospedada por , selecione **Office 365 Germany.** | A falha na conclusão dessa tarefa antes do estágio 5 [Migração do Exchange] começar pode resultar em NDRs para emails roteados entre sua implantação local do Exchange e o Office 365.  
| (Post-Stage 5) - Executar o HCW usando as configurações do Office 365 Worldwide <br><br> <i>Você pode iniciar essa atividade depois de receber a notificação do centro de mensagens de que sua Migração do Exchange está concluída (Fase 5).</i>| Desinstalar e executar novamente o HCW a partir do Estágio 5 irá redefinir a configuração local para configuração híbrida com apenas [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) o Office 365 global. <p><li> Na caixa de listagem abaixo **da organização do Meu Office 365** é hospedada por , selecione Office **365 Worldwide**. | A falha na conclusão dessa tarefa antes do Estágio 9 [Conclusão da Migração] pode resultar em NDRs para emails roteados entre sua implantação local do Exchange e o Office 365.  
| Estabeleça o AuthServer local apontando para STS (Serviço de Token de Segurança) global para autenticação | Isso garante que as solicitações de autenticação para solicitações de disponibilidade do Exchange de usuários em estado de migração destinados ao ambiente local híbrido sejam autenticadas para acessar o serviço local. Da mesma forma, isso garantirá a autenticação de solicitações do local para os pontos de extremidade dos serviços globais do Office 365. | Depois que a migração do Azure AD (fase 2) for concluída, o administrador da topologia local do Exchange (híbrido) deverá adicionar um novo ponto de extremidade do serviço de autenticação para os serviços Globais do Office 365. Com este comando do Exchange PowerShell, substitua pela ID de locatário da sua organização encontrada no portal do `<TenantID>` Azure no Azure Active Directory.<br>`New-AuthServer GlobalMicrosoftSts -AuthMetadataUrl https://accounts.accesscontrol.windows.net/<TenantId>/metadata/json/1`<br> A falha na conclusão dessa tarefa pode resultar em solicitações híbridas de ocupado livre que não fornecem informações para usuários de caixa de correio que foram migrados do Microsoft Cloud Deutschland para os serviços do Office 365.  |
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**Aplica-se a**: clientes do Skype For Business Online<br>
**Quando aplicado:** a qualquer momento antes do início da fase 7

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Implantar o cliente de área de trabalho do Teams para usuários que acessam o Skype for Business na Alemanha. | A migração move os usuários do Skype for Business para o Microsoft Teams para colaboração, chamadas e chat. Implante o cliente de área de trabalho do Microsoft Teams ou verifique se um navegador com suporte está disponível. | A inação resultará na indisponibilidade dos serviços de colaboração do Microsoft Teams. |
| Revise e prepare-se para alterações de DNS relacionadas à migração. | Alterações na zona DNS de propriedade do cliente para o Skype for Business Online. |<ul><li>Recomendamos que você atualize o TTL (Time-to-Live) para quaisquer registros DNS de domínio de propriedade do cliente para 5 minutos para acelerar a atualização de registros DNS. No entanto, a transferência gerenciada pela Microsoft associada a essa alteração DNS pode ocorrer a qualquer momento dentro da janela de alteração de 24 horas fornecida. </li><li>A interrupção do serviço é possível no futuro. Os usuários não poderão fazer logoff no Skype for Business e serão redirecionados para a experiência migrada do Teams nos serviços do Office 365. </li></ul>|
| Preparar treinamento e preparação do Usuário Final e administração para a transição para o Microsoft Teams. | Seja bem-sucedido em sua transição do Skype para o Teams planejando a comunicação e a prontidão do usuário. | <ul><li>Os clientes precisam estar cientes dos novos serviços e como usar depois que seus serviços são transitivos para os serviços do Office 365. </li><li>Depois que as alterações de DNS são feitas para os domínios de cliente e para o domínio inicial, os usuários entrariam no Skype for Business e veriam que eles agora são migrados para o Teams. Isso também baixaria o cliente da área de trabalho para o Teams em segundo plano. </li></ul>|
||||

## <a name="mobile-device-management"></a>Gerenciamento de dispositivo móvel

<!-- before phase 5 -->
**Aplica-se a:** Clientes que usam uma solução de gerenciamento de dispositivo móvel (MDM) de terceiros<br>
**Quando aplicado:** a qualquer momento antes do início da fase 5

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Prepare o treinamento de administração e usuário final sobre os usuários removendo e adicionando sua conta ao Microsoft Outlook para iOS e Android. | As contas do Microsoft Outlook para iOS e Android configuradas com caixas de correio no Microsoft Cloud Deutschland podem ter que ser removidas e adicionadas novamente ao Outlook para sincronizar corretamente a nova configuração de serviços do Office 365. | Microsoft Outlook para clientes iOS e Android | As caixas de correio do Outlook configuradas anteriormente para o Microsoft Cloud Deutschland podem não escolher a nova configuração dos Serviços do Office 365, levando a erros e ao desempenho degradado de outras experiências de usuário. Os administradores de IT são incentivados a fornecer documentação que instrui proativamente os usuários a remover e adicionar suas contas ao Microsoft Outlook para iOS e Android se ocorrerem problemas com a entrada ou sincronização de emails após a migração. |
| Determine se qualquer reconfiguração é necessária após a migração. | As soluções de Gerenciamento de Dispositivo Móvel (MDM) podem direcionar `outlook.de` pontos de extremidade. Nesta transição para o Office 365 Services, os perfis de cliente devem ser atualizados para a URL dos serviços do Office 365, `outlook.office365.com` . | Clientes do Exchange Online e MDM | Os clientes podem continuar a funcionar enquanto o ponto de extremidade estiver acessível, mas falharão se os pontos de extremidade do `outlook.de` Microsoft Cloud Deutschland não estão mais disponíveis. |
|||||

## <a name="line-of-business-apps"></a>Aplicativos de linha de negócios

**Aplica-se a:** Clientes que usam aplicativos de linha de negócios (LOB) com pontos de extremidade fornecidos pelo Microsoft Cloud Deutschland<br>
**Quando aplicado:** após a conclusão da fase 2 e antes do final da fase 9

Se você estiver usando um serviço de terceiros ou aplicativos de linha de negócios (LOB) integrados ao Office 365, você deve resolver quaisquer dependências nos pontos de extremidade fornecidos pela instância do Microsoft Cloud Deutschland. Por exemplo, se seus aplicativos LOB estão se conectando `https://graph.microsoft.de/` a , você deve alterar o ponto de extremidade para `https://graph.microsoft.com/` . Os pontos de extremidade do serviço Microsoft Office 365 Global ficam disponíveis para seu locatário após a fase 2.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Determine se qualquer reconfiguração é necessária após a migração. | Serviços e aplicativos de terceiros que se integram ao Office 365 podem ser codificados para esperar endereços IP e URLs do Microsoft Cloud Deutschland. | Ação necessária. A inação pode resultar em falhas do serviço ou do software cliente. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Aplica-se a**: clientes que usam o Microsoft Dynamics 365

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Para assinaturas de área de segurança do Dynamics 365, baixe o ambiente de produção da instância SQL Dynamics da sua assinatura do Dynamics 365 no Microsoft Cloud Deutschland. O backup de produção mais recente deve ser restaurado para a área de segurança antes da migração da área de segurança. | A migração do Dynamics 365 exige que os clientes assegurem que o ambiente de Área Desarmada seja atualizado com o banco de dados de produção mais recente. | A equipe do FastTrack ajudará os clientes na execução de execução de execução a seco para validar a atualização de versão de 8.x para 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Aplica-se a**: clientes que usam o Power BI

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Remoção de objetos de assinaturas do Power BI que não serão migrados do Power BI Microsoft Cloud Deutschland para serviços do Office 365. | A migração dos serviços do Power BI exigirá a ação do cliente para excluir determinados artefatos, como conjuntos de dados e painéis. | <ul><li>Os administradores podem ter que remover os seguintes itens de sua assinatura: </li><li>Real-Time dados (por exemplo, conjuntos de dados de streaming ou push) </li><li>Fonte de dados e configuração local do Power BI </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

Se você estiver usando a mesma partição de identidade do Azure Active Directory para o Office 365 e o Microsoft Azure na instância do Microsoft Cloud Deutschland, certifique-se de que você está se preparando para a migração orientada pelo cliente dos serviços do Microsoft Azure.

> [!NOTE]
> A migração dos serviços do Microsoft Azure não deve ser iniciada antes que o locatário do Office 365 tenha atingido a fase de migração 3 e deve ser concluída antes da conclusão da fase 8 de migração.

Os clientes que usam recursos do Office 365 e do Azure (por exemplo, rede, computação e armazenamento) realizarão a migração de recursos para a instância de serviços do Office 365. Essa migração é responsabilidade do cliente. As postagens da Central de Mensagens sinalizam o início. A migração deve ser concluída antes da finalização da organização do Azure AD no ambiente de serviços do Office 365. Para migrações do Azure, consulte o manual de migração do Azure, Visão geral das diretrizes de migração [para o Azure Germany](https://docs.microsoft.com/azure/germany/germany-migration-main).

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Determine quais serviços do Azure estão em uso e prepare-se para a migração futura da Alemanha para o locatário de serviços do Office 365 trabalhando com seus parceiros. Siga as etapas descritas no playbook de migração [do Azure](/azure/germany/germany-migration-main). |<ul><li>A migração de recursos do Azure é uma responsabilidade do cliente e requer esforço manual seguindo as etapas prescritas. Entender quais serviços estão em uso na organização é fundamental para a migração bem-sucedida dos serviços do Azure. </li><li> Os clientes do Office 365 Germany que têm assinaturas do Azure sob a mesma partição de identidade (organização) devem seguir a ordem prescrita pela Microsoft quando podem iniciar a migração de assinatura e serviços.</li></ul>|<ul><li>Os clientes podem ter várias assinaturas do Azure, cada assinatura contendo infraestrutura, serviços e componentes de plataforma. </li><li> Os administradores devem identificar assinaturas e participantes para garantir que a migração e a validação de prompts seja possível como parte desse evento de migração. </li><li>A falha na conclusão da migração dessas assinaturas e componentes do Azure dentro da linha do tempo prescrita afetará a conclusão da transição do Office e do Azure AD para os serviços do Office 365 e poderá resultar em perda de dados. </li><li> Uma notificação do Centro de Mensagens sinaliza o ponto no qual a migração liderada pelo cliente pode começar. </li></ul>|
||||

<!--
Reworked as text:

**Step:** Determine which Azure services are in use and prepare for future migration from Germany to the Office 365 services tenant by working with your partners. Follow the steps described in the [Azure migration playbook](/azure/germany/germany-migration-main).

**Description:** Migration of Azure resources is a customer responsibility and requires manual effort following prescribed steps. Understanding what services are in use in the organization is key to successful migration of Azure services. 

Office 365 Germany customers who have Azure subscriptions under the same identity partition (organization) must follow the Microsoft-prescribed order when they can begin subscription and services migration.

**Applies to:** Azure Customers

**Impact:** 

- Customers may have multiple Azure subscriptions, each subscription containing infrastructure, services, and platform components. 
- Administrators should identify subscriptions and stakeholders to ensure prompt migration and validation is possible as part of this migration event.

  Failing to successfully complete migration of these subscriptions and Azure components within the prescribed timeline will affect completion of the Office and Azure AD transition to Office 365 services and may result in data loss.
- A Message center notification will signal the point at which customer-led migration can begin.
-->

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
