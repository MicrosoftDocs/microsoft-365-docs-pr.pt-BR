---
title: Gerenciar dispositivos inscritos no Gerenciamento de Dispositivo Móvel no Microsoft 365
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
description: A Mobilidade Básica e Segurança pode ajudá-lo a proteger e gerenciar dispositivos móveis.
ms.openlocfilehash: 4954da0ff44276d9bd46cabc78bc52c7879e5e26
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876955"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Gerenciar dispositivos inscritos no Gerenciamento de Dispositivo Móvel no Microsoft 365

O gerenciamento de dispositivo móvel integrado para o Microsoft 365 ajuda você a proteger e gerenciar dispositivos móveis de seus usuários, como iPhones, iPads, Androids e telefones Windows. A primeira etapa é entrar no Microsoft 365 e configurar o Basic Mobility and Security. Para obter mais informações, [consulte Configurar Mobilidade Básica e Segurança.](set-up.md)

Depois que você a configurar, as pessoas em sua organização deverão registrar seus dispositivos no serviço. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança.](enroll-your-mobile-device.md)Em seguida, você pode usar o Basic Mobility and Security para ajudar a gerenciar dispositivos em sua organização. Por exemplo, você pode usar políticas de segurança de dispositivo para ajudar a limitar o acesso a emails ou outros serviços, exibir relatórios de dispositivos e apagar remotamente um dispositivo. Normalmente, você vai para o Centro de Conformidade & segurança para realizar essas tarefas. Para saber mais, confira o [Centro de conformidade do Microsoft 365.](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)

## <a name="device-management-tasks"></a>Tarefas de gerenciamento de dispositivos

Para chegar ao painel de gerenciamento de dispositivos, siga estas etapas:

1. Vá para o [Centro de administração do Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. Digite Gerenciamento de Dispositivo Móvel no campo de pesquisa e selecione **Gerenciamento de** Dispositivo   Móvel na lista de resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opção de gerenciamento de dispositivo móvel":::

3. Selecione  **Vamos começar.**

## <a name="manage-mobile-devices"></a>Gerenciar dispositivos móveis

Depois de configurar a Mobilidade Básica e Segurança, aqui estão algumas maneiras de gerenciar os dispositivos móveis em sua organização.

|**Para fazer isso**|**Faça isto**|
|:----------------|:------------------------------------------------------------------------------|
|Apagar um dispositivo |No painel de Gerenciamento de Dispositivos, selecione o nome do *dispositivo,* em seguida, apagando totalmente para excluir todas as informações ou apagando seletivamente para excluir somente as informações  ****     ****   organizacionais no dispositivo. Para obter mais informações, [consulte Apagar um dispositivo móvel em Mobilidade Básica e Segurança.](wipe-mobile-device.md)|
|Bloquear o acesso de dispositivos sem suporte ao email do Exchange usando o Exchange ActiveSync |No painel gerenciamento de dispositivos, selecione  **Bloquear**. |
|Configurar políticas de dispositivo, como requisitos de senha e configurações de segurança |No painel de Gerenciamento de Dispositivos, selecione **Políticas de segurança do dispositivo** Adicionar   >  **+**. Para obter mais informações, [consulte Criar políticas de segurança de dispositivos em Mobilidade Básica e Segurança.](create-device-security-policies.md)|
|Exibir a lista de dispositivos bloqueados  |No painel gerenciamento de dispositivos, em  **Selecionar uma exibição selecione**     **Bloqueado**. |
|Desbloquear um dispositivo incompatível ou sem suporte para um usuário ou para um grupo de usuários  |Escolha um dos seguintes para desbloquear dispositivos:<br/>- Remova o usuário ou usuários do grupo de segurança ao que a política foi aplicada. Vá para o Centro de administração do Microsoft 365 > **Grupos** e selecione o nome do grupo. Selecione **Editar membros e administradores.**<br/>- Remova o grupo de segurança do que os usuários são membros da política de dispositivo. Vá para o Centro de Conformidade & segurança > **políticas de segurança do**   >  **dispositivo.** Selecione o nome da política de dispositivo e selecione **Editar**  >  **Implantação.**<br/>- Desbloquear todos os dispositivos não compatíveis para uma política de dispositivo. Vá para o Centro de Conformidade & segurança > **políticas de segurança do**   >  **dispositivo.** Selecione o nome da política de dispositivo e, em seguida, **selecione Editar**  >  **requisitos de acesso.** Selecione  **Permitir acesso e relatar violação**.<br/>- Para desbloquear um dispositivo incompatível ou sem suporte para um usuário ou grupo de usuários, vá  **** para o Centro de Conformidade do & segurança >Políticas de segurança Gerenciamento de dispositivo Gerenciar configurações de acesso de   >  ****   >  **** dispositivo. Adicione um grupo de segurança com os membros que você deseja excluir do bloqueio de acesso ao Microsoft 365. Para saber mais, confira Criar, editar ou excluir um grupo de [segurança no centro de administração do Microsoft 365.](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)|
|Remover usuários para que seus dispositivos não sejam mais gerenciados pelo Basic Mobility and Security |Para remover o usuário, edite o grupo de segurança que tem políticas de gerenciamento de dispositivos para Mobilidade Básica e Segurança. Para saber mais, confira Criar, editar ou excluir um grupo de  [segurança no centro de administração do Microsoft 365.](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)<br/>Para remover o Basic Mobility and Security de todos os seus usuários do Microsoft 365, confira Desativar [Mobilidade e Segurança Básica.](turn-off.md)|

Live (v14)