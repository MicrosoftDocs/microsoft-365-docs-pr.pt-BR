---
title: Proteção contra ameaças
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Os administradores podem saber mais sobre a proteção contra ameaças no Microsoft 365 e configurar como usá-la para sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 98a20c8805ff9eb735ca880cfc24a0acf9698b3e
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561196"
---
# <a name="protect-against-threats"></a>Proteção contra ameaças

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Aqui está um guia de início rápido que divide a configuração do defender para Office 365 em partes. Se você é novo em recursos de proteção contra ameaças no Office 365, não tem certeza de onde começar, ou se você aprende melhor *fazendo* isso, use este guia como uma lista de verificação e um ponto de partida.

> [!IMPORTANT]
> **As configurações iniciais recomendadas são incluídas para cada tipo de política; no entanto, muitas opções estão disponíveis e você pode ajustar suas configurações para atender às necessidades específicas da sua organização**. Aguarde aproximadamente 30 minutos para que as políticas ou as alterações funcionem da mesma forma por meio do datacenter.

## <a name="requirements"></a>Requisitos

### <a name="subscriptions"></a>Assinaturas

Os recursos de proteção contra ameaças estão incluídos em *todas as* assinaturas do Microsoft ou do Office 365; no entanto, algumas assinaturas têm recursos avançados. A tabela a seguir lista os recursos de proteção incluídos neste artigo junto com os requisitos mínimos de assinatura.

> [!TIP]
> Observe que, além das instruções para ativar a auditoria, *as etapas* iniciam o anti-malware, o anti-phishing e o antispam, que são marcados como parte do Office 365 proteção do Exchange Online (**EOP**). Isso pode parecer estranho em um artigo do defender para Office 365, até que você se lembre (o **defender para Office 365**) contém e cria o EOP.

****

|Tipo de proteção|Requisito de assinatura|
|---|---|
|Log de auditoria (para fins de relatórios)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Proteção antimalware|[Proteção do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Proteção anti-phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Proteção antispam|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Limpeza automática de zero horas (para email)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Proteção contra URLs e arquivos mal-intencionados em emails e documentos do Office (links seguros e anexos seguros)|[Microsoft defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Ativar a ATP para cargas de trabalho do SharePoint, OneDrive e Microsoft Teams|[Defender para Office 365 ](atp-for-spo-odb-and-teams.md)|
|Proteção anti-phishing avançada|[Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Funções e permissões

Para configurar as políticas do defender for Office 365, você deve receber uma função apropriada no [centro de conformidade & segurança](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Confira a tabela abaixo para funções que podem executar essas ações.

****

|Função ou grupo de funções|Onde saber mais|
|---|---|
|administrador global|[Sobre as funções de administrador do Microsoft 365 ](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Administrador de Segurança|[Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gerenciamento de Organização do Exchange Online|[Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>e<br> [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Para saber mais, confira [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Antes de começar, ative o log de auditoria para relatórios e investigação

Inicie o log de auditoria no início. Você precisará de **auditoria para realizar** algumas das etapas a seguir. O log de auditoria está disponível em assinaturas que incluem o [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para exibir dados em relatórios de proteção contra ameaças, como o [painel de segurança](security-dashboard.md), [relatórios de segurança de email](view-email-security-reports.md)e [Explorer](threat-explorer.md), o log de auditoria deve estar *ativado*. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="part-1---anti-malware-protection"></a>Parte 1-proteção Antimalware

A [proteção Antimalware](anti-malware-protection.md) está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. No [centro de conformidade & segurança](https://protection.office.com), escolha **Threat management**  >  **Policy**  >  **anti-malware** de política de gerenciamento de ameaças.

2. Clique duas vezes na política **padrão** e, em seguida, escolha **configurações**.

3. Especifique as seguintes configurações:

    - Na seção **resposta de detecção de malware** , mantenha a configuração padrão **no**.

    - Na seção **filtro de tipos de anexo comuns** , escolha **ativado**.

4. Clique em **Salvar**.

Para saber mais sobre opções de política Antimalware, consulte [Configure anti-malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection"></a>Parte 2-proteção contra phishing

A [proteção contra phishing](anti-phishing-protection.md) está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). A proteção contra phishing avançada está disponível no [defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

O procedimento a seguir descreve como configurar uma política anti-phishing no Microsoft defender para Office 365. As etapas são semelhantes à configuração de uma política anti-phishing no EOP.

1. No [centro de conformidade & segurança](https://protection.office.com), escolha política de **Gerenciamento de ameaças**  >  **Policy**  >  **ATP anti-phishing**.

2. Clique em **política padrão**.

3. Na seção **representação** , clique em **Editar** e especifique as seguintes configurações:

   - Na guia **Adicionar usuários para proteger** *, ative a* proteção. Em seguida, adicione usuários, como os membros da diretoria da sua organização, seu CEO, CFO e outros líderes seniores. (Você pode digitar um endereço de email individual ou clicar para exibir uma lista.)

   - Na guia **adicionar domínios para proteger** , ative **automaticamente os domínios que eu sou proprietário**. Se você tiver domínios personalizados, adicione-os agora.

   - Na guia **ações** , selecione **colocar a mensagem em quarentena** para as opções **usuário representado** e **domínio representado** . Além disso, ative as dicas de segurança de representação.

   - Na guia **inteligência de caixa de correio** , verifique se a inteligência de caixa de correio está ativada e ative a proteção de representação baseada em inteligência de caixa de correio. Na lista **se o email é enviado por um usuário representado** , escolha **colocar a mensagem em quarentena**.

   - Na guia **Adicionar remetentes confiáveis e domínios** , especifique os remetentes ou domínios confiáveis que você deseja adicionar.

   - **Salve** na guia **revisar suas configurações** depois de revisar suas configurações.

4. Na seção **spoof** , clique em **Editar** e especifique as seguintes configurações:

   - Na guia **configurações de filtro de falsificação** , verifique se a proteção contra falsificação está ativada.

   - Na guia **ações** , escolha **colocar a mensagem em quarentena**.

   - **Salve** na guia **revisar suas configurações** depois de revisar as alterações. (Se você não fez nenhuma alteração, **cancele**.)

5. Feche a página de configurações de política padrão.

Para saber mais sobre suas opções de política anti-phishing, consulte [Configure anti-phishing Policies in Microsoft defender for Office 365](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection"></a>Parte 3-proteção antispam

A [proteção](anti-spam-protection.md) antispam está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. No [centro de conformidade & segurança](https://protection.office.com), escolha **Threat management**  >  **Policy**  >  **anti-spam** de política de gerenciamento de ameaças.

2. Na guia **Personalizar** , ative as configurações personalizadas.

3. Expanda **política de filtro de spam padrão**, clique em **Editar política** e especifique as seguintes configurações:

   - Na seção **ações de spam e em massa** , defina o limite para um valor de 5 ou 6.

   - Na seção **permitir listas** , revise (e/ou edite) seus remetentes e domínios permitidos.

4. Clique em **Salvar**.

Para saber mais sobre suas opções de política antispam, consulte [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4-proteção contra URLs e arquivos mal-intencionados (links seguros e anexos seguros no defender para Office 365)

A proteção de horário de clique de URLs e arquivos mal-intencionados está disponível em assinaturas que incluem [o Microsoft defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Ela é configurada por meio de [anexos seguros](atp-safe-attachments.md) e políticas de [links seguros](atp-safe-links.md) .

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Políticas de anexos seguros no Microsoft defender para Office 365

Para configurar [anexos seguros](atp-safe-attachments.md), crie pelo menos uma política de links seguros.

1. No [centro de conformidade & segurança](https://protection.office.com), escolha a política de **Gerenciamento de ameaças**  >  **Policy**  >  e **anexos seguros de ATP** e clique em **criar**.

2. No assistente de **nova política de anexos seguros** que aparece, defina as seguintes configurações:

   - Na caixa **nome** , digite `Block malware` e clique em **Avançar**.

   - Na página **configurações** , defina as seguintes configurações:
     - Na seção **resposta de malware desconhecido de anexos seguros** , escolha **Bloquear**.
     - Na seção **redirecionar anexo** , selecione a opção **habilitar redirecionamento**. Especifique o endereço de email para o operador ou administrador de segurança da sua organização, que examinará os arquivos detectados.

     Clique em **Avançar**.

3. Na página **aplicado a** , clique em **Adicionar uma condição**, escolha **aplicado se: o domínio do destinatário é**, clique em **Adicionar**, selecione seu domínio ou domínios, clique em **Adicionar**, em **concluído** e em **Avançar**.

4. Revise suas configurações e clique em **concluir**.

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Políticas de links seguros no Microsoft defender para Office 365

Para configurar [links seguros](atp-safe-links.md), revise e edite suas configurações globais para links seguros e crie pelo menos uma política de links seguros.

1. No [centro de conformidade do & de segurança](https://protection.office.com), escolha links seguros de ATP da política de gerenciamento de **ameaças**  >  **Policy**  >  **ATP Safe Links** e clique em **configurações globais** e defina as seguintes configurações:

   - Verify **use Safe links in: os aplicativos do Office 365** estão ativados: ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .
   - **Não rastrear quando os usuários clicarem em links seguros**: desativar esta configuração para rastrear cliques do usuário: desativar ![ ](../../media/scc-toggle-off.png) .
   - **Não permitir que os usuários cliquem em links seguros para a URL original**: Verifique se esta configuração está ativada: ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   Quando concluir, clique em **Salvar**.

2. De volta à página principais links seguros, clique em **criar**.

3. No assistente **criar política de links seguros** que aparece, defina as seguintes configurações:

   - Na caixa **nome** , digite um nome, como `Safe Links` e clique em **Avançar**.

   - Na página **configurações** , defina as seguintes configurações:
     - **Selecione a ação para URLs possivelmente mal-intencionadas desconhecidas em mensagens**: escolha **ativado**.
     - **Selecione a ação para URLs desconhecidas ou potencialmente mal-intencionadas no Microsoft Teams**: escolha **ativada**.
     - **Aplicar links seguros a mensagens de email enviadas dentro da organização**
     - **Aguarde a conclusão da verificação de URL antes de entregar a mensagem**
     - **Aplicar links seguros a mensagens de email enviadas dentro da organização**
     - **Não permitir que os usuários cliquem através da URL original**

     Clique em **Avançar**

4. Na página **aplicado a** , clique em **Adicionar uma condição**, escolha **aplicado se: o domínio do destinatário é**, clique em **Adicionar**, selecione seu domínio ou domínios, clique em **Adicionar**, em **concluído** e em **Avançar**.

5. Revise suas configurações e clique em **concluir**.

Para saber mais, confira [Configurar políticas de Links Seguros](set-up-atp-safe-links-policies.md).

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Parte 5: verificar a ATP para SharePoint, OneDrive e Microsoft Teams está ativado

Cargas de trabalho como o SharePoint, o OneDrive e o Microsoft Teams são criadas para colaboração. O uso do defender para Office 365 ajuda no bloqueio e na detecção de arquivos identificados como mal-intencionados em sites de equipe e bibliotecas de documentos. Você pode ler mais sobre como isso funciona [aqui](atp-for-spo-odb-and-teams.md).

> [!IMPORTANT]
> **Antes de iniciar esse procedimento, certifique-se de que o log de auditoria já esteja ativado para seu ambiente do Microsoft 365**. Isso geralmente é feito por alguém que tenha a função de logs de auditoria atribuída no Exchange Online. Para obter mais informações, consulte [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md)!

1. No [centro de conformidade & segurança](https://protection.office.com), escolha a política de **Gerenciamento de ameaças**  >  **Policy**  >  e **anexos seguros de ATP** e clique em **configurações globais**.

2. Verifique se a **opção Ativar ATP para SharePoint, onedrive e Microsoft Teams** está ativada para a direita: ![ Ativar/desativar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) e clique em **salvar**.

3. Revise (e, conforme apropriado, edite) as [políticas de anexos seguros](set-up-atp-safe-attachments-policies.md) da sua organização e [as políticas de links seguros](set-up-atp-safe-links-policies.md).

4. Recomenda Como administrador global ou administrador do SharePoint Online, execute o cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** com o parâmetro _DisallowInfectedFileDownload_ definido como `$true` .

   - `$true` bloqueia todas as ações (exceto excluir) para arquivos detectados. As pessoas não podem abrir, mover, copiar ou compartilhar arquivos detectados.
   - `$false` bloqueia todas as ações, exceto excluir e baixar. As pessoas podem optar por aceitar o risco e baixar um arquivo detectado.

   > [!TIP]
   > Para saber mais sobre como usar o PowerShell com o Microsoft 365, confira [gerenciar o microsoft 365 com o PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).

5. Aguarde até 30 minutos para que as alterações se espalhem para todos os datacenters da Microsoft 365.

### <a name="now-set-up-alerts-for-detected-files"></a>Agora configure alertas para arquivos detectados

Para receber notificações quando um arquivo no SharePoint Online, no OneDrive for Business ou no Microsoft Teams foi identificado como mal-intencionado, você pode configurar um alerta.

1. No [centro de conformidade & segurança](https://protection.office.com), escolha **alertas** \> **Gerenciar alertas**.

2. Escolha **nova política de alerta**.

3. Especifique um nome para o alerta. Por exemplo, você pode digitar arquivos mal-intencionados em bibliotecas.

4. Digite uma descrição para o alerta. Por exemplo, você pode digitar notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, no OneDrive ou no Microsoft Teams.

5. Na seção **Enviar este alerta quando...** , defina:

   a. Na lista **atividades** , escolha **malware detectado em arquivo**.

   b. Deixe o campo **usuários** vazio.

6. Na seção **Enviar este alerta para...** , selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificações quando um arquivo mal-intencionado for detectado.

7. **Salvar**.

Para saber mais sobre alertas, confira [criar alertas de atividade no centro de conformidade de & de segurança](../../compliance/create-activity-alerts.md).

> [!NOTE]
> Quando terminar de configurar o, use estes links para iniciar investigações de carga de trabalho:
>
>- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
>- [Usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [O que fazer quando um arquivo mal-intencionado é encontrado no SharePoint Online, no OneDrive ou no Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Gerenciar arquivos e mensagens em quarentena como um administrador no Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6-configurações adicionais a serem definidas

Além de configurar a proteção contra malware, URLs e arquivos mal-intencionados, phishing e spam, recomendamos que você configure a limpeza automática de zero hora.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Limpeza automática de zero horas para email no EOP

[A limpeza automática de zero horas](zero-hour-auto-purge.md) (zap) está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Essa proteção é ativada por padrão; no entanto, as seguintes condições devem ser atendidas para que a proteção entre em vigor:

- As ações de spam são definidas para **mover mensagens para a pasta lixo eletrônico** em [políticas antispam](anti-spam-protection.md).

- Os usuários têm mantido suas [configurações padrão de lixo eletrônico](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)e não desativaram a proteção de lixo eletrônico.

Para saber mais, confira [exclusão automática de zero horas-proteção contra spam e malware](zero-hour-auto-purge.md).

## <a name="post-setup-tasks-and-next-steps"></a>Tarefas pós-instalação e próximas etapas

Depois de configurar os recursos de proteção contra ameaças, certifique-se de monitorar como esses recursos estão funcionando! Revise e revise suas políticas para que elas façam o que você precisa. Além disso, Assista a novos recursos e atualizações de serviço que podem agregar valor.

****

|O que fazer|Recursos para saber mais|
|---|---|
|Veja como os recursos de proteção contra ameaças estão trabalhando para sua organização exibindo relatórios|[Painel de segurança](security-dashboard.md)<br/>[Relatórios de segurança de email](view-email-security-reports.md)<br/>[Relatórios do Microsoft defender para Office 365](view-reports-for-atp.md)<br/>[Explorador de Ameaças](threat-explorer.md)|
|Revisar e revisar periodicamente suas políticas de proteção contra ameaças, conforme necessário|[Classificação de segurança](../mtp/microsoft-secure-score.md)<br/>[Relatórios inteligentes e insights](reports-and-insights-in-security-and-compliance.md)<br/>[Investigação de ameaças e recursos de resposta da Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Assista a novos recursos e atualizações de serviço|[Opções de lançamento direcionado e padrão](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Centro de Mensagens](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Descrições de serviço](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Saiba mais sobre as configurações de segurança padrão e rígidas para o EOP e o defender para Office 365|[Configurações recomendadas para a segurança do EOP e do Microsoft defender para Office 365](recommended-settings-for-eop-and-office365-atp.md)|
