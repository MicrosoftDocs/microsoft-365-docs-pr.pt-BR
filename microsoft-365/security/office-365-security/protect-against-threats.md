---
title: Proteção contra ameaças
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Os administradores podem aprender sobre a proteção contra ameaças Microsoft 365 e configurar como usá-la para sua organização.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3381ce66433f1f4e32f0251c45601e3cb84865b6
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538718"
---
# <a name="protect-against-threats"></a>Proteção contra ameaças

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Aqui está um guia de início rápido que quebra a configuração do Defender para Office 365 em partes. Se você é novo nos recursos de proteção contra ameaças no Office 365, não sabe por onde começar ou se aprendeu melhor fazendo *isso,* use essa orientação como uma lista de verificação e um ponto de partida.

> [!IMPORTANT]
> **As configurações recomendadas** iniciais são incluídas para cada tipo de política; no entanto, muitas opções estão disponíveis e você pode ajustar suas configurações para atender às necessidades de sua organização específica. Permita aproximadamente 30 minutos para que suas políticas ou alterações funcionem por meio do datacenter.

## <a name="requirements"></a>Requisitos

### <a name="subscriptions"></a>Assinaturas

Os recursos de proteção contra ameaças estão incluídos em todas *as* assinaturas Office 365 Microsoft; no entanto, algumas assinaturas têm recursos avançados. A tabela a seguir lista os recursos de proteção incluídos neste artigo juntamente com os requisitos mínimos de assinatura.

> [!TIP]
> Observe que, além das instruções para ativar a *auditoria,* as etapas iniciam anti-malware, anti-phishing e anti-spam, que são marcados como parte do Office 365 Proteção do Exchange Online (**EOP**). Isso pode parecer estranho em um artigo do Defender para Office 365, até que você se lembre (**Defender para** Office 365 ) contém e se baseia no EOP.

****

|Tipo de proteção|Requisitos de assinatura|
|---|---|
|Log de auditoria (para fins de relatório)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Proteção antimalware|[Proteção do Exchange Online](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Proteção anti-phishing|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Proteção antispam|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Limpeza automática de hora zero (para email)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Proteção contra URLs mal-intencionadas e arquivos no email e Office documentos (Cofre Links e Cofre Anexos)|[Obter o Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams cargas de trabalho|[Obter o Microsoft Defender para Office 365](turn-on-mdo-for-spo-odb-and-teams.md)|
|Proteção avançada antiphishing|[Obter o Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Funções e permissões

Para configurar o Defender Office 365 políticas de Office 365, você deve ter uma função apropriada no Centro de Conformidade & [Segurança.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) Confira a tabela abaixo para ver as funções que podem fazer essas ações.

****

|Função ou grupo de funções|Onde saber mais|
|---|---|
|administrador global|[Sobre as funções de administrador do Microsoft 365 ](../../admin/add-users/about-admin-roles.md)|
|Administrador de Segurança|[Permissões da função de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gerenciamento de Organização do Exchange Online|[Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo) <p> e <p> [PowerShell do Exchange Online](/powershell/exchange/exchange-online-powershell)|
|

Para saber mais, confira Permissões no Centro de [Conformidade & Segurança.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Antes de começar, a turn on Audit logging for reporting and investigation

Inicie o log de auditoria mais cedo. Você precisará da auditoria para estar **on** em determinadas etapas a seguir. O log de auditoria está disponível em assinaturas que incluem [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para exibir dados em relatórios de proteção contra ameaças, como o Painel de [Segurança,](security-dashboard.md)os relatórios de segurança de [email](view-email-security-reports.md)e o [Explorer,](threat-explorer.md)o log de auditoria deve *estar em*. Para saber mais, confira Ativar ou desativar a pesquisa de [log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Parte 1 - Proteção anti-malware

[A proteção anti-malware](anti-malware-protection.md) está disponível em assinaturas que incluem [eOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. No Centro [de Conformidade & segurança,](https://protection.office.com)escolha Política de **Gerenciamento de** \> **Ameaças** \> **Anti-malware**.

2. Clique duas vezes na **política Padrão** e escolha **configurações**.

3. Especifique as seguintes configurações:

    - Na seção **Resposta à Detecção de Malware,** mantenha a configuração padrão de **Não**.

    - Na seção **Filtro de Tipos de Anexo Comum,** escolha **Em**.

4. Clique em **Salvar**.

Para saber mais sobre as opções de política anti-malware, consulte [Configure anti-malware policies](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection"></a>Parte 2 - Proteção anti-phishing

[A proteção anti-phishing](anti-phishing-protection.md) está disponível em assinaturas que incluem [eOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). A proteção anti-phishing avançada está disponível no [Defender para](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365 .

O procedimento a seguir descreve como configurar uma política anti-phishing no Microsoft Defender para Office 365. As etapas são semelhantes para configurar uma política anti-phishing no EOP.

1. No Centro [de Conformidade & segurança,](https://protection.office.com)escolha **Política** de Gerenciamento de \> **Ameaças** \> **Anti-phishing**.

2. Clique **em Política padrão**.

3. Na seção **Representação,** clique em **Editar** e especifique as seguintes configurações:

   - Na guia **Adicionar usuários para proteger,** acentue *a proteção.* Em seguida, adicione usuários, como membros do conselho da sua organização, seu CEO, CFO e outros líderes sênior. (Você pode digitar um endereço de email individual ou clicar para exibir uma lista.)

   - Na guia **Adicionar domínios para proteger,** a aciona **Automaticamente incluir os domínios que eu tenho**. Se você tiver domínios personalizados, adicione-os agora.

   - Na guia **Ações,** selecione Colocar em quarentena **a mensagem** para o usuário personificado **e** as opções de **domínio personificados.** Além disso, a turn on impersonation safety tips.

   - Na guia **Inteligência de** Caixa de Correio, certifique-se de que a inteligência da caixa de correio está 100% 100% 100% 2000 e a proteção de representação baseada em inteligência de caixa de correio. Na lista Se o email for enviado por uma lista **de usuários personificados,** escolha Colocar em quarentena **a mensagem**.

   - Na guia **Adicionar senders e domínios** confiáveis, especifique qualquer senders ou domínios confiáveis que você deseja adicionar.

   - **Salve** na guia **Revisar suas configurações** depois de revisar suas configurações.

4. Na seção **Spoof,** clique em **Editar** e especifique as seguintes configurações:

   - Na guia **Configurações de filtro de spoofing,** certifique-se de que a proteção anti-spoofing está 100% 100% 2000.

   - Na guia **Ações,** escolha **Colocar em quarentena a mensagem**.

   - **Salve** na guia **Revisar suas configurações** depois de revisar suas alterações. (Se você não fez nenhuma alteração, **Cancel**.)

5. Feche a página de configurações de política padrão.

Para saber mais sobre suas opções de política anti-phishing, consulte [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection"></a>Parte 3 - Proteção anti-spam

[A proteção anti-spam](anti-spam-protection.md) está disponível em assinaturas que incluem [eOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. No Centro [de Conformidade & segurança,](https://protection.office.com)escolha Política de **Gerenciamento de** \> **Ameaças** \> **Anti-spam**.

2. Na guia **Personalizado,** a opção Configurações personalizadas.

3. Expanda **a política de filtro de spam padrão,** clique em Editar **política** e especifique as seguintes configurações:

   - Na seção **Spam e ações em massa,** de definir o limite como um valor de 5 ou 6.

   - Na seção **Permitir listas,** revise (e/ou edit) seus senders e domínios permitidos.

4. Clique em **Salvar**.

Para saber mais sobre suas opções de política anti-spam, consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4 - Proteção contra URLs e arquivos mal-intencionados (Cofre Links e Cofre anexos no Defender para Office 365)

A proteção de tempo de clique contra URLs mal-intencionadas e arquivos está disponível em assinaturas que incluem [o Microsoft Defender para](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365 . Ela é configurada por meio de Cofre [anexos](safe-attachments.md) e Cofre [links.](safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Cofre Políticas de anexos no Microsoft Defender para Office 365

Para configurar Cofre [Anexos,](safe-attachments.md)crie pelo menos uma política Cofre Links.

1. No Centro [de Conformidade & segurança,](https://protection.office.com)escolha **Política** de Gerenciamento de Ameaças \>  \> **ATP Cofre Anexos** e clique em **Criar**.

2. No assistente **nova Cofre de política de anexos** que aparece, configure as seguintes configurações:

   - Na caixa **Nome,** digite `Block malware` e clique em **Próximo**.

   - Na página **Configurações,** configure as seguintes configurações:
     - Na seção **Cofre de resposta a malware** desconhecidos, escolha **Bloquear**.
     - Na seção **Redirecionar anexo,** selecione a opção **Habilitar redirecionamento**. Especifique o endereço de email para o administrador ou operador de segurança da sua organização, que revisará os arquivos detectados.

     Clique em **Avançar**.

3. Na página **Aplicado** a, clique em Adicionar uma **condição,** escolha Aplicado **se:** O domínio do destinatário é , clique em **Adicionar,** selecione seu domínio ou domínios, clique em **Adicionar**, clique em Feito **e** clique em **Próximo**.

4. Revise suas configurações e clique em **Concluir**.

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Cofre Políticas de links no Microsoft Defender para Office 365

Para configurar Cofre [Links,](safe-links.md)revise e edite suas configurações globais para links Cofre e crie pelo menos uma política Cofre Links.

1. No Centro [de Conformidade &](https://protection.office.com)  segurança, escolha Política de Gerenciamento de Ameaças ATP Cofre Links e clique em Configurações Globais e, em \>  \> seguida, configure as seguintes configurações:

   - Verificar **Usar Cofre Links em: Office 365 aplicativos está** ligado: ![ Alternar em ](../../media/scc-toggle-on.png) .
   - **Não rastreia quando os usuários clicam Cofre Links**: desativar essa configuração para controlar cliques do usuário: ![ Desativar ](../../media/scc-toggle-off.png) .
   - **Não permitir que os usuários cliquem em links seguros** para a URL original : Verifique se essa configuração está conexões: ![ Alternar em ](../../media/scc-toggle-on.png) .

   Quando concluir, clique em **Salvar**.

2. De volta à página principal Cofre Links, clique em **Criar**.

3. No assistente **de política Criar Cofre Links** que aparece, configure as seguintes configurações:

   - Na caixa **Nome,** digite um nome, como `Safe Links` , e clique em **Próximo**.

   - Na página **Configurações,** configure as seguintes configurações:
     - **Selecione a ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens**: Escolha **Em**.
     - **Selecione a ação para URLs desconhecidas** ou potencialmente mal-intencionadas em Microsoft Teams : Choose **On**.
     - **Aplicar links seguros a mensagens de email enviadas dentro da organização**
     - **Aguarde a conclusão da verificação de URL antes de entregar a mensagem**
     - **Aplicar links seguros a mensagens de email enviadas dentro da organização**
     - **Não permitir que os usuários cliquem na URL original**

     Clique em **Avançar**

4. Na página **Aplicado** a, clique em Adicionar uma **condição,** escolha Aplicado **se:** O domínio do destinatário é , clique em **Adicionar,** selecione seu domínio ou domínios, clique em **Adicionar**, clique em Feito **e** clique em **Próximo**.

5. Revise suas configurações e clique em **Concluir**.

Para saber mais, confira [Configurar políticas de Links Seguros](set-up-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Parte 5 - Verificar Cofre anexos para SharePoint, OneDrive e Microsoft Teams está ligado

Cargas de trabalho como SharePoint, OneDrive e Teams são criadas para colaboração. Usar o Defender para Office 365 ajuda a bloquear e detectar arquivos identificados como mal-intencionados em sites de equipe e bibliotecas de documentos. Você pode ler mais sobre como isso funciona [aqui.](mdo-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> **Antes de começar este procedimento, certifique-se** de que o log de auditoria já está ligado para seu Microsoft 365 ambiente . Isso normalmente é feito por alguém que tem a função Logs de Auditoria atribuída Exchange Online. Para obter mais informações, consulte Ativar ou desativar a [pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md)!

1. No Centro [de Conformidade & segurança,](https://protection.office.com) **escolha** Política de gerenciamento de ameaças atp Cofre \>  \> **anexos** e clique em **Configurações globais**.

2. Verifique se a alternância Ativar o Defender Office 365 para **SharePoint, OneDrive** e Microsoft Teams está à direita: Alterne e clique em ![ ](../../media/scc-toggle-on.png) **Salvar**.

3. Revise (e, conforme apropriado, edite) as políticas de Cofre [anexos](set-up-safe-attachments-policies.md) e Cofre de links da [sua organização.](set-up-safe-links-policies.md)

4. (Recomendado) Como administrador global ou administrador SharePoint Online, execute o cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** com o parâmetro _DisallowInfectedFileDownload_ definido como `$true` .

   - `$true` bloqueia todas as ações (exceto Excluir) para arquivos detectados. As pessoas não podem abrir, mover, copiar ou compartilhar arquivos detectados.
   - `$false` bloqueia todas as ações, exceto Excluir e Baixar. As pessoas podem optar por aceitar o risco e baixar um arquivo detectado.

   > [!TIP]
   > Para saber mais sobre como usar o PowerShell com Microsoft 365, consulte [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).

5. Permita até 30 minutos para que suas alterações se spread para todos os Microsoft 365 datacenters.

### <a name="now-set-up-alerts-for-detected-files"></a>Agora, configurar alertas para arquivos detectados

Para receber uma notificação quando um arquivo no SharePoint Online, OneDrive for Business ou Microsoft Teams tiver sido identificado como mal-intencionado, você pode configurar um alerta.

1. No Centro [de Conformidade & segurança,](https://protection.office.com)escolha **Alertas** \> **Gerenciar alertas**.

2. Escolha **Nova política de alerta.**

3. Especifique um nome para o alerta. Por exemplo, você pode digitar Arquivos Mal-Intencionados em Bibliotecas.

4. Digite uma descrição do alerta. Por exemplo, você pode digitar Notifies admins quando arquivos mal-intencionados são detectados no SharePoint Online, OneDrive ou Microsoft Teams.

5. Na seção **Enviar esse alerta quando...**

   a. Na lista **Atividades,** escolha **Malware detectado no arquivo**.

   b. Deixe o **campo Usuários** vazio.

6. Na seção **Enviar esse alerta para...** selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificação quando um arquivo mal-intencionado for detectado.

7. **Salvar**.

Para saber mais sobre alertas, consulte [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).

> [!NOTE]
> Quando terminar de configurar, use esses links para iniciar investigações de carga de trabalho:
>
>- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
>- [Use o Centro de Conformidade & segurança para gerenciar arquivos em quarentena](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [O que fazer quando um arquivo mal-intencionado é encontrado no SharePoint Online, OneDrive ou Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Gerenciar mensagens e arquivos em quarentena como administrador em Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6 - Configurações adicionais a ser configuradas

Junto com a configuração de proteção contra malware, URLs mal-intencionadas e arquivos, phishing e spam, recomendamos configurar a limpeza automática de zero hora.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Limpeza automática de hora zero para email no EOP

[A limpeza automática](zero-hour-auto-purge.md) zero hora (ZAP) está disponível em assinaturas que incluem [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Essa proteção está 100% 100%. no entanto, as seguintes condições devem ser atendidas para que a proteção entre em vigor:

- As ações de spam são definidas como **Mover mensagem para a** pasta Lixo Eletrônico em políticas [anti-spam.](anti-spam-protection.md)

- Os usuários mantiveram suas configurações padrão [de lixo eletrônico](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)e não desligaram a proteção contra lixo eletrônico.

Para saber mais, confira [Limpeza automática zero hora - proteção contra spam e malware](zero-hour-auto-purge.md).

## <a name="post-setup-tasks-and-next-steps"></a>Tarefas pós-instalação e próximas etapas

Depois de configurar os recursos de proteção contra ameaças, certifique-se de monitorar como esses recursos estão funcionando! Revise e revise suas políticas para que elas faça o que você precisa. Além disso, observe novos recursos e atualizações de serviço que podem adicionar valor.

****

|O que fazer|Recursos para saber mais|
|---|---|
|Veja como os recursos de proteção contra ameaças estão funcionando para sua organização exibindo relatórios|[Painel de segurança](security-dashboard.md) <p> [Relatórios de segurança de email](view-email-security-reports.md) <p> [Relatórios do Microsoft Defender para Office 365](view-reports-for-mdo.md) <p> [Explorador de Ameaças](threat-explorer.md)|
|Revise e revise periodicamente suas políticas de proteção contra ameaças conforme necessário|[Classificação de segurança](../defender/microsoft-secure-score.md) <p> [Relatórios inteligentes e insights](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 de investigação e resposta contra ameaças](./office-365-ti.md)|
|Assista a novos recursos e atualizações de serviço|[Opções de versão padrão e direcionada](../../admin/manage/release-options-in-office-365.md) <p> [Centro de Mensagens](../../admin/manage/message-center.md) <p> [Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descrições do serviço](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Saiba os detalhes sobre as configurações de segurança padrão e estrita recomendadas para EOP e Defender para Office 365|[Configurações recomendadas para o EOP e o Microsoft Defender para Office 365 segurança](recommended-settings-for-eop-and-office365.md)|
