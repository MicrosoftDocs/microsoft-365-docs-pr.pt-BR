---
title: Gerenciar dispositivos registrados no gerenciamento de dispositivos móveis no Microsoft 365
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
description: Mobilidade e segurança básica podem ajudá-lo a proteger e gerenciar dispositivos móveis.
ms.openlocfilehash: e07ff0704afcb5bca1db4e2a5c2aff9c7d6008fd
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430053"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Gerenciar dispositivos registrados no gerenciamento de dispositivos móveis no Microsoft 365

O gerenciamento de dispositivo móvel interno para o Microsoft 365 ajuda você a proteger e gerenciar os dispositivos móveis dos seus usuários, como iPhones, iPads, Androids e Windows phones. A primeira etapa é entrar no Microsoft 365 e configurar a mobilidade básica e a segurança. Para obter mais informações, consulte [Configurar mobilidade básica e segurança](set-up.md).

Após a configuração, as pessoas da sua organização devem registrar seus dispositivos no serviço. Para saber mais, confira [registrar seu dispositivo móvel usando mobilidade básica e segurança](enroll-your-mobile-device.md).Em seguida, você pode usar mobilidade básica e segurança para ajudar a gerenciar dispositivos em sua organização. Por exemplo, você pode usar políticas de segurança de dispositivo para ajudar a limitar o acesso de email ou outros serviços, exibir relatórios de dispositivos e apagar remotamente um dispositivo. Normalmente, você vai para o centro de conformidade & segurança para executar essas tarefas. Para obter mais informações, consulte [centro de conformidade do Microsoft 365](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

## <a name="device-management-tasks"></a>Tarefas de gerenciamento de dispositivos

Para acessar o painel de gerenciamento de dispositivo, siga estas etapas:

1. Vá para o [centro de administração do Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Digite gerenciamento de dispositivo móvel no campo de pesquisa e selecione **Gerenciamento de dispositivo móvel**   na lista de resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opção de gerenciamento de dispositivo móvel":::

3. Selecione  **gerenciar dispositivos**.

## <a name="manage-mobile-devices"></a>Gerenciar dispositivos móveis
    
Após ter a mobilidade básica e a configuração de segurança, veja aqui algumas maneiras de gerenciar os dispositivos móveis em sua organização.

|**Para fazer isso**|**Faça isto**|
|:----------------|:------------------------------------------------------------------------------|
|Apagar um dispositivo |No painel gerenciamento de dispositivos, selecione *nome do dispositivo*e  **apagamento completo**   para excluir todas as informações ou  **limpeza seletiva**   para excluir apenas as informações organizacionais no dispositivo. Para obter mais informações, consulte [apagar um dispositivo móvel em mobilidade básica e segurança](wipe-mobile-device.md).|
|Bloquear o acesso de dispositivos sem suporte ao email do Exchange usando o Exchange ActiveSync |No painel gerenciamento de dispositivos, selecione  **Bloquear**. |
|Configurar políticas de dispositivo, como requisitos de senha e configurações de segurança |No painel gerenciamento de dispositivo, selecione **políticas de segurança de dispositivo**   >  **Adicionar +**. Para obter mais informações, consulte [Create Device Security Policies in Basic Mobility and Security](create-device-security-policies.md).|
|Exibir a lista de dispositivos bloqueados  |No painel gerenciamento de dispositivo, em  **selecionar um modo de exibição** ,   selecione  **bloqueado**. |
|Desbloquear um dispositivo incompatível ou sem suporte para um usuário ou para um grupo de usuários  |Escolha uma das seguintes opções para desbloquear dispositivos:<br/>-Remova o usuário ou os usuários do grupo de segurança ao qual a política foi aplicada. Vá para centro de administração do Microsoft 365 > **grupos**e selecione nome do grupo. Selecione **Editar Membros e administradores**.<br/>– Remover o grupo de segurança do qual os usuários são membros da política de dispositivo. Vá para segurança & centro de conformidade  **>políticas**de   >  **segurança de dispositivos**. Selecione nome da política de dispositivo e, em seguida, selecione **Editar**  >  **implantação**.<br/>-Desbloqueie todos os dispositivos não compatíveis de uma política de dispositivo. Vá para segurança & centro de conformidade  **>políticas**de   >  **segurança de dispositivos**. Selecione nome da política de dispositivo e, em seguida, selecione **Editar**  >  **requisitos de acesso**. Selecione  **permitir acesso e violação de relatório**.<br/>– Para desbloquear um dispositivo sem conformidade ou não compatível com um usuário ou um grupo de usuários, vá até segurança & centro de conformidade > **políticas de segurança**   >  **Gerenciamento de dispositivos**   >  **gerenciar configurações de acesso do dispositivo**. Adicione um grupo de segurança com os membros que você deseja excluir do acesso bloqueado ao Microsoft 365. Para obter mais informações, consulte [criar, editar ou excluir um grupo de segurança no centro de administração do Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb).|
|Remova os usuários para que seus dispositivos não sejam mais gerenciados pela mobilidade básica e segurança |Para remover o usuário, edite o grupo de segurança que tem políticas de gerenciamento de dispositivos para mobilidade básica e segurança. Para obter mais informações, consulte  [criar, editar ou excluir um grupo de segurança no centro de administração do Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb).<br/>Para remover a mobilidade básica e a segurança de todos os seus usuários do Microsoft 365, consulte [desative a mobilidade básica e a segurança](turn-off.md).|

Live (v14)