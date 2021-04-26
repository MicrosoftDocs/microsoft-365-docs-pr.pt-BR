---
title: Gerenciar dispositivos inscritos no Gerenciamento de Dispositivos Móveis no Microsoft 365
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
description: A Mobilidade Básica e a Segurança podem ajudá-lo a proteger e gerenciar dispositivos móveis.
ms.openlocfilehash: 4ff1c43343e00b7eac7aa38b2d266f163f79e2a7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023876"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Gerenciar dispositivos inscritos no Gerenciamento de Dispositivos Móveis no Microsoft 365

O gerenciamento de dispositivo móvel integrado para o Microsoft 365 ajuda você a proteger e gerenciar dispositivos móveis de seus usuários, como iPhones, iPads, Androids e telefones Windows. A primeira etapa é entrar no Microsoft 365 e configurar o Basic Mobility and Security. Para obter mais informações, [consulte Set up Basic Mobility and Security](set-up.md).

Depois de defini-lo, as pessoas em sua organização devem registrar seus dispositivos no serviço. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md).Em seguida, você pode usar o Basic Mobility and Security para ajudar a gerenciar dispositivos em sua organização. Por exemplo, você pode usar políticas de segurança de dispositivo para ajudar a limitar o acesso a email ou outros serviços, exibir relatórios de dispositivos e apagar remotamente um dispositivo. Normalmente, você irá até o Centro de Conformidade & segurança para realizar essas tarefas. Para obter mais informações, consulte Centro de conformidade do [Microsoft 365](../../compliance/microsoft-365-compliance-center.md).

## <a name="device-management-tasks"></a>Tarefas de gerenciamento de dispositivos

Para chegar ao painel de gerenciamento de dispositivos, siga estas etapas:

1. Vá para o Centro de administração [do Microsoft 365.](../../admin/admin-overview/about-the-admin-center.md)

2. Digite Gerenciamento de Dispositivo Móvel no campo de pesquisa e selecione Gerenciamento de Dispositivo **Móvel**   na lista de resultados.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opção de gerenciamento de dispositivo móvel":::

3. Selecione  **Vamos começar**.

## <a name="manage-mobile-devices"></a>Gerenciar dispositivos móveis

Depois de configurar o Basic Mobility and Security, veja algumas maneiras de gerenciar os dispositivos móveis em sua organização.

|**Para fazer isso**|**Faça isto**|
|:----------------|:------------------------------------------------------------------------------|
|Apagar um dispositivo |No painel Gerenciamento de Dispositivos,  ****  *selecione* nome do dispositivo , apagar completo para excluir todas as informações ou Apagar Seletiva para excluir apenas informações organizacionais   no  ****   dispositivo. Para obter mais informações, [consulte Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).|
|Bloquear o acesso de dispositivos sem suporte ao email do Exchange usando o Exchange ActiveSync |No painel Gerenciamento de Dispositivos, selecione  **Bloquear**. |
|Configurar políticas de dispositivo como requisitos de senha e configurações de segurança |No painel Gerenciamento de Dispositivos, selecione **Políticas de segurança do dispositivo** Adicionar   >  **+**. Para obter mais informações, consulte [Create device security policies in Basic Mobility and Security](create-device-security-policies.md).|
|Exibir a lista de dispositivos bloqueados  |No painel Gerenciamento de Dispositivos, em  **Selecione um exibição**   selecione  **Bloqueado**. |
|Desbloquear um dispositivo incompatível ou sem suporte para um usuário ou para um grupo de usuários  |Escolha um dos seguintes para desbloquear dispositivos:<br/>- Remova o usuário ou os usuários do grupo de segurança ao que a política foi aplicada. Vá para o Centro de administração do Microsoft 365 > **Grupos** e selecione nome do grupo. Selecione **Editar membros e administradores**.<br/>- Remova o grupo de segurança do que os usuários são membros da política de dispositivo. Vá para o Centro de Conformidade & Segurança > **Políticas** de segurança   >  **do dispositivo.** Selecione o nome da política de dispositivo e selecione **Editar**  >  **Implantação**.<br/>- Desbloqueie todos os dispositivos não compatíveis para uma política de dispositivo. Vá para o Centro de Conformidade & Segurança > **Políticas** de segurança   >  **do dispositivo.** Selecione o nome da política de dispositivo e selecione **Editar**  >  **requisitos do Access.** Selecione  **Permitir acesso e violação de relatório.**<br/>- Para desbloquear um dispositivo não compatível ou sem suporte para um usuário ou um grupo de  **** usuários, vá para o Centro de Conformidade & Segurança >Políticas de segurança Gerenciamento de dispositivo Gerenciar configurações de acesso ao dispositivo   >  ****   >  ****. Adicione um grupo de segurança com os membros que você deseja excluir do acesso bloqueado ao Microsoft 365. Para obter mais informações, [consulte Create, edit, or delete a security group in the Microsoft 365 admin center](../../admin/email/create-edit-or-delete-a-security-group.md).|
|Remover usuários para que seus dispositivos não sejam mais gerenciados pela Mobilidade Básica e Segurança |Para remover o usuário, edite o grupo de segurança que tem políticas de gerenciamento de dispositivos para Mobilidade Básica e Segurança. Para obter mais informações,  [consulte Create, edit, or delete a security group in the Microsoft 365 admin center](../../admin/email/create-edit-or-delete-a-security-group.md).<br/>Para remover a Mobilidade Básica e a Segurança de todos os usuários do Microsoft 365, consulte [Desativar a Mobilidade Básica e a Segurança.](turn-off.md)|

Live (v14)