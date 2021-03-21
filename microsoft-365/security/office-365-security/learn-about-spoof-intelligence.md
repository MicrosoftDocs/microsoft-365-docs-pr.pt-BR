---
title: Configurar a inteligência contra falsificação
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre a inteligência de spoof no Exchange Online Protection (EOP), onde você pode permitir ou bloquear envios de spoofed específicos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bdc68f5a7e1f21969f5cd787cfdb0b58bc26cd83
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926907"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Configurar a inteligência de spoof no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações do Exchange Online Protection (EOP) autônomas sem caixas de correio do Exchange Online, as mensagens de email de entrada são automaticamente protegidas contra a falsas informações pelo EOP a partir de outubro de 2018. O EOP usa a inteligência de fraude como parte da defesa geral da sua organização contra phishing. Para obter mais informações, consulte [Anti-spoofing protection in EOP](anti-spoofing-protection.md).

Quando um remetente faz a spoofes de um endereço de email, ele parece ser um usuário em um dos domínios da sua organização ou um usuário em um domínio externo que envia emails para sua organização. Os invasores que spoof remetentes para enviar emails de spam ou phishing precisam ser bloqueados. Mas há cenários em que os envios legítimos são spoofing. Por exemplo:

- Cenários legítimos para a spoofing de domínios internos:

  - Os envios de terceiros usam seu domínio para enviar emails em massa para seus próprios funcionários para sondagens da empresa.
  - Uma empresa externa gera e envia atualizações de anúncios ou produtos em seu nome.
  - Um assistente precisa enviar emails regularmente para outra pessoa em sua organização.
  - Um aplicativo interno envia notificações por email.

- Cenários legítimos para a spoofing de domínios externos:

  - O remetente está em uma lista de email (também conhecida como lista de discussão), e a lista de emails retransmite emails do remetente original para todos os participantes na lista de email.
  - Uma empresa externa envia emails em nome de outra empresa (por exemplo, um relatório automatizado ou uma empresa de software como serviço).

A inteligência de spoof e, especificamente, a política de inteligência de spoof (e somente) padrão, ajuda a garantir que o email empoado enviado por remetentes legítimos não seja capturado em filtros de spam do EOP ou sistemas de email externos, enquanto protege seus usuários contra ataques de spam ou phishing.

Você pode gerenciar a inteligência de spoof no Centro de Conformidade & Segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente à página de **Configurações antispam**, use <https://protection.office.com/antispam>. Para ir diretamente para a página **Anti-phishing,** use <https://protection.office.com/antiphishing> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:
  - Para modificar a política de inteligência de spoof ou habilitar ou  desabilitar a inteligência de spoof, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.
  - Para acesso somente leitura à política de inteligência de spoof, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossas configurações recomendadas para a inteligência de spoof, consulte Configurações de política [anti-phishing](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)padrão do EOP.

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Usar o Centro de Conformidade & segurança para gerenciar os envios com spoofed

> [!NOTE]
> Se você tiver uma assinatura do Microsoft 365 Enterprise E5 ou tiver comprado separadamente um complemento do Microsoft Defender para Office 365, você também poderá gerenciar os envios que estão spoofando seu domínio por meio do insight [Spoof Intelligence](walkthrough-spoof-intelligence-insight.md).

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **Configurações anti-spam,** clique em ![ Expandir ícone para expandir a política de inteligência de ](../../media/scc-expand-icon.png) **Spoof.**

   ![Selecione a política de inteligência de spoof](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Faça uma das seguintes seleções:

   - **Revisar novos envios**
   - **Mostrar-me os envios que já revisei**

4. No guia Decidir se esses senders têm permissão para fazer a **spoofe** do seu flyout de usuários que aparece, selecione uma das seguintes guias:

   - **Seus Domínios**: Os senders são os usuários que são depondo em seus domínios internos.
   - **Domínios Externos**: Os senders são os usuários depondo em domínios externos.

5. Clique ![ em Expandir ícone na coluna Permitido a ](../../media/scc-expand-icon.png) **spoof?** Escolha **Sim** para permitir que o remetente spoofed ou escolha **Não** para marcar a mensagem como falsa. A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**). Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

   ![Captura de tela mostrando o sobrevoo de remetentes e se o remetente tem permissão para fazer a spoof](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   As colunas e os valores que você vê são explicados na lista a seguir:

   - **Usuário com spoofed**: a conta de usuário que está sendo esofada. Esse é o remetente da mensagem no endereço De (também conhecido como endereço) mostrado `5322.From` nos clientes de email. A validade desse endereço não é verificada pelo SPF.

     - Na guia **Seus Domínios,** o valor contém um único endereço de email ou, se o servidor de email de origem estiver spoofando várias contas de usuário, ele contém **Mais de um**.

     - Na guia **Domínios Externos,** o valor contém o domínio do usuário espouado, não o endereço de email completo.

   - **Infraestrutura de** Envio : o domínio encontrado em um registro DET (pesquisa DNS) reverso do endereço IP do servidor de email de origem. Se o endereço IP de origem não tiver registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).

     Para obter mais informações sobre fontes de mensagens e envios de mensagens, consulte Uma visão [geral dos padrões de mensagens de email.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

   - **# de mensagens**: o número de mensagens da infraestrutura de envio para sua organização que contêm o remetente ou remetentes despojados especificados nos últimos 30 dias.

   - **# de reclamações do usuário**: Reclamações registradas por seus usuários contra esse remetente nos últimos 30 dias. As reclamações geralmente são na forma de envios de lixo eletrônico para a Microsoft.

   - **Resultado da** autenticação : um dos seguintes valores:
      - **Passado**: o remetente passou verificações de autenticação de email de remetente (SPF ou DKIM).
      - **Falha**: O remetente falhou nas verificações de autenticação do remetente EOP.
      - **Desconhecido**: o resultado dessas verificações não é conhecido.

   - **Decisão definida por**: Mostra quem determinou se a infraestrutura de envio tem permissão para fazer a spoof do usuário:
       - **Política de inteligência de spoof** (automática)
       - **Admin** (manual)

   - **Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.

   - **Permitido a spoof?**: Os valores que você vê aqui são:
     - **Sim**: As mensagens da combinação de usuário e de envio de infraestruturas falsas são permitidas e não tratadas como emails falsas.
     - **Não**: As mensagens da combinação de usuário e de envio de infraestruturas falsas são marcadas como falsas. A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**). Consulte a próxima seção para obter mais informações.

     - **Alguns usuários** ( somente a guia **Domínios):** uma infraestrutura de envio é a spoofing de vários usuários, onde alguns usuários com spoofed são permitidos e outros não. Use a **guia Detalhada** para ver os endereços específicos.

6. Na parte inferior da página, clique em **Salvar**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Usar o PowerShell para gerenciar os envios de spoofed

Para exibir os envios permitidos e bloqueados em inteligência de spoof, use a seguinte sintaxe:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

Este exemplo retorna informações detalhadas sobre todos os senders que têm permissão para espocar usuários em seus domínios.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).

Para configurar os envios permitidos e bloqueados na inteligência de spoof, siga estas etapas:

1. Capture a lista atual de envios esofados detectados escrevendo a saída do cmdlet **Get-PhishFilterPolicy** em um arquivo CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Edite o arquivo CSV para adicionar ou modificar os valores **SpoofedUser** (endereço de email) e **AllowedToSpoof** (Sim ou Não). Salve o arquivo, leia o arquivo e armazene o conteúdo como uma variável chamada `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Use a `$UpdateSpoofedSenders` variável para configurar a política de inteligência de spoof:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Usar o Centro de Conformidade & segurança para configurar a inteligência de spoof

As opções de configuração para a inteligência de fraude são descritas em Configurações de [Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

Você pode configurar configurações de inteligência de spoof na política anti-phishing padrão e também em políticas personalizadas. Para obter instruções com base em sua assinatura, consulte um dos seguintes tópicos:

- [Configurar políticas anti-phishing no EOP](configure-anti-phishing-policies-eop.md).

- [Configurar políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou a inteligência de spoof com os senders que têm permissão e não têm permissão para fazer a spoof e que você configurou as configurações de inteligência de spoof, use qualquer uma das seguintes etapas:

- No Centro de Conformidade & Segurança,  vá até Política de Gerenciamento de Ameaças Política De expansão de Spoof intelligence selecione Mostrar remetentes Que eu já revisei selecione a guia Seus Domínios ou Domínios Externos e verifique o valor Permitido para a \>  \>  \>  \>  \> **spoof?**   para o remetente.

- No PowerShell, execute os seguintes comandos para exibir os senders que têm permissão e não têm permissão para fazer a spoof:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- No PowerShell, execute o seguinte comando para exportar a lista de todos os envios despojados para um arquivo CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- No Centro de Conformidade & segurança, vá para Política de Gerenciamento de Ameaças  \>  \> **Anti-phishing** ou **anti-phishing atp** e faça uma das seguintes etapas:  

  - Selecione uma política na lista. No sobrevoo exibido, verifique os valores na seção **Spoof.**
  - Clique **em Política padrão**. No sobrevoo exibido, verifique os valores na seção **Spoof.**

- No PowerShell do Exchange Online, substitua pelo Padrão AntiPhish do Office365 ou o nome de uma política personalizada e execute o seguinte comando para verificar \<Name\> as configurações:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Outras maneiras de gerenciar a fraude e o phishing

Seja diligente sobre a proteção contra fraude e phishing. Aqui estão as maneiras relacionadas de verificar os envios que fazem a spoofing do seu domínio e ajudar a impedir que eles danificarem sua organização:

- Verifique o **Relatório de Email de Spoof.** Você pode usar esse relatório com frequência para exibir e ajudar a gerenciar os envios com spoofed. Para obter informações, consulte [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).

- Revise a configuração da Estrutura de Política do Remetente (SPF). Para obter uma introdução rápida à SPF e para configurá-la rapidamente, confira [Configurar a SPF no Microsoft 365 para ajudar a evitar falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para compreender melhor como o Office 365 usa SPF, para solucionar problemas, ou para saber mais sobre implantações incomuns, como implantações híbridas, comece com [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Revise sua configuração DKIM (DomainKeys Identified Mail). Você deve usar o DKIM, além de SPF e DMARC, para ajudar a impedir que os invasores enviem mensagens que pareçam que vêm do seu domínio. O DKIM possibilita adicionar uma assinatura digital a mensagens de email no cabeçalho da mensagem. Para obter informações, [consulte Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).

- Revise sua configuração de Autenticação, Relatório e Conformidade (DMARC) baseada em domínio. Implementar o DMARC com SPF e DKIM proporciona proporção adicional contra o spoofing e o phishing no email. O DMARC ajuda os sistemas de recepção de email a determinarem o que fazer com as mensagens enviadas a partir do seu domínio que falharem em verificações de SPF ou de DKIM. Para obter informações, [consulte Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).