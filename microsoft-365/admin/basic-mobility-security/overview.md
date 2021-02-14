---
title: Visão geral do Basic Mobility and Security para o Microsoft 365
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
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430057"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Visão geral do Basic Mobility and Security para o Microsoft 365

Você pode gerenciar e proteger dispositivos móveis quando eles estão conectados à sua organização do Microsoft 365 usando Mobilidade e Segurança Básica. Dispositivos móveis, como smartphones e tablets, que são usados para acessar o email de trabalho, o calendário, os contatos e documentos tem um papel importante garantir que os funcionários consigam trabalhar a qualquer momento, de praticamente qualquer lugar. Portanto, é fundamental que você ajude a proteger as informações da sua organização quando as pessoas usam dispositivos. Você pode usar o Basic Mobility and Security para definir políticas de segurança de dispositivos e regras de acesso e apagar dispositivos móveis se eles são perdidos ou roubados.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configuração básica de mobilidade e segurança":::

## <a name="what-types-of-devices-can-you-manage"></a>Que tipos de dispositivos você pode gerenciar?

Você pode usar o Basic Mobility and Security para gerenciar vários tipos de dispositivos móveis, como Windows Phone, Android, iPhone e iPad. Para gerenciar dispositivos móveis usados por pessoas em sua organização, cada pessoa deve ter uma licença aplicável do Microsoft 365 e seu dispositivo deve estar inscrito no Basic Mobility and Security.

Para ver o que o Basic Mobility and Security suporta para cada tipo de dispositivo, consulte [Recursos de Mobilidade e Segurança Básica.](capabilities.md)

## <a name="setup-steps-for-basic-mobility-and-security"></a>Etapas de configuração para Mobilidade Básica e Segurança

Um administrador global do Microsoft 365 deve concluir as etapas a seguir para ativar e configurar o Basic Mobility and Security. Para obter etapas detalhadas, siga as orientações em [Configurar Mobilidade Básica e Segurança.](set-up.md) 

Veja um resumo das etapas:

**Etapa 1:** Ative o Basic Mobility and Security seguindo as etapas na  [configuração básica de mobilidade e segurança.](set-up.md)

**Etapa 2:** Configurar a Mobilidade Básica e Segurança criando, por exemplo, um certificado APNs para gerenciar dispositivos iOS e adicionando um registro DNS (Sistema de Nomes de Domínio) para seu domínio para dar suporte a telefones Windows.

**Etapa 3:** Crie políticas de dispositivo e aplique-as a grupos de usuários. Quando você faz isso, os usuários receberão uma mensagem de registro em seus dispositivos e, quando eles concluirem o registro, seus dispositivos serão restritos pelas políticas que você definiu para eles. Para obter mais informações, consulte [Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança.](enroll-your-mobile-device.md) 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações de política básica de segurança e mobilidade":::

## <a name="device-management-tasks"></a>Tarefas de gerenciamento de dispositivos

Depois de configurar a Mobilidade Básica e Segurança e os usuários registrarem seus dispositivos, você poderá gerenciar os dispositivos, bloquear o acesso ou apagar um dispositivo, se necessário. Para saber mais sobre algumas tarefas comuns de gerenciamento de dispositivos, incluindo onde concluir as tarefas, confira Gerenciar dispositivos inscritos no Gerenciamento de Dispositivo Móvel do [Microsoft 365.](manage-enrolled-devices.md)

## <a name="other-ways-to-manage-devices-and-apps"></a>Outras maneiras de gerenciar dispositivos e aplicativos

Se você precisar apenas do gerenciamento de aplicativos móveis (MAM), talvez para pessoas atualizando projetos de trabalho em seus próprios dispositivos, o Intune oferece outra opção além de registrar e gerenciar dispositivos. Uma assinatura do Intune permite configurar políticas de MAM usando o portal do Azure, mesmo que os dispositivos das pessoas não sejam inscritos no Intune. Para obter mais informações, consulte Visão [geral das políticas de proteção de aplicativos.](https://go.microsoft.com/fwlink/?LinkId=2132517)

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a Mobilidade Básica e a Segurança](set-up.md)

[Registrar seu dispositivo móvel usando Mobilidade Básica e Segurança](enroll-your-mobile-device.md)

[Gerenciar dispositivos inscritos no Gerenciamento de Dispositivo Móvel do Microsoft 365](manage-enrolled-devices.md)

[Obter detalhes sobre dispositivos gerenciados pela Mobilidade Básica e Segurança](get-details-about-managed-devices.md)