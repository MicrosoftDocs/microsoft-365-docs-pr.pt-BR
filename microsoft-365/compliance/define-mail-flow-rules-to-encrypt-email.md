---
title: Definir regras de fluxo de email para criptografar mensagens de email
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 9b7daf19-d5f2-415b-bc43-a0f5f4a585e8
ms.collection:
- M365-security-compliance
description: Os administradores podem aprender a criar regras de fluxo de emails (regras de transporte) para criptografar e descriptografar mensagens usando a criptografia de mensagem do Office 365.
ms.openlocfilehash: f9e9440c40b68f36d0dcca069dcd0797412af184
ms.sourcegitcommit: f70f75b9dd163c00a3c6bc4b9f9b055e90c50367
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2020
ms.locfileid: "43790700"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definir regras de fluxo de email para criptografar mensagens de email

Como administrador global, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para ajudar a proteger mensagens de email enviadas e recebidas. Você pode configurar regras para criptografar qualquer mensagem de email de saída e remover a criptografia de mensagens criptografadas de dentro da sua organização ou de respostas para mensagens criptografadas enviadas da sua organização. Você pode usar o centro de administração do Exchange (Eat) ou o PowerShell do Exchange Online para criar essas regras. Além das regras de criptografia geral, também é possível habilitar ou desabilitar opções de criptografia de mensagens individuais para usuários finais.

Você não pode criptografar emails de entrada de remetentes fora da sua organização.

Se você migrou recentemente do AD RMS para a proteção de informações do Azure, precisará revisar suas regras de fluxo de emails existentes para garantir que eles continuem funcionando em seu novo ambiente. Além disso, se você quiser aproveitar as vantagens dos novos recursos de criptografia de mensagens do Office 365 (OME) disponíveis por meio da proteção de informações do Azure, precisará atualizar suas regras de fluxo de email existentes. Caso contrário, seus usuários continuarão a receber emails criptografados que usam o formato de anexo HTML anterior em vez da nova experiência de OME sem problemas. Se você ainda não configurou o OME, confira [configurar novos recursos de criptografia de mensagens do Office 365](set-up-new-message-encryption-capabilities.md) para obter informações.

Para obter informações sobre os componentes que compõem as regras de fluxo de emails e como as regras de fluxo de emails funcionam, consulte [regras de fluxo de emails (regras de transporte) no Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). Para obter informações adicionais sobre como as regras de fluxo de emails funcionam com a proteção de informações do Azure, consulte [Configuring Exchange Online Mail Flow Rules for Azure Information Protection Labels](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> Para ambientes híbridos do Exchange, os usuários locais podem enviar mensagens criptografadas usando o OME somente se o email for roteado pelo Exchange Online. Para configurar o OME em um ambiente híbrido do Exchange, primeiro você precisa [Configurar o híbrido usando o assistente de configuração híbrida](https://docs.microsoft.com/Exchange/exchange-hybrid) e, em seguida, [Configurar o email para que ele flua do seu servidor de email para o Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365). Depois de configurar o email para fluir pelo Office 365, você poderá configurar regras de fluxo de email para o OME usando esta orientação.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Criar regras de fluxo de email para criptografar mensagens de email com os novos recursos do OME

Você pode definir regras de fluxo de email para acionar a criptografia de mensagens com os novos recursos do OME usando o Eat.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Use o Eat para criar uma regra para criptografar mensagens de email com os novos recursos do OME

1. Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador global, [entre no Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Escolha o bloco **administrador** .

3. No centro de administração do Microsoft 365, escolha central de **Administração** \> do **Exchange**.

4. No Eat, vá para **regras** de **fluxo** \> de email e selecione **novo** ![novo](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> ícone **criar uma nova regra**. Para obter mais informações sobre como usar o Eat, consulte [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Em **nome**, digite um nome para a regra, como criptografar email para DrToniRamos@hotmail.com.

6. Em **Aplicar esta regra se**, selecione uma condição e digite um valor, se necessário. Por exemplo, para criptografar mensagens enviadas a DrToniRamos@hotmail.com:

   1. Em **Aplicar esta regra se**, selecione **o destinatário é**.

   2. Escolha um nome existente na lista de contatos ou digite um novo endereço de email na caixa **verificar nomes**.

      - Para selecionar um nome existente, escolha-o na lista e clique em **OK**.

      - Para inserir um novo nome, digite um endereço de email na caixa **verificar nomes** e selecione **verificar nomes** \> **OK**.

7. Para adicionar mais condições, escolha **mais opções** e escolha **Adicionar condição** e selecione na lista.

   Por exemplo, para aplicar a regra apenas se o destinatário estiver fora da sua organização, selecione **Adicionar condição** e selecione **o destinatário é externo/interno** \> **fora da organização** \> **OK**.

8. Para habilitar a criptografia usando os novos recursos do OME, em **faça o seguinte**, selecione **Modificar a segurança da mensagem** e, em seguida, escolha **aplicar a criptografia de mensagens e a proteção de direitos do Office 365**. Selecione um modelo do RMS na lista, escolha **salvar**e, em seguida, escolha **OK**.
  
  A lista de modelos inclui todos os modelos e opções padrão, bem como os modelos personalizados que você criou para uso pelo Office 365. Se a lista estiver vazia, verifique se você configurou a criptografia de mensagem do Office 365 com os novos recursos, conforme descrito em [configurar novos recursos de criptografia de mensagens do office 365](set-up-new-message-encryption-capabilities.md). Para obter informações sobre os modelos padrão, consulte [Configurando e Gerenciando modelos para a proteção de informações do Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obter informações sobre a opção não **encaminhar** , confira a [opção não encaminhar para emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obter informações sobre a opção **somente criptografia** , confira a [opção criptografar somente para emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  Você pode escolher **Adicionar ação** se quiser especificar outra ação.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Use o Eat para atualizar uma regra de fluxo de email existente para usar os novos recursos do OME

1. Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador global, [entre no Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Escolha o bloco **administrador** .

3. No centro de administração do Microsoft 365, escolha central de **Administração** \> do **Exchange**.

4. No EAC, vá para **Fluxo de emails** \> **Regras**.

5. Na lista de regras de fluxo de emails, selecione a regra que você deseja modificar para usar os novos recursos do ome **Edit** ![e, em](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)seguida, escolha Editar ícone de edição.

6. Para habilitar a criptografia usando os novos recursos do OME, em **faça o seguinte**, escolha **Modificar a segurança da mensagem** e, em seguida, escolha **aplicar a criptografia de mensagens e a proteção de direitos do Office 365**. Selecione um modelo do RMS na lista, escolha **salvar** e, em seguida, escolha **OK**.

   A lista de modelos inclui todos os modelos e opções padrão, bem como os modelos personalizados que você criou para uso pelo Office 365. Se a lista estiver vazia, verifique se você configurou a criptografia de mensagem do Office 365 com os novos recursos, conforme descrito em [configurar novos recursos de criptografia de mensagens do office 365 criados na parte superior da proteção de informações do Azure](set-up-new-message-encryption-capabilities.md). Para obter informações sobre os modelos padrão, consulte [Configurando e Gerenciando modelos para a proteção de informações do Azure](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates). Para obter informações sobre a opção não **encaminhar** , confira a [opção não encaminhar para emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obter informações sobre a opção **somente criptografia** , confira a [opção criptografar somente para emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Você pode escolher **Adicionar ação** se quiser especificar outra ação.

7. Na lista a **seguir** , remova todas as ações atribuídas para **Modificar a segurança** \> da mensagem **aplique a versão anterior do ome**.

8. Selecione **Salvar**.

## <a name="create-mail-flow-rules-to-remove-encryption-for-outgoing-email-messages-with-the-new-ome-capabilities"></a>Criar regras de fluxo de email para remover a criptografia para mensagens de email de saída com os novos recursos do OME

Você pode definir regras de fluxo de email para o disparo de remover criptografia de mensagem com os novos recursos do OME usando o Eat.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Use o Eat para criar uma regra para remover a criptografia de mensagens de email com os novos recursos do OME

1. Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador global, [entre no Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Escolha o bloco **administrador** .

3. No centro de administração do Microsoft 365, escolha central de **Administração** \> do **Exchange**.

4. No Eat, vá para **regras** de **fluxo** \> de email e selecione **novo** ![novo](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> ícone **criar uma nova regra**. Para obter mais informações sobre como usar o Eat, consulte [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Em **nome**, digite um nome para a regra, como remover a criptografia de emails de saída.

6. Em **aplicar esta regra se** selecionar as condições em que a criptografia deve ser removida das mensagens, adicione **o remetente está localizado** \> **dentro da organização**. Agora, adicione mais condições a destinatários específicos de destino, como **o destinatário está localizado** \> **fora da organização**.

7. Em **faça o seguinte**, selecione **Modificar a segurança** \> da mensagem **remover a criptografia de mensagem do Office 365 e a proteção de direitos**.

8. Selecione **Salvar**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Criar regras de fluxo de email para a criptografia de mensagem do Office 365 sem os novos recursos

Se você ainda não tiver movido sua organização para os novos recursos do OME, use essas tarefas para definir regras de fluxo de emails para criptografar mensagens para sua organização. A Microsoft recomenda que você faça um plano para migrar para os novos recursos do OME assim que for razoável para sua organização. Para obter instruções, consulte [configurar novos recursos de criptografia de mensagem do Office 365 criados com base na proteção de informações do Azure](set-up-new-message-encryption-capabilities.md).

### <a name="use-the-eac-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Use o Eat para criar uma regra de fluxo de emails para criptografar mensagens de email sem os novos recursos do OME

1. Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador global, [entre no Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Escolha o bloco **administrador** .

3. No centro de administração do Microsoft 365, escolha central de **Administração** \> do **Exchange**.

4. No Eat, vá para **regras** de **fluxo** \> de email e selecione **novo** ![novo](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> ícone **criar uma nova regra**. Para obter mais informações sobre como usar o Eat, consulte [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Em **nome**, digite um nome para a regra, como criptografar email para DrToniRamos@hotmail.com.

6. Em **Aplicar esta regra se**, selecione uma condição e digite um valor, se necessário. Por exemplo, para criptografar mensagens enviadas a DrToniRamos@hotmail.com:

   1. Em **Aplicar esta regra se**, selecione **o destinatário é**.

   2. Escolha um nome existente na lista de contatos ou digite um novo endereço de email na caixa **verificar nomes**.

      - Para selecionar um nome existente, escolha-o na lista e clique em **OK**.

      - Para inserir um novo nome, digite um endereço de email na caixa **verificar nomes** e selecione **verificar nomes** \> **OK**.

7. Para adicionar mais condições, escolha **mais opções** e selecione **Adicionar condição** e selecione na lista.

   Por exemplo, para aplicar a regra apenas se o destinatário estiver fora da sua organização, selecione **Adicionar condição** e selecione **o destinatário é externo/interno** \> **fora da organização** \> **OK**.

8. Para habilitar a criptografia sem usar os novos recursos do ome, em **faça o seguinte**, selecione **Modificar a segurança** \> da mensagem **aplique a versão anterior do ome**e, em seguida, escolha **salvar**.

  Se você receber um erro informando que o licenciamento do IRM não está habilitado, então você ainda não configurou o OME para sua organização. Se quiser configurar o OME agora, você deve configurá-lo para usar os novos recursos do OME. Para saber mais, confira [configurar novos recursos de criptografia de mensagem do Office 365 criados na parte superior da proteção de informações do Azure](set-up-new-message-encryption-capabilities.md). A Microsoft não oferece mais suporte para a configuração de novas implantações do OME sem os novos recursos.

  Você pode escolher **Adicionar ação** se quiser especificar outra ação.

### <a name="use-exchange-online-powershell-to-create-a-mail-flow-rule-for-encrypting-email-messages-without-the-new-ome-capabilities"></a>Usar o PowerShell do Exchange Online para criar uma regra de fluxo de emails para criptografar mensagens de email sem os novos recursos do OME

1. Conecte-se ao PowerShell do Exchange Online. Para saber mais, confira [Conectar-se ao Exchange Online usando o PowerShell Remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Crie uma regra usando o cmdlet **New-TransportRule** e defina o parâmetro _ApplyOME_ para `$true`.

   Este exemplo requer que todas as mensagens de email enviadas para DrToniRamos@hotmail.com devem ser criptografadas.

   ```powershell
   New-TransportRule -Name "Encrypt rule for Dr Toni Ramos" -SentTo "DrToniRamos@hotmail.com" -SentToScope "NotinOrganization" -ApplyOME $true
   ```

   **Observações**:

   - O nome exclusivo da nova regra é "criptografar regra para Dr Toni ramos".

   - O parâmetro _SentTo_ especifica os destinatários da mensagem (identificados por nome, endereço de email, nome diferenciado, etc.). Neste exemplo, o destinatário é identificado pelo endereço de email "DrToniRamos@hotmail.com".

   - O parâmetro _SentToScope_ especifica a localização dos destinatários da mensagem. Neste exemplo, a caixa de correio do destinatário está no hotmail e não faz parte da organização, portanto, o `NotInOrganization` valor é usado.

   Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).

### <a name="remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Remover a criptografia de respostas de email criptografadas sem os novos recursos do OME

Quando os usuários de email enviam mensagens criptografadas, os destinatários dessas mensagens podem responder com respostas criptografadas. Você pode criar regras de fluxo de email para remover automaticamente a criptografia das respostas para que os usuários de email em sua organização não precisem entrar no portal de criptografia para exibi-las. Você pode usar os cmdlets Eat ou Windows PowerShell para definir essas regras. Se você ainda não estiver usando os novos recursos do OME, só poderá descriptografar as mensagens que são enviadas de dentro da sua organização ou mensagens que são respostas às mensagens enviadas de dentro da sua organização. Você não pode descriptografar mensagens criptografadas de fora da sua organização.

#### <a name="use-the-eac-to-create-a-rule-for-removing-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Use o Eat para criar uma regra para remover a criptografia de respostas de email criptografadas sem os novos recursos do OME

1. Em um navegador da Web, usando uma conta corporativa ou de estudante que recebeu permissões de administrador, [entre no Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).

2. Escolha o bloco **administrador** .

3. No centro de administração do Microsoft 365, escolha central de **Administração** \> do **Exchange**.

4. No Eat, vá para **regras** de **fluxo** \> de email e selecione **novo** ![novo](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> ícone **criar uma nova regra**. Para obter mais informações sobre como usar o Eat, consulte [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).

5. Em **nome**, digite um nome para a regra, como remover criptografia de emails de entrada.

6. Em **aplicar esta regra, se** selecionar as condições em que a criptografia deve ser removida das mensagens, como **o destinatário está localizado** \> **dentro da organização**.

7. Em **faça o seguinte**, selecione **Modificar a segurança** \> da mensagem **remover a versão anterior do ome**.

8. Selecione **Salvar**.

#### <a name="use-exchange-online-powershell-to-create-a-rule-to-remove-encryption-from-email-replies-encrypted-without-the-new-ome-capabilities"></a>Usar o PowerShell do Exchange Online para criar uma regra para remover a criptografia de respostas de email criptografadas sem os novos recursos do OME

1. Conecte-se ao PowerShell do Exchange Online. Para saber mais, confira [Conectar-se ao Exchange Online usando o PowerShell Remoto](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

2. Crie uma regra usando o cmdlet **New-TransportRule** e defina o parâmetro _RemoveOME_ para `$true`.

   Este exemplo remove a criptografia de todos os emails enviados para destinatários na organização.

   ```powershell
   New-TransportRule -Name "Remove encryption from incoming mail" -SentToScope "InOrganization" -RemoveOME $true
   ```

   **Observações**:

   - O nome exclusivo da nova regra é "remover a criptografia de emails de entrada".

   - O parâmetro _SentToScope_ especifica a localização dos destinatários da mensagem. Neste exemplo, o `InOrganization` valor Value é usado, o que indica:

     - O destinatário é uma caixa de correio, usuário de email, grupo ou pasta pública habilitada para email em sua organização.

       ou

     - O endereço de email do destinatário está em um domínio aceito configurado como um domínio autoritativo ou um domínio de retransmissão interno em sua organização, _e_ a mensagem foi enviada ou recebida através de uma conexão autenticada.

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/New-TransportRule).

## <a name="related-topics"></a>Tópicos Relacionados

[Criptografia no Office 365](encryption.md)

[Configurar novos recursos de Criptografia de Mensagens do Office 365](set-up-new-message-encryption-capabilities.md)

[Adicione identidade visual a mensagens criptografadas](add-your-organization-brand-to-encrypted-messages.md)

[Regras de fluxo de emails (regras de transporte) no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Regras de fluxo de emails (regras de transporte) no Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=506708)
