---
title: Gerenciar envios com spoofed usando a política de inteligência de spoof e o insight de inteligência de spoof
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a usar a política de inteligência de spoof e o insight de inteligência spoof para permitir ou bloquear os envios esofados detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f0e5c83bc50197e30c12f8f7aeedc83930d7ff5e
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793203"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a>Gerenciar envios com spoofed usando a política de inteligência de spoof e o insight de inteligência de spoof no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Este artigo descreve a experiência de gerenciamento de remetentes despojado mais antiga que está sendo substituída. Para obter mais informações sobre a nova experiência, consulte [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)

Em organizações Microsoft 365 com caixas de correio no Exchange Online ou organizações de Proteção do Exchange Online (EOP) autônomas sem caixas de correio Exchange Online, as mensagens de email de entrada são automaticamente protegidas contra a falsas informações pelo EOP a partir de outubro de 2018. O EOP usa **a inteligência de** fraude como parte da defesa geral da sua organização contra phishing. Para obter mais informações, consulte [Anti-spoofing protection in EOP](anti-spoofing-protection.md).

A política de inteligência de **spoof** (e somente) padrão ajuda a garantir que os emails espoados enviados por remetentes legítimos não são capturados em filtros de spam do EOP enquanto protegem seus usuários contra ataques de spam ou phishing. Você também pode usar o insight de inteligência **Spoof** para determinar rapidamente quais envios externos estão enviando emails não autenticados (mensagens de domínios que não passam verificações SPF, DKIM ou DMARC).

Você pode gerenciar a inteligência de spoof no Centro de Conformidade & Segurança ou no PowerShell (Exchange Online PowerShell para organizações Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem Exchange Online caixas de correio).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>.
  - Para ir diretamente para a página **Configurações anti-spam** para a política de inteligência de spoof, use <https://protection.office.com/antispam> .
  - Para ir diretamente para a página **Painel de segurança** para o insight de inteligência de spoof, use <https://protection.office.com/searchandinvestigation/dashboard> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:
  - Para modificar a política de inteligência de spoof ou habilitar ou  desabilitar a inteligência de spoof, você precisa ser membro dos grupos de função Gerenciamento da Organização ou Administrador **de** Segurança.
  - Para acesso somente leitura à política de inteligência de spoof, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.

- As opções de inteligência de spoof são descritas em Configurações de [Spoof em políticas anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

- Você pode habilitar, desabilitar e configurar as configurações de inteligência de spoof em políticas anti-phishing. Para obter instruções com base em sua assinatura, consulte um dos seguintes tópicos:

  - [Configurar políticas anti-phishing no EOP](configure-anti-phishing-policies-eop.md).
  - [Configure políticas anti-phishing no Microsoft Defender para Office 365](configure-atp-anti-phishing-policies.md).

- Para nossas configurações recomendadas para a inteligência de spoof, consulte Configurações de política [anti-phishing do EOP.](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)

## <a name="manage-spoofed-senders"></a>Gerenciar envios com spoofed

Há duas maneiras de permitir e bloquear os envios de spoofed:

- [Usar a política de inteligência de spoof](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [Usar o insight de inteligência de spoof](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a>Gerenciar envios com spoofed na política de inteligência de spoof

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **Configurações anti-spam,** clique em ![ Expandir ícone para expandir a política de inteligência de ](../../media/scc-expand-icon.png) **Spoof.**

   ![Selecione a política de inteligência de spoof](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Faça uma das seguintes seleções:

   - **Revisar novos envios**
   - **Mostrar-me os envios que já revisei**

4. No guia Decidir se esses senders têm permissão para fazer a **spoofe** do seu flyout de usuários que aparece, selecione uma das seguintes guias:

   - **Seus Domínios**: Os senders são os usuários que são depondo em seus domínios internos.
   - **Domínios Externos**: Os senders são os usuários depondo em domínios externos.

5. Clique ![ em Expandir ícone na coluna Permitido a ](../../media/scc-expand-icon.png) **spoof?** Escolha **Sim** para permitir que o remetente spoofed ou escolha **Não** para marcar a mensagem como falsa. A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**). Para saber mais, confira [Configurações de inteligência contra falsificação nas políticas anti phishing](set-up-anti-phishing-policies.md#spoof-settings).

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

#### <a name="use-powershell-to-manage-spoofed-senders"></a>Usar o PowerShell para gerenciar os envios de spoofed

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

1. Capture a lista atual de envios esofados detectados escrevendo a saída do cmdlet **Get-PhishFilterPolicy** em um arquivo CSV executando o seguinte comando:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Edite o arquivo CSV para adicionar ou modificar os seguintes valores:
   - **Remetente** (domínio no registro PTR do servidor de origem ou endereço IP/24)
   - **SpoofedUser**: um dos seguintes valores:
     - O endereço de email do usuário interno.
     - O domínio de email do usuário externo.
     - Um valor em branco que indica que você deseja bloquear ou permitir todas as mensagens falsas do Remetente especificado **,** independentemente do endereço de email falsa.
   - **AllowedToSpoof** (Sim ou Não)
   - **SpoofType** (Interno ou Externo)

   Salve o arquivo, leia o arquivo e armazene o conteúdo como uma variável `$UpdateSpoofedSenders` nomeada executando o seguinte comando:

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Use a variável para configurar a política de inteligência de `$UpdateSpoofedSenders` spoof executando o seguinte comando:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a>Gerenciar envios com spoofed no insight de inteligência de spoof

1. No Centro de Conformidade & segurança, vá para **Painel de Gerenciamento de** \> **Ameaças.**

2. Na linha **Insights,** procure um dos seguintes itens:

   - **Domínios provavelmente desfalsados** nos últimos sete dias : Essa visão indica que a inteligência de spoof está habilitada (ela está habilitada por padrão).
   - **Habilitar** a Proteção contra Spoof : essa visão indica que a inteligência de spoof está desabilitada e clicar no insight permite que você habilita a inteligência de spoof.

3. O insight no painel mostra informações como esta:

   ![Captura de tela do insight de inteligência de spoof](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   Esse insight tem dois modos:

   - **Modo de** visão : se a inteligência falsa estiver habilitada, a visão mostra quantas mensagens foram impactadas por nossos recursos de inteligência falsa nos últimos sete dias.
   - **E se o modo**: se a inteligência falsa estiver  desabilitada, a visão mostra quantas mensagens teriam sido impactadas por nossos recursos de inteligência falsas nos últimos sete dias.

   De qualquer forma, os domínios despojados exibidos no insight são separados em duas **categorias: domínios** suspeitos e domínios não **suspeitos.**

   - **Domínios suspeitos**:
     - **Spoof** de alta confiança: com base nos padrões de envio históricos e na pontuação de reputação dos domínios, estamos altamente confiantes de que os domínios são falsas, e as mensagens desses domínios são mais propensas a serem mal-intencionadas.
     - **Spoof** de confiança moderada : com base nos padrões de envio históricos e na pontuação de reputação dos domínios, estamos moderadamente confiantes de que os domínios são falsas e que as mensagens enviadas desses domínios são legítimas. Falsos positivos são mais prováveis nessa categoria do que falsos falsos.
   - **Domínios não suspeitos**: O domínio com falha na autenticação de email explícito verifica [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)e [DMARC](use-dmarc-to-validate-email.md)). No entanto, o domínio passou nossas verificações implícitas de autenticação de email ([autenticação composta](email-validation-and-authentication.md#composite-authentication)). Como resultado, nenhuma ação anti-spoofing foi tomada na mensagem.

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a>Exibir informações detalhadas sobre domínios suspeitos e não suspiciosos

1. No insight de inteligência de spoof, clique em **Domínios** suspeitos ou **domínios** não suspeitos para ir para a página de informações de **inteligência de Spoof.** A página de informações **do Spoof Intelligence** contém as seguintes informações:

   - **Domínio spoofed**: O domínio do usuário que é exibido na caixa **De** em clientes de email. Esse endereço também é conhecido como `5322.From` endereço.
   - **Infraestrutura**: Também conhecida como infraestrutura _de envio._ O domínio encontrado em um registro DNS reverso (registro PTR) do endereço IP do servidor de email de origem. Se o endereço IP de origem não tiver registro PTR, a infraestrutura de envio será identificada como \<source IP\> /24 (por exemplo, 192.168.100.100/24).
   - **Contagem de** mensagens : o número de mensagens da infraestrutura de envio para sua organização que contêm o domínio empoeirado especificado nos últimos 7 dias.
   - **Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.
   - **Tipo de spoof**: esse valor é **Externo**.
   - **Permitido a spoof?**: Os valores que você vê aqui são:
     - **Sim**: As mensagens da combinação do domínio do usuário falsa e da infraestrutura de envio são permitidas e não tratadas como emails falsas.
     - **Não**: As mensagens da combinação do domínio do usuário falsa e da infraestrutura de envio são marcadas como falsas. A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é Mover mensagem para a pasta **Lixo Eletrônico**).

2. Selecione um item na lista para exibir detalhes sobre o par de infraestrutura de envio/domínio em um sobremenu. As informações incluem:
   - Por que pegamos isso.
   - O que você precisa fazer.
   - Um resumo de domínio.
   - WhoIs dados sobre o remetente.
   - Mensagens semelhantes que vimos em seu locatário do mesmo remetente.

   A partir daqui, você também pode optar por adicionar ou remover o par de infraestrutura de envio/domínio da lista de permissão Permitido para **spoof** remetente. Basta definir a alternância de acordo.

   ![Captura de tela de um domínio no painel de detalhes de informações de inteligência de Spoof](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou a inteligência de spoof com os senders que têm permissão e não têm permissão para fazer a spoof, use qualquer uma das seguintes etapas:

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
