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
description: Use a Mobilidade Básica e Segurança para criar políticas de dispositivo que protejam as informações da sua organização.
ms.openlocfilehash: 077f1e7e0d763aaecfc38fd4b57d9e8912900a3c
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877063"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Criar políticas de segurança de dispositivos em Mobilidade Básica e Segurança

Você pode usar Mobilidade Básica e Segurança para criar políticas de dispositivo que ajudam a proteger as informações da sua organização no Microsoft 365 contra acesso não autorizado. Você pode aplicar políticas a qualquer dispositivo móvel em sua organização onde o usuário do dispositivo tem uma licença aplicável do Microsoft 365 e registrou o dispositivo na Mobilidade Básica e Segurança.

## <a name="before-you-begin"></a>Antes de começar

> [!IMPORTANT]
> Antes de criar uma política de dispositivo móvel, você deve ativar e configurar o Basic Mobility and Security. Para obter mais informações, consulte Visão geral de Mobilidade Básica e Segurança.

- Saiba mais sobre os dispositivos, aplicativos de dispositivo móvel e configurações de segurança compatíveis com a Mobilidade Básica e Segurança. Consulte [Recursos de Mobilidade Básica e Segurança.](capabilities.md)
- Crie grupos de segurança que incluam usuários do Microsoft 365 para os que você deseja implantar políticas para e para usuários que talvez você queira excluir do bloqueio de acesso ao Microsoft 365. Recomendamos que antes de implantar uma nova política em sua organização, teste a política implantando-a em um pequeno número de usuários. Você pode criar e usar um grupo de segurança que inclua apenas você mesmo ou um pequeno número de usuários do Microsoft 365 que podem testar a política para você. Para saber mais sobre grupos de segurança, [consulte Criar, editar ou excluir um grupo de segurança.](https://go.microsoft.com/fwlink/p/?LinkId=518555)
- Para criar e implantar políticas básicas de mobilidade e segurança no Microsoft 365, você precisa ser um administrador global do Microsoft 365. Para obter mais informações, [consulte Permissões no Centro de Conformidade e & Segurança.](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1)
- Antes de implantar políticas, deixe sua organização saber os possíveis impactos do registro de um dispositivo no Basic Mobility and Security. Dependendo de como você configurar as políticas, os dispositivos não compatíveis podem ser impedidos de acessar o Microsoft 365 e os dados, incluindo aplicativos instalados, fotos e informações pessoais em um dispositivo inscrito, e os dados podem ser excluídos.

>[!NOTE]
>Políticas e regras de acesso criadas no Basic Mobility and Security para o Microsoft 365 Business Standard substituem as políticas de caixa de correio de dispositivo móvel do Exchange ActiveSync e as regras de acesso a dispositivo criadas no Centro de administração do Exchange. Depois que um dispositivo é inscrito no Basic Mobility and Security para o Microsoft 365 Business Standard, qualquer política de caixa de correio de dispositivo móvel do Exchange ActiveSync ou regra de acesso ao dispositivo aplicada ao dispositivo é ignorada. Para saber mais sobre o Exchange ActiveSync, consulte [Exchange ActiveSync no Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Etapa 1: Criar uma política de dispositivo e implantar em um grupo de teste

Antes de começar, certifique-se de ter ativado e definido a Mobilidade Básica e Segurança. Para obter instruções, [consulte Visão geral do Basic Mobility and Security](overview.md).

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecione **Criar uma política.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações de política básica de mobilidade e segurança":::

3. Na página **Configurações de política,** especifique os requisitos que você deseja aplicar aos dispositivos móveis em sua organização.

4. **Exigir o gerenciamento de perfil de email:** quando habilitado, os dispositivos que não têm um perfil de email gerenciado pela Mobilidade Básica e Segurança são considerados não compatíveis. Um dispositivo não pode ter um perfil de email gerenciado quando não é direcionado corretamente ou se o usuário configurar manualmente a conta de email no dispositivo. Quando você o deixa **não habilitado** (padrão), essa configuração não é avaliada por conformidade ou não conformidade. Para obter instruções sobre como os usuários podem ficar em conformidade quando essa opção é selecionada, consulte Uma conta de email existente [foi encontrada.](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)

5. Na página **Deseja aplicar essa política agora?** Escolha os grupos aos quais deseja aplicar essa política.

6. Selecione **Criar esta política.**

A política é aplicada ao dispositivo de cada usuário na próxima vez que ele entrar no Microsoft 365 usando seu dispositivo móvel. Se os usuários ainda não tiveram uma política aplicada ao dispositivo móvel antes, depois de implantar a política, eles receberão uma notificação em seus dispositivos que inclui as etapas para registrar e ativar a Mobilidade Básica e Segurança. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança.](enroll-your-mobile-device.md) Até que eles concluam o registro no Basic Mobility and Security hospedado pelo Serviço do Intune, o acesso ao email, OneDrive e outros serviços é restrito. Depois de concluir o registro usando o aplicativo Portal da Empresa do Intune, eles poderão usar os serviços e a política será aplicada ao dispositivo.

## <a name="step-2-verify-that-your-policy-works"></a>Etapa 2: Verificar se sua política funciona

Depois de criar uma política de dispositivo, verifique se a política funciona como esperado antes de implantá-la em sua organização.

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecione **Exibir a lista de dispositivos gerenciados.**
3. Verifique o status de dispositivos do usuário com a política aplicada. Você deseja que **o Estado** dos dispositivos seja **Gerenciado.**
4. Você também pode fazer uma limpeza completa ou seletiva em  um dispositivo  clicando em Redefinir fábrica ou remover dados da empresa do botão Gerenciar após selecionar um dispositivo.  Para obter instruções, confira [Apagar um dispositivo móvel no Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Etapa 3: Implantar uma política em sua organização

Depois de criar uma política de dispositivo e verificar se ela funciona conforme o esperado, implante-a em sua organização.

1. No seu tipo de navegador: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecione a política que você deseja implantar e escolha **Editar** ao lado de **Grupos aplicados.**
3. Procure um grupo para adicionar e clique em **Selecionar**.
4. Selecione **a configuração** **Fechar e Alterar.**
5. Selecione **Fechar** e **Editar política.**

A política é aplicada ao dispositivo móvel de cada usuário na próxima vez em que ele entrar no Microsoft 365 a partir de seu dispositivo móvel. Se os usuários ainda não tiveram uma política aplicada ao dispositivo móvel, eles receberão uma notificação em seus dispositivos com etapas para se inscrever e ativá-la para Mobilidade e Segurança Básica. Depois que eles concluíram o registro, a política é aplicada ao dispositivo. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança.](enroll-your-mobile-device.md)

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Etapa 4: Bloquear o acesso ao email para dispositivos sem suporte

Para ajudar a proteger as informações da sua organização, você deve bloquear o acesso do aplicativo ao email do Microsoft 365 para dispositivos móveis que não têm suporte do Basic Mobility and Security. Para uma lista de dispositivos com suporte, consulte [Dispositivos com suporte.](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices)

**Para bloquear o acesso ao aplicativo:**

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecione **Gerenciar configurações de acesso a dispositivos em toda a organização.**
3. Para bloquear dispositivos sem  suporte, escolha Bloquear em Se um dispositivo não tiver suporte do Basic Mobility and Security para **o Microsoft 365** e, em seguida, **selecione Salvar.**

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Opção de acesso básico de bloqueio de mobilidade e segurança":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Etapa 5: Escolher grupos de segurança a serem excluídos de verificações de acesso condicional

Se quiser excluir algumas pessoas de verificações de acesso condicional em seus dispositivos móveis e você criou um ou mais grupos de segurança para essas pessoas, adicione os grupos de segurança aqui. As pessoas nesses grupos não terão nenhuma política imposta para seus dispositivos móveis com suporte. Essa é a opção recomendada se você não quiser mais usar a Mobilidade Básica e Segurança em sua organização.

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecione **Gerenciar configurações de acesso a dispositivos em toda a organização.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Mobilidade Básica e Segurança criam uma opção de política":::

3. Selecione **Adicionar** para adicionar o grupo de segurança que tem usuários que você deseja excluir de ter acesso bloqueado ao Microsoft 365. Quando um usuário é adicionado a essa lista, ele pode acessar o email do Microsoft 365 quando estiver usando um dispositivo sem suporte.

4. Selecione o grupo de segurança que você deseja usar no **painel Selecionar** grupo.

5. Selecione o nome e, em **seguida, Adicione**  >  **Salvar.**

6. No painel **de configurações de acesso a dispositivos** em toda a organização, escolha **Salvar**.

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Mobilidade Básica e Segurança permitem a opção de acesso":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Qual é o impacto das políticas de segurança em tipos diferentes de dispositivos?

Quando você aplica uma política a dispositivos do usuário, o impacto em cada dispositivo varia um pouco entre os tipos de dispositivo. Consulte a tabela a seguir para obter exemplos do impacto das políticas em dispositivos diferentes.

|**Política de Segurança**|**Android 4 e posterior**|**Samsung KNOX**|**iOS 6 e posterior**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|Exigir backup criptografado|Não|Sim|Sim|Backup criptografado do iOS necessário.|
|Bloquear cópia de segurança na nuvem|Sim|Sim|Sim|Bloquear backup no Google no Android (esmaecido), backup na nuvem no iOS.|
|Bloquear sincronização de documento|Não|Não|Sim|iOS: Bloquear documentos na nuvem.|
|Bloquear sincronização de fotos |Não|Não|Sim|iOS (nativo): Bloquear fluxo de foto.|
|Bloquear captura de tela |Não|Sim|Sim|Bloqueado quando tentado.|
|Bloquear videoconferência |Não|Não|Sim|FaceTime bloqueado no iOS, não no Skype ou em outros.|
|Bloquear o envio de dados de diagnóstico |Não|Sim|Sim|Bloquear o envio de relatório de falha do Google no Android.|
|Bloquear o acesso à loja de aplicativos |Não|Sim|Sim|Ícone de armazenamento de aplicativo ausente na página inicial do Android, desabilitado no Windows, ausente no iOS.|
|Exigir senha para a loja de aplicativos |Não|Não|Sim|iOS: Senha necessária para compras do iTunes.|
|Bloquear a conexão ao armazenamento removível |Não|Sim|N/D|Android: o cartão SD está es cinza nas configurações, o Windows notifica o usuário, os aplicativos instalados não estão disponíveis|
|Bloquear conexão Bluetooth |Consulte observações|Consulte observações|Sim|Não é possível desabilitar BlueTooth como uma configuração no Android. Em vez disso, desabilitaremos todas as transações que exigem BlueTooth: Distribuição avançada de áudio, controle remoto de áudio/vídeo, dispositivos sem mãos, fone de ouvido, acesso à agenda telefônica e porta serial. Uma mensagem em caixa de informações aparece na parte inferior da página quando qualquer um desses dispositivos são usados.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>O que acontece quando você exclui uma política ou remove um usuário da política?

Quando você exclui uma política ou remove um usuário de um grupo no qual a política foi implantada, as configurações de política, o perfil de email do Microsoft 365 e os emails armazenados em cache podem ser removidos do dispositivo do usuário. Consulte a tabela a seguir para ver o que é removido para os diferentes tipos de dispositivo.

|**O que é removido**|**iOS 6 e posterior**|**Android 4 e posterior (incluindo Samsung KNOX**|
|:-----|:-----|:-----|
|Perfis de email<sup>gerenciados 1</sup>|Sim|Não|
|Bloquear backup em nuvem|Sim|Não|

<sup>1</sup> Se a política foi implantada com a opção **Perfil** de email é gerenciado selecionado, o perfil de email gerenciado e os emails armazenados em cache nesse perfil são excluídos do dispositivo do usuário.

A política é removida do dispositivo móvel para cada usuário, a política se aplica à próxima vez que o dispositivo faz o logons com Mobilidade Básica e Segurança. Se você implantar uma nova política que se aplique a esses dispositivos de usuário, eles serão solicitados a se inscreverem no Basic Mobility and Security.

Você também pode apagar um dispositivo completamente ou limpar seletivamente as informações organizacionais do dispositivo. Para obter mais informações, [consulte Apagar um dispositivo móvel em Mobilidade Básica e Segurança.](wipe-mobile-device.md)

## <a name="related-topics"></a>Tópicos relacionados

[Visão geral da Mobilidade e Segurança Básicas](overview.md)

[Capacidades de Mobilidade e Segurança Básica](capabilities.md)
