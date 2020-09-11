---
title: Visão geral da mobilidade básica e segurança para o Microsoft 365
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
description: Use mobilidade básica e segurança para definir políticas de segurança de dispositivos e regras de acesso.
ms.openlocfilehash: 177b0769f3cad928d05a41cfe95d5d62ab2b4786
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430057"
---
# <a name="overview-of-basic-mobility-and-security-for-microsoft-365"></a>Visão geral da mobilidade básica e segurança para o Microsoft 365

Você pode gerenciar e proteger dispositivos móveis quando eles estão conectados à sua organização do Microsoft 365 usando mobilidade e segurança básica. Dispositivos móveis, como smartphones e tablets, que são usados para acessar o email de trabalho, o calendário, os contatos e documentos tem um papel importante garantir que os funcionários consigam trabalhar a qualquer momento, de praticamente qualquer lugar. Portanto, é fundamental que você ajude a proteger as informações da sua organização quando as pessoas usam dispositivos. Você pode usar mobilidade básica e segurança para definir políticas de segurança de dispositivos e regras de acesso e para apagar dispositivos móveis se eles forem perdidos ou roubados.

:::image type="content" source="../../media/basic-mobility-security/bms-3-setup.png" alt-text="Configuração básica de segurança e mobilidade":::

## <a name="what-types-of-devices-can-you-manage"></a>Que tipos de dispositivos você pode gerenciar?

Você pode usar mobilidade básica e segurança para gerenciar muitos tipos de dispositivos móveis, como Windows Phone, Android, iPhone e iPad. Para gerenciar dispositivos móveis usados por pessoas em sua organização, cada pessoa deve ter uma licença do Microsoft 365 aplicável e o dispositivo deve ser inscrito em mobilidade básica e segurança.

Para ver quais mobilidade e segurança básica dão suporte a cada tipo de dispositivo, consulte [recursos de mobilidade básica e segurança](capabilities.md).

## <a name="setup-steps-for-basic-mobility-and-security"></a>Etapas de configuração para mobilidade básica e segurança

Um Microsoft 365 global admin deve concluir as seguintes etapas para ativar e configurar mobilidade e segurança básicas. Para obter etapas detalhadas, siga as orientações em [Configurar mobilidade e segurança básica](set-up.md). 

Veja um resumo das etapas:

**Etapa 1:** Ative a mobilidade básica e a segurança seguindo as etapas descritas em [Configurar mobilidade básica e segurança](set-up.md).

**Etapa 2:** Configurar mobilidade básica e segurança por exemplo, criando um certificado APNs para gerenciar dispositivos iOS e adicionar um registro DNS (sistema de nomes de domínio) para seu domínio para dar suporte a telefones Windows.

**Etapa 3:** Criar políticas de dispositivo e aplicá-las a grupos de usuários. Ao fazer isso, os usuários recebem uma mensagem de registro em seus dispositivos e, quando concluíram o registro, seus dispositivos são restritos pelas políticas que você configurou para eles. Para saber mais, confira [registrar seu dispositivo móvel usando mobilidade básica e segurança](enroll-your-mobile-device.md). 

:::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configurações básicas de política de segurança e mobilidade":::

## <a name="device-management-tasks"></a>Tarefas de gerenciamento de dispositivos

Depois que você tiver uma mobilidade básica e uma configuração de segurança e seus usuários tiverem inscrito seus dispositivos, você poderá gerenciar os dispositivos, bloquear o acesso ou apagar um dispositivo, se necessário. Para saber mais sobre algumas tarefas comuns de gerenciamento de dispositivos, incluindo onde concluir as tarefas, confira [gerenciar dispositivos registrados no gerenciamento de dispositivo móvel para o Microsoft 365](manage-enrolled-devices.md).

## <a name="other-ways-to-manage-devices-and-apps"></a>Outras maneiras de gerenciar dispositivos e aplicativos

Se você precisar apenas do gerenciamento de aplicativo móvel (MAM), talvez para pessoas que estejam Atualizando projetos de trabalho em seus próprios dispositivos, o Intune fornecerá outra opção além de registrar e gerenciar dispositivos. Uma assinatura do Intune permite que você configure políticas de MAM usando o portal do Azure, mesmo se os dispositivos de pessoas não estiverem registrados no Intune. Para saber mais, confira [visão geral de políticas de proteção de aplicativo](https://go.microsoft.com/fwlink/?LinkId=2132517).

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a Mobilidade Básica e a Segurança](set-up.md)

[Registrar seu dispositivo móvel usando mobilidade básica e segurança](enroll-your-mobile-device.md)

[Gerenciar dispositivos registrados no gerenciamento de dispositivos móveis para o Microsoft 365](manage-enrolled-devices.md)

[Obter detalhes sobre dispositivos gerenciados pela mobilidade básica e segurança](get-details-about-managed-devices.md)