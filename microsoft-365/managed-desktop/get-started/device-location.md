---
title: Serviço de localização do Windows 10
description: Como ter os serviços de localização do Windows atados para seus dispositivos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929455"
---
# <a name="windows-10-location-service"></a>Serviço de localização do Windows 10

Os dispositivos na Área de Trabalho Gerenciada da Microsoft são registrados usando o Windows Autopilot. Esse processo nos permite gerenciá-los com o Azure Active Directory e o Microsoft Intune. Por padrão, o serviço de localização do Windows 10 é desabilitado quando um dispositivo é ativado pela primeira vez, a menos que esse recurso esteja habilitado nas configurações de Privacidade durante a "experiência fora da caixa". Essas configurações ficam ocultas durante o registro do Piloto Automático na Área de Trabalho Gerenciada da Microsoft. Para obter mais informações sobre como o Autopilot está definido, consulte Experiência de primeira executar com o Autopilot e a [Página de Status do Registro.](esp-first-run.md)

Por esse motivo, os dispositivos da Área de Trabalho Gerenciada da Microsoft não podem obter a localização do dispositivo, o que limita a funcionalidade de vários recursos do Windows, como fusos horário. Para obter mais informações sobre o serviço de localização do Windows 10, consulte Serviço de localização e [privacidade do Windows 10.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Você não precisa usar o serviço de localização para participar da Área de Trabalho Gerenciada da Microsoft, mas a experiência do usuário será restrita. Por exemplo, os dispositivos não poderão determinar automaticamente o fuso horário em que estão quando seus usuários trabalham em um fuso horário diferente.

## <a name="enable-the-location-service"></a>Habilitar o serviço de localização

Você pode optar por usar o serviço de localização ao registrar dispositivos no serviço de Área de Trabalho Gerenciada da Microsoft ou ativar ou desativar o serviço após o registro.

### <a name="opt-in-during-enrollment"></a>Optar durante o registro

Você pode fazer com que o serviço de Área de Trabalho Gerenciada da Microsoft habilita o serviço de localização. Durante a sequência de inscrição, você será solicitado a selecionar se deseja permitir que o serviço de localização do Windows 10 seja habilitado em dispositivos.

### <a name="control-the-location-service-after-enrollment"></a>Controlar o serviço de localização após o registro

Você pode ter o serviço de localização ligado (ou desligado) [a](../working-with-managed-desktop/admin-support.md) qualquer momento enviando uma solicitação de suporte por meio do portal [de administração](access-admin-portal.md).

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Como a Área de Trabalho Gerenciada da Microsoft configura o serviço de localização do Windows 10

Se você optar por usar o serviço de localização, usamos as configurações mínimas necessárias sem afetar a privacidade dos usuários. Para obter mais informações, consulte [Serviço de localização e privacidade do Windows 10.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

A Área de Trabalho Gerenciada da Microsoft habilita a **configuração de** privacidade local nas **configurações do Windows** para Permitir o acesso ao local neste **dispositivo.** A interface do usuário tem esta aparência:

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Configurações de local nas configurações do Windows":::

> [!NOTE]
> Se você optar por usar o serviço de localização, isso só se aplica ao próprio sistema operacional Windows. Os aplicativos não têm permissão para usar serviços de localização. Cada usuário pode escolher se permite que os aplicativos acessem sua localização.