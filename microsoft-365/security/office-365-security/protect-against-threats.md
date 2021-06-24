---
title: Proteger contra ameaças no Microsoft Defender para Office 365, anti-malware, anti-phishing, anti-spam, links Cofre, anexos Cofre, zap (limpeza automática de hora zero), configuração de segurança do MDO
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 06/22/2021
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
ms.openlocfilehash: 7e37b67dbed75e3283070ba94321fcb03979a5a6
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105387"
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
>
> Para ignorar a configuração manual da maioria das políticas no Defender para Office 365, você pode usar políticas de segurança predefinidas no nível Padrão ou Estrito. Para obter mais informações, consulte [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).

## <a name="requirements"></a>Requisitos

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
|Proteção contra URLs mal-intencionadas e arquivos no email e Office documentos (Cofre Links e Cofre Anexos)|[Obter o Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Funções e permissões

Para configurar o Defender para Office 365, você deve ter uma função apropriada. Confira a tabela abaixo para ver as funções que podem fazer essas ações.

<br>

****

|Função ou grupo de funções|Onde saber mais|
|---|---|
|administrador global|[Sobre as funções de administrador do Microsoft 365 ](../../admin/add-users/about-admin-roles.md)|
|Administrador de Segurança|[Permissões da função de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gerenciamento de Organização do Exchange Online|[Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo)|
|

Para saber mais, confira [Permissões no Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Ativar o log de auditoria para relatórios e investigação

- Inicie o log de auditoria mais cedo. Você precisará que a auditoria seja **on** para algumas das etapas a seguir. O log de auditoria está disponível em assinaturas que incluem [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para exibir dados em relatórios de proteção contra ameaças, os relatórios de segurança de [email](view-email-security-reports.md)e o [Explorer](threat-explorer.md), o log de auditoria devem *estar em*. Para saber mais, confira Ativar ou desativar a pesquisa de [log de auditoria.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Parte 1 - Proteção anti-malware no EOP

Para obter mais informações sobre as configurações recomendadas para anti-malware, consulte [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).

1. Abra a **página Anti-malware** no portal Microsoft 365 Defender em <https://security.microsoft.com/antimalwarev2> .

2. Na página **Anti-malware,** selecione a política chamada **Padrão (Padrão)** clicando no nome.

3. No sobremenu de detalhes da política que é aberto, clique em Editar configurações **de proteção** e, em seguida, configure as seguintes configurações:
   - **Seção Configurações de** proteção:
     - **Habilita o filtro de anexos comuns:** Selecione (ative). Clique **em Personalizar tipos de** arquivo para adicionar mais tipos de arquivo.
     - **Habilitar a limpeza automática de** hora zero para malware : Verifique se essa configuração está selecionada. Para obter mais informações sobre o ZAP para malware, consulte [Zero-hour auto purge (ZAP) for malware](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware).
   - **Seção** Notificação: Verifique se nenhuma das configurações de notificação está selecionada.

   Quando concluir, clique em **Salvar**.

4. De volta ao submenu de detalhes da política, clique em **Fechar**.

Para obter instruções detalhadas sobre como configurar políticas anti-malware, consulte [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Parte 2 - Proteção anti-phishing no EOP e no Defender para Office 365

[A proteção anti-phishing](anti-phishing-protection.md) está disponível em assinaturas que incluem [eOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). A proteção anti-phishing avançada está disponível no [Defender para](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365 .

Para obter mais informações sobre as configurações recomendadas para políticas [anti-phishing, consulte EOP anti-phishing](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) policy settings and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

O procedimento a seguir descreve como configurar a política anti-phishing padrão. Configurações que estão disponíveis apenas no Defender para Office 365 estão claramente marcados.

1. Abra a **página Anti-phishing** no portal Microsoft 365 Defender em <https://security.microsoft.com/antiphishing> .

2. Na página **Anti-phishing,** selecione a política chamada **Office365 AntiPhish Default (Default)** clicando no nome.

3. No sobremenu de detalhes da política exibido, configure as seguintes configurações:
   - Seção de proteção & limite de **phishing:** clique em **Editar** configurações de proteção e configure as seguintes configurações no sobrevoo que será aberto:
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

   - **Seção Ações:** Clique **em Editar ações** e configure as seguintes configurações no sobrevoo que será aberto:
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

1. Abra a **página Políticas anti-spam** no portal Microsoft 365 Defender em <https://security.microsoft.com/antispam> .

2. Na página **Políticas anti-spam,** selecione a política chamada Política de entrada **anti-spam (Padrão)** na lista clicando no nome.

3. No sobremenu de detalhes da política exibido, configure as seguintes configurações:
   - **Limite de email em massa & seção propriedades de spam:** Clique em **Editar limite de spam e propriedades**. No sobrevoo exibido, configure as seguintes configurações:
     - **Limite de email em massa:** de definir esse valor como 5 (Estrito) ou 6 (Padrão).
     - Deixe outras configurações em seus valores padrão (**Off** ou **None**).

     Quando concluir, clique em **Salvar**.

   - **Seção Ações:** Clique **em Editar ações**. No sobrevoo exibido, configure as seguintes configurações:
     - **Seção Ações de** mensagem:
       - **Spam**: Verifique **se a pasta Mover mensagem para Lixo** Eletrônico está selecionada (Padrão) ou selecione Mensagem de **quarentena** (Estrita).
       - **Spam de alta confiança**: Selecione **Mensagem de quarentena**.
       - **Phishing**: Selecione **Mensagem de quarentena**.
       - **Phishing de alta confiança**: Verifique se **as mensagens de quarentena** estão selecionadas.
       - **Em** massa: Verifique **se a pasta Mover mensagem para** Lixo Eletrônico está selecionada (Padrão) ou selecione Mensagem de **quarentena** (Estrita).
     - **Mantenha o spam em quarentena por esses muitos dias:** Verifique o valor **de 30** dias.
     - **Habilitar dicas de segurança de** spam : Verifique se essa configuração está selecionada (ativada).
     - **Habilitar a limpeza automática de** hora zero (ZAP) : Verifique se essa configuração está selecionada (ativada).
       - **Habilitar para mensagens de phishing**: Verifique se essa configuração está selecionada (ativada). Para obter mais informações, consulte [Zero-hour auto purge (ZAP) for phishing](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing).
       - **Habilitar para mensagens de spam**: Verifique se essa configuração está selecionada (ativada). Para obter mais informações, consulte Zap (limpeza automática de hora [zero) para spam](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam).
     - **Seção Notificações:**
       - Selecione **Habilitar notificações de spam do usuário final**.
         - **Enviar notificações de spam do usuário final a cada (dias)**: Verifique o valor **de 3** dias.
         - **Idioma**: Verifique o valor **Padrão** ou selecione um idioma.

     Quando concluir, clique em **Salvar**.

   - **Seção Remetentes e domínios permitidos e bloqueados:** Revise ou edite seus remetentes permitidos e domínios permitidos conforme descrito em Criar listas de remetentes bloqueados no [EOP](create-block-sender-lists-in-office-365.md) ou Criar listas de [remetentes seguros](create-safe-sender-lists-in-office-365.md)no EOP .

     Quando concluir, clique em **Salvar**.

4. Quando terminar, clique em **Fechar**.

Para obter instruções detalhadas sobre como configurar políticas anti-spam, consulte [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4 - Proteção contra URLs e arquivos mal-intencionados (Cofre Links e Cofre anexos no Defender para Office 365)

A proteção de tempo de clique contra URLs mal-intencionadas e arquivos está disponível em assinaturas que incluem [o Microsoft Defender para](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)Office 365 . Ela é configurada por meio de Cofre [anexos](safe-attachments.md) e Cofre [links.](safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Cofre Políticas de anexos no Microsoft Defender para Office 365

Para obter mais informações sobre as configurações recomendadas para Cofre Anexos, consulte . [Cofre de anexos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

1. Abra a **página Cofre anexos** no portal Microsoft 365 Defender em <https://security.microsoft.com/safeattachmentv2> .

2. Na página **Cofre Anexos,** clique em **Configurações** globais e, em seguida, configure as seguintes configurações no sobrevoo que aparece:
   - **A opção Ativar o Defender para** Office 365 para SharePoint, OneDrive e Microsoft Teams : Ativar essa configuração ( Ativar ![ ](../../media/scc-toggle-on.png) ).

     > [!IMPORTANT]
     > **Antes de ativar Cofre anexos** para SharePoint, OneDrive e Microsoft Teams, verifique se o log de auditoria está transformado em sua organização. Essa ação geralmente é feita por alguém que tem a função Logs de Auditoria atribuída Exchange Online. Para obter mais informações, consulte Ativar ou desativar a [pesquisa de log de auditoria](../../compliance/turn-audit-log-search-on-or-off.md)!

   - **Ativar Cofre Documentos para clientes Office**: Ativar essa configuração ( Ativar ![ ](../../media/scc-toggle-on.png) ). Observe que esse recurso está disponível e significativo somente com Microsoft 365 E5 ou Microsoft 365 E5 Security licenças.
   - **Permitir que as** pessoas cliquem em Exibição Protegida, mesmo que Cofre documentos identificaram o arquivo como mal-intencionado : Verifique se essa configuração está desligada ( ![ Alternar ](../../media/scc-toggle-off.png) ).

   Quando terminar, clique em **Salvar**

3. De volta à página **Cofre Anexos,** clique ![ em Criar ícone ](../../media/m365-cc-sc-create-icon.png) .

4. No assistente **de política Criar Cofre Anexos** que é aberto, configure as seguintes configurações:
   - **Nomeia sua página de** política:
     - **Nome**: Insira algo exclusivo e descritivo.
     - **Descrição**: insira uma descrição opcional.
   - **Página Usuários e domínios:** Como essa é sua primeira política e você provavelmente deseja maximizar a cobertura, considere inserir seus [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) na caixa **Domínios.** Caso contrário, você pode usar as **caixas Usuários** e **Grupos** para um controle mais granular. Você pode especificar exceções selecionando **Excluir esses usuários, grupos e domínios** e inserindo valores.
   - **Configurações** página:
     - **Cofre resposta de malware desconhecido anexos**: Selecione **Bloquear**.
     - **Anexo de redirecionamento com anexos detectados** **:** Habilitar redirecionamento : ativar essa configuração (selecionar) e inserir um endereço de email para receber mensagens detectadas.
     - **Aplique a Cofre de** detecção de Anexos se a verificação não puder ser concluída (tempo de conclusão ou erros) : Verifique se essa configuração está selecionada.

5. Quando terminar, clique em **Enviar** e clique em **Concluído**.

6. (Recomendado) Como administrador global ou administrador SharePoint Online, execute o cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** com o parâmetro _DisallowInfectedFileDownload_ definido como `$true` no SharePoint Online PowerShell.
   - `$true` bloqueia todas as ações (exceto Excluir) para arquivos detectados. As pessoas não podem abrir, mover, copiar ou compartilhar arquivos detectados.
   - `$false` bloqueia todas as ações, exceto Excluir e Baixar. As pessoas podem optar por aceitar o risco e baixar um arquivo detectado.

7. Permita até 30 minutos para que suas alterações se spread para todos os Microsoft 365 datacenters.

Para obter instruções detalhadas sobre como configurar Cofre de anexos e configurações globais para Cofre anexos, consulte os seguintes tópicos:

- [Configurar políticas Cofre anexos no Microsoft Defender para Office 365](set-up-safe-attachments-policies.md)
- [Ative os anexos seguros para SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)
- [Documentos Seguros no Microsoft 365 E5](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Cofre Políticas de links no Microsoft Defender para Office 365

Para obter mais informações sobre as configurações recomendadas para links Cofre, [consulte Cofre Configurações de Links](recommended-settings-for-eop-and-office365.md#safe-links-settings).

1. Abra a **página Cofre Links** no portal Microsoft 365 Defender em <https://security.microsoft.com/safelinksv2> .

2. Na página **Cofre Links,** clique em **Configurações globais** e, em seguida, configure as seguintes configurações no sobrevoo que aparece:
   - **Configurações que se aplicam ao conteúdo na seção Office 365 aplicativos com** suporte:
     - **Use Cofre Links em Office 365 aplicativos**: Verifique se essa configuração está conexões ( ![ Para ](../../media/scc-toggle-on.png) alternar).
     - **Não rastreia quando os usuários clicam em links protegidos Office 365 aplicativos**: Desativar essa configuração ( ![ Desativar ](../../media/scc-toggle-off.png) ).
     - **Não permitir que os usuários cliquem na URL original** em aplicativos Office 365 : Verifique se essa configuração está 100% 100 % 2000 . ![ ](../../media/scc-toggle-on.png)

   Quando terminar, clique em **Salvar**

3. De volta à página **Cofre Links,** clique ![ em Criar ícone ](../../media/m365-cc-sc-create-icon.png) .

4. No assistente **de política Criar Cofre Links** que é aberto, configure as seguintes configurações:
   - **Nomeia sua página de** política:
     - **Nome**: Insira algo exclusivo e descritivo.
     - **Descrição**: insira uma descrição opcional.
   - **Página Usuários e domínios:** Como essa é sua primeira política e você provavelmente deseja maximizar a cobertura, considere inserir seus [domínios aceitos](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) na caixa **Domínios.** Caso contrário, você pode usar as **caixas Usuários** e **Grupos** para um controle mais granular. Você pode especificar exceções selecionando **Excluir esses usuários, grupos e domínios** e inserindo valores.
   - **Página de configurações de** proteção:
     - **Selecione a ação para URLs mal-intencionadas desconhecidas em mensagens**: Ativar essa **configuração**.
     - **Selecione a ação para URLs desconhecidas** ou potencialmente mal-intencionadas Microsoft Teams : Ativar essa **configuração.** A partir de março de 2020, essa configuração está em Visualização e está disponível ou funcional apenas para membros do Programa de Adoção de Tecnologia Microsoft Teams (TAP).
     - **Aplicar verificação de URL** em tempo real para links suspeitos e links que apontam para arquivos : Selecione essa configuração (ativar).
       - **Aguarde a conclusão da verificação de URL antes de entregar a mensagem**: Selecione essa configuração (ativar).
     - **Aplicar Cofre Links para mensagens de email enviadas dentro da** organização : Selecione essa configuração (ativar).
     - **Não rastrear cliques do usuário**: Verifique se essa configuração não está selecionada (desligada).
     - **Não permitir que os usuários cliquem na URL original**: Verifique se essa configuração está 2016 (selecionada).
     - Exibir a identidade visual da organização nas páginas de notificação e aviso **:** Selecionar essa configuração (ative-a) só será significativa depois que você seguir as instruções em Personalizar o tema Microsoft 365 para [sua](../../admin/setup/customize-your-organization-theme.md) organização carregar o logotipo da sua empresa.
     - **Não reescreva as SEGUINTES URLs**: Não temos nenhuma recomendação específica para essa configuração. Para obter mais informações, consulte ["Não reescrever as seguintes URLs" em Cofre Políticas de Links.](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)
   - **Página de** notificação:
     - **Gostaria de notificar os usuários?** seção: Opcionalmente, você pode selecionar **Usar texto de notificação personalizado** para inserir texto de notificação personalizado a ser usado. Você também pode selecionar **Usar Microsoft Translator para** localização automática para traduzir o texto de notificação personalizado para o idioma do usuário. Caso contrário, **deixe Usar o texto de notificação padrão** selecionado.

5. Quando terminar, clique em **Enviar** e clique em **Concluído**.

Para obter instruções detalhadas sobre como configurar Cofre políticas de links e configurações globais para links Cofre, consulte os seguintes tópicos:

- [Configurar políticas Cofre links no Microsoft Defender para Office 365](set-up-safe-links-policies.md)
- [Configurar configurações globais para Cofre links no Microsoft Defender para Office 365](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>Agora, configurar alertas para arquivos detectados no SharePoint Online ou OneDrive for Business

Para receber notificação quando um arquivo no SharePoint Online ou OneDrive for Business tiver sido identificado como mal-intencionado, você pode configurar um alerta conforme descrito nesta seção.

1. No portal Microsoft 365 Defender em , acesse Email & colaboração Políticas & <https://security.microsoft.com>  \> **regras** Política de \> **alerta.**

2. Na página **Política de alerta,** clique em **Nova política de alerta.**

3. O **assistente nova política de** alerta é aberto. Na página **Nome,** configure as seguintes configurações:
   - **Nome**: Insira um nome exclusivo e descritivo. Por exemplo, você pode digitar Arquivos Mal-Intencionados em Bibliotecas.
   - **Descrição**: insira uma descrição opcional.
   - **Severidade**: Selecione **Baixo,** **Médio** ou **Alto**.
   - **Categoria**: Selecione **Gerenciamento de ameaças**.

   Quando terminar, clique em **Próximo**

4. Na página **Criar configurações de** alerta, configure as seguintes configurações:
   - **O que você deseja alertar?** section: **Activity is** \> **Detected malware in file**.
   - **Como você deseja que o alerta seja** disparado seção: Verificar Sempre que uma atividade corresponde à **regra** for selecionada.

   Quando terminar, clique em **Próximo**

5. Na página **Definir seus destinatários,** configure as seguintes configurações:
   - **Enviar notificações por email**: Verifique se essa configuração foi selcted.
   - **Destinatários de** email : selecione um ou mais administradores globais, administradores de segurança ou leitores de segurança que devem receber notificação quando um arquivo mal-intencionado for detectado.
   - **Limite de notificação diário**: Verifique **se nenhum limite** está selecionado.

   Quando terminar, clique em **Próximo**

6. Na página **Revisar suas configurações,** revise suas configurações, verifique **Sim,** a opção Ativar imediatamente está selecionada e clique em **Concluir**

Para saber mais sobre políticas de alerta, consulte [Políticas de alerta no Centro de conformidade do Microsoft 365](../../compliance/alert-policies.md).

> [!NOTE]
> Quando terminar de configurar, use esses links para iniciar investigações de carga de trabalho:
>
>- [Relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
>- [Use o portal Microsoft 365 Defender para gerenciar arquivos em quarentena no Defender para Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [O que fazer quando um arquivo mal-intencionado é encontrado no SharePoint Online, OneDrive ou Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Gerenciar mensagens e arquivos em quarentena como administrador em Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>Tarefas pós-instalação e próximas etapas

Depois de configurar os recursos de proteção contra ameaças, certifique-se de monitorar como esses recursos estão funcionando! Revise e revise suas políticas para que elas faça o que você precisa. Além disso, observe novos recursos e atualizações de serviço que podem adicionar valor.

<br>

****

|O que fazer|Recursos para saber mais|
|---|---|
|Veja como os recursos de proteção contra ameaças estão funcionando para sua organização exibindo relatórios|[Relatórios de segurança de email](view-email-security-reports.md) <p> [Relatórios do Microsoft Defender para Office 365](view-reports-for-mdo.md) <p> [Explorador de Ameaças](threat-explorer.md)|
|Revise e revise periodicamente suas políticas de proteção contra ameaças conforme necessário|[Classificação de segurança](../defender/microsoft-secure-score.md) <p> [Microsoft 365 de investigação e resposta contra ameaças](./office-365-ti.md)|
|Assista a novos recursos e atualizações de serviço|[Opções de versão padrão e direcionada](../../admin/manage/release-options-in-office-365.md) <p> [Centro de Mensagens](../../admin/manage/message-center.md) <p> [Roteiro do Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descrições do serviço](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
