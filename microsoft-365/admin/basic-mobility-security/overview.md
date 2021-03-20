---
title: Visão geral da Mobilidade Básica e Segurança do Microsoft 365
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
description: Use o Basic Mobility and Security para definir políticas de segurança de dispositivos e regras de acesso.
ms.openlocfilehash: e74a5df6d10f8f3fb7b420e428380af97ba75597
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906247"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Visão geral da Mobilidade Básica e Segurança do Microsoft 365

Você pode gerenciar e proteger dispositivos móveis quando eles estão conectados à sua organização do Microsoft 365 usando o Basic Mobility and Security. Dispositivos móveis, como smartphones e tablets, que são usados para acessar o email de trabalho, o calendário, os contatos e documentos tem um papel importante garantir que os funcionários consigam trabalhar a qualquer momento, de praticamente qualquer lugar. Portanto, é fundamental que você ajude a proteger as informações da sua organização quando as pessoas usam dispositivos. Você pode usar o Basic Mobility and Security para definir políticas de segurança de dispositivos e regras de acesso e apagar dispositivos móveis se eles são perdidos ou roubados.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Instalação básica de mobilidade e segurança":::

## <a name="what-types-of-devices-can-you-manage"></a>Que tipos de dispositivos você pode gerenciar?

Você pode usar o Basic Mobility and Security para gerenciar muitos tipos de dispositivos móveis, como Windows Phone, Android, iPhone e iPad. Para gerenciar dispositivos móveis usados por pessoas em sua organização, cada pessoa deve ter uma licença do Microsoft 365 aplicável e seu dispositivo deve estar inscrito em Mobilidade Básica e Segurança.

Para ver o que o Basic Mobility and Security oferece suporte para cada tipo de dispositivo, consulte [Capabilities of Basic Mobility and Security](capabilities.md).

## <a name="setup-steps-for-basic-mobility-and-security"></a>Etapas de instalação para Mobilidade Básica e Segurança

Um administrador global do Microsoft 365 deve concluir as etapas a seguir para ativar e configurar o Basic Mobility and Security. Para obter etapas detalhadas, siga as orientações [em Configurar a Mobilidade Básica e a Segurança.](set-up.md) 

Veja um resumo das etapas:

**Etapa 1:** Ative a Mobilidade Básica e a Segurança seguindo as etapas  [na configuração de Mobilidade Básica e Segurança.](set-up.md)

**Etapa 2:** Set up Basic Mobility and Security by, for example, creating an APNs certificate to manage iOS devices and adding a Domain Name System (DNS) record for your domain to support Windows phones.

**Etapa 3:** Crie políticas de dispositivo e aplique-as a grupos de usuários. Ao fazer isso, os usuários receberão uma mensagem de registro em seu dispositivo e, quando concluirem o registro, seus dispositivos serão restritos pelas políticas que você definiu para eles. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md). 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações básicas de política de segurança e mobilidade":::

## <a name="device-management-tasks"></a>Tarefas de gerenciamento de dispositivos

Depois de configurar o Basic Mobility and Security e os usuários registrarem seus dispositivos, você poderá gerenciar os dispositivos, bloquear o acesso ou apagar um dispositivo, se necessário. Para saber mais sobre algumas tarefas comuns de gerenciamento de dispositivos, incluindo onde concluir as tarefas, consulte [Manage devices enrolled in Mobile Device Management for Microsoft 365](manage-enrolled-devices.md).

## <a name="other-ways-to-manage-devices-and-apps"></a>Outras maneiras de gerenciar dispositivos e aplicativos

Se você precisar apenas de gerenciamento de aplicativo móvel (MAM), talvez para pessoas atualizando projetos de trabalho em seus próprios dispositivos, o Intune fornece outra opção além de registrar e gerenciar dispositivos. Uma assinatura do Intune permite configurar políticas de MAM usando o portal do Azure, mesmo que os dispositivos das pessoas não sejam inscritos no Intune. Para obter mais informações, consulte [Visão geral das políticas de proteção de aplicativos.](/mem/intune/apps/app-protection-policy)

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a Mobilidade Básica e a Segurança](set-up.md)

[Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md)

[Gerenciar dispositivos inscritos no Gerenciamento de Dispositivo Móvel para o Microsoft 365](manage-enrolled-devices.md)

[Obter detalhes sobre dispositivos gerenciados pela Mobilidade Básica e Segurança](get-details-about-managed-devices.md)