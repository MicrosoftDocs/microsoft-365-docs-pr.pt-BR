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
description: Os administradores podem aprender a criar regras de fluxo de emails (regras de transporte) para criptografar e descriptografar mensagens usando Criptografia de Mensagens do Office 365.
ms.openlocfilehash: 4dfa019de99a65df7696c1ca58d777bf8a506c37
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623864"
---
# <a name="define-mail-flow-rules-to-encrypt-email-messages"></a>Definir regras de fluxo de emails para criptografar mensagens de email

Como administrador que gerencia o Exchange Online, você pode criar regras de fluxo de emails (também conhecidas como regras de transporte) para ajudar a proteger mensagens de email enviadas e recebidas. Você pode configurar regras para criptografar qualquer mensagem de email de saída e remover a criptografia de mensagens criptografadas provenientes de dentro da sua organização ou de respostas a mensagens criptografadas enviadas de sua organização. Você pode usar o Exchange de administração (EAC) ou Exchange Online PowerShell para criar essas regras. Além das regras de criptografia gerais, também é possível habilitar ou desabilitar as opções de criptografia de mensagens individuais para os usuários finais.

Não é possível criptografar emails de entrada de envios fora da sua organização.

Se você migrou recentemente do RmS do Active Directory para a Proteção de Informações do Azure, precisará revisar as regras de fluxo de emails existentes para garantir que elas continuem a funcionar em seu novo ambiente. Além disso, se você quiser aproveitar os novos recursos de Criptografia de Mensagens do Office 365 (OME) disponíveis para você por meio da Proteção de Informações do Azure, você precisa atualizar suas regras de fluxo de emails existentes. Caso contrário, seus usuários continuarão a receber emails criptografados que usam o formato de anexo HTML anterior em vez da nova experiência OME contínua. Se você ainda não tiver definido o OME, consulte [Configurar novos](set-up-new-message-encryption-capabilities.md) recursos Criptografia de Mensagens do Office 365 para obter informações.

Para obter informações sobre os componentes que comem regras de fluxo de emails e como funcionam as regras de fluxo de emails, consulte Regras de fluxo de email (regras de [transporte) em Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules). Para obter informações adicionais sobre como as regras de fluxo de emails funcionam com a Proteção de Informações do Azure, consulte [Configuring Exchange Online mail flow rules for Azure Information Protection labels](/azure/information-protection/deploy-use/configure-exo-rules).

> [!IMPORTANT]
> Para ambientes Exchange híbridos, os usuários locais podem enviar e receber emails criptografados usando o OME somente se o email for roteado por meio de Exchange Online. Para configurar o OME em um ambiente de [](/Exchange/exchange-hybrid) Exchange híbrido, você precisa primeiro configurar o híbrido usando o assistente de Configuração Híbrida e, em seguida, configurar o email para fluir do Office 365 para o seu servidor de [email](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-1-configure-mail-to-flow-from-office-365-to-your-on-premises-email-server) e configurar o email para fluir do seu servidor de [email](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)para Office 365 . Depois de configurar o email para fluir Office 365, você poderá configurar regras de fluxo de emails para OME usando essas diretrizes.

## <a name="create-mail-flow-rules-to-encrypt-email-messages-with-the-new-ome-capabilities"></a>Criar regras de fluxo de emails para criptografar mensagens de email com os novos recursos OME

Você pode definir regras de fluxo de emails para disparar a criptografia de mensagens com os novos recursos OME usando o EAC.

### <a name="use-the-eac-to-create-a-rule-for-encrypting-email-messages-with-the-new-ome-capabilities"></a>Use o EAC para criar uma regra para criptografar mensagens de email com os novos recursos OME

1. Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões de administrador global, entre [no](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365 .

2. Escolha o **painel** Administrador.

3. No centro Microsoft 365 de administração, escolha **Centros de administração** \> **Exchange**.

4. No EAC, vá para **Regras de fluxo de email** e selecione \>  **Novo** ícone Criar ![ uma nova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regra.** Para obter mais informações sobre como usar o EAC, [consulte Exchange centro de administração em Exchange Online](/exchange/exchange-admin-center).

5. Em **Nome**, digite um nome para a regra, como Criptografar email para DrToniRamos@hotmail.com.

6. Em **Aplicar essa regra se**, selecione uma condição e insira um valor, se necessário. Por exemplo, para criptografar mensagens enviadas a DrToniRamos@hotmail.com:

   1. Em **Aplicar esta regra se**, selecione **o destinatário é**.

   2. Escolha um nome existente na lista de contatos ou digite um novo endereço de email na caixa **verificar nomes**.

      - Para selecionar um nome existente, escolha-o na lista e clique em **OK**.

      - Para inserir um novo nome, digite um endereço de email na **caixa** de nomes de seleção e selecione nomes **de verificação** \> **OK**.

7. Para adicionar mais condições, escolha **Mais opções** e escolha **adicionar condição** e selecione na lista.

   Por exemplo, para aplicar a regra somente se o destinatário estiver fora da sua organização, selecione **adicionar** condição e selecione O destinatário é **externo/interno** Fora \> **da organização** \> **OK**.

8. Para habilitar a criptografia usando os novos  recursos OME, em **Fazer** o seguinte, selecione Modificar a segurança da mensagem e escolha Aplicar Criptografia de Mensagens do Office 365 **proteção de direitos.** Selecione um modelo RMS na lista, escolha **Salvar** e, em seguida, escolha **OK**.
  
  A lista de modelos inclui todos os modelos e opções padrão, bem como todos os modelos personalizados que você criou para uso por Office 365. Se a lista estiver vazia, verifique se você Criptografia de Mensagens do Office 365 com os novos recursos, conforme descrito em Configurar novos recursos [Criptografia de Mensagens do Office 365.](set-up-new-message-encryption-capabilities.md) Para obter informações sobre os modelos padrão, consulte [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Para obter informações sobre a **opção Não Encaminhar,** consulte [a opção Não Encaminhar para emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obter informações sobre **a opção somente** criptografar, consulte [Encrypt-only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

  Você pode escolher **adicionar ação** se quiser especificar outra ação.

### <a name="use-the-eac-to-update-an-existing-mail-flow-rule-to-use-the-new-ome-capabilities"></a>Use o EAC para atualizar uma regra de fluxo de emails existente para usar os novos recursos OME

1. Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões de administrador global, entre [no](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365 .

2. Escolha o **painel** Administrador.

3. No centro Microsoft 365 de administração, escolha **Centros de administração** \> **Exchange**.

4. No EAC, vá para **Fluxo de emails** \> **Regras**.

5. Na lista de regras de fluxo de emails, selecione a regra que você deseja modificar para usar os novos recursos OME e escolha **Editar** ![ ícone editar ](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) .

6. Para habilitar a criptografia usando os novos  recursos OME, em **Fazer** o seguinte, escolha Modificar a segurança da mensagem e escolha Aplicar Criptografia de Mensagens do Office 365 **proteção de direitos.** Selecione um modelo RMS na lista, escolha **Salvar** e escolha **OK**.

   A lista de modelos inclui todos os modelos e opções padrão, bem como todos os modelos personalizados que você criou para uso por Office 365. Se a lista estiver vazia, certifique-se de que você tenha Criptografia de Mensagens do Office 365 com os novos recursos, conforme descrito em Configurar novos recursos Criptografia de Mensagens do Office 365 criadas em cima da Proteção de Informações do [Azure.](set-up-new-message-encryption-capabilities.md) Para obter informações sobre os modelos padrão, consulte [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates). Para obter informações sobre a opção Não Encaminhar, consulte [a opção Não Encaminhar para emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails). Para obter informações sobre a opção somente criptografar, consulte [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

   Você pode escolher **adicionar ação** se quiser especificar outra ação.

7. Na lista **Fazer a seguir,** remova todas as ações atribuídas a **Modificar** a segurança da mensagem Aplique a versão anterior \> **do OME**.

8. Escolha **Salvar**.

## <a name="create-mail-flow-rules-to-remove-encryption-for-email-messages-with-the-new-ome-capabilities"></a>Criar regras de fluxo de emails para remover a criptografia para mensagens de email com os novos recursos OME

Você pode definir regras de fluxo de emails para disparar a criptografia de mensagens com os novos recursos OME usando o EAC.

### <a name="use-the-eac-to-create-a-rule-to-remove-encryption-from-email-messages-with-the-new-ome-capabilities"></a>Use o EAC para criar uma regra para remover a criptografia de mensagens de email com os novos recursos OME

Você pode remover a criptografia acessível pela sua organização. Isso significa que qualquer email com criptografia aplicado pela organização ou qualquer email protegido com restrições somente criptografia.

1. Em um navegador da Web, usando uma conta de trabalho ou de estudante que recebeu permissões de administrador global, entre [no](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)Office 365 .

2. Escolha o **painel** Administrador.

3. No centro Microsoft 365 de administração, escolha **Centros de administração** \> **Exchange**.

4. No EAC, vá para **Regras de fluxo de email** e selecione \>  **Novo** ícone Criar ![ uma nova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regra.** Para obter mais informações sobre como usar o EAC, [consulte Exchange centro de administração em Exchange Online](/exchange/exchange-admin-center).

5. Em **Nome**, digite um nome para a regra, como Remover criptografia de emails de saída.

6. In **Apply this rule if**, select the conditions where encryption should be removed from messages. Adicionar **O remetente está localizado** Dentro da organização \> **ou**  O destinatário **está localizado** Dentro da \> **organização**.

7. Em **Fazer o seguinte**, selecione Modificar a segurança **da** mensagem Remover Criptografia de Mensagens do Office 365 e proteção \> **de direitos.**

8. Selecione **Salvar**.

## <a name="create-mail-flow-rules-for-office-365-message-encryption-without-the-new-capabilities"></a>Criar regras de fluxo de emails para Criptografia de Mensagens do Office 365 sem os novos recursos

Se você ainda não tiver movido sua organização para os novos recursos OME, a Microsoft recomenda que você faça um plano para mover para os novos recursos OME assim que for razoável para sua organização. Para obter instruções, [consulte Set up new Criptografia de Mensagens do Office 365 capabilities built on on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). Caso contrário, [consulte Defining mail flow rules for Criptografia de Mensagens do Office 365 that don't use the new OME capabilities](legacy-information-for-message-encryption.md#defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities).

## <a name="related-topics"></a>Tópicos Relacionados

[Criptografia no Office 365](encryption.md)

[Configurar novos recursos de Criptografia de Mensagens do Office 365](set-up-new-message-encryption-capabilities.md)

[Adicione identidade visual a mensagens criptografadas](add-your-organization-brand-to-encrypted-messages.md)

[Regras de fluxo de emails (regras de transporte) no Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
