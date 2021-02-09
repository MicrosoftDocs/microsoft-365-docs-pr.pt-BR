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
description: Os administradores podem aprender sobre a proteção contra ameaças no Microsoft 365 e configurar como usá-la para sua organização.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb2866fd3e60c021ae89ffabe7149f4b415d63bc
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150707"
---
# <a name="protect-against-threats"></a>Proteção contra ameaças

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Aqui está um guia de início rápido que divide a configuração do Defender para Office 365 em partes. Se você é novo nos recursos de proteção contra ameaças no Office 365, não sabe por onde começar ou se aprende melhor fazendo *isso,* use essas diretrizes como uma lista de verificação e um ponto de partida.

> [!IMPORTANT]
> **As configurações** iniciais recomendadas são incluídas para cada tipo de política; no entanto, muitas opções estão disponíveis e você pode ajustar suas configurações para atender às necessidades específicas da sua organização. Permita aproximadamente 30 minutos para que suas políticas ou alterações funcionem no seu datacenter.

## <a name="requirements"></a>Requisitos

### <a name="subscriptions"></a>Assinaturas

Os recursos de proteção contra ameaças estão incluídos *em todas as* assinaturas da Microsoft ou do Office 365; No entanto, algumas assinaturas têm recursos avançados. A tabela a seguir lista os recursos de proteção incluídos neste artigo juntamente com os requisitos mínimos de assinatura.

> [!TIP]
> Observe que, além das instruções para ativar a *auditoria,* as etapas iniciam anti-malware, anti-phishing e anti-spam, que são marcadas como parte do Office 365 Exchange Online Protection **(EOP).** Isso pode parecer estranho em um artigo do Defender para Office 365, até que você se lembre de que o Defender para **Office 365** contém e se baseia no EOP.

****

|Tipo de proteção|Requisito de assinatura|
|---|---|
|Log de auditoria (para fins de relatório)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Proteção antimalware|[Proteção do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Proteção anti-phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Proteção antispam|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Limpeza automática zero hora (para email)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Proteção contra URLs e arquivos mal-intencionados em emails e documentos do Office (links seguros e anexos seguros)|[Microsoft Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Ativar anexos seguros para cargas de trabalho do SharePoint, OneDrive e Microsoft Teams|[Defender para Office 365 ](atp-for-spo-odb-and-teams.md)|
|Proteção anti-phishing avançada|[Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Funções e permissões

Para configurar as políticas do Defender para Office 365, você deve ter uma função apropriada no Centro de [& Conformidade](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)e Segurança. Dê uma olhada na tabela abaixo para ver as funções que podem fazer essas ações.

****

|Função ou grupo de funções|Onde saber mais|
|---|---|
|administrador global|[Sobre as funções de administrador do Microsoft 365 ](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Administrador de Segurança|[Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gerenciamento de Organização do Exchange Online|[Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> e <p> [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Para saber mais, consulte Permissões no Centro de Conformidade [e & Segurança.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Antes de começar, a adoção do log de auditoria para relatórios e investigação

Inicie o log de auditoria mais cedo. Você precisará da auditoria para estar **ON** em determinadas etapas a seguir. O log de auditoria está disponível em assinaturas que incluem [o Exchange Online.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Para exibir dados em relatórios de proteção contra ameaças, como o Painel de [Segurança,](security-dashboard.md)relatórios de segurança de [email](view-email-security-reports.md)e o [Explorer,](threat-explorer.md)o log de auditoria deve estar *em .* Para saber mais, confira Ativar ou desativar [a pesquisa de log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Parte 1 - Proteção anti-malware

[A proteção anti-malware](anti-malware-protection.md) está disponível em assinaturas que incluem [o EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. In the [Security & Compliance Center](https://protection.office.com), choose Threat **management** \> **Policy** \> **Anti-malware**.

2. Clique duas vezes na **política** Padrão e escolha **as configurações.**

3. Especifique as seguintes configurações:

    - Na seção **Resposta à Detecção de Malware,** mantenha a configuração padrão **Não**.

    - Na seção **Filtro de Tipos de Anexos Comuns,** escolha **Em**.

4. Clique em **Salvar**.

Para saber mais sobre as opções de política anti-malware, consulte [Configurar políticas anti-malware.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection"></a>Parte 2 - Proteção anti-phishing

[A proteção anti-phishing](anti-phishing-protection.md) está disponível em assinaturas que incluem [o EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) A proteção anti-phishing avançada está disponível no [Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

O procedimento a seguir descreve como configurar uma política anti-phishing no Microsoft Defender para Office 365. As etapas são semelhantes para configurar uma política anti-phishing no EOP.

1. In the [Security & Compliance Center](https://protection.office.com), choose Threat **management** \> **Policy** \> **ATP anti-phishing**.

2. Clique **em Política padrão.**

3. Na seção **Representação,** clique em **Editar** e especifique as seguintes configurações:

   - Na guia **Adicionar usuários para proteger,** a ligue *a* proteção. Em seguida, adicione usuários, como membros do conselho da sua organização, seu CEO, CFO e outros líderes sênior. (Você pode digitar um endereço de email individual ou clicar para exibir uma lista.)

   - On the **Add domains to protect** tab, turn on Automatically include the **domains I own**. Se você tiver domínios personalizados, adicione-os agora.

   - Na guia **Ações,** selecione **Colocar em quarentena a mensagem** para as opções de usuário personificado **e** de **domínio personificado.** Além disso, a adição de dicas de segurança de representação.

   - Na guia Inteligência **de Caixa de** Correio, certifique-se de que a inteligência de caixa de correio está turn on e a proteção contra representação baseada em inteligência de caixa de correio. In the **If email is sent by an impersonated user** list, choose Quarantine the **message**.

   - Na guia **Adicionar domínios** e senders confiáveis, especifique quaisquer domínios ou rementes confiáveis que você deseja adicionar.

   - **Salve** na **guia Revisar suas configurações** depois de revisar suas configurações.

4. Na seção **Spoof,** clique em **Editar** e especifique as seguintes configurações:

   - Na guia **Configurações do filtro de Spoofing,** certifique-se de que a proteção anti-spoofing está turned on.

   - Na guia **Ações,** escolha **Colocar em Quarentena a mensagem.**

   - **Salve** na **guia Revisar suas configurações** depois de analisar suas alterações. (Se você não fez nenhuma alteração, **cancele.)**

5. Feche a página de configurações de política padrão.

Para saber mais sobre suas opções de política anti-phishing, consulte Configurar políticas [anti-phishing no Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection"></a>Parte 3 - Proteção anti-spam

[A proteção anti-spam](anti-spam-protection.md) está disponível em assinaturas que incluem [o EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. In the [Security & Compliance Center](https://protection.office.com), choose Threat **management** \> **Policy** \> **Anti-spam**.

2. On the **Custom** tab, turn on Custom settings.

3. Expanda **a política de filtro de spam** padrão, clique em **Editar** política e especifique as seguintes configurações:

   - Na seção **Spam e ações em massa,** de definida o limite para um valor de 5 ou 6.

   - Na seção **Listas de Permissão,** revise (e/ou edite) seus senders e domínios permitidos.

4. Clique em **Salvar**.

Para saber mais sobre suas opções de política anti-spam, consulte [Configurar políticas anti-spam no EOP.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4 - Proteção contra URLs e arquivos mal-intencionados (Links seguros e anexos seguros no Defender para Office 365)

A proteção de hora de clique contra URLs e arquivos mal-intencionados está disponível em assinaturas que incluem o [Microsoft Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Ele é definido por meio das políticas [de Anexos Seguros](atp-safe-attachments.md) [e Links Seguros.](atp-safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Políticas de Anexos Seguros no Microsoft Defender para Office 365

Para configurar [anexos seguros,](atp-safe-attachments.md)crie pelo menos uma política de Links seguros.

1. In the [Security & Compliance Center,](https://protection.office.com)choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Create**.

2. No assistente **de política Novos Anexos Seguros** exibido, de configure as seguintes configurações:

   - Na caixa **Nome,** digite `Block malware` e clique em **Próximo.**

   - Na página **Configurações,** de configure as seguintes configurações:
     - In the **Safe attachments unknown malware response** section, choose **Block**.
     - Na seção **Redirecionar anexo,** selecione a opção Habilitar **redirecionamento.** Especifique o endereço de email do administrador ou operador de segurança da sua organização, que analisará os arquivos detectados.

     Clique em **Avançar**.

3. On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.

4. Revise suas configurações e clique em **Concluir.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Políticas de Links Seguros no Microsoft Defender para Office 365

Para configurar [links](atp-safe-links.md)seguros, revise e edite suas configurações globais para Links seguros e crie pelo menos uma política de Links seguros.

1. No Centro [de Conformidade &](https://protection.office.com)  Segurança, escolha Links Seguros atp da Política de Gerenciamento de Ameaças e clique em \>  \>  **Configurações** Globais e de definir as seguintes configurações:

   - Verifique **se o uso de Links seguros em: aplicativos do Office 365** está ligado: ![ ](../../media/scc-toggle-on.png) Alternar.
   - **Não rastreia quando os usuários clicam em Links Seguros:** desativar essa configuração para controlar os cliques do usuário: ![ ](../../media/scc-toggle-off.png) Desativar.
   - **Não permitir que os usuários cliquem em links seguros para** a URL original: Verifique se essa configuração está conexões: ![ ](../../media/scc-toggle-on.png) Alternar.

   Quando concluir, clique em **Salvar**.

2. De volta à página principal links seguros, clique em **Criar**.

3. No assistente **de política Criar Links Seguros** exibido, de configure as seguintes configurações:

   - In the **Name** box, type a name, such as `Safe Links` , and then click **Next**.

   - Na página **Configurações,** de configure as seguintes configurações:
     - **Selecione a ação para URLs potencialmente mal-intencionadas desconhecidas em mensagens:** Escolher **Em**.
     - **Selecione a ação para URLs desconhecidas** ou potencialmente mal-intencionadas no Microsoft Teams: **Choose On**.
     - **Aplicar links seguros a mensagens de email enviadas dentro da organização**
     - **Aguarde a conclusão da verificação de URL antes de entregar a mensagem**
     - **Aplicar links seguros a mensagens de email enviadas dentro da organização**
     - **Não permitir que os usuários cliquem na URL original**

     Clique em **Avançar**

4. On the **Applied to** page, click **Add a condition**, choose **Applied if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.

5. Revise suas configurações e clique em **Concluir.**

Para saber mais, confira [Configurar políticas de Links Seguros](set-up-atp-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Parte 5 - Verificar se anexos seguros para o SharePoint, OneDrive e Microsoft Teams estão ligado

Cargas de trabalho como o SharePoint, o OneDrive e o Teams são criadas para colaboração. Usar o Defender para Office 365 ajuda a bloquear e detectar arquivos identificados como mal-intencionados em sites de equipe e bibliotecas de documentos. Você pode ler mais sobre como isso funciona [aqui.](atp-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> Antes de começar este procedimento, certifique-se de que o log de auditoria já está **ligado para seu ambiente do Microsoft 365.** Isso geralmente é feito por alguém que tem a função Logs de Auditoria atribuída no Exchange Online. Para obter mais informações, consulte Ativar ou desativar a pesquisa [de log de auditoria!](../../compliance/turn-audit-log-search-on-or-off.md)

1. In the [Security & Compliance Center,](https://protection.office.com)choose **Threat management** \> **Policy** \> **ATP Safe Attachments**, and then click **Global settings**.

2. Verifique se a alternância Ativar o Defender para **Office 365 para SharePoint, OneDrive** e Microsoft Teams está à direita: ativar e clicar em ![ ](../../media/scc-toggle-on.png) **Salvar.**

3. Revise (e, conforme apropriado, edite) as políticas de [Anexos](set-up-atp-safe-attachments-policies.md) seguros e as políticas [de Links seguros da sua organização.](set-up-atp-safe-links-policies.md)

4. (Recomendado) Como administrador global ou administrador do SharePoint Online, execute o cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** com o parâmetro _DisallowInfectedFileDownload_ definido como `$true` .

   - `$true` bloqueia todas as ações (exceto Excluir) para arquivos detectados. As pessoas não podem abrir, mover, copiar ou compartilhar arquivos detectados.
   - `$false` bloqueia todas as ações, exceto Excluir e Baixar. As pessoas podem optar por aceitar o risco e baixar um arquivo detectado.

   > [!TIP]
   > Para saber mais sobre como usar o PowerShell com o Microsoft 365, confira [Gerenciar o Microsoft 365 com o PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)

5. Permita até 30 minutos para que suas alterações se estendem em todos os datacenters do Microsoft 365.

### <a name="now-set-up-alerts-for-detected-files"></a>Agora, configurar alertas para arquivos detectados

Para receber notificações quando um arquivo no SharePoint Online, OneDrive for Business ou Microsoft Teams foi identificado como mal-intencionado, você pode configurar um alerta.

1. No Centro [de Conformidade & segurança,](https://protection.office.com)escolha **Alertas Gerenciar** \> **alertas.**

2. Escolha **Nova política de alerta.**

3. Especifique um nome para o alerta. Por exemplo, você pode digitar Arquivos Mal-intencionados em Bibliotecas.

4. Digite uma descrição para o alerta. Por exemplo, você pode digitar Notifica os administradores quando arquivos mal-intencionados são detectados no SharePoint Online, no OneDrive ou no Microsoft Teams.

5. Na seção **Enviar este alerta quando...** definir:

   a. Na lista **Atividades,** escolha **Malware detectado no arquivo.**

   b. Deixe o **campo Usuários** vazio.

6. Na seção **Enviar esse alerta para...** selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificação quando um arquivo mal-intencionado for detectado.

7. **Salvar**.

Para saber mais sobre alertas, consulte [Criar alertas de atividade no Centro de conformidade & segurança.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> Quando terminar de configurar, use estes links para iniciar investigações de carga de trabalho:
>
>- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
>- [Usar o Centro de Conformidade & segurança para gerenciar arquivos em quarentena](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [O que fazer quando um arquivo mal-intencionado é encontrado no SharePoint Online, OneDrive ou Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Gerenciar mensagens e arquivos em quarentena como administrador no Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6 - Configurações adicionais a definir

Além de configurar a proteção contra malware, URLs e arquivos mal-intencionados, phishing e spam, recomendamos configurar a limpeza automática zero hora.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Limpeza automática zero hora para email no EOP

A ZAP [(limpeza automática](zero-hour-auto-purge.md) zero hora) está disponível em assinaturas que incluem [o EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Por padrão, essa proteção é 1. No entanto, as seguintes condições devem ser atendidas para que a proteção entre em vigor:

- As ações de spam são definidas **para Mover mensagem para a pasta Lixo Eletrônico** em políticas [anti-spam.](anti-spam-protection.md)

- Os usuários manteram suas [configurações padrão de lixo eletrônico](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)e não desligaram a proteção contra lixo eletrônico.

Para saber mais, consulte [Limpeza automática zero hora - proteção contra spam e malware](zero-hour-auto-purge.md).

## <a name="post-setup-tasks-and-next-steps"></a>Tarefas pós-instalação e próximas etapas

Depois de configurar os recursos de proteção contra ameaças, certifique-se de monitorar como esses recursos estão funcionando! Revise e revise suas políticas para que elas fazem o que você precisa. Além disso, observe novos recursos e atualizações de serviço que podem agregar valor.

****

|O que fazer|Recursos para saber mais|
|---|---|
|Veja como os recursos de proteção contra ameaças estão funcionando para sua organização exibindo relatórios|[Painel de segurança](security-dashboard.md) <p> [Relatórios de segurança de email](view-email-security-reports.md) <p> [Relatórios do Microsoft Defender para Office 365](view-reports-for-atp.md) <p> [Explorador de Ameaças](threat-explorer.md)|
|Revise e revise periodicamente suas políticas de proteção contra ameaças conforme necessário|[Classificação de segurança](../mtp/microsoft-secure-score.md) <p> [Relatórios inteligentes e insights](reports-and-insights-in-security-and-compliance.md) <p> [Recursos de investigação e resposta a ameaças do Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Assista a novos recursos e atualizações de serviço|[Opções de lançamento padrão e direcionado](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365) <p> [Centro de Mensagens](https://docs.microsoft.com/microsoft-365/admin/manage/message-center) <p> [Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descrições do serviço](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Saiba os detalhes sobre as configurações de segurança Padrão e Estrito recomendadas para o EOP e o Defender para Office 365|[Configurações recomendadas para o EOP e o Microsoft Defender para segurança do Office 365](recommended-settings-for-eop-and-office365-atp.md)|
