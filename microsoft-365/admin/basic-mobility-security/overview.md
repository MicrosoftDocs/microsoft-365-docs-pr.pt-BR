---
title: Visão geral da mobilidade básica e segurança para Microsoft 365
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
ms.openlocfilehash: 37be420a4b9499da3d1290b8b6a898b9fcb09c5b
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706305"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Visão geral da mobilidade básica e segurança para Microsoft 365

Você pode gerenciar e proteger dispositivos móveis quando eles estão conectados à sua organização Microsoft 365 usando o Basic Mobility and Security. Dispositivos móveis, como smartphones e tablets, que são usados para acessar o email de trabalho, o calendário, os contatos e documentos tem um papel importante garantir que os funcionários consigam trabalhar a qualquer momento, de praticamente qualquer lugar. Portanto, é fundamental que você ajude a proteger as informações da sua organização quando as pessoas usam dispositivos. Você pode usar o Basic Mobility and Security para definir políticas de segurança de dispositivos e regras de acesso e apagar dispositivos móveis se eles são perdidos ou roubados.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Instalação básica de mobilidade e segurança":::

## <a name="what-types-of-devices-can-you-manage"></a>Que tipos de dispositivos você pode gerenciar?

Você pode usar o Basic Mobility and Security para gerenciar vários tipos de dispositivos móveis, como Windows Phone, Android, iPhone e iPad. Para gerenciar dispositivos móveis usados por pessoas em sua organização, cada pessoa deve ter uma licença Microsoft 365 aplicável e seu dispositivo deve estar inscrito em Mobilidade Básica e Segurança.

Para ver o que o Basic Mobility and Security oferece suporte para cada tipo de dispositivo, consulte [Capabilities of Basic Mobility and Security](capabilities.md).

## <a name="setup-steps-for-basic-mobility-and-security"></a>Etapas de instalação para Mobilidade Básica e Segurança

Um Microsoft 365 global deve concluir as etapas a seguir para ativar e configurar o Basic Mobility and Security. Para obter etapas detalhadas, siga as orientações [em Configurar a Mobilidade Básica e a Segurança.](set-up.md) 

Veja um resumo das etapas:

**Etapa 1:** Ative a Mobilidade Básica e a Segurança seguindo as etapas  [na configuração de Mobilidade Básica e Segurança.](set-up.md)

**Etapa 2:** Configurar a Mobilidade Básica e a Segurança criando, por exemplo, um certificado APNs para gerenciar dispositivos iOS e adicionar um registro DNS (Sistema de Nomes de Domínio) para seu domínio para dar suporte Windows telefones.

**Etapa 3:** Crie políticas de dispositivo e aplique-as a grupos de usuários. Ao fazer isso, os usuários receberão uma mensagem de registro em seu dispositivo e, quando concluirem o registro, seus dispositivos serão restritos pelas políticas que você definiu para eles. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md). 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações básicas de política de segurança e mobilidade":::

## <a name="device-management-tasks"></a>Tarefas de gerenciamento de dispositivos

Depois de configurar o Basic Mobility and Security e os usuários registrarem seus dispositivos, você poderá gerenciar os dispositivos, bloquear o acesso ou apagar um dispositivo, se necessário. Para saber mais sobre algumas tarefas comuns de gerenciamento de dispositivos, incluindo onde concluir as tarefas, consulte [Manage devices enrolled](manage-enrolled-devices.md)in Mobile Device Management for Microsoft 365 .

## <a name="other-ways-to-manage-devices-and-apps"></a>Outras maneiras de gerenciar dispositivos e aplicativos

Se você precisar apenas de gerenciamento de aplicativo móvel (MAM), talvez para pessoas atualizando projetos de trabalho em seus próprios dispositivos, o Intune fornece outra opção além de registrar e gerenciar dispositivos. Uma assinatura do Intune permite configurar políticas de MAM usando o portal do Azure, mesmo que os dispositivos das pessoas não sejam inscritos no Intune. Para obter mais informações, consulte [Visão geral das políticas de proteção de aplicativos.](/mem/intune/apps/app-protection-policy)

## <a name="related-content"></a>Conteúdo relacionado

[Configurar Mobilidade Básica e Segurança](set-up.md) (artigo)\
[Registrar seu dispositivo móvel usando o Basic Mobility and Security](enroll-your-mobile-device.md) (artigo)\
[Gerenciar dispositivos inscritos no Gerenciamento de Dispositivo Móvel Microsoft 365](manage-enrolled-devices.md) (artigo)\
[Obter detalhes sobre dispositivos gerenciados](get-details-about-managed-devices.md) pela Basic Mobility and Security (artigo)