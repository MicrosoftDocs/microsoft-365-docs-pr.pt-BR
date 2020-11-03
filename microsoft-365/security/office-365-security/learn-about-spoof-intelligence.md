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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender sobre a inteligência de falsificação na proteção do Exchange Online (EOP), onde você pode permitir ou bloquear remetentes falsificados específicos.
ms.openlocfilehash: 4ebc32a6c87c58edcceb0d57ee8d55be43f2dd20
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841823"
---
# <a name="configure-spoof-intelligence-in-eop"></a>Configurar o spoof Intelligence no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nas organizações do Microsoft 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, as mensagens de email de entrada são protegidas automaticamente contra falsificação por EOP a partir de outubro de 2018. O EOP usa a inteligência de falsificação como parte da defesa geral da sua organização contra phishing. Para obter mais informações, consulte [proteção contra falsificação no EOP](anti-spoofing-protection.md).

Quando um remetente falsifica um endereço de email, ele parece ser um usuário em um dos domínios da sua organização ou um usuário em um domínio externo que envia emails para sua organização. Invasores que falsificam remetentes para enviar spam ou phishing email precisam ser bloqueados. Mas há situações em que remetentes legítimos estão falsificando. Por exemplo:

- Cenários legítimos para falsificação de domínios internos:

  - Remetentes de terceiros usam seu domínio para enviar emails em massa aos seus próprios funcionários para pesquisas da empresa.
  - Uma empresa externa gera e envia anúncios ou atualizações de produtos em seu nome.
  - Um assistente precisa regularmente enviar emails para outra pessoa em sua organização.
  - Um aplicativo interno envia notificações por email.

- Cenários legítimos para falsificação de domínios externos:

  - O remetente está em uma lista de endereçamento (também conhecida como lista de discussão) e a lista de endereçamento envia emails do remetente original para todos os participantes na lista de endereçamento.
  - Uma empresa externa envia emails em nome de outra empresa (por exemplo, um relatório automatizado ou uma empresa de software como serviço).

A inteligência de falsificação e, especificamente, a política de inteligência de fraudes padrão (e apenas) ajuda a garantir que o email falso enviado por remetentes legítimos não seja detectado nos filtros de spam do EOP ou sistemas de email externos, enquanto protege seus usuários contra ataques de spam ou phishing.

Você pode gerenciar a inteligência de falsificação no centro de conformidade & segurança ou no PowerShell (Exchange Online PowerShell para organizações do Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem caixas de correio do Exchange Online).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente à página de **Configurações antispam** , use <https://protection.office.com/antispam>. Para ir diretamente para a página **anti-phishing** , use <https://protection.office.com/antiphishing> .

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa ter permissões atribuídas antes de poder executar os procedimentos neste tópico:

  - Para modificar a política de inteligência de spoof ou habilitar ou desabilitar a inteligência de spoof, você precisa ser membro de um dos grupos de função a seguir:

    - **Gerenciamento de organizações** ou **Administrador de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento de organizações** ou **Gerenciamento de higiene** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para acesso somente leitura à política de inteligência de falsificação, você precisa ser membro de um dos grupos de função a seguir:

    - **Leitor de segurança** no [Centro de segurança e conformidade](permissions-in-the-security-and-compliance-center.md).
    - **Gerenciamento da organização Somente visualização** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

- Para obter as configurações recomendadas para a inteligência de falsificação, confira [configurações de política anti-phishing padrão do EOP](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>Usar o centro de conformidade de & de segurança para gerenciar remetentes falsificados

> [!NOTE]
> Se você tiver uma assinatura do Microsoft 365 Enterprise E5 ou tiver adquirido separadamente um complemento do Microsoft defender para Office 365, também poderá gerenciar os remetentes que estão falsificando seu domínio por meio da [compreensão de inteligência de falsificação](walkthrough-spoof-intelligence-insight.md).

1. No Centro de Conformidade e Segurança, vá para **Gerenciamento de ameaças** \> **Política** \> **Antispam**.

2. Na página **configurações antispam** , clique em ![ expandir ícone ](../../media/scc-expand-icon.png) para expandir política de **inteligência de fraude**.

   ![Selecione a política de inteligência de spoof](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. Faça uma das seguintes seleções:

   - **Revisar novos remetentes**
   - **Mostrar os remetentes que eu já revisei**

4. Em **decidir se esses remetentes têm permissão para falsificar o** submenu de usuários exibido, selecione uma das seguintes guias:

   - **Seus domínios** : remetentes que falsificam usuários em seus domínios internos.
   - **Domínios externos** : remetentes que falsificam usuários em domínios externos.

5. Clique em ![ expandir ícone ](../../media/scc-expand-icon.png) na coluna **permitido para falsificação?** . Escolha **Sim** para permitir o remetente falsificado ou escolha **não** para marcar a mensagem como falsificada. A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é **mover mensagem para a pasta lixo eletrônico** ). Para obter mais informações, consulte [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

   ![Captura de tela mostrando o submenu de remetentes falsificados e se o remetente tem permissão para falsificar](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   As colunas e os valores que você vê são explicados na lista a seguir:

   - **Usuário falsificado** : a conta de usuário que está sendo falsificada. Este é o remetente da mensagem no endereço de (também conhecido como o `5322.From` endereço) que é mostrado nos clientes de email. A validade desse endereço não é verificada por SPF.

     - Na guia **domínios** , o valor contém um único endereço de email ou, se o servidor de email de origem estiver falsificando várias contas de usuário, ele conterá **mais de um**.

     - Na guia **domínios externos** , o valor contém o domínio do usuário falsificado, e não o endereço de email completo.

   - **Infraestrutura de envio** : o domínio encontrado em uma pesquisa de DNS inversa (registro PTR) do endereço IP do servidor de email de origem ou o endereço IP, se a fonte não tiver um registro PTR.

     Para obter mais informações sobre fontes de mensagens e remetentes de mensagens, consulte [uma visão geral dos padrões de mensagens de email](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).

   - **n º de mensagens** : o número de mensagens da infraestrutura de envio para sua organização que contêm o remetente falsificado especificado ou remetentes nos últimos 30 dias.

   - **n º de reclamações de usuários** : reclamações arquivadas pelos usuários em relação a esse remetente nos últimos 30 dias. As reclamações geralmente estão na forma de envios de lixo eletrônico para a Microsoft.

   - **Resultado da autenticação** : um dos seguintes valores:

      - **Aprovado** : o remetente passou por verificações de autenticação de email do remetente (SPF ou DKIM).
      - **Falha** : o remetente falhou EOP verificações de autenticação do remetente.
      - **Desconhecido** : o resultado dessas verificações não é conhecido.

   - **Decisão definida por** : mostra quem determinou se a infraestrutura de envio tem permissão para falsificar o usuário:

       - **Política de inteligência de spoof** (automática)
       - **Administrador** (manual)

   - **Última vista** : a última data em que uma mensagem foi recebida da infraestrutura de envio que contém o usuário falsificado.

   - **Permitido para falsificar?** : os valores que você vê aqui são:

     - **Sim** : as mensagens da combinação de usuário falsificado e infraestrutura de envio são permitidas e não são tratadas como email falsificado.

     - **No** : as mensagens da combinação de usuário falsificado e infraestrutura de envio são marcadas como falsificadas. A ação é controlada pela política anti-phishing padrão ou políticas anti-phishing personalizadas (o valor padrão é **mover mensagem para a pasta lixo eletrônico** ). Consulte a próxima seção para obter mais informações.

     - **Alguns usuários** (apenas **a guia Domínios** ): uma infraestrutura de envio está falsificando vários usuários, onde alguns usuários falsificados são permitidos e outros não. Use a guia **detalhada** para ver os endereços específicos.

6. Na parte inferior da página, clique em **Salvar**.

## <a name="use-powershell-to-manage-spoofed-senders"></a>Usar o PowerShell para gerenciar remetentes falsificados

Para exibir os remetentes permitidos e bloqueados no spoof Intelligence, use a seguinte sintaxe:

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

Este exemplo retorna informações detalhadas sobre todos os remetentes que têm permissão para falsificar usuários em seus domínios.

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).

Para configurar remetentes permitidos e bloqueados no spoof Intelligence, siga estas etapas:

1. Capture a lista atual de remetentes falsificados detectados escrevendo a saída do cmdlet **Get-PhishFilterPolicy** para um arquivo CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. Edite o arquivo CSV para adicionar ou modificar os valores de **SpoofedUser** (endereço de email) e **AllowedToSpoof** (Sim ou não). Salve o arquivo, leia o arquivo e armazene o conteúdo como uma variável chamada `$UpdateSpoofedSenders` :

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. Use a `$UpdateSpoofedSenders` variável para configurar a política de inteligência de falsificação:

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>Usar o centro de conformidade de & de segurança para configurar o spoof Intelligence

As opções de configuração para a inteligência de falsificação são descritas em [configurações de spoof em políticas anti-phishing](set-up-anti-phishing-policies.md#spoof-settings).

Você pode definir as configurações de inteligência de spoofing na política anti-phishing padrão e também em políticas personalizadas. Para obter instruções com base em sua assinatura, consulte um dos seguintes tópicos:

- [Configure as políticas anti-phishing no EOP](configure-anti-phishing-policies-eop.md).

- [Configure as políticas anti-phishing no Microsoft defender para Office 365 no microsoft 365](configure-atp-anti-phishing-policies.md).

## <a name="how-do-you-know-these-procedures-worked"></a>Como saber se esses procedimentos funcionaram?

Para verificar se você configurou a inteligência de spoof com remetentes que são permitidos e não têm permissão para falsificar e se você configurou as configurações de inteligência de spoof, use qualquer uma das seguintes etapas:

- No centro de conformidade e segurança &, vá para política de **Gerenciamento de ameaças** \> **Policy** \> **anti-spam** \> expanda **política de inteligência de falsificação** \> selecionar **Mostrar remetentes que eu já revisei** \> Selecione a guia **domínios** ou **domínios externos** e verifique o valor **permitido para falsificação?** para o remetente.

- No PowerShell, execute os seguintes comandos para exibir os remetentes que são permitidos e não podem ser falsificados:

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- No PowerShell, execute o seguinte comando para exportar a lista de todos os remetentes falsificados para um arquivo CSV:

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- No centro de conformidade & segurança, vá para política de **Gerenciamento de ameaças** anti-phishing \> **Policy** \> **Anti-phishing** ou **anti-phishing de ATP** e execute uma das seguintes etapas:  

  - Selecione uma política na lista. No submenu exibido, verifique os valores na seção **spoof** .
  - Clique em **política padrão**. No submenu exibido, verifique os valores na seção **spoof** .

- No PowerShell do Exchange Online, substitua \<Name\> com o padrão de antiphishing do Office365 ou o nome de uma política personalizada e execute o seguinte comando para verificar as configurações:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>Outras maneiras de gerenciar falsificação e phishing

Fique à medida sobre falsificação e proteção contra phishing. Aqui estão as maneiras relacionadas à verificação de remetentes que falsificam seu domínio e ajudam a evitar que eles danifiquem sua organização:

- Verifique o **relatório de falsificação de emails**. Você pode usar esse relatório com frequência para exibir e ajudar a gerenciar remetentes falsificados. Para saber mais, confira [relatório de detecções de spoof](view-email-security-reports.md#spoof-detections-report).

- Revise a configuração da estrutura de política de remetente (SPF). Para obter uma introdução rápida à SPF e para configurá-la rapidamente, confira [Configurar a SPF no Microsoft 365 para ajudar a evitar falsificação](set-up-spf-in-office-365-to-help-prevent-spoofing.md). Para compreender melhor como o Office 365 usa SPF, para solucionar problemas, ou para saber mais sobre implantações incomuns, como implantações híbridas, comece com [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).

- Revise sua configuração de email identificado do DomainKeys (DKIM). Você deve usar o DKIM além de SPF e DMARC para ajudar a impedir que os invasores enviem mensagens parecidas com o seu domínio. O DKIM possibilita adicionar uma assinatura digital a mensagens de email no cabeçalho da mensagem. Para saber mais, confira [usar DKIM para validar emails de saída enviados do seu domínio personalizado no Office 365](use-dkim-to-validate-outbound-email.md).

- Revise a configuração de autenticação, geração de relatórios e conformidade da mensagem baseada em domínio (DMARC). Implementar o DMARC com SPF e DKIM proporciona proporção adicional contra o spoofing e o phishing no email. O DMARC ajuda os sistemas de recepção de email a determinarem o que fazer com as mensagens enviadas a partir do seu domínio que falharem em verificações de SPF ou de DKIM. Para saber mais, confira [usar DMARC para validar emails no Office 365](use-dmarc-to-validate-email.md).
