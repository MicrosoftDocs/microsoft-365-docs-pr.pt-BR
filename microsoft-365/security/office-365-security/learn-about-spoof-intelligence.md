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
description: Os administradores podem saber mais sobre a inteligência contra spoof no Exchange Online Protection (EOP), onde você pode permitir ou bloquear envios de spoofed específicos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a65400d1b48abfc6ac0e4dd38a8245dd7b4f87b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289682"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Configurar inteligência contra spoof no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, as mensagens de email de entrada são automaticamente protegidas contra a spoofing pelo EOP a partir de outubro de 2018. O EOP usa a inteligência contra spoof como parte da defesa geral da sua organização contra phishing. Para obter mais informações, [consulte Proteção anti-spoofing no EOP](anti-spoofing-protection.md).

Quando um remetente spoofs um endereço de email, ele parece ser um usuário em um dos domínios da sua organização ou um usuário em um domínio externo que envia emails para sua organização. Os invasores que spoofers para enviar emails de spam ou phishing precisam ser bloqueados. Mas há cenários em que os remententes legítimos são spoofing. Por exemplo:

- Cenários legítimos para a spoofagem de domínios internos:

  - Os envios de terceiros usam seu domínio para enviar emails em massa para seus próprios funcionários para votações da empresa.
  - Uma empresa externa gera e envia anúncios ou atualizações de produto em seu nome.
  - Um assistente precisa enviar emails regularmente para outra pessoa em sua organização.
  - Um aplicativo interno envia notificações por email.

- Cenários legítimos para a spoofing de domínios externos:

  - O remetente está em uma lista de discussão (também conhecida como lista de discussão) e a lista de discussão retransmite emails do remetente original para todos os participantes na lista de discussão.
  - Uma empresa externa envia emails em nome de outra empresa (por exemplo, um relatório automatizado ou uma empresa de software como serviço).

A inteligência contra spoof e, especificamente, a política de inteligência contra spoof (e somente) padrão, ajuda a garantir que os emails spoofed enviados por remetentes legítimos não se aprecem nos filtros de spam do EOP ou sistemas de email externos, enquanto protege seus usuários contra ataques de spam ou phishing.

Você pode gerenciar a inteligência contra spo & of no Centro de Conformidade e Segurança ou no PowerShell (organizações do PowerShell do Exchange Online para Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente à página de **Configurações antispam**, use <https://protection.office.com/antispam>. Para ir diretamente para a **página anti-phishing,** use <https://protection.office.com/antiphishing> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - Para modificar a política de inteligência contra spoof ou habilitar ou  desabilitar a inteligência contra spoof, você precisa ser membro dos grupos de função Gerenciamento da Organização ou **Administrador de** Segurança.
  - Para acesso somente leitura à política de inteligência de spoof, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- Para nossas configurações recomendadas para inteligência contra spoof intelligence, consulte as configurações de política [anti-phishing](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)padrão do EOP.

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Usar o Centro de Conformidade & segurança para gerenciar os envios de spoofed

> [!NOTE]
> Se você tiver uma assinatura do Microsoft 365 Enterprise E5 ou tiver comprado separadamente um complemento do Microsoft Defender para Office 365, também poderá gerenciar os envios que estão spoofando seu domínio por meio do insight de Inteligência contra [Spoof Intelligence.](walkthrough-spoof-intelligence-insight.md)

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **Configurações anti-spam,** clique no ícone Expandir para expandir a ![ política de inteligência contra ](../../media/scc-expand-icon.png) **spoof.**

   ![Selecionar a política de inteligência contra spoof](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Faça uma das seguintes seleções:

   - **Revisar novos envios**
   - **Mostrar-me os senders que já revisei**

4. In the **Decide if these senders are allowed to spoof your users flyout** that appears, select one of the following tabs:

   - **Seus Domínios**: Os usuários de envio de mensagens de spoofing em seus domínios internos.
   - **Domínios Externos:** Os usuários de envios de mensagens de spoofing em domínios externos.

5. Click ![ Expand icon in the Allowed to ](../../media/scc-expand-icon.png) **spoof?** column. Escolha **Sim** para permitir o remetente spoofado ou **escolha** Não para marcar a mensagem como falsa. A ação é controlada pela política anti-phishing padrão ou pelas políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta Lixo **Eletrônico).** Para obter mais informações, consulte [Configurações de Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

   ![Screenshot showing the spoofed senders flyout, and whether the sender is allowed to spoof](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   As colunas e os valores que você vê são explicados na lista a seguir:

   - **Usuário spoofed**: a conta de usuário que está sendo spoofed. Esse é o remetente da mensagem no endereço De (também conhecido como endereço) que `5322.From` é mostrado nos clientes de email. A validade desse endereço não é verificada pelo SPF.

     - Na guia **Seus Domínios,** o valor contém um único endereço de email ou, se o servidor de email de origem estiver spoofando várias contas de usuário, ele contém **mais de um**.

     - Na guia **Domínios Externos,** o valor contém o domínio do usuário spoofed, não o endereço de email completo.

   - **Infraestrutura de** Envio : o domínio encontrado em um registro PTR (pesquisa de DNS reverso) do endereço IP do servidor de email de origem. Se o endereço IP de origem não tiver nenhum registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).

     Para obter mais informações sobre fontes de mensagens e envios de mensagens, consulte [Uma visão geral dos padrões de mensagens de email.](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)

   - **Número de mensagens:** o número de mensagens da infraestrutura de envio para sua organização que contêm o remetente ou remetentes falsas especificados nos últimos 30 dias.

   - **Número de reclamações de usuários:** reclamações apresentadas por seus usuários contra esse remetente nos últimos 30 dias. As reclamações geralmente estão na forma de envios de lixo eletrônico à Microsoft.

   - **Resultado da** autenticação: um dos seguintes valores:
      - **Passado:** o remetente passou nas verificações de autenticação de email do remetente (SPF ou DKIM).
      - **Falha:** o remetente falhou nas verificações de autenticação do remetente do EOP.
      - **Desconhecido**: o resultado dessas verificações não é conhecido.

   - **Decisão definida por:** mostra quem determinou se a infraestrutura de envio tem permissão para fazer spoof do usuário:
       - **Política de inteligência contra spoof** (automática)
       - **Admin** (manual)

   - **Visto pela última** vez: a última data em que uma mensagem foi recebida da infraestrutura de envio que contém o usuário falsa.

   - **Permissão para fazer spoof?**: Os valores que você vê aqui são:
     - **Sim:** as mensagens da combinação de usuário falsa e da infraestrutura de envio são permitidas e não tratadas como emails falsas.
     - **Não:** as mensagens da combinação de usuário falsa e da infraestrutura de envio são marcadas como falsas. A ação é controlada pela política anti-phishing padrão ou pelas políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta Lixo **Eletrônico).** Consulte a próxima seção para obter mais informações.

     - **Alguns usuários** (somente a guia **Domínios):** uma infraestrutura de envio está fazendo a spoofing de vários usuários, em que alguns usuários são permitidos e outros não. Use a **guia Detalhes** para ver os endereços específicos.

6. Na parte inferior da página, clique em **Salvar**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Usar o PowerShell para gerenciar os envios de spoofed

Para exibir os solicitantes permitidos e bloqueados em inteligência contra spoof intelligence, use a seguinte sintaxe:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

Este exemplo retorna informações detalhadas sobre todos os senders que têm permissão para fazer spoof de usuários em seus domínios.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Para informações detalhadas de sintaxes e de parâmetros, [consulte Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).

Para configurar os envios permitidos e bloqueados em inteligência contra spoof intelligence, siga estas etapas:

1. Capture a lista atual de enviadores com spoofed detectados escrevendo a saída do cmdlet **Get-PhishFilterPolicy** para um arquivo CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Edite o arquivo CSV para adicionar ou modificar os valores **SpoofedUser** (endereço de email) e **AllowedToSpoof** (Sim ou Não). Salve o arquivo, leia o arquivo e armazene o conteúdo como uma variável chamada `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Use a `$UpdateSpoofedSenders` variável para configurar a política de inteligência contra spoof:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Usar o Centro de Conformidade & segurança para configurar a inteligência contra spoof

As opções de configuração para inteligência contra spoof são descritas nas configurações [de Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

Você pode definir as configurações de inteligência contra spoof na política anti-phishing padrão e também em políticas personalizadas. Para obter instruções baseadas em sua assinatura, consulte um dos seguintes tópicos:

- [Configurar políticas anti-phishing no EOP.](configure-anti-phishing-policies-eop.md)

- [Configurar políticas anti-phishing no Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou a inteligência contra spoof com os envios permitidos e não autorizados a fazer spoof e se você configurou as configurações de inteligência contra spoof, use uma das seguintes etapas:

- No Centro de Conformidade de Segurança  &, vá para Política de Gerenciamento de Ameaças Política anti-spam Expanda Política de Inteligência contra \>  \>  \> **Spoof** selecione Mostrar-me remetentes Já \>  \> **revisei**  selecione a guia Seus Domínios ou Domínios Externos e verifique o valor Permitido para **spoof?** para o remetente.

- No PowerShell, execute os seguintes comandos para exibir os envios permitidos e não autorizados a spoof:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- No PowerShell, execute o seguinte comando para exportar a lista de todos os senders spoofed para um arquivo CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- No Centro de Conformidade & Segurança, vá para Política de Gerenciamento de Ameaças  \>  \> **Anti-phishing** ou **anti-phishing da ATP** e faça uma das seguintes etapas:  

  - Selecione uma política na lista. No flyout exibido, verifique os valores na **seção Spoof.**
  - Clique **em Política padrão.** No flyout exibido, verifique os valores na **seção Spoof.**

- No PowerShell do Exchange Online, substitua pelo Padrão AntiPhish do Office365 ou o nome de uma política personalizada e execute o seguinte comando para verificar \<Name\> as configurações:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Outras maneiras de gerenciar a spoofing e phishing

Seja atento à proteção contra phishing e spoofing. Aqui estão as maneiras relacionadas de verificar se os enviadores estão fazendo a spoofagem do seu domínio e ajudar a impedir que eles danificarem sua organização:

- Verifique o **Relatório de Email de Spoof.** Você pode usar esse relatório com frequência para exibir e ajudar a gerenciar os envios de spoofed. Para obter informações, consulte [Relatório de Detecções de Spoof](view-email-security-reports.md#spoof-detections-report).

- Revise a configuração da Estrutura de Política do Remetente (SPF). Para obter uma introdução rápida à SPF e para configurá-la rapidamente, confira [Configurar a SPF no Microsoft 365 para ajudar a evitar falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para compreender melhor como o Office 365 usa SPF, para solucionar problemas, ou para saber mais sobre implantações incomuns, como implantações híbridas, comece com [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Revise sua configuração de DomainKeys Identified Mail (DKIM). Você deve usar o DKIM, além do SPF e do DMARC, para ajudar a impedir que os invasores enviem mensagens que pareçam estar vindo do seu domínio. O DKIM possibilita adicionar uma assinatura digital a mensagens de email no cabeçalho da mensagem. Para saber mais, confira Usar DKIM para validar emails de saída [enviados de seu domínio personalizado no Office 365.](use-dkim-to-validate-outbound-email.md)

- Revise sua configuração de Autenticação de Mensagens, Relatórios e Conformidade (DMARC) baseada em domínio. Implementar o DMARC com SPF e DKIM proporciona proporção adicional contra o spoofing e o phishing no email. O DMARC ajuda os sistemas de recepção de email a determinarem o que fazer com as mensagens enviadas a partir do seu domínio que falharem em verificações de SPF ou de DKIM. Para saber mais, [confira Usar o DMARC para validar emails no Office 365.](use-dmarc-to-validate-email.md)
