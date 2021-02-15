---
title: Definir regras de fluxo de emails para criptografar mensagens de email
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
description: Os administradores podem aprender a criar regras de fluxo de emails (regras de transporte) para criptografar e descriptografar mensagens usando a Criptografia de Mensagens do Office 365.
ms.openlocfilehash: 28486f601a79e294550bbceb48ad57069024fd5a
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408601"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definir regras de fluxo de emails para criptografar mensagens de email

Como administrador global, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para ajudar a proteger mensagens de email enviadas e recebidas. Você pode configurar regras para criptografar qualquer mensagem de email de saída e remover a criptografia de mensagens criptografadas provenientes de dentro da sua organização ou de respostas a mensagens criptografadas enviadas de sua organização. Você pode usar o Centro de administração do Exchange (EAC) ou o PowerShell do Exchange Online para criar essas regras. Além das regras de criptografia gerais, também é possível habilitar ou desabilitar as opções de criptografia de mensagens individuais para os usuários finais.

Não é possível criptografar emails de entrada de senders fora da sua organização.

Se você migrou recentemente do Active Directory RMS para a Proteção de Informações do Azure, precisará revisar suas regras de fluxo de emails existentes para garantir que elas continuem a funcionar em seu novo ambiente. Além disso, se você quiser aproveitar os novos recursos de Criptografia de Mensagem do Office 365 (OME) disponíveis para você por meio da Proteção de Informações do Azure, será necessário atualizar suas regras de fluxo de emails existentes. Caso contrário, os usuários continuarão a receber emails criptografados que usam o formato de anexo HTML anterior em vez da nova experiência OME contínua. Se você ainda não tiver definido o OME, confira Configurar novos recursos de Criptografia de Mensagens do [Office 365](set-up-new-message-encryption-capabilities.md) para obter informações.

Para obter informações sobre os componentes que comem regras de fluxo de emails e como funcionam as regras de fluxo de emails, consulte Regras de fluxo de email (regras de [transporte) no Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) Para obter informações adicionais sobre como as regras de fluxo de emails funcionam com a Proteção de Informações do Azure, consulte Configurando regras de fluxo de emails do Exchange Online para rótulos da Proteção de Informações do [Azure.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-exo-rules)

> [!IMPORTANT]
> Para ambientes híbridos do Exchange, os usuários locais podem enviar e receber emails criptografados usando o OME somente se o email for roteado pelo Exchange Online. Para configurar o OME em um ambiente [](https://docs.microsoft.com/Exchange/exchange-hybrid) híbrido do Exchange, você precisa primeiro configurar a configuração híbrida usando o assistente de Configuração Híbrida e configurar o email para que ele flua do [Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) para seu servidor de email e configurar o email para que ele flua do seu servidor de email para o [Office 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365) Depois de configurar o email para fluir pelo Office 365, você poderá configurar regras de fluxo de emails para o OME usando estas diretrizes.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Criar regras de fluxo de emails para criptografar mensagens de email com os novos recursos do OME

Você pode definir regras de fluxo de emails para acionar a criptografia de mensagens com os novos recursos do OME usando o EAC.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Usar o EAC para criar uma regra para criptografar mensagens de email com os novos recursos do OME

1. Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões de administrador global, entre no [Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. Escolha o **painel** Administrador.

3. No Centro de administração do Microsoft 365, escolha **Centros de administração do** \> **Exchange.**

4. No EAC, vá para Regras **de fluxo** \> **de** emails e selecione **Novo** ícone Criar uma ![ nova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regra.** Para saber mais sobre como usar o EAC, confira o Centro [de administração do Exchange no Exchange Online.](https://docs.microsoft.com/exchange/exchange-admin-center)

5. In **Name**, type a name for the rule, such as Encrypt mail for DrToniRamos@hotmail.com.

6. In **Apply this rule if**, select a condition, and enter a value if necessary. Por exemplo, para criptografar mensagens enviadas a DrToniRamos@hotmail.com:

   1. Em **Aplicar esta regra se**, selecione **o destinatário é**.

   2. Escolha um nome existente na lista de contatos ou digite um novo endereço de email na caixa **verificar nomes**.

      - Para selecionar um nome existente, escolha-o na lista e clique em **OK**.

      - Para inserir um novo nome, digite um endereço de email na caixa de seleção **de** nomes e selecione **verificar nomes** \> **OK**.

7. Para adicionar mais condições, escolha **Mais opções** e, em seguida, escolha **adicionar condição** e selecione na lista.

   Por exemplo, para aplicar a regra somente se o destinatário estiver fora da sua organização, selecione **adicionar** condição e, em seguida, selecione O destinatário é **externo/interno** \> **Fora da organização** \> **OK**.

8. Para habilitar a criptografia usando os novos  recursos do OME, em **Fazer** o seguinte, selecione Modificar a segurança da mensagem e, em seguida, escolha Aplicar a Criptografia de Mensagem do **Office 365** e a proteção de direitos. Selecione um modelo rmS na lista, escolha **Salvar** e, em seguida, escolha **OK**.
  
  A lista de modelos inclui todos os modelos e opções padrão, bem como todos os modelos personalizados que você criou para uso pelo Office 365. Se a lista estiver vazia, verifique se você definiu a Criptografia de Mensagens do Office 365 com os novos recursos, conforme descrito em Configurar novos recursos de Criptografia de Mensagens do [Office 365.](set-up-new-message-encryption-capabilities.md) Para obter informações sobre os modelos padrão, consulte Configurando e gerenciando modelos para a Proteção de [Informações do Azure.](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates) Para obter informações sobre a **opção Não Encaminhar,** consulte [a opção Não Encaminhar para emails.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Para obter informações sobre a **opção somente criptografar,** consulte a opção [Criptografar Somente para emails.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

  Você pode escolher **adicionar ação** se quiser especificar outra ação.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Usar o EAC para atualizar uma regra de fluxo de emails existente para usar os novos recursos do OME

1. Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões de administrador global, entre no [Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. Escolha o **painel** Administrador.

3. No Centro de administração do Microsoft 365, escolha **Centros de administração do** \> **Exchange.**

4. No EAC, vá para **Fluxo de emails** \> **Regras**.

5. Na lista de regras de fluxo de emails, selecione a regra que você deseja modificar para usar os novos recursos do OME e escolha **Editar** ![ ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) ícone.

6. Para habilitar a criptografia usando os novos  recursos do OME, em **Faça** o seguinte, escolha Modificar a segurança da mensagem e, em seguida, aplique a Criptografia de Mensagem do **Office 365** e a proteção de direitos. Selecione um modelo RMS na lista, escolha **Salvar** e, em seguida, escolha **OK**.

   A lista de modelos inclui todos os modelos e opções padrão, bem como todos os modelos personalizados que você criou para uso pelo Office 365. Se a lista estiver vazia, certifique-se de que você tenha definido a Criptografia de Mensagens do Office 365 com os novos recursos, conforme descrito em Configurar novos recursos de Criptografia de Mensagens do [Office 365](set-up-new-message-encryption-capabilities.md)com base na Proteção de Informações do Azure. Para obter informações sobre os modelos padrão, consulte Configurando e gerenciando modelos para a Proteção de [Informações do Azure.](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates) Para obter informações sobre a **opção Não Encaminhar,** consulte [a opção Não Encaminhar para emails.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) Para obter informações sobre a **opção somente criptografar,** consulte a opção [Criptografar Somente para emails.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

   Você pode escolher **adicionar ação** se quiser especificar outra ação.

7. Na lista **Fazer a seguir,** remova todas  as ações atribuídas para Modificar a segurança da mensagem. Aplique a versão anterior \> **do OME.**

8. Escolha **Salvar**.

## <a name="create-mail-flow-rules-to-remove-encryption-for-outgoing-email-messages-with-the-new-ome-capabilities"></a>Criar regras de fluxo de emails para remover a criptografia de mensagens de email de saída com os novos recursos do OME

Você pode definir regras de fluxo de emails para disparar a criptografia de mensagens com os novos recursos do OME usando o EAC.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Usar o EAC para criar uma regra para remover a criptografia de mensagens de email com os novos recursos do OME

1. Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões de administrador global, entre no [Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)

2. Escolha o **painel** Administrador.

3. No Centro de administração do Microsoft 365, escolha **Centros de administração do** \> **Exchange.**

4. No EAC, vá para Regras **de fluxo** \> **de** emails e selecione **Novo** ícone Criar uma ![ nova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regra.** Para saber mais sobre como usar o EAC, confira o Centro [de administração do Exchange no Exchange Online.](https://docs.microsoft.com/exchange/exchange-admin-center)

5. In **Name**, type a name for the rule, such as Remove encryption from outgoing mail.

6. In **Apply this rule if**, select the conditions where encryption should be removed from messages. Add **The sender is located** Inside the \> **organization**. Agora adicione outras condições para direcionar destinatários específicos, como **o destinatário está localizado** fora da \> **organização.**

7. Em **Do the following**, select Modify the message **security** Remove \> **Office 365 Message Encryption and rights protection**.

8. Selecione **Salvar**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Criar regras de fluxo de emails para a Criptografia de Mensagens do Office 365 sem os novos recursos

Se você ainda não moveu sua organização para os novos recursos do OME, a Microsoft recomenda que você faça um plano para mudar para os novos recursos do OME assim que for razoável para sua organização. Para obter instruções, confira Configurar novos recursos de Criptografia de Mensagens do [Office 365, construídos](set-up-new-message-encryption-capabilities.md)com base na Proteção de Informações do Azure. Caso contrário, confira Definindo regras de fluxo de emails para a Criptografia de Mensagens do [Office 365](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities)que não usam os novos recursos do OME.

## <a name="related-topics"></a>Tópicos Relacionados

[Criptografia no Office 365](encryption.md)

[Configurar novos recursos de Criptografia de Mensagens do Office 365](set-up-new-message-encryption-capabilities.md)

[Adicione identidade visual a mensagens criptografadas](add-your-organization-brand-to-encrypted-messages.md)

[Regras de fluxo de emails (regras de transporte) no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=506707)

[Regras de fluxo de emails (regras de transporte) no Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=506708)
