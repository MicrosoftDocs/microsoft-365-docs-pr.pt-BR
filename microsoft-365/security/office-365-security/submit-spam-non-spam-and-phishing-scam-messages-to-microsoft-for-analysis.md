---
title: Enviar mensagens manualmente para a Microsoft para análise
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Você e seus usuários podem enviar mensagens de spam falsas negativas e falsos positivos para a Microsoft para análise. '
ms.openlocfilehash: 13b2e42f749b54e0c2b71fe095c077992560ea8c
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032799"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Enviar mensagens manualmente para a Microsoft para análise

> [!NOTE]
> Se você for um administrador em uma organização do Office 365 com caixas de correio do Exchange Online, recomendamos que você use o portal de envios no centro de conformidade & segurança do Office 365. Para obter mais informações, consulte [usar o envio do administrador para enviar spam, phishing, URLs e arquivos suspeitos à Microsoft](admin-submission.md).

Pode ser frustrante quando os usuários da sua organização recebem mensagens de lixo eletrônico (spam) ou mensagens de phishing em sua caixa de entrada ou se não recebem uma mensagem de email legítima porque estão marcados como lixo eletrônico. Estamos constantemente ajustando os nossos filtros de spam para serem mais precisos.

Você e seus usuários podem ajudar nesse processo enviando falsos positivos (emails satisfatórios marcados como defeituosos), falsos negativos (email incorreto) e mensagens de phishing para a Microsoft para análise.

> [!NOTE]
> Devido ao alto volume de envios que recebemos, talvez não seja possível atender a todas as solicitações para análise.

## <a name="submit-false-negatives-to-microsoft"></a>Enviar falsos negativos para a Microsoft

> [!TIP]
> Em vez de usar os procedimentos a seguir para relatar falsos negativos, os usuários do Outlook e do Outlook na Web (anteriormente conhecido como Outlook Web App) podem usar o suplemento de mensagem de relatório para o Microsoft Outlook. Para obter informações sobre como instalar e usar essa ferramenta, consulte [habilitar o suplemento de mensagem de relatório](enable-the-report-message-add-in.md).

Se você receber uma mensagem que passa pelo filtro de spam que deve ter sido identificada como spam ou phishing, você pode enviar a mensagem para a análise de spam da Microsoft e para as equipes de análise de phishing da Microsoft, conforme apropriado. Os analistas revisarão a mensagem e a adicionarão aos filtros de todo o serviço se atenderem aos critérios de classificação.

1. Crie uma nova mensagem de email em branco com um dos seguintes destinatários:

   - **Lixo eletrônico**:`junk@office365.microsoft.com`

   - **Phishing**:`phish@office365.microsoft.com`

2. Arraste e solte a mensagem de lixo eletrônico ou phishing na nova mensagem. Isso salvará o lixo eletrônico ou a mensagem de phishing como um anexo na nova mensagem. Não copie e cole o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os cabeçalhos da mensagem).

   > [!NOTE]
   > <ul><li>Você pode anexar várias mensagens na nova mensagem. Certifique-se de que todas as mensagens são do mesmo tipo: mensagens golpes de phishing ou mensagens de lixo eletrônico.</li><li>Deixe o corpo da nova mensagem vazio.<li></li>Use formatos. msg (formato padrão do Outlook) ou. eml (padrão Outlook no formato da Web) para as mensagens anexadas.</li></ul>

3. Quando tiver terminado, clique em **Enviar**.

> [!TIP]
> Os administradores têm várias maneiras diferentes de bloquear mensagens específicas que estão sendo inalgumas identificadas como spam. Para obter detalhes, consulte [criar listas de remetentes bloqueados no Office 365](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Enviar falsos positivos para a Microsoft

> [!TIP]
> Em vez de usar os procedimentos a seguir para relatar falsos positivos, os usuários do Outlook e do Outlook na Web podem usar o suplemento de mensagem de relatório para o Microsoft Outlook. Para obter informações sobre como instalar e usar essa ferramenta, consulte [habilitar o suplemento de mensagem de relatório](enable-the-report-message-add-in.md).

Se uma mensagem foi identificada incorretamente como spam, você pode enviar a mensagem para a equipe de análise de spam da Microsoft. Os analistas avaliarão a mensagem e (dependendo dos resultados da análise) os filtros de todo o serviço podem ser ajustados para permitir a mensagem.

1. Crie uma nova mensagem de email em branco `not_junk@office365.microsoft.com` com o destinatário:

2. Arraste e solte a mensagem inidentificada na nova mensagem. Isso salvará a mensagem inidentificada como um anexo na nova mensagem. Não copie e cole o conteúdo da mensagem ou encaminhe a mensagem (precisamos da mensagem original para que possamos inspecionar os cabeçalhos da mensagem).

   > [!NOTE]
   > <ul><li>Você pode anexar várias mensagens na nova mensagem. Certifique-se de que todas as mensagens são do mesmo tipo: mensagens golpes de phishing ou mensagens de lixo eletrônico.</li><li>Deixe o corpo da nova mensagem vazio.<li></li>Use formatos. msg (formato padrão do Outlook) ou. eml (padrão Outlook no formato da Web) para as mensagens anexadas.</li></ul>

3. Quando tiver terminado, clique em **Enviar**.

> [!TIP]
> Os administradores têm várias maneiras diferentes de permitir que mensagens específicas ignorem a filtragem de spam. Para obter detalhes, consulte [criar listas de remetentes seguros no Office 365](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Criar uma regra de fluxo de email para receber cópias de mensagens relatadas para a Microsoft

Você pode criar uma regra de fluxo de emails (também conhecida como regra de transporte) que procura mensagens de email relatadas à Microsoft usando os métodos descritos neste tópico, e você pode configurar destinatários Cco para receber cópias dessas mensagens relatadas.

Você pode criar a regra de fluxo de emails no centro de administração do Exchange (Eat) e no PowerShell (Exchange Online PowerShell para clientes do Office 365; PowerShell de proteção do Exchange Online para clientes autônomos do EOP).

### <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Você precisa receber permissões no Exchange Online antes de poder executar estes procedimentos. Especificamente, você precisa receber a função de **regras de transporte** , que é atribuída às funções de gerenciamento da **organização**, **Gerenciamento de conformidade**e gerenciamento de **registros** por padrão. Para saber mais, confira [Gerenciar Grupos de Funções do Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Para abrir o Eat no Exchange Online, confira [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para se conectar ao PowerShell da Proteção do Exchange Online autônoma, confira [Conectar ao PowerShell da Proteção do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Para obter mais informações sobre regras de fluxo de emails no Exchange Online e EOP autônomos, consulte os seguintes tópicos:

  - [Regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [Condições e exceções de regra de fluxo de emails (predicados) no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [Ações de regra de fluxo de email no Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Use o Eat para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas

1. No EAC, vá para **Fluxo de emails** \> **Regras**.

2. Clique em **Adicionar** ![ícone](../../media/ITPro-EAC-AddIcon.png) de adição e selecione **criar uma nova regra**.

3. Na página **nova regra** que é aberta, defina as seguintes configurações:

   - **Name**: Insira um nome exclusivo e descritivo para a regra. Por exemplo, as mensagens Cco relatadas para a Microsoft.

   - Clique em **mais opções**.

   - **Aplicar esta regra se**: selecione **o** \> **endereço do destinatário inclui qualquer uma destas palavras**: na caixa de diálogo **especificar palavras ou expressões** que aparece, insira um dos seguintes valores, clique em **Adicionar** ![ícone](../../media/ITPro-EAC-AddIcon.png)de adição e repita até inserir todos os valores.

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     Para editar uma entrada, selecione-a e **Edit** ![clique em Editar](../../media/ITPro-EAC-EditIcon.png)ícone de edição. Para remover uma entrada, selecione-a e **Remove** ![clique em Remover](../../media/ITPro-EAC-DeleteIcon.png)ícone Remover.

     Quando tiver concluído, clique em **OK**.

   - **Faça o seguinte**: selecione **Adicionar destinatários** \> **à caixa Cco**. Na caixa de diálogo exibida, localize e selecione os destinatários que você deseja adicionar. Quando tiver concluído, clique em **OK**.

4. Você pode fazer seleções adicionais para auditar a regra, testar a regra, ativar a regra durante um período de tempo específico e outras configurações. Recomendamos testar a regra antes de aplicá-la.

5. Quando concluir, clique em **Salvar**.

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a>Use o PowerShell para criar uma regra de fluxo de emails para receber cópias de mensagens relatadas

Este exemplo cria uma nova regra de fluxo de emails chamada Cco mensagens relatadas à Microsoft que procura mensagens de email relatadas à Microsoft usando os métodos descritos neste tópico e adiciona os usuários laura@contoso.com e julia@contoso.com como destinatários Cco.

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você configurou uma regra de fluxo de emails para receber cópias de mensagens relatadas, execute uma das seguintes etapas:

- No Eat, vá para **regras** \> de fluxo \> de **emails** selecione \> a regra clique em](../../media/ITPro-EAC-EditIcon.png) **Editar** ![ícone de edição e verifique as configurações.

- No PowerShell, execute o seguinte comando para verificar as configurações:

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- Envie uma mensagem de teste para um dos endereços de email de relatório e verifique os resultados.
