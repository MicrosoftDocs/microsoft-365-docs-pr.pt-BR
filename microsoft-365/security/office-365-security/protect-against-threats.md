---
title: Proteção contra ameaças
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Os administradores podem saber mais sobre a proteção contra ameaças no Microsoft 365 e configurar como usá-la para sua organização.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4176aabb88d177c7cff0f32f32543a251b558170
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587987"
---
# <a name="protect-against-threats"></a>Proteção contra ameaças

O Microsoft 365 inclui vários recursos de proteção contra ameaças. Este é um guia de início rápido que você pode usar como uma lista de verificação para garantir que seus recursos de proteção contra ameaças estejam configurados para sua organização. Se você é novo em recursos de proteção contra ameaças no Office 365, ou se não tem certeza de onde começar, use a seguinte orientação como ponto de partida.

> [!IMPORTANT]
> **As configurações iniciais recomendadas são incluídas para cada tipo de política; no entanto, muitas opções estão disponíveis e você pode ajustar suas configurações para atender às necessidades específicas da sua organização**. Aguarde aproximadamente 30 minutos para que as políticas ou as alterações funcionem da mesma forma por meio do datacenter.

## <a name="requirements"></a>Requirements

### <a name="subscriptions"></a>Assinaturas

Os recursos de proteção contra ameaças estão incluídos em todas as assinaturas do Microsoft 365; no entanto, algumas assinaturas incluem recursos mais avançados. A tabela a seguir lista os recursos de proteção incluídos neste artigo junto com os requisitos mínimos de assinatura.<br/>

|||
|---|---|
|**Tipo de proteção**|**Requisito de assinatura**|
|Proteção antimalware|[Proteção do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)|
|Proteção contra URLs e arquivos mal-intencionados em emails e documentos do Office|[Proteção avançada contra ameaças do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)|
|Proteção anti-phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Proteção anti-phishing avançada|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Proteção antispam|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Limpeza automática de zero horas (para email)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Log de auditoria (usado para fins de relatório)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>Funções e permissões

Você deve receber uma função apropriada para configurar as políticas no [centro de conformidade & segurança](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). A tabela abaixo fornece alguns exemplos:

|Função ou grupo de funções|Onde saber mais|
|---------|---------|
|administrador global|[Sobre as funções de administrador do Microsoft 365 ](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Administrador de Segurança|[Permissões da função de administrador no Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gerenciamento de Organização do Exchange Online|[Permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>e<br> [PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)|
|

Para saber mais, confira [permissões no &amp; centro de conformidade de segurança](permissions-in-the-security-and-compliance-center.md).

## <a name="part-1---anti-malware-protection"></a>Parte 1-proteção Antimalware

A [proteção Antimalware](anti-malware-protection.md) está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. No [centro de conformidade & segurança](https://protection.office.com), escolha **Threat management**  >  **Policy**  >  **anti-malware**de política de gerenciamento de ameaças.

2. Clique duas vezes na política **padrão** e, em seguida, escolha **configurações**.

3. Especifique as seguintes configurações:

    - Na seção **resposta de detecção de malware** , mantenha a configuração padrão **no**.

    - Na seção **filtro de tipos de anexo comuns** , escolha **ativado**.

4. Clique em **Salvar**.

Para saber mais sobre opções de política Antimalware, consulte [Configure anti-malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Parte 2: proteção contra arquivos e URLs maliciosos

A proteção de horário de clique de URLs e arquivos mal-intencionados está disponível em assinaturas que incluem o [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) e é configurada por meio de [anexos seguros de ATP](atp-safe-attachments.md) e políticas de [links seguros de ATP](atp-safe-links.md) .

### <a name="atp-safe-attachments-policies"></a>Políticas de anexos seguros de ATP

Para configurar [anexos de segurança ATP](atp-safe-attachments.md), você deve definir pelo menos uma política de anexos seguros de ATP.

1. No [centro de conformidade & segurança](https://protection.office.com), escolha a política de **Gerenciamento de ameaça**  >  **Policy**  >  **anexos seguros de ATP**.

2. Selecione a opção **ativar a ATP para SharePoint, onedrive e Microsoft Teams**.

3. Na seção **proteger anexos de email** , clique no sinal de mais ( **+** ).

4. Especifique as seguintes configurações:

   - Na caixa **nome** , digite `Block malware` .

   - Na seção resposta, escolha **Bloquear**.

   - Na seção **redirecionar anexo** , selecione a opção **habilitar redirecionamento**e, em seguida, especifique o endereço de email para o administrador ou operador de segurança da sua organização que examinará os arquivos detectados.

   - Na seção **aplica-se** a, escolha **o domínio do destinatário**. Em seguida, selecione o seu domínio, escolha **Adicionar**e clique em **OK**.

5. Clique em **Salvar**.

6. (**Etapa adicional recomendada**) Como um administrador global ou um administrador do SharePoint Online, execute o cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** com o parâmetro **DisallowInfectedFileDownload** definido como *true* para seu ambiente do Microsoft 365. (Isso impede que as pessoas abram, movam, copiem ou compartilhem arquivos detectados como mal-intencionados.)

Para saber mais, confira [configurar as políticas de anexos seguros do Microsoft office 365 ATP](set-up-atp-safe-attachments-policies.md) e [ativar o Office 365 ATP para SharePoint, onedrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Políticas de links seguros de ATP

Para configurar [links de ATP seguros](atp-safe-links.md), revise e edite sua política padrão e adicione uma política para usuários específicos.

1. No [centro de conformidade & segurança](https://protection.office.com), escolha política de **Gerenciamento de ameaça**  >  **Policy**  >  **links seguros de ATP**.

2. Clique duas vezes na política **padrão** .

3. Na seção **usar links seguros em** , selecione a opção **Microsoft 365 aplicativos para empresas, Office para IOS e Android**e clique em **salvar**.

4. Na seção **políticas que se aplicam a destinatários específicos** , clique no sinal de mais ( **+** ).

5. Especifique as seguintes configurações:

   - Na caixa **nome** , digite um nome, como `Safe Links` .

   - Na seção **Selecionar ação** , escolha **ativado**.

   - Selecione estas opções:

     - **Usar anexos seguros para examinar Conteúdo baixável**

     - **Aplicar links seguros a mensagens de email enviadas dentro da organização**

     - **Não permitir que os usuários cliquem por meio de links seguros para a URL original**

   - Na seção **aplica-se** a, escolha **o domínio do destinatário**. Em seguida, selecione o seu domínio, escolha **Adicionar**e clique em **OK**.

6. Clique em **Salvar**.

Para saber mais, confira [Configurar políticas de Links Seguros ATP do Office 365](set-up-atp-safe-links-policies.md).

## <a name="part-3---anti-phishing-protection"></a>Parte 3-proteção contra phishing

[Anti-phishing]

A [proteção contra phishing](anti-phishing-protection.md) está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). A proteção contra phishing avançada está disponível na [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

O procedimento a seguir descreve como configurar uma política anti-phishing do ATP. As etapas são semelhantes à configuração de uma política anti-phishing (sem ATP).

1. No [centro de conformidade & segurança](https://protection.office.com), escolha política de **Gerenciamento de ameaças**  >  **Policy**  >  **ATP anti-phishing**.

2. Clique em **política padrão**.

3. Na seção **representação** , clique em **Editar**e especifique as seguintes configurações:

   - Na guia **Adicionar usuários para proteger** , ative a proteção. Em seguida, adicione usuários, como os membros da diretoria da sua organização, seu CEO, CFO e outros líderes seniores. (Você pode digitar um endereço de email individual ou clicar para exibir uma lista.)

   - Na guia **adicionar domínios para proteger** , ative **automaticamente os domínios que eu sou proprietário**. Se você tiver domínios personalizados, adicione-os também.

   - Na guia **ações** , selecione **colocar a mensagem em quarentena** para as opções **usuário representado** e **domínio representado** . Além disso, ative as dicas de segurança de representação.

   - Na guia **inteligência de caixa de correio** , verifique se a inteligência de caixa de correio está ativada. Além disso, ative a proteção de representação baseada em inteligência de caixa de correio. Na lista **se o email é enviado por um usuário representado** , escolha **colocar a mensagem em quarentena**.

   - Na guia **Adicionar remetentes confiáveis e domínios** , especifique os remetentes ou domínios confiáveis que você deseja adicionar.

   - Na guia **revise Your Settings** , depois de revisar as configurações, clique em **salvar**.

4. Na seção **spoof** , clique em **Editar**e especifique as seguintes configurações:

   - Na guia **configurações de filtro de falsificação** , verifique se a proteção contra falsificação está ativada.

   - Na guia **ações** , escolha **colocar a mensagem em quarentena**.

   - Na guia **revise Your Settings** , depois de revisar as configurações, clique em **salvar**. Se não fizer alterações, clique em **Cancelar**.

5. Feche a página de configurações de política padrão.

Para saber mais sobre suas opções de política anti-phishing, consulte [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).

## <a name="part-4---anti-spam-protection"></a>Parte 4-proteção antispam

A [proteção](anti-spam-protection.md) antispam está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. No [centro de conformidade & segurança](https://protection.office.com), escolha **Threat management**  >  **Policy**  >  **anti-spam**de política de gerenciamento de ameaças.

2. Na guia **Personalizar** , ative **as configurações personalizadas** .

3. Expanda **política de filtro de spam padrão**, clique em **Editar política**e especifique as seguintes configurações:

   - Na seção **ações de spam e em massa** , defina o limite para um valor de 5 ou 6.

   - Na seção **permitir listas** , revise (e, se necessário, edite) seus remetentes e domínios permitidos.

4. Clique em **Salvar**.

Para saber mais sobre suas opções de política antispam, consulte [Configure anti-spam Policies in EOP](configure-your-spam-filter-policies.md).

## <a name="part-5---additional-settings-to-configure"></a>Parte 5-configurações adicionais a serem definidas

Além de configurar a proteção contra malware, URLs e arquivos mal-intencionados, phishing e spam, recomendamos que você defina as configurações de limpeza automática de zero horas e log de auditoria.

### <a name="zero-hour-auto-purge-for-email"></a>Limpeza automática de zero horas para email

[A limpeza automática de zero horas](zero-hour-auto-purge.md) (zap) está disponível em assinaturas que incluem [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Essa proteção é ativada por padrão; no entanto, as seguintes condições devem ser atendidas para que a proteção entre em vigor:

- As ações de spam são definidas para **mover mensagens para a pasta lixo eletrônico** em [políticas antispam](anti-spam-protection.md).

- Os usuários mantiveram suas [configurações de lixo eletrônico](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)padrão e não desativaram a proteção de lixo eletrônico.

Para saber mais, confira [exclusão automática de zero horas-proteção contra spam e malware](zero-hour-auto-purge.md).

### <a name="audit-logging-for-reporting-and-investigation"></a>Log de auditoria para relatórios e investigação

O log de auditoria está disponível em assinaturas que incluem o [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para exibir dados em relatórios de proteção contra ameaças, como o [painel de segurança](security-dashboard.md), [relatórios de segurança de email](view-email-security-reports.md)e [Explorer](threat-explorer.md), o log de auditoria deve estar ativado para sua organização. Para saber mais, confira [Ativar ou desativar a pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Tarefas pós-instalação

Depois de configurar seus recursos de proteção contra ameaças, não deixe de monitorar como esses recursos estão funcionando, revise e revise suas políticas conforme necessário e observe os novos recursos e atualizações de serviço.

|||
|---|---|
|**O que fazer**|**Recursos para saber mais**|
|Veja como os recursos de proteção contra ameaças estão trabalhando para sua organização exibindo relatórios|[Painel de segurança](security-dashboard.md)<br/>[Relatórios de segurança de email](view-email-security-reports.md)<br/>[Relatórios para o Office 365 ATP](view-reports-for-atp.md)<br/>[Explorador de ameaças](threat-explorer.md)|
|Revisar e revisar periodicamente suas políticas de proteção contra ameaças, conforme necessário|[Classificação de segurança](../mtp/microsoft-secure-score.md)<br/>[Relatórios inteligentes e insights](reports-and-insights-in-security-and-compliance.md)<br/>[Investigação de ameaças e recursos de resposta da Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Assista a novos recursos e atualizações de serviço|[Opções de lançamento direcionado e padrão](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Centro de Mensagens](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Descrições de serviço](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
