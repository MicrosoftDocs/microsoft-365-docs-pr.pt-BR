---
title: Criar políticas de segurança de dispositivo na mobilidade básica e segurança
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
description: Use mobilidade básica e segurança para criar políticas de dispositivos que protegem as informações da sua organização.
ms.openlocfilehash: 7bbc4a128505ce6e569db4b4d7d98e132c503965
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336722"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Criar políticas de segurança de dispositivo na mobilidade básica e segurança 

Você pode usar mobilidade básica e segurança para criar políticas de dispositivos que ajudam a proteger as informações da sua organização no Microsoft 365 contra o acesso não autorizado. Você pode aplicar políticas a qualquer dispositivo móvel em sua organização, onde o usuário do dispositivo tem uma licença do Microsoft 365 aplicável e registrou o dispositivo em mobilidade básica e segurança.

## <a name="before-you-begin"></a>Antes de começar

>[!IMPORTANT]
>Antes de poder criar uma política de dispositivo móvel, você deve ativar e configurar a mobilidade e a segurança básica. Para obter mais informações, consulte Visão geral da mobilidade básica e segurança.

- Saiba mais sobre os dispositivos, os aplicativos de dispositivos móveis e as configurações de segurança com suporte a mobilidade básica e segurança. Consulte [recursos de mobilidade e segurança básicos](capabilities-of-basic-mobility-and-secruity.md).
- Crie grupos de segurança que incluam os usuários do Microsoft 365 para os quais você deseja implantar políticas no e para os usuários que você deseja excluir do acesso bloqueado ao Microsoft 365. Recomendamos que antes de implantar uma nova política em sua organização, teste a política implantando-a em um pequeno número de usuários. Você pode criar e usar um grupo de segurança que inclua apenas você ou um pequeno número de usuários do Microsoft 365 que possam testar a política para você. Para saber mais sobre grupos de segurança, confira [criar, editar ou excluir um grupo de segurança](https://go.microsoft.com/fwlink/p/?LinkId=518555).
- Para criar e implantar políticas básicas de mobilidade e segurança no Microsoft 365, você precisa ser um administrador global do Microsoft 365. Para obter mais informações, consulte [permissões no centro de conformidade de & de segurança](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1).
- Antes de implantar as políticas, permita que sua organização Conheça os possíveis impactos de registrar um dispositivo em mobilidade e segurança básica. Dependendo de como você configura as políticas, os dispositivos sem conformidade podem ser impedidos de acessar o Microsoft 365 e dados, incluindo aplicativos instalados, Fotos e informações pessoais em um dispositivo inscrito, e os dados podem ser excluídos.

>[!NOTE]
>Políticas e regras de acesso criadas no MDM para o Microsoft 365 Business Standard substitua as políticas de caixa de correio do dispositivo móvel do Exchange ActiveSync e as regras de acesso do dispositivo criadas no centro de administração do Exchange. Depois que um dispositivo está inscrito no MDM para o Microsoft 365 Business Standard, qualquer política de caixa de correio de dispositivo móvel ou regra de acesso de dispositivo do Exchange ActiveSync aplicada ao dispositivo é ignorada. Para saber mais sobre o Exchange ActiveSync, confira [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Etapa 1: criar uma política de dispositivo e implantar em um grupo de teste

Antes de começar, verifique se você ativou e configurou a mobilidade básica e a segurança. Para obter instruções, consulte [Overview of Basic Mobility and Security](overview-of-basic-mobility-and-security-for-microsoft-365.md).

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecione **criar uma política**.

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações de política de segurança e mobilidade básica":::

3. Na página **configurações de política** , especifique os requisitos que você deseja aplicar aos dispositivos móveis em sua organização.

4. **Exigir gerenciamento de perfil de email**: quando habilitado, os dispositivos que não têm um perfil de email gerenciado pela mobilidade básica e segurança são considerados não compatíveis. Um dispositivo não pode ter um perfil de email gerenciado quando não está direcionado corretamente, ou se o usuário configurou manualmente a conta de email no dispositivo. Quando você deixar que ele **não seja habilitado** (padrão), essa configuração não será avaliada para conformidade ou não conformidade. Para obter instruções sobre como os usuários podem obter conformidade quando essa opção é selecionada, consulte [uma conta de email existente foi encontrada](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

5. Na página **deseja aplicar esta política agora?** , escolha os grupos aos quais você deseja aplicar essa política.

6. Selecione **criar esta política**.

A política é enviada para o dispositivo de cada usuário a política se aplica à próxima vez que entrar no Microsoft 365 usando seu dispositivo móvel. Se os usuários não tiverem uma política aplicada ao dispositivo móvel antes, depois que você implantar a política, ele receberá uma notificação em seu dispositivo que inclui as etapas para registrar e ativar a mobilidade e a segurança básica. Para saber mais, confira [registrar seu dispositivo móvel usando mobilidade básica e segurança](enroll-your-mobile-device-using-basic-mobility-and-security.md). Até que eles concluam o registro na mobilidade básica e segurança hospedado pelo serviço do Intune, o acesso ao email, ao OneDrive e a outros serviços é restrito. Depois de concluir o registro usando o aplicativo portal da empresa do Intune, eles podem usar os serviços e a política é aplicada ao dispositivo.

## <a name="step-2-verify-that-your-policy-works"></a>Etapa 2: verificar se a política funciona

Depois de criar uma política de dispositivo, verifique se a política funciona como esperado antes de implantá-la em sua organização.

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecione **exibir a lista de dispositivos gerenciados**.
3. Verifique o status de dispositivos do usuário com a política aplicada. Você deseja que o **estado** dos dispositivos sejam **gerenciados.**
4. Você também pode fazer uma limpeza completa ou seletiva em um dispositivo clicando em **reinicializar fábrica** ou **remover dados da empresa** do botão **gerenciar** depois de selecionar um dispositivo. Para obter instruções, consulte [apagar um dispositivo móvel no Microsoft 365.

Etapa 3: implantar uma política na sua organização

Depois de criar uma política de dispositivo e verificar se ela funciona conforme o esperado, implante-a na sua organização.

1. No tipo de navegador: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecione a política que você deseja implantar e escolha **Editar** ao lado de **grupos aplicados a.**
3. Procure um grupo para adicionar e clique em **selecionar**.
4. Selecione **fechar** e **Alterar configuração.**
5. Selecione **fechar** e **Editar política.**

A política é enviada para o dispositivo móvel de cada usuário a política se aplica à próxima vez que entrar no Microsoft 365 a partir de seu dispositivo móvel. Se os usuários não tiverem uma política aplicada ao dispositivo móvel, eles receberão uma notificação em seu dispositivo com etapas para inscrever-se e ativá-lo para mobilidade básica e segurança. Depois de concluir o registro, a política é aplicada ao dispositivo. Para saber mais, confira [registrar seu dispositivo móvel usando mobilidade básica e segurança](enroll-your-mobile-device-using-basic-mobility-and-security.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Etapa 4: bloquear o acesso de email para dispositivos sem suporte

Para ajudar a proteger as informações da sua organização, você deve bloquear o acesso do aplicativo aos emails do Microsoft 365 para dispositivos móveis que não são suportados pela mobilidade básica e segurança. Para obter uma lista de dispositivos compatíveis, confira [dispositivos com suporte](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices). 

**Para bloquear o acesso do aplicativo:**

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecione **gerenciar configurações de acesso de dispositivo para toda a organização**.
3. Para bloquear dispositivos não suportados, escolha **Bloquear** em **se um dispositivo não for suportado pelo MDM para o Microsoft 365**e selecione **salvar**.

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Opção de acesso de bloqueio de segurança e mobilidade básica":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Etapa 5: Escolher grupos de segurança a serem excluídos de verificações de acesso condicional

Se quiser excluir algumas pessoas de verificações de acesso condicional em seus dispositivos móveis e você criou um ou mais grupos de segurança para essas pessoas, adicione os grupos de segurança aqui. As pessoas nesses grupos não terão nenhuma política imposta para seus dispositivos móveis compatíveis. Esta é a opção recomendada se você não deseja mais usar mobilidade básica e segurança em sua organização.

1. No navegador, digite [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecione **gerenciar configurações de acesso de dispositivo para toda a organização**.

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Mobilidade básica e segurança criar uma opção de política":::

3. Selecione **Adicionar** para adicionar o grupo de segurança que tem usuários que você deseja excluir do acesso bloqueado ao Microsoft 365. Quando um usuário foi adicionado a essa lista, ele pode acessar o email do Microsoft 365 quando estiver usando um dispositivo sem suporte.

4. Selecione o grupo de segurança que você deseja usar no painel **selecionar grupo** .

5. Selecione o nome e, em seguida, **adicione**  >  **salvar**.

6. No painel **configurações de acesso de dispositivo para toda a organização** , escolha **salvar**.

    :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Mobilidade básica e opção permitir acesso de segurança":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Qual é o impacto das políticas de segurança em tipos diferentes de dispositivos?

Quando você aplica uma política aos dispositivos de usuário, o impacto em cada dispositivo varia de certa forma entre os tipos de dispositivos. Consulte a tabela a seguir para obter exemplos do impacto das políticas em dispositivos diferentes.

|**Política de segurança**|**Android 4 e posterior**|**Samsung KNOX**|**iOS 6 e posterior**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|Exigir backup criptografado|Não|Sim|Sim|backup criptografado do iOS necessário.|
|Bloquear cópia de segurança na nuvem|Sim|Sim|Sim|Bloquear backup no Google no Android (esmaecido), backup na nuvem no iOS.|
|Bloquear sincronização de documento|Não|Não|Sim|iOS: Bloquear documentos na nuvem.|
|Bloquear sincronização de fotos |Não|Não|Sim|iOS (nativo): Bloquear fluxo de foto.|
|Bloquear captura de tela |Não|Sim|Sim|Bloqueado quando tentado.|
|Bloquear videoconferência |Não|Não|Sim|FaceTime bloqueado no iOS, não no Skype ou em outros.|
|Bloquear o envio de dados de diagnóstico |Não|Sim|Sim|Bloquear o envio de relatório de falha do Google no Android.|
|Bloquear o acesso à loja de aplicativos |Não|Sim|Sim|Ícone de armazenamento de aplicativo ausente na página inicial do Android, desabilitado no Windows, ausente no iOS.|
|Exigir senha para a loja de aplicativos |Não|Não|Sim|iOS: Senha necessária para compras do iTunes.|
|Bloquear a conexão ao armazenamento removível |Não|Sim|N/D|Android: o cartão SD está acinzentado em configurações, o Windows notifica que o usuário, aplicativos instalados não estão disponíveis|
|Bloquear conexão Bluetooth |Consulte observações|Consulte observações|Sim|Não é possível desabilitar o BlueTooth como uma configuração no Android. Em vez disso, desativamos todas as transações que exigem BlueTooth: distribuição avançada de áudio, controle remoto de áudio/vídeo, dispositivos de mão livre, fone de ouvido, acesso de catálogo telefônico e porta serial. Uma mensagem em caixa de informações aparece na parte inferior da página quando qualquer um desses dispositivos são usados.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>O que acontece quando você exclui uma política ou remove um usuário da política?

Quando você exclui uma política ou remove um usuário de um grupo ao qual a política foi implantada, as configurações de política, o perfil de email do Microsoft 365 e os emails armazenados em cache podem ser removidos do dispositivo do usuário. Consulte a tabela a seguir para ver o que foi removido para os diferentes tipos de dispositivos.

|**O que é removido**|**iOS 6 e posterior**|**Android 4 e posterior (incluindo Samsung KNOX**|
|:-----|:-----|:----------------------|
|Perfis de email gerenciados<sup>1</sup>|Sim|Não|
|Bloquear backup em nuvem|Sim|Não|
<sup>1</sup> Se a política foi implantada com a opção o **perfil de email é gerenciado** selecionado, o perfil de email gerenciado e os emails armazenados em cache nesse perfil são excluídos do dispositivo do usuário.

A política é removida do dispositivo móvel para cada usuário que a política aplica à próxima vez que o dispositivo faz check-in com mobilidade básica e segurança. Se você implantar uma nova política que se aplica a esses dispositivos de usuário, será solicitado a reinscrever-se em mobilidade e segurança básica.

Você também pode apagar um dispositivo completamente ou limpar seletivamente as informações organizacionais do dispositivo. Para obter mais informações, consulte [apagar um dispositivo móvel em mobilidade básica e segurança](wipe-mobile-device.md). 

## <a name="related-topics"></a>Tópicos relacionados

[Visão geral da mobilidade básica e segurança](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[Recursos de mobilidade básica e segurança](capabilities-of-basic-mobility-and-secruity.md)
