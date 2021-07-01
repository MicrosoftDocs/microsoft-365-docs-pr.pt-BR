---
title: Criar políticas de segurança de dispositivos em Mobilidade Básica e Segurança
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Use o Basic Mobility and Security para criar políticas de dispositivo que protejam as informações da sua organização.
ms.openlocfilehash: 62dc2eef87d413a9cb62a01541126860620eec3f
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228250"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Criar políticas de segurança de dispositivos em Mobilidade Básica e Segurança

Você pode usar o Basic Mobility and Security para criar políticas de dispositivo que ajudam a proteger as informações da sua organização Microsoft 365 acesso não autorizado. Você pode aplicar políticas a qualquer dispositivo móvel em sua organização em que o usuário do dispositivo tenha uma licença de Microsoft 365 aplicável e tenha inscrito o dispositivo em Mobilidade Básica e Segurança.

## <a name="before-you-begin"></a>Antes de começar

> [!IMPORTANT]
> Antes de criar uma política de dispositivo móvel, você deve ativar e configurar o Basic Mobility and Security. Para obter mais informações, consulte Overview of Basic Mobility and Security.

- Saiba mais sobre os dispositivos, aplicativos de dispositivo móvel e configurações de segurança compatíveis com a Mobilidade Básica e Segurança. Consulte [Recursos de Mobilidade Básica e Segurança.](capabilities.md)
- Crie grupos de segurança que incluam Microsoft 365 usuários que você deseja implantar políticas para e para usuários que talvez você queira excluir do acesso bloqueado a Microsoft 365. Recomendamos que antes de implantar uma nova política em sua organização, teste a política implantando-a em um pequeno número de usuários. Você pode criar e usar um grupo de segurança que inclui apenas você ou um pequeno número Microsoft 365 usuários que podem testar a política para você. Para saber mais sobre grupos de segurança, consulte [Create, edit, or delete a security group](../email/create-edit-or-delete-a-security-group.md).
- Para criar e implantar políticas básicas de mobilidade e segurança no Microsoft 365, você precisa ser um administrador Microsoft 365 global. Para obter mais informações, consulte Permissões no Centro de [Conformidade & Segurança.](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md)
- Antes de implantar políticas, deixe sua organização saber os possíveis impactos de registrar um dispositivo em Mobilidade Básica e Segurança. Dependendo de como você configura as políticas, dispositivos não compatíveis podem ser impedidos de acessar Microsoft 365 e dados, incluindo aplicativos instalados, fotos e informações pessoais em um dispositivo inscrito e os dados podem ser excluídos.

> [!NOTE]
> Políticas e regras de acesso criadas no Basic Mobility and Security for Microsoft 365 Business Standard substituem Exchange ActiveSync de caixa de correio de dispositivo móvel e regras de acesso a dispositivos criadas no centro de administração Exchange. Depois que um dispositivo é inscrito no Basic Mobility and Security for Microsoft 365 Business Standard Exchange ActiveSync, qualquer política de caixa de correio de dispositivo móvel ou regra de acesso de dispositivo móvel aplicada ao dispositivo é ignorada. Para saber mais sobre Exchange ActiveSync, [consulte Exchange ActiveSync em Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Etapa 1: criar uma política de dispositivo e implantar em um grupo de teste

Antes de começar, certifique-se de ter ativado e configurar o Basic Mobility and Security. Para obter instruções, consulte [Overview of Basic Mobility and Security](overview.md).

1. No navegador, digite <https://protection.office.com/devicev2> .

2. Selecione **Criar uma política**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações básicas de política de mobilidade e segurança":::

3. Na página **Configurações de Política,** especifique os requisitos que você deseja aplicar a dispositivos móveis em sua organização.

4. **Exigir o gerenciamento do perfil de** email : Quando habilitados, os dispositivos que não têm um perfil de email gerenciado pela Mobilidade Básica e Segurança são considerados não compatíveis. Um dispositivo não pode ter um perfil de email gerenciado quando não é direcionado corretamente ou se o usuário configurar manualmente a conta de email no dispositivo. Quando você o deixa **não habilitado** (padrão), essa configuração não é avaliada para conformidade ou não conformidade. Para obter instruções sobre como os usuários podem ser compatíveis quando essa opção é selecionada, consulte [Uma conta de email existente foi encontrada](/intune-user-help/existing-company-email-account-found).

5. Na página Deseja aplicar essa política **agora?** Escolha os grupos aos quais deseja aplicar essa política.

6. Selecione **Criar essa política**.

A política é empurrada para o dispositivo de cada usuário, a política se aplica à próxima vez que ele entrar Microsoft 365 seu dispositivo móvel. Se os usuários ainda não tiveram uma política aplicada ao dispositivo móvel antes, depois de implantar a política, eles receberão uma notificação em seu dispositivo que inclui as etapas para registrar e ativar a Mobilidade Básica e Segurança. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md). Até que eles concluam o registro no Basic Mobility and Security hospedado pelo Serviço do Intune, o acesso ao email, OneDrive e outros serviços é restrito. Depois de concluir o registro usando o aplicativo Portal da Empresa do Intune, eles podem usar os serviços e a política é aplicada ao dispositivo.

## <a name="step-2-verify-that-your-policy-works"></a>Etapa 2: Verificar se sua política funciona

Depois de criar uma política de dispositivo, verifique se a política funciona conforme o esperado antes de implantá-la em sua organização.

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecione **Exibir a lista de dispositivos gerenciados**.
3. Verifique o status de dispositivos do usuário com a política aplicada. Você deseja que **o estado** dos dispositivos seja **Gerenciado.**
4. Você também pode fazer uma limpeza completa ou seletiva em um dispositivo  clicando em **Redefinição** de fábrica ou **Remover** dados da empresa do botão Gerenciar após selecionar um dispositivo. Para obter instruções, consulte [Wipe a mobile device in Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Etapa 3: Implantar uma política em sua organização

Depois de criar uma política de dispositivo e verificar se ela funciona conforme o esperado, implante-a em sua organização.

1. No seu tipo de navegador: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecione a política que deseja implantar e escolha **Editar** ao lado de **Grupos aplicados.**
3. Procure um grupo para adicionar e clique em **Selecionar**.
4. Selecione **Fechar** e **Alterar configuração.**
5. Selecione **Fechar** e **Editar política.**

A política é empurrada para o dispositivo móvel de cada usuário, a política se aplica à próxima vez que ele entrar Microsoft 365 de seu dispositivo móvel. Se os usuários não tiveram uma política aplicada ao dispositivo móvel, eles receberão uma notificação em seus dispositivos com etapas para registrar e ativá-la para Mobilidade Básica e Segurança. Depois de concluir o registro, a política será aplicada ao dispositivo. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Etapa 4: Bloquear o acesso de email para dispositivos sem suporte

Para ajudar a proteger as informações da sua organização, você deve bloquear o acesso do aplicativo Microsoft 365 email para dispositivos móveis que não são suportados pela Mobilidade Básica e Segurança. Para ver uma lista de dispositivos com suporte, consulte [Dispositivos com suporte](../../admin/basic-mobility-security/capabilities.md).

**Para bloquear o acesso ao aplicativo:**

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecione **Gerenciar configurações de** acesso a dispositivos em toda a organização.
3. Para bloquear dispositivos sem suporte, escolha **Bloquear** em Se um dispositivo não tiver suporte da **Mobilidade** Básica e segurança para Microsoft 365 e selecione **Salvar**.

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Opção de acesso de bloqueio básico de mobilidade e segurança":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Etapa 5: Escolher grupos de segurança a serem excluídos de verificações de acesso condicional

Se quiser excluir algumas pessoas de verificações de acesso condicional em seus dispositivos móveis e você criou um ou mais grupos de segurança para essas pessoas, adicione os grupos de segurança aqui. As pessoas nesses grupos não terão políticas impostas para seus dispositivos móveis com suporte. Essa é a opção recomendada se você não quiser mais usar o Basic Mobility and Security em sua organização.

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecione **Gerenciar configurações de** acesso a dispositivos em toda a organização.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Mobilidade Básica e Segurança criar uma opção de política":::

3. Selecione **Adicionar** para adicionar o grupo de segurança que tem usuários que você deseja excluir de ter acesso bloqueado a Microsoft 365. Quando um usuário é adicionado a essa lista, ele pode acessar Microsoft 365 email quando estiver usando um dispositivo sem suporte.

4. Selecione o grupo de segurança que você deseja usar no **painel Selecionar** grupo.

5. Selecione o nome e, em seguida, **Adicionar**  >  **Salvar**.

6. No painel **Configurações de** acesso a dispositivos em toda a organização, escolha **Salvar**.

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Opção de acesso de acesso de Mobilidade Básica e Segurança":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Qual é o impacto das políticas de segurança em tipos diferentes de dispositivos?

Quando você aplica uma política a dispositivos de usuário, o impacto em cada dispositivo varia um pouco entre os tipos de dispositivo. Consulte a tabela a seguir para obter exemplos do impacto das políticas em dispositivos diferentes.

|**Política de Segurança**|**Android 4 e posterior**|**Samsung KNOX**|**iOS 6 e posterior**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|Exigir backup criptografado|Não|Sim|Sim|O backup criptografado do iOS é necessário.|
|Bloquear cópia de segurança na nuvem|Sim|Sim|Sim|Bloquear backup no Google no Android (esmaecido), backup na nuvem no iOS.|
|Bloquear sincronização de documento|Não|Não|Sim|iOS: Bloquear documentos na nuvem.|
|Bloquear sincronização de fotos |Não|Não|Sim|iOS (nativo): Bloquear fluxo de foto.|
|Bloquear captura de tela |Não|Sim|Sim|Bloqueado quando tentado.|
|Bloquear videoconferência |Não|Não|Sim|FaceTime bloqueado no iOS, não em Skype ou em outros.|
|Bloquear o envio de dados de diagnóstico |Não|Sim|Sim|Bloquear o envio de relatório de falha do Google no Android.|
|Bloquear o acesso à loja de aplicativos |Não|Sim|Sim|Ícone de armazenamento de aplicativo ausente na página inicial do Android, desabilitado no Windows, ausente no iOS.|
|Exigir senha para a loja de aplicativos |Não|Não|Sim|iOS: Senha necessária para compras do iTunes.|
|Bloquear a conexão ao armazenamento removível |Não|Sim|N/D|Android: o cartão SD está acinzado nas configurações, Windows notifica o usuário, os aplicativos instalados não estão disponíveis|
|Bloquear conexão Bluetooth |Consulte anotações|Consulte anotações|Sim|Não podemos desabilitar BlueTooth como uma configuração no Android. Em vez disso, desabilitaremos todas as transações que exigem BlueTooth: Distribuição de Áudio Avançada, Controle Remoto de Áudio/Vídeo, dispositivos mãos-livres, fone de ouvido, Telefone Acesso para Livro e Porta Serial. Uma mensagem em caixa de informações aparece na parte inferior da página quando qualquer um desses dispositivos são usados.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>O que acontece quando você exclui uma política ou remove um usuário da política?

Quando você exclui uma política ou remove um usuário de um grupo para o qual a política foi implantada, as configurações de política, Microsoft 365 perfil de email e emails armazenados em cache podem ser removidas do dispositivo do usuário. Consulte a tabela a seguir para ver o que é removido para os diferentes tipos de dispositivo.

|**O que é removido**|**iOS 6 e posterior**|**Android 4 e posterior (incluindo Samsung KNOX**|
|:-----|:-----|:-----|
|Perfis de email<sup>gerenciados 1</sup>|Sim|Não|
|Bloquear backup em nuvem|Sim|Não|

<sup>1</sup> Se a política foi  implantada com a opção Perfil de email é gerenciado selecionado, o perfil de email gerenciado e emails armazenados em cache nesse perfil são excluídos do dispositivo do usuário.

A política é removida do dispositivo móvel para cada usuário, a política se aplica à próxima vez que o dispositivo faz o logons com a Mobilidade Básica e a Segurança. Se você implantar uma nova política que se aplique a esses dispositivos de usuário, eles serão solicitados a se inscrever no Basic Mobility and Security.

Você também pode apagar um dispositivo completamente ou limpar seletivamente as informações organizacionais do dispositivo. Para obter mais informações, [consulte Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-content"></a>Conteúdo relacionado

[Visão geral da Mobilidade Básica e Segurança](overview.md) (artigo)\
[Recursos de Mobilidade Básica e Segurança](capabilities.md) (artigo)