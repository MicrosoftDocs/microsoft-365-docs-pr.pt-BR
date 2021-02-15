---
title: Ações e impactos das fases de migração para a migração do Microsoft Cloud Deutschland (geral)
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 01/26/2021
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
description: 'Resumo: entenda as ações das fases de migração e os impactos da mudança do Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região de datacenter alemã.'
ms.openlocfilehash: 9dc2f4c0923f52bfc83a9177b595a6955a3afa8f
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242729"
---
# <a name="migration-phases-actions-and-impacts-for-the-migration-from-microsoft-cloud-deutschland-general"></a>Ações e impactos das fases de migração para a migração do Microsoft Cloud Deutschland (geral)

As migrações de locatário do Microsoft Cloud Deutschland para a região Alemanha dos serviços do Office 365 da Microsoft são executadas como um conjunto de fases e suas ações configuradas para cada carga de trabalho. Esta figura mostra as nove fases da migração para os novos datacenters alemães.

![As nove fases da migração para os novos datacenters da Alemanha](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

As fases e suas ações garantem que dados e experiências essenciais sejam migrados para os serviços do Office 365. Depois que seu locatário for adicionado à fila de migração, cada carga de trabalho será concluída como um conjunto de etapas executadas no serviço de back-back. Algumas cargas de trabalho podem exigir ações do administrador (ou do usuário) ou a migração pode afetar o uso das fases executadas e discutidas em Como a migração [é organizada?](ms-cloud-germany-transition.md#how-is-the-migration-organized)

As seções a seguir contêm ações e efeitos para cargas de trabalho à medida que avançam por várias fases da migração. Revise as tabelas e determine quais ações ou efeitos são aplicáveis à sua organização. Verifique se você está preparado para executar as etapas nas respectivas fases, conforme necessário. A falha na conclusão das etapas necessárias pode resultar em interrupção do serviço e pode atrasar a conclusão da migração para os serviços do Office 365.

## <a name="sharepoint-online-phase-4-of-9"></a>SharePoint Online (Fase 4 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| O SharePoint e o OneDrive são transições. | O SharePoint e o OneDrive são migrados do Microsoft Cloud Deutschland para os serviços do Office 365 nesta fase. As URLs existentes do Microsoft Cloud Deutschland são preservadas (por exemplo, `contoso.sharepoint.de` ). Os tokens emitidos pelos serviços do Microsoft Cloud Deutschland ou do Office 365 são válidos durante a transição. | Clientes do SharePoint | - O conteúdo será somente leitura por dois breves períodos durante a migração. Durante esse tempo, espere uma faixa "não é possível editar conteúdo" no SharePoint. <br><br> - O índice de pesquisa não será preservado e pode levar até 10 dias para ser reconstruído. <br><br> - O conteúdo do SharePoint/OneDrive será somente leitura por dois breves períodos durante a migração. Os usuários verão uma faixa "você não pode editar conteúdo" brevemente durante esse período. <br><br> - O índice de pesquisa pode estar indisponível enquanto o índice é reconstruído. Durante esse período, as consultas de pesquisa podem não retornar resultados completos. <br><br> - Os sites existentes são preservados. |
|||||

Considerações adicionais:

- Após a conclusão da migração do SharePoint Online para a região alemã, os índices de dados são reconstruídos. Os recursos que dependem dos índices de pesquisa podem ser afetados enquanto a reindexação é concluída.

- Se sua organização ainda usa fluxos de trabalho do SharePoint 2010, eles não funcionarão mais após 31 de dezembro de 2021. Os fluxos de trabalho do SharePoint 2013 permanecerão com suporte, embora seja desligado por padrão para novos locatários a partir de 1º de novembro de 2020. Após a conclusão da migração para o serviço do SharePoint Online, recomendamos que você vá para o Power Automate ou outras soluções com suporte.

- Após a conclusão da migração do OneDrive para a região alemã, os índices de dados são reconstruídos. Os recursos que dependem dos índices de pesquisa podem ser afetados enquanto a reindexação está em andamento.

- Os clientes do Microsoft Cloud Deutschland cuja instância do SharePoint Online ainda não migrou precisam permanecer no módulo PowerShell do SharePoint Online/Microsoft.SharePointOnline.CSOM versão 16.0.20616.12000 ou abaixo. Caso contrário, as conexões com o SharePoint Online via PowerShell ou o modelo de objeto do lado do cliente falharão.

- Os clientes do Microsoft Cloud Deutschland cuja instância do SharePoint Online é migrada devem atualizar o módulo do PowerShell do SharePoint Online/Microsoft.SharePointOnline.CSOM para a versão 16.0.20717.12000 ou superior. Caso contrário, as conexões com o SharePoint Online via PowerShell ou o modelo de objeto do lado do cliente falharão.


## <a name="exchange-online-phase-5-of-9"></a>Exchange Online (Fase 5 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| A nova região da Alemanha é adicionada à configuração existente da organização, e as caixas de correio são movidas para os serviços do Office 365. | A configuração do Exchange Online adiciona a nova região alemã go-local à organização de transição. Essa região de serviços do Office 365 é definida como padrão, o que permite que o serviço de balanceamento de carga interno redistribua caixas de correio para a região padrão apropriada nos serviços do Office 365. Nesta transição, os usuários de ambos os lados (serviços da Alemanha ou do Office 365) estão na mesma organização e podem usar qualquer ponto de extremidade de URL. | Exchange Online | – Fazer a transição de usuários e serviços das URLs da Alemanha para as URLs de serviços do Office 365 ( `https://outlook.office365.com` ). <br><br> - Os usuários continuarão acessando o serviço por meio de URLs herddas da Alemanha durante a migração. Nenhuma ação imediata necessária. <br><br> - Os usuários devem começar a usar o portal office.com para recursos do Office Online (Calendário, Email, Pessoas). A navegação para serviços que ainda não foram migrados para os serviços do Office 365 não funcionará até a migração. <br><br> - O Outlook Web App não fornecerá a experiência de pasta pública durante a migração. |
|||||

Considerações adicionais:

- `myaccount.msft.com` só funcionará após a mudança do Office 365. Os links produzirão mensagens de erro "algo deu errado" até esse momento.

- Os usuários do Outlook Web App que acessam uma caixa de correio compartilhada em outro ambiente (por exemplo, um usuário no ambiente da Alemanha acessa uma caixa de correio compartilhada no ambiente global) serão solicitados a autenticar uma segunda vez. O usuário deve primeiro autenticar e acessar sua caixa de correio, em `outlook.office.de` seguida, abrir a caixa de correio compartilhada que está em `outlook.office365.com` . Eles precisarão autenticar uma segunda vez ao acessar os recursos compartilhados hospedados no outro serviço.

- Para clientes existentes do Microsoft Cloud Deutschland ou aqueles em transição, quando uma caixa de correio compartilhada é adicionada ao Outlook usando o Arquivo **> Informações >** Adicionar Conta, a exibição de permissões de calendário pode falhar (o cliente do Outlook tenta usar a API `https://outlook.office.de/api/v2.0/Me/Calendars` Rest).) Os clientes que quiserem adicionar uma conta para exibir permissões de calendário podem adicionar a chave do Registro conforme descrito nas alterações de experiência do usuário para compartilhar um calendário no [Outlook para](https://support.microsoft.com/office/user-experience-changes-for-sharing-a-calendar-in-outlook-5978620a-fe6c-422a-93b2-8f80e488fdec) garantir que essa ação seja bem-sucedida. Essa chave do Registro pode ser implantada em toda a organização usando a Política de Grupo.

- Durante a fase de migração, o uso dos cmdlets Do PowerShell **New-migrationEndpoint**, **Set-MigrationEndpoint** e **Test-MigrationsServerAvailability** pode resultar em erros (erro no proxy). Isso acontece quando a caixa de correio de arbitragem migrou para todo o mundo, mas a caixa de correio de administrador não migrou ou vice-versa. Para resolver isso, ao criar a sessão do PowerShell do locatário, use a caixa de correio de arbitragem como a dica de roteamento no **ConnectionUri**. Por exemplo: `New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid?email=Migration.8f3e7716-2011-43e4-96b1-aba62d229136@TENANT.onmicrosoft.de" -Credential $UserCredential -Authentication Basic -AllowRedirection`

- Se você estiver usando o Exchange Online híbrido:

    - Você deve reenviar o assistente de Configuração Híbrida (HCW) para atualizar a configuração local no Microsoft Cloud Deutschland antes da transição e, em caso de limpeza, no HCW, nos serviços do Office 365. Atualizações de DNS adicionais podem ser necessárias se você usar domínios personalizados.

Para saber mais sobre as diferenças para as organizações na migração e após a migração dos recursos do Exchange Online, revise as informações na experiência do cliente durante a migração para os serviços do [Office 365](ms-cloud-germany-transition-experience.md)nas novas regiões de datacenter alemãs.

## <a name="exchange-online-protection-phase-6-of-9"></a>Proteção do Exchange Online (Fase 6 de 9)

Os recursos do Exchange Online Protection (EOP) back-end são copiados para a nova região da Alemanha. 

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração do roteamento do Exchange Online e detalhes históricos das mensagens. | O Exchange Online permite o roteamento de hosts externos para o Office 365. Os registros MX externos são transições para roteamento para o serviço EOP. A configuração do locatário e os detalhes históricos são migrados. | Clientes do Exchange Online | – As entradas dns gerenciadas pela Microsoft são atualizadas do EOP do Office 365 Germany para os serviços do Office 365. <br><br> - Os clientes devem aguardar 30 dias após a gravação dupla do EOP para a migração do EOP. Caso contrário, pode haver perda de dados. |
|||||



## <a name="skype-for-business-online-phase-7-of-9"></a>Skype for Business Online (Fase 7 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Migração do Skype for Business para o Teams. | Os clientes existentes do Skype for Business são migrados para os serviços do Office 365 na Europa e, em seguida, migrados para o Microsoft Teams na região alemã dos serviços do Office 365. | Clientes do Skype for Business | - Os usuários não poderão entrar no Skype for Business na data de migração. Dez dias antes da migração, postaremos no Centro de administração para que você saiba quando a migração ocorrerá e novamente quando iniciarmos a migração. <br><br> - A configuração de política é migrada. <br><br> - Os usuários serão migrados para o Teams e não terão mais o Skype for Business após a migração. <br><br> - Os usuários devem ter o cliente de área de trabalho do Teams instalado. A instalação ocorrerá durante os 10 dias por meio da política na infraestrutura do Skype for Business, mas se isso falhar, os usuários ainda precisarão baixar o cliente ou se conectar com um navegador suportado. <br><br> - Contatos e reuniões serão migrados para o Teams. <br><br> - Os usuários não poderão entrar no Skype for Business entre as transições de serviço de tempo para os serviços do Office 365 e não até que as entradas DNS do cliente sejam concluídas. <br><br> - Os contatos e as reuniões existentes continuarão a funcionar como reuniões do Skype for Business. |
|||||


## <a name="office-apps-phase-8-of-9"></a>Aplicativos do Office (Fase 8 de 9)

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Clientes, Office Online durante a reposição do cliente do Office, o Azure AD finaliza o escopo do locatário para apontar para os serviços do Office 365. | Essa alteração de configuração permite que os clientes do Office atualizem e apontem para os pontos de extremidade de serviços do Office 365. | Todos os clientes do Office | - Notifique os usuários para fechar todos os aplicativos do _Office_ e, em seguida, entre novamente (ou force os clientes a reiniciar e os usuários a entrar) para permitir que os clientes do Office atendam à alteração. <br><br> - Notifique os usuários  e a equipe de help desk de que os usuários podem ver uma faixa do Office solicitando que eles reativam os aplicativos do Office dentro de 72 horas após a mudança. <br><br> - Todos os aplicativos do Office em máquinas pessoais devem ser fechados, e os usuários devem sair e entrar novamente. Na barra de ativação Amarela, entre para reativar os serviços do Office 365. <br><br> - Máquinas compartilhadas exigirão ações semelhantes a máquinas pessoais e não exigirão um procedimento especial. <br><br> - Em dispositivos móveis, os usuários devem sair dos aplicativos, feche-os e entre novamente. |
|||||


## <a name="office-services"></a>Serviços do Office

O serviço de mru (mru) usado mais recentemente no Office é uma migração do serviço da Alemanha para os serviços do Office 365, não uma migração. Somente os links DE MRU do lado dos serviços do Office 365 estarão visíveis após a migração do Office.com portal. Os links de MRU do serviço da Alemanha não são visíveis como links MRU nos serviços do Office 365. No Office 365, os links de MRU são acessíveis somente depois que a migração do locatário é concluída.

## <a name="subscription"></a>Assinatura

| Step(s) | Descrição | Aplicável a | Impacto |
|:-------|:-----|:-------|:-------|
| Não é possível migrar os clientes sem o consentimento. | A Microsoft obtém o direito de migrar de duas maneiras, o que permite à Microsoft orquestrar a transição de dados e serviços para a instância de serviços do Office 365. <br> O administrador opta pela migração orientada pela Microsoft. <br> Os clientes renovam todas as assinaturas em seu locatário do Microsoft Cloud Deutschland após 1º de maio de 2020. Notificaremos esses clientes sobre o direito de migração a cada mês, aguardaremos 30 dias para dar aos clientes a chance de cancelar e, em seguida, optaremos diretamente pelo ICM. | Todos os clientes do Office | - O locatário é marcado como consentido para migração, e o Centro de Administração exibe a confirmação. <br><br> - A confirmação é postada no locatário do Centro de Mensagens do Cloud Germany. A configuração do serviço continua dos pontos de extremidade do Microsoft Cloud Deutschland. <br><br> – Monitore o Centro de Mensagens para atualizações sobre o status da fase migração. |
| As assinaturas são transferidas e as licenças são reatribuídas. | Depois que o locatário for transferido para os serviços do Office 365, as assinaturas de serviços correspondentes do Office 365 serão adquiridas para as assinaturas transferidas do Microsoft Cloud Deutschland. Os usuários com licenças atribuídas do Microsoft Cloud Deutschland receberão licenças de serviços do Office 365. As assinaturas herdada do Microsoft Cloud Deutschland são removidas do locatário de serviços do Office 365 após a conclusão. | Todos os clientes do Office | - As alterações nas assinaturas existentes serão bloqueadas (por exemplo, nenhuma nova compra de assinatura ou alterações na contagem de estações) durante essa fase. <br><br> - As alterações de atribuição de licença serão bloqueadas. <br><br> - A assinatura do Microsoft Cloud Deutschland será migrada para a assinatura de serviços do Office 365 correspondente. A oferta de serviços do Office 365 dessa assinatura é definida pela Microsoft (também conhecida como mapeamento _de oferta)._ <br><br> - O número de recursos (planos de serviço) oferecidos pelos serviços do Office 365 pode ser maior do que a oferta original do Microsoft Cloud Deutschland. As licenças de usuário nos serviços do Office 365 serão equivalentemente atribuídas a recursos semelhantes do Microsoft Cloud Deutschland (planos de serviço). As licenças de usuário de todos os usuários serão atribuídas automaticamente aos novos recursos. O administrador precisa tomar uma ação explícita para desabilitar essas licenças, se necessário. <br><br> - Quando a migração de assinatura estiver concluída, tanto os serviços do Office 365 quanto as assinaturas da Alemanha estarão visíveis no Portal de Administração do Office 365, com o status das assinaturas da Alemanha como _desprovisionadas._ <br><br> - Os usuários receberão licenças reatribuídas vinculadas às novas assinaturas de serviços do Office 365. Todos os processos do cliente que têm dependências em assinaturas da Alemanha ou GUIDs de SKU serão desfeitos e precisarão ser revisados com a oferta de serviços do Office 365. <br><br> – Novas assinaturas nos serviços do Office 365 serão adquiridas com o novo termo (mensal/trimestral/anual) e o cliente receberá um reembolso rateado pelo saldo não usado da assinatura do Microsoft Cloud Deutschland. <br><br> - Os locatários do Parceiro Microsoft Cloud Deutschland não serão migrados. Os clientes CSP serão migrados para os serviços do Office 365 sob o novo locatário de serviços do Office 365 do mesmo parceiro. Após a migração do cliente, o parceiro só pode gerenciar esse cliente a partir do locatário de serviços do Office 365. <br><br> - Funcionalidade adicional disponível (por exemplo, Microsoft Planner e Microsoft Flow), a menos que seja desabilitada pelo administrador de locatários. Para obter informações sobre como desabilitar planos de serviço atribuídos às licenças dos usuários, consulte Desabilitar o acesso aos serviços do [Microsoft 365](disable-access-to-services-while-assigning-user-licenses.md)ao atribuir licenças de usuário.  |
|||||

## <a name="next-step"></a>Próxima etapa

[Executar pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)

## <a name="more-information"></a>Mais informações

Iniciando:

- [Migração do Microsoft Cloud Deutschland para os serviços do Office 365 nas novas regiões de datacenter alemãs](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)
- [Experiência do cliente durante a migração](ms-cloud-germany-transition-experience.md)

Passando pela transição:

- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD](ms-cloud-germany-transition-azure-ad.md), [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
