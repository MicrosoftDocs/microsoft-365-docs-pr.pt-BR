---
title: Atividades de pré-migração para a migração do Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 05/12/2021
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
description: 'Resumo: pré-trabalho ao mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para Office 365 serviços na nova região do datacenter alemão.'
ms.openlocfilehash: db4563b4a63dc39ee8171e80fd76ae15b7cd10e9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844281"
---
# <a name="pre-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a>Atividades de pré-migração para a migração do Microsoft Cloud Deutschland

Use esses links para chegar às etapas de pré-migração relevantes para sua organização.

Se você estiver usando

- **Office 365 no Microsoft Cloud Deutschland**, faça [estas etapas.](#general-tenant-migration-considerations)
- **Domínios personalizados**, [faça esta etapa](#dns-entries-for-custom-domains).
- **Office Apps**, considere [esta etapa](#office-apps).
- **SharePoint Online**, faça [esta etapa](#sharepoint-online).
- **Exchange Online** ou **Exchange Híbrido,** faça [esta etapa](#exchange-online).
- **Skype for Business Online**, faça [esta etapa](#skype-for-business-online).
- **Dynamics 365**, faça [esta etapa.](#dynamics365)
- **Power BI**, faça [esta etapa](#power-bi).
- **Serviços de Federação do Active Directory** para o Azure AD Conexão, faça estas [etapas](#active-directory-federation-services-ad-fs).
- **Serviços de terceiros ou** aplicativos de linha de negócios **(LOB)** integrados ao Office 365, [faça esta etapa](#line-of-business-apps).
- Uma solução de gerenciamento de dispositivo móvel (MDM) de terceiros, [faça esta etapa](#mobile-device-management).
- **Serviços do Azure** com sua assinatura Office 365, [faça esta etapa](#microsoft-azure).

## <a name="general-tenant-migration-considerations"></a>Considerações gerais sobre migração de locatários

**Aplica-se a:** Todos os clientes que Office 365 na instância do Microsoft Deutschland Cloud

Office 365 identificadores de usuário e locatário são preservados durante a migração. As chamadas de serviço do Azure AD são redirecionadas do Microsoft Cloud Deutschland para Office 365 Serviços Globais e são transparentes para Office 365 serviços.

- As Solicitações gerais de Assunto de Proteção de Dados (RGPD) são executadas a partir do portal de administração do Azure para solicitações futuras. Quaisquer dados de diagnóstico herdados ou não do cliente residentes no Microsoft Cloud Deutschland são excluídos em ou antes de 30 dias.
- Solicitações de autenticação multifafatória (MFA) que usam Microsoft Authenticator são exibidas como objectID do usuário (um GUID) enquanto o locatário é copiado para serviços Office 365 usuário. As solicitações de MFA terão o desempenho esperado apesar desse comportamento de exibição.  Microsoft Authenticator contas que foram ativadas usando pontos de extremidade Office 365 serviços exibirão o nome principal do usuário (UPN).  Contas adicionadas usando pontos de extremidade do Microsoft Cloud Deutschland exibirão o objectID do usuário, mas funcionarão com pontos de extremidade do Microsoft Cloud Deutschland e Office 365 serviços.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Prepare-se para notificar os usuários sobre como reiniciar e entrar e sair de seus clientes após a migração. | Office licenciamento de cliente fará a transição do Microsoft Cloud Deutschland para Office 365 serviços na migração. Os clientes escolhem uma nova licença válida depois de entrar e sair para Office clientes. | Os produtos Office usuários precisam atualizar licenças de serviços Office 365 usuários. Se as licenças não são atualizadas, os produtos Office podem ter erros de validação de licença. |
| Certifique-se de conectividade de rede [Office 365 URLs de serviços e endereços IP.](https://aka.ms/o365urls) | Todos os clientes e serviços hospedados pelo cliente que são usados para acessar Office 365 serviço devem ser capazes de acessar os pontos de extremidade Office 365 serviços globais. <br>Caso você ou seus parceiros de colaboração tenham regras de firewall em vigor que impeçam o acesso às URLs e endereços IP listados em [URLs](https://aka.ms/o365urls) de serviços do Office 365 e endereços IP devem alterar as regras de firewall para permitir o acesso aos pontos de extremidade de serviço global do Office 365| Falhas do serviço ou do software cliente podem ocorrer se isso não for feito antes da Fase 4  |
| Cancele assinaturas de avaliação. | As assinaturas de avaliação não serão migradas e bloquearão a transferência de assinaturas pagas. | Os serviços de avaliação expiram e não funcionam se acessados pelos usuários após o cancelamento. |
| Analise as diferenças nos recursos de licença entre o Microsoft Cloud Deutschland e o Office 365 Global Services. | Office 365 serviços incluem recursos e serviços adicionais não disponíveis no Microsoft Cloud Deutschland atual. Durante a transferência de assinatura, novos recursos estarão disponíveis para os usuários. | <ul><li> Analise os diferentes recursos fornecidos pelas licenças do Microsoft Cloud Deutschland e Office 365 Global Services. Comece com a descrição [do serviço Office 365 plataforma.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description) </li><li> Determine se os novos recursos dos serviços Office 365 devem ser desabilitados inicialmente para limitar os efeitos nos usuários ou no gerenciamento de alterações do usuário e alterar as atribuições de licença do usuário conforme necessário. </li><li>Preparar usuários e equipe de help desk para novos serviços e recursos fornecidos pelos Office 365 serviços. |
| Crie políticas de [retenção em](/microsoft-365/compliance/retention) toda a organização para proteger contra exclusão inadvertida de conteúdo durante a migração.  |<ul><li>Para garantir que o conteúdo não seja excluído inadvertidamente pelos usuários finais durante a migração, os clientes podem optar por habilitar uma política de retenção em toda a organização. </li><li>Embora a retenção não seja necessária, já que as retenções colocadas a qualquer momento durante a migração devem funcionar conforme o esperado, ter uma política de retenção é um mecanismo de segurança de back-up. Ao mesmo tempo, uma política de retenção pode não ser usada por todos os clientes, especialmente aqueles que estão preocupados com a preservação.</li></ul>| Aplicar política de retenção conforme descrito em [Saiba mais sobre políticas de retenção e rótulos de retenção.](/microsoft-365/compliance/retention-policies) Falhas do serviço ou do software cliente podem ocorrer se isso não for feito antes da Fase 4 de 9. </li></ul>|
|||||

## <a name="dns-entries-for-custom-domains"></a>Entradas DNS para domínios personalizados

<!-- before phase 9 -->

**Aplica-se** a : clientes que definiram um CNAME _msoid_ personalizado em seu próprio domínio DNS ou que usam um domínio para Exchange Online

Se configurado, o CNAME _msoid_ afetará apenas clientes usando o cliente desktop Office (Microsoft 365 Apps, Office 365 ProPlus, Office 2019, 2016, ...).

Caso você tenha definido um CNAME DNS chamado _msoid_ em um ou muitos namespaces DNS que você possui, você precisa remover o CNAME até o final da fase 8 no máximo. Você pode remover o _msoid_ CNAME a qualquer momento antes do final da fase 8.

Para verificar se você definiu um CNAME em seu namespace DNS, siga as etapas abaixo e substitua contoso.com _pelo_ seu próprio nome de domínio:

```console
nslookup -querytype=CNAME msoid.contoso.com
```

Se a linha de comando retornar um registro DNS, remova o CNAME _msoid_ do seu domínio.

> [!NOTE]
> Se você estiver usando um domínio personalizado para Exchange Online, precisará ter acesso ao seu provedor de hospedagem DNS. Certifique-se de que você pode acessar e editar suas configurações de DNS, você modificará os registros DNS durante a migração.

## <a name="office-apps"></a>Office Aplicativos

**Aplica-se a**: clientes que usam Office Aplicativos, especialmente em Windows clientes <br>
**Quando aplicado:** a qualquer momento antes do início da fase 9

Office 365 locatários em transição para a região "Alemanha" exigem que todos os usuários fechem, saiam do Office 365 e voltem para todos os aplicativos de área de trabalho do Office (Word, Excel, PowerPoint, Outlook, etc.) e OneDrive for Business cliente após a migração do locatário atingir a fase 9. Entrar e entrar, permite que os serviços Office obtenham novos tokens de autenticação do serviço global do Azure AD.

Isso é necessário para todos os clientes. Para garantir uma experiência de migração suave, é altamente recomendável informar e instruir todos os usuários afetados com antecedência e em um estágio inicial sobre essa atividade futura.

Os clientes com clientes Windows clientes gerenciados podem preparar Windows máquinas com a ferramenta de recortamento de cliente [Office (OCCT)](https://github.com/microsoft/OCCT). A OCCT foi projetada para ser executado periodicamente em clientes Windows até que o locatário atingiu a fase 9 da migração. Quando a fase 9 for atingida, a OCCT executará todas as alterações necessárias no computador automaticamente sem a interação do usuário.

A OCCT pode ser implantada em Windows clientes a qualquer momento antes da fase 9. Se a OCCT deve dar suporte à experiência de migração, recomendamos iniciar a implantação assim que possível para equipar um número máximo de clientes.

## <a name="active-directory-federation-services-ad-fs"></a>Serviços de Federação do Active Directory (AD FS)

**Aplica-se a**: clientes que usam o AD FS no local para autenticar usuários que se conectam a Microsoft Office 365<br>
**Quando aplicado:** a qualquer momento antes do início da fase 2

Ler e aplicar as etapas [de Migração do ADFS](ms-cloud-germany-transition-add-adfs.md)

## <a name="sharepoint-online"></a>SharePoint Online

**Aplica-se a**: clientes usando SharePoint 2013 local<br>
**Quando aplicado:** a qualquer momento antes do início da fase 4

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Limite SharePoint fluxos de trabalho de 2013, use durante a migração SharePoint Online. | Reduza SharePoint fluxos de trabalho de 2013 e conclua fluxos de trabalho de pré-voo antes das transições. | A inação pode resultar em confusão do usuário e chamadas de help desk. |
||||

## <a name="exchange-online"></a>Exchange Online

<!-- before phase 5 -->

**Aplica-se a**: Exchange Online clientes<br>
**Quando aplicado:** a qualquer momento antes do final da fase 9

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Notifique parceiros externos sobre a próxima transição para Office 365 serviços. |  Os clientes devem notificar seus parceiros com os quais eles habilitaram a configuração de espaço de endereço de disponibilidade e calendário de compartilhamento (permitir o compartilhamento de informações de disponibilidade com Office 365). A configuração de disponibilidade precisa fazer a transição para usar os pontos de extremidade [Office 365 em](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide) todo o mundo quando Exchange Online a migração for concluída. | A falha ao fazer isso pode resultar em falha no serviço ou no cliente em uma fase posterior da migração do cliente. |
| Notifique os usuários das alterações de cliente IMAP4/POP3/SMTP necessárias. | Os usuários que têm conexões de dispositivo com pontos de extremidade do Microsoft Cloud Deutschland para protocolos cliente IMAP4, POP3, SMTP são necessários para atualizar manualmente seus dispositivos cliente para alternar para os nomes de servidor [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/pop3-and-imap4#settings-users-use-to-set-up-pop3-or-imap4-access-to-their-exchange-online-mailboxes). | Antes de comunicar essa dependência aos usuários desses protocolos e garantir que eles alternem para usar Outlook ou Outlook na Web durante essa migração. A falha na atualização dos pontos de extremidade do cliente resultará em falhas de conexão do cliente em relação ao Microsoft Cloud Deutschland quando as caixas de correio de usuário são migradas. |
||||

### <a name="exchange-online-hybrid-customers"></a>Exchange Online Clientes híbridos

**Aplica-se a:** Todos os clientes que usam uma configuração Exchange híbrida ativa com Exchange servidores locais<br>
**Quando aplicado:** a qualquer momento antes do início da Fase 5

Enterprise clientes com uma implantação híbrida do Exchange Online e um Exchange Server local executem o Assistente de Configuração Híbrida (HCW) e o AAD Conexão para manter e estabelecer a instalação híbrida.
Exchange Online Os administradores híbridos devem executar o assistente de Configuração Híbrida **(HCW)** várias vezes como parte dessa transição.
Ao fazer a transição do Microsoft Cloud Deutschland para a região Office 365 Alemanha, o administrador deve executar a com build mais recente do HCW no modo "Office 365 Alemanha" antes do início da migração Exchange (Fase 5). Em seguida, execute o HCW novamente no modo "Office 365 Worldwide" na conclusão da Fase 5 para finalizar a implantação local com as configurações da região Office 365 Alemanha. A execução do HCW não deve ser executada durante a Fase 5, é importante executar o HCW não até que a fase 5 seja final.
Os atributos de diretório são sincronizados entre o Office 365 e o Azure AD com a implantação local por meio do AAD Conexão.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Executar o HCW usando as configurações Office 365 Alemanha <br><br> <i>Você pode iniciar essa atividade imediatamente após receber a notificação do centro de mensagens de que sua Office 365 de locatários foi iniciada (fase 1).</i>| Desinstalar e executar novamente o HCW (17.0.5378.0 ou superior) antes da Fase 5 garantirá que sua configuração local esteja preparada para enviar e receber emails com usuários do Microsoft Cloud Deutschland e usuários migrados para a região Office 365 [https://aka.ms/hybridwizard](https://aka.ms/hybridwizard) Alemanha. <p><li> No HCW, para a caixa de listagem abaixo Minha organização **Office 365 é** hospedada por , selecione Office 365 **Alemanha.** | A falha na conclusão dessa tarefa antes do início da Fase 5 [Exchange Migração] pode resultar em NDRs para emails roteados entre sua implantação Exchange local e Office 365.
| Preservando configurações de Caixa de Correio Compartilhada | Alguns clientes híbridos converteram caixas de correio de usuário na nuvem para serem caixas de correio "compartilhadas" usando Exchange Online comandos. Essa configuração de caixa de correio de nuvem é escrita na caixa de correio e no diretório Exchange Online local, no entanto, ela não é sincronizada novamente com o Active Directory do cliente por meio do AAD Conexão. O resultado é uma discrepância entre a representação do Active Directory dos valores RemoteRecipientType e RemoteDisplayType da caixa de correio e que, Exchange Online definindo a caixa de correio como compartilhada. <br><br> O cliente é responsável por garantir que todas as caixas de correio compartilhadas sejam provisionadas corretamente `New-RemoteMailbox -Shared` usando `Enable-RemoteMailbox -Shared` , ou `Set-RemoteMailbox -Shared` .  Consulte esta referência sobre como [converter a caixa de correio de um usuário em um ambiente híbrido](/microsoft-365/admin/email/convert-user-mailbox-to-shared-mailbox?view=o365-worldwide).| A falha na conclusão dessa tarefa antes da Fase 5 [Exchange Online Migração] pode resultar em NDRs para Caixas de Correio Compartilhadas que se convertem novamente em caixas de correio não licençadas e perda de acesso compartilhado para caixas de correio afetadas. [As caixas de](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes) correio compartilhadas são convertidas inesperadamente em caixas de correio de usuário depois que a sincronização de diretório é executado em uma implantação híbrida Exchange descreve o impacto de não resolver isso antes da conclusão Exchange Online Migração.
||||

## <a name="skype-for-business-online"></a>Skype for Business Online

<!-- before phase 7 -->

**Aplica-se a**: Skype para clientes do Business Online<br>
**Quando aplicado:** a qualquer momento antes do início da fase 7

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Implantar Teams cliente de área de trabalho para usuários que acessam Skype for Business na Alemanha. | A migração Skype for Business os usuários Microsoft Teams para colaboração, chamada e chat. Implante o cliente Microsoft Teams desktop ou verifique se um navegador com suporte está disponível. | A inação resultará na indisponibilidade dos Microsoft Teams de colaboração. |
| Revise e prepare-se para alterações de DNS relacionadas à migração. | Alterações na zona DNS de propriedade do cliente para Skype for Business Online. |<ul><li>Recomendamos que você atualize o TTL (Time-to-Live) para quaisquer registros DNS de domínio de propriedade do cliente para 5 minutos para acelerar a atualização de registros DNS. No entanto, a transferência gerenciada pela Microsoft associada a essa alteração DNS pode ocorrer a qualquer momento dentro da janela de alteração de 24 horas fornecida. </li><li>A interrupção do serviço é possível no futuro. Os usuários não poderão fazer logoff no Skype for Business e serão redirecionados para a experiência de Teams migradas nos serviços Office 365 serviços. </li></ul>|
| Preparar treinamento do Usuário Final e Administração e preparação para a transição para Microsoft Teams. | Seja bem-sucedido em sua transição de Skype para Teams planejando a comunicação e a prontidão do usuário. | <ul><li>Os clientes precisam estar cientes dos novos serviços e como usar depois que seus serviços são transitivos para os serviços Office 365 serviços. </li><li>Depois que as alterações de DNS são feitas para os domínios de cliente e para o domínio inicial, os usuários entrariam no Skype for Business e veriam que eles agora são migrados para Teams. Isso também baixaria o cliente da área de trabalho para Teams em segundo plano. </li></ul>|
||||

## <a name="mobile-device-management"></a>Gerenciamento de dispositivo móvel

<!-- before phase 5 -->
**Aplica-se a:** Clientes que usam uma solução de gerenciamento de dispositivo móvel (MDM) de terceiros<br>
**Quando aplicado:** a qualquer momento antes do início da fase 5

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Prepare o treinamento de administração e usuário final sobre os usuários removendo e adicionando sua conta ao Microsoft Outlook para iOS e Android. | As contas do Microsoft Outlook para iOS e Android configuradas com caixas de correio no Microsoft Cloud Deutschland podem ter que ser removidas e adicionadas novamente ao Outlook para sincronizar corretamente a nova configuração de serviços Office 365. | Microsoft Outlook para clientes iOS e Android | Outlook caixas de correio configuradas anteriormente para o Microsoft Cloud Deutschland podem não escolher a nova configuração do Office 365 Services, levando a erros e desempenho degradado de outras experiências de usuário. Os administradores de IT são incentivados a fornecer documentação que instrui proativamente os usuários a remover e adicionar suas contas ao Microsoft Outlook para iOS e Android se ocorrerem problemas com a entrada ou sincronização de emails após a migração. |
| Determine se qualquer reconfiguração é necessária após a migração. | As soluções de Gerenciamento de Dispositivo Móvel (MDM) podem direcionar `outlook.de` pontos de extremidade. Nesta transição para serviços Office 365, os perfis de cliente devem ser atualizados para a URL de serviços Office 365, `outlook.office365.com` . | Exchange Online e clientes MDM | Os clientes podem continuar a funcionar enquanto o ponto de extremidade estiver acessível, mas falharão se os pontos de extremidade do `outlook.de` Microsoft Cloud Deutschland não estão mais disponíveis. |
|||||

## <a name="line-of-business-apps"></a>Aplicativos de linha de negócios

**Aplica-se a:** Clientes que usam aplicativos de linha de negócios (LOB) com pontos de extremidade fornecidos pelo Microsoft Cloud Deutschland<br>
**Quando aplicado:** após a conclusão da fase 2 e antes do final da fase 9

Se você estiver usando um serviço de terceiros ou aplicativos de linha de negócios (LOB) integrados ao Office 365, você deve resolver quaisquer dependências nos pontos de extremidade fornecidos pela instância do Microsoft Cloud Deutschland. Por exemplo, se seus aplicativos LOB estão se conectando `https://graph.microsoft.de/` a , você deve alterar o ponto de extremidade para `https://graph.microsoft.com/` . Os pontos de extremidade do serviço Microsoft Office 365 Global ficam disponíveis para seu locatário após a fase 2.

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Determine se qualquer reconfiguração é necessária após a migração. | Serviços e aplicativos de terceiros que se integram Office 365 podem ser codificados para esperar endereços IP e URLs do Microsoft Cloud Deutschland. | Ação necessária. A inação pode resultar em falhas do serviço ou do software cliente. |
||||

## <a name="dynamics-365"></a>Dynamics 365

**Aplica-se a**: clientes que usam o Microsoft Dynamics 365

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Para assinaturas de área de segurança do Dynamics 365, baixe o ambiente de produção da instância SQL Dynamics da sua assinatura do Dynamics 365 no Microsoft Cloud Deutschland. O backup de produção mais recente deve ser restaurado para a área de segurança antes da migração da área de segurança. | A migração do Dynamics 365 exige que os clientes assegurem que o ambiente de Área Desarmada seja atualizado com o banco de dados de produção mais recente. | A equipe do FastTrack ajudará os clientes na execução de execução de execução a seco para validar a atualização de versão de 8.x para 9.1.x. |
||||

## <a name="power-bi"></a>Power BI

**Aplica-se a**: clientes que usam Power BI

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Remoção de objetos Power BI assinaturas que não serão migradas Power BI Microsoft Cloud Deutschland para Office 365 serviços. | A migração Power BI serviços exigirá ação do cliente para excluir determinados artefatos, como conjuntos de dados e painéis. | <ul><li>Os administradores podem ter que remover os seguintes itens de sua assinatura: </li><li>Real-Time dados (por exemplo, conjuntos de dados de streaming ou push) </li><li>Power BI configuração e fonte de dados do Gateway de Dados local </li></ul>|
||||

## <a name="microsoft-azure"></a>Microsoft Azure

Se você estiver usando a mesma partição de Azure Active Directory de identidade para Office 365 e Microsoft Azure na instância do Microsoft Cloud Deutschland, certifique-se de que você está se preparando para a migração orientada pelo cliente dos serviços Microsoft Azure.

> [!NOTE]
> A migração de seus serviços Microsoft Azure pode não começar antes que seu locatário Office 365 tenha atingido a fase de migração 9 e deve ser concluída antes que a fase 10 de migração tenha sido iniciada.

Os clientes que usam Office 365 e recursos do Azure (por exemplo, rede, computação e armazenamento) realizarão a migração de recursos para a instância de serviços Office 365. Essa migração é responsabilidade do cliente. As postagens da Central de Mensagens sinalizam o início. A migração deve ser concluída antes da finalização da organização do Azure AD no ambiente Office 365 serviços. Para migrações do Azure, consulte o manual de migração do Azure, Visão geral das diretrizes de migração [para o Azure Germany](/azure/germany/germany-migration-main).

| Step(s) | Descrição | Impacto |
|:-------|:-------|:-------|
| Determine quais serviços do Azure estão em uso e prepare-se para a migração futura da Alemanha para o locatário Office 365 serviços de segurança trabalhando com seus parceiros. Siga as etapas descritas no playbook de migração [do Azure](/azure/germany/germany-migration-main). |<ul><li>A migração de recursos do Azure é uma responsabilidade do cliente e requer esforço manual seguindo as etapas prescritas. Entender quais serviços estão em uso na organização é fundamental para a migração bem-sucedida dos serviços do Azure. </li><li> Office 365 Os clientes alemães que têm assinaturas do Azure sob a mesma partição de identidade (organização) devem seguir a ordem prescrita pela Microsoft quando podem iniciar a migração de assinatura e serviços.</li></ul>|<ul><li>Os clientes podem ter várias assinaturas do Azure, cada assinatura contendo infraestrutura, serviços e componentes de plataforma. </li><li> Os administradores devem identificar assinaturas e participantes para garantir que a migração e a validação de prompts seja possível como parte desse evento de migração. </li><li>A falha na conclusão da migração dessas assinaturas e componentes do Azure dentro da linha do tempo prescrita afetará a conclusão da transição do Office e do Azure AD para os serviços Office 365 e poderá resultar em perda de dados. </li><li> Uma notificação do Centro de Mensagens sinaliza o ponto no qual a migração liderada pelo cliente pode começar. </li></ul>|
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

- [Migração do Microsoft Cloud Deutschland para serviços Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
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
