---
title: Configurar a entrega de simulações de phishing de terceiros para usuários e mensagens não filtradas para caixas de correio SecOps
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Os administradores podem aprender a usar a política de entrega avançada no Proteção do Exchange Online (EOP) para identificar mensagens que não devem ser filtradas em cenários com suporte específico (simulações de phishing de terceiros e mensagens entregues às caixas de correio de operações de segurança (SecOps).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 819f78883aa75fbbdded2e47c1bb85945f080233
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108398"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Configurar a entrega de simulações de phishing de terceiros para usuários e mensagens não filtradas para caixas de correio SecOps

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> O recurso descrito neste artigo está em Visualização, não está disponível para todos e está sujeito a alterações.

Para manter sua organização segura por [padrão,](secure-by-default.md)o Proteção do Exchange Online (EOP) não permite listas seguras ou bypass de filtragem para mensagens identificadas como malware ou phishing de alta confiança. Porém, há cenários específicos que exigem a entrega de mensagens não filtradas. Por exemplo:

- **Simulações de phishing de** terceiros : Ataques simulados podem ajudá-lo a identificar usuários vulneráveis antes que um ataque real impacte sua organização.
- Caixas de correio de operações de segurança **(SecOps)**: Caixas de correio dedicadas que são usadas pelas equipes de segurança para coletar e analisar mensagens não filtradas (boas e ruins).

Você usa a _política de entrega_ avançada Microsoft 365 impedir que essas mensagens nesses _cenários específicos_ seja filtrada. <sup>\*</sup> A política de entrega avançada garante que as mensagens nesses cenários alcancem os seguintes resultados:

- Os filtros no EOP e no Microsoft Defender Office 365 tomar nenhuma ação nessas mensagens.<sup>\*</sup>
- [A limpeza zero hora (ZAP)](zero-hour-auto-purge.md) para spam e phishing não toma nenhuma ação nessas mensagens.<sup>\*</sup>
- [Os alertas padrão do](alerts.md) sistema não são disparados para esses cenários.
- [AIR e clustering no Defender para Office 365](office-365-air.md) ignora essas mensagens.
- Especificamente para simulações de phishing de terceiros:
  - [Os envios de administrador](admin-submission.md) geram uma resposta automática dizendo que a mensagem faz parte de uma campanha de simulação de phishing e não é uma ameaça real. Os alertas e o AIR não serão disparados.
  - [Cofre Links no Defender para Office 365](safe-links.md) não bloqueia ou detona as URLs especificamente identificadas nessas mensagens.
  - [Cofre Anexos no Defender para](safe-attachments.md) Office 365 não detona anexos nessas mensagens.

<sup>\*</sup> Não é possível ignorar a filtragem de malware ou o ZAP para malware.

As mensagens identificadas pela política de entrega avançada não são ameaças de segurança, portanto, as mensagens são marcadas como substituições do sistema. Os administradores podem filtrar e analisar essas substituições do sistema nas seguintes experiências:

- [Explorador de Ameaças/Detecções em tempo real no Defender para Office 365 plano 2](threat-explorer.md)
- A [Página da entidade email no Explorador de Ameaças/Detecções em tempo real](mdo-email-entity-page.md)
- O [relatório de status de proteção contra ameaças](view-email-security-reports.md#threat-protection-status-report)
- [Busca avançada no Microsoft Defender para Ponto de Extremidade](../defender-endpoint/advanced-hunting-overview.md)
- [Modos de Exibição de Campanha](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o portal do Microsoft 365 Defender em <https://security.microsoft.com>. Para ir diretamente para a **página Entrega** Avançada, abra <https://security.microsoft.com/advanceddelivery> .

- Você precisa ter permissões atribuídas antes de poder fazer os procedimentos neste artigo:
  - Para criar, modificar ou remover configurações configuradas na política de entrega  avançada, você precisa ser membro do grupo de  função Administrador de Segurança no **portal do Microsoft 365 Defender** e membro do grupo de função Gerenciamento da Organização **no Exchange Online**.  
  - Para acesso somente leitura à política de entrega avançada, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, consulte [Permissões no portal Microsoft 365 Defender e](permissions-microsoft-365-security-center.md) Permissões no [Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > Adicionar usuários à função Azure Active Directory correspondente fornece aos usuários as permissões necessárias no _portal_ Microsoft 365 Defender e permissões para outros recursos no Microsoft 365. Para obter mais informações, confira [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Use o portal Microsoft 365 Defender para configurar caixas de correio SecOps na política de entrega avançada

1. No portal Microsoft 365 Defender, vá para **Email & Políticas** de Colaboração & Regras De acordo com a página Regras seção Entrega \>  \>  \>  \> **avançada**.

2. Na página **Entrega Avançada,** verifique se a guia caixa de correio **SecOps** está selecionada e, em seguida, faça uma das seguintes etapas:
   - Clique ![ em Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar**.
   - Se não houver simulações de phishing configuradas, clique em **Adicionar**.

3. No sobrevoo Editar caixas de correio **SecOps** que são abertas, insira uma caixa de correio Exchange Online existente que você deseja designar como caixa de correio SecOps, seguindo uma das seguintes etapas:
   - Clique na caixa, deixe a lista de caixas de correio resolver e selecione a caixa de correio.
   - Clique na caixa comece a digitar um identificador para a caixa de correio (nome, nome de exibição, alias, endereço de email, nome da conta etc.) e selecione a caixa de correio (nome de exibição) dos resultados.

     Repita essa etapa quantas vezes forem necessárias. Grupos de distribuição não são permitidos.

     Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

4. Quando concluir, clique em **Salvar**.

As entradas de caixa de correio SecOps que você configurou são exibidas na guia caixa de **correio SecOps.** Para fazer alterações, clique em ![ Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar** na guia.

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Use o Microsoft 365 Defender portal para configurar simulações de phishing de terceiros na política de entrega avançada

1. No portal Microsoft 365 Defender, vá para **Email & Políticas** de Colaboração & Regras De acordo com a página Regras seção Entrega \>  \>  \>  \> **avançada**.

2. Na página **Entrega Avançada,** selecione a guia **Simulação de Phishing** e, em seguida, faça uma das seguintes etapas:
   - Clique ![ em Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar**.
   - Se não houver simulações de phishing configuradas, clique em **Adicionar**.

3. No **sub-sublinhado Editar simulação de phishing** de terceiros que é aberto, configure as seguintes configurações:

   - **Domínio** de envio : expanda essa configuração e insira pelo menos um domínio de endereço de email (por exemplo, contoso.com) clicando na caixa, inserindo um valor e pressionando Enter ou selecionando o valor exibido abaixo da caixa. Repita essa etapa quantas vezes forem necessárias. Você pode adicionar até 10 entradas.
   - **Envio de IP**: expanda essa configuração e insira pelo menos um endereço IPv4 válido é necessário clicando na caixa, inserindo um valor e pressionando Enter ou selecionando o valor exibido abaixo da caixa. Repita essa etapa quantas vezes forem necessárias. Você pode adicionar até 10 entradas. Os valores válidos são:
     - IP único: por exemplo, 192.168.1.1.
     - Intervalo ip: por exemplo, 192.168.0.1-192.168.0.254.
     - IP CIDR: Por exemplo, 192.168.0.1/25.
   - **URLs** de simulação para permitir : Expanda essa configuração e, opcionalmente, insira URLs específicas que fazem parte da sua campanha de simulação de phishing que não devem ser bloqueadas ou detonadas clicando na caixa, inserindo um valor e pressionando Enter ou selecionando o valor exibido abaixo da caixa. Você pode adicionar até 10 entradas.

   Para remover uma entrada existente, clique em Remover ![Ícone Remover](../../media/m365-cc-sc-remove-selection-icon.png) ao lado do valor.

4. Quando terminar, faça uma das seguintes etapas:
   - **Primeira vez:** clique **em Adicionar** e clique em **Fechar**.
   - **Editar existente**: clique em **Salvar** e clique em **Fechar**.

As entradas de simulação de phishing de terceiros que você configurou são exibidas na guia **Simulação de Phishing.** Para fazer alterações, clique em ![ Editar ícone ](../../media/m365-cc-sc-edit-icon.png) **Editar** na guia.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Cenários adicionais que exigem bypass de filtragem

Além dos dois cenários em que a política de entrega avançada pode ajudá-lo, há outros cenários que podem exigir que você ignore a filtragem:

- **Filtros de** terceiros : Se o  registro MX do seu domínio não apontar para o Office 365 (as mensagens são roteadas primeiro para outro [lugar),](secure-by-default.md) a segurança por padrão não está *disponível*.

  Para ignorar a filtragem da Microsoft para mensagens que já foram avaliadas pela filtragem de terceiros, use as regras de fluxo de emails (também conhecidas como regras de transporte). Para obter mais informações, [consulte Use mail flow rules to set the SCL in messages](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md).

- **Falsos positivos** em revisão : talvez você queira permitir temporariamente determinadas mensagens que ainda estão sendo analisadas pela Microsoft por meio de envios de administrador para relatar mensagens boas [conhecidas](admin-submission.md) que estão sendo marcadas incorretamente como ruins para a Microsoft (falsos positivos). Como com todas as substituições, é **_altamente recomendável_** que essas concessões sejam temporárias.
