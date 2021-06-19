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
ms.openlocfilehash: 407838c815a85ce7c73322a0de176970ee93e537
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029604"
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

## <a name="requirements"></a>Requirements

### <a name="subscriptions"></a>Assinaturas

Os recursos de proteção contra ameaças estão incluídos em todas *as* assinaturas Office 365 Microsoft; no entanto, algumas assinaturas têm recursos avançados. A tabela a seguir lista os recursos de proteção incluídos neste artigo juntamente com os requisitos mínimos de assinatura.

> [!TIP]
> Observe que, além das instruções para ativar a *auditoria,* as etapas iniciam anti-malware, anti-phishing e anti-spam, que são marcados como parte do Office 365 Proteção do Exchange Online (**EOP**). Isso pode parecer estranho em um artigo do Defender para Office 365, até que você se lembre (**Defender para** Office 365 ) contém e se baseia no EOP.

<br>

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

<br>

****

|Função ou grupo de funções|Onde saber mais|
|---|---|
|administrador global|[Sobre as funções de administrador do Microsoft 365 ](../../admin/add-users/about-admin-roles.md)|
|Administrador de Segurança|[Permissões da função de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gerenciamento de Organização do Exchange Online|[Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo) <p> e <p> [PowerShell do Exchange Online](/powershell/exchange/exchange-online-powershell)|
|

Para saber mais, confira Permissões no Centro de [Conformidade & Segurança.](permissions-in-the-security-and-compliance-center.md)

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Ativar o log de auditoria para relatórios e investigação

- Inicie o log de auditoria mais cedo. Você precisará que a auditoria seja **on** para algumas das etapas a seguir. O log de auditoria está disponível em assinaturas que incluem [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para exibir dados em relatórios de proteção contra ameaças, como o Painel de [Segurança,](security-dashboard.md)os relatórios de segurança de [email](view-email-security-reports.md)e o [Explorer,](threat-explorer.md)o log de auditoria deve *estar em*. Para saber mais, confira Ativar ou desativar a pesquisa de [log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Parte 1 - Proteção anti-malware no EOP

Para obter mais informações sobre as configurações recomendadas para anti-malware, consulte [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).

1. Abra <https://security.microsoft.com/antimalwarev2> .

2. Na página **Anti-malware,** selecione a política chamada **Política** padrão clicando no nome.

3. No sobremenu de detalhes da política que é aberto, clique em Editar configurações **de proteção** e, em seguida, configure as seguintes configurações:
   - Selecione **Habilitar o filtro de anexos comuns** para ativar o filtro de anexos comuns. Clique **em Personalizar tipos de** arquivo para adicionar mais tipos de arquivo.
   - Verifique se **Enable zero-hour auto purge for malware** is selected.
   - Verifique se nenhuma das configurações na seção **Notificação** está selecionada.

   Quando concluir, clique em **Salvar**.

4. De volta ao submenu de detalhes da política, clique em **Fechar**.

Para obter instruções detalhadas sobre como configurar políticas anti-malware, consulte [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Parte 2 - Proteção anti-phishing no EOP e no Defender para Office 365

[A proteção anti-phishing](anti-phishing-protection.md) está disponível em assinaturas que incluem [eOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). A proteção anti-phishing avançada está disponível no [Defender para](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365 .

Para obter mais informações sobre as configurações recomendadas para políticas [anti-phishing, consulte EOP anti-phishing](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) policy settings and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

O procedimento a seguir descreve como configurar a política anti-phishing padrão. Configurações que estão disponíveis apenas no Defender para Office 365 estão claramente marcados.

1. Abra <https://security.microsoft.com/antiphishing> .

2. Na página **Anti-phishing,** selecione a política chamada **Office365 AntiPhish Default (Default)** clicando no nome.

3. No sobremenu de detalhes da política exibido, configure as seguintes configurações:

   - **Seção Limite de phishing &** proteção: clique em **Editar** configurações de proteção e configure as seguintes configurações no flyout **Editar** configurações de proteção que é aberto:
     - **Limite de email de phishing** <sup>\*</sup> : Selecione **2 - Agressivo** (Padrão) ou **3 - Mais Agressivo** (Estrito).
     - **Seção Representação** <sup>\*</sup> : Configurar os seguintes valores:
       - Selecione **Permitir** que os usuários protejam , clique no link Gerenciar **remetentes (nn)** exibido e adicione remetentes internos e externos para proteger contra representação, como membros do conselho da sua organização, seu CEO, CFO e outros líderes sêniores.
       - Selecione **Habilitar domínios para proteger** e, em seguida, configure as seguintes configurações que aparecem:
         - Selecione **Incluir domínios que eu tenho** para proteger os envios internos em seus domínios aceitos (visível clicando em Exibir meus **domínios**) de representação.
         - Para proteger os senders em outros domínios, selecione Incluir **domínios personalizados**, clique no link Gerenciar **(nn) domínios** personalizados exibidos e adicione outros domínios para proteger contra representação.
     - **Adicionar remetentes** e domínios confiáveis seção : Clique em Gerenciar (nn) remetentes confiáveis e <sup>\*</sup> **domínios(s)** para configurar exceções de domínio de remetente e remetente para proteção de representação, se necessário.
     - Configurações de inteligência de caixa de correio : Verifique se Habilitar inteligência de caixa de correio e <sup>\*</sup> **Habilitar inteligência para proteção de representação** estão selecionados. 
     - **Seção Spoof:** Verifique **se Habilitar a inteligência de spoof** está selecionada.

     Quando concluir, clique em **Salvar**.

   - **Seção Ações:** clique **em Editar ações** e configure as seguintes configurações no flyout Editar **ações** que é aberto:
     - **Seção Ações de** mensagem: Configure as seguintes configurações:
       - **Se a mensagem for detectada como um usuário personificado** <sup>\*</sup> : Selecione Colocar em quarentena a **mensagem**.
       - **Se a mensagem for detectada como um domínio personificado** <sup>\*</sup> : Selecione Colocar em quarentena a **mensagem**.
       - **Se a inteligência da caixa de** correio detectar um usuário personificado : Selecione Mover mensagem para as pastas de Lixo Eletrônico (Padrão) dos destinatários ou Coloque em quarentena a <sup>\*</sup> **mensagem** (Estrita). 
       - Se a mensagem for detectada como **spoof**: Selecione Mover mensagem para as pastas lixo eletrônico dos **destinatários** (Standard) ou Coloque em quarentena a **mensagem** (Estrita).
     - **Dicas de segurança & seção indicadores:** Configure as seguintes configurações:
       - **Mostrar o primeiro contato dica de segurança**: Selecione (ativar).
       - **Mostrar a identidade do usuário dica de segurança**: Selecione <sup>\*</sup> (ativar).
       - **Mostrar a representação de domínio dica de segurança**: Selecione <sup>\*</sup> (ativar).
       - **Mostrar caracteres incomuns de** representação do usuário dica de segurança <sup>\*</sup> : Selecione (ativar).
       - **Mostrar (?) para** envios não autenticados para spoof : Selecione (ativar).
       - **Mostrar a marca "via":** Selecione (ativar).

     Quando concluir, clique em **Salvar**.

   <sup>\*</sup>Essa configuração está disponível somente no Defender para Office 365.

4. Clique **em Salvar** e clique em **Fechar**

Para obter instruções detalhadas sobre como configurar políticas anti-phishing, consulte [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) and [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection-in-eop"></a>Parte 3 - Proteção anti-spam no EOP

Para obter mais informações sobre as configurações recomendadas para anti-spam, consulte [EOP anti-spam policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

1. Abra <https://security.microsoft.com/antispam> .

2. Na página **Políticas anti-spam,** selecione a política chamada Política de entrada **anti-spam (Padrão)** na lista clicando no nome.

3. No sobremenu de detalhes da política exibido, faça as seguintes etapas:
   - **Limite de email em massa & seção propriedades de spam:** Clique em **Editar limite de spam e propriedades**. No limite **de spam e** no sobrevoo de propriedades que aparece, de definir o valor limite de **email** em massa como 5 (Estrito) ou 6 (Standard). Quando concluir, clique em **Salvar**.
   - **Seção Senders e domínios permitidos e bloqueados:** Revise ou edite seus senders permitidos e domínios permitidos.

4. Quando terminar, clique em **Fechar**.

Para obter instruções detalhadas sobre como configurar políticas anti-spam, consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

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
>- [Use o portal Microsoft 365 Defender para gerenciar arquivos em quarentena no Defender para Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [O que fazer quando um arquivo mal-intencionado é encontrado no SharePoint Online, OneDrive ou Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Gerenciar mensagens e arquivos em quarentena como administrador em Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6 - Configurações adicionais a ser configuradas

Junto com a configuração de proteção contra malware, URLs mal-intencionadas e arquivos, phishing e spam, recomendamos configurar a limpeza automática de zero hora.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Limpeza automática de hora zero para email no EOP

[A limpeza automática](zero-hour-auto-purge.md) zero hora (ZAP) está disponível em assinaturas que incluem [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Essa proteção está 100% 100%. no entanto, as seguintes condições devem ser atendidas para que a proteção entre em vigor:

- As ações de spam são definidas como **Mover mensagem para a** pasta Lixo Eletrônico em políticas [anti-spam.](anti-spam-protection.md)

- Os usuários mantiveram suas configurações padrão [de lixo eletrônico](configure-junk-email-settings-on-exo-mailboxes.md)e não desligaram a proteção contra lixo eletrônico.

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
