---
title: Serviço de localização do Windows 10
description: Como ter os Windows de localização atados para seus dispositivos
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

Os dispositivos Área de Trabalho Gerenciada da Microsoft são registrados usando o Windows Autopilot. Esse processo nos permite gerenciá-los com Azure Active Directory e Microsoft Intune. Por padrão, o serviço de Windows 10 local é desabilitado quando um dispositivo está ativado pela primeira vez, a menos que esse recurso esteja habilitado nas configurações de Privacidade durante a "experiência fora da caixa". Essas configurações ficam ocultas durante o registro do Piloto Automático no Área de Trabalho Gerenciada da Microsoft. Para obter mais informações sobre como o Autopilot está definido, consulte Experiência de primeira executar com o Autopilot e a [Página de Status do Registro.](esp-first-run.md)

Por esse motivo, Área de Trabalho Gerenciada da Microsoft dispositivos não podem obter a localização do dispositivo, o que limita a funcionalidade de vários recursos Windows, como fusos horário. Para obter mais informações sobre o serviço Windows 10 local, [consulte Windows 10 local e privacidade.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Você não precisa usar o serviço de localização para participar do Área de Trabalho Gerenciada da Microsoft, mas a experiência do usuário será restrita. Por exemplo, os dispositivos não poderão determinar automaticamente o fuso horário em que estão quando seus usuários trabalham em um fuso horário diferente.

## <a name="enable-the-location-service"></a>Habilitar o serviço de localização

Você pode optar por usar o serviço de localização ao registrar dispositivos no serviço Área de Trabalho Gerenciada da Microsoft ou ativar ou desativar o serviço após o registro.

### <a name="opt-in-during-enrollment"></a>Optar durante o registro

Você pode ter o serviço Área de Trabalho Gerenciada da Microsoft habilitar o serviço de localização. Durante a sequência de inscrição, você será solicitado a selecionar se deseja permitir que o serviço de Windows 10 local seja habilitado em dispositivos.

### <a name="control-the-location-service-after-enrollment"></a>Controlar o serviço de localização após o registro

Você pode ter o serviço de localização ligado (ou desligado) [a](../working-with-managed-desktop/admin-support.md) qualquer momento enviando uma solicitação de suporte por meio do portal [de administração](access-admin-portal.md).

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Como Área de Trabalho Gerenciada da Microsoft configura o serviço de Windows 10 local

Se você optar por usar o serviço de localização, usamos as configurações mínimas necessárias sem afetar a privacidade dos usuários. Para obter mais informações, [consulte Windows 10 local e privacidade.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Área de Trabalho Gerenciada da Microsoft habilita a **configuração de** privacidade local **em Windows para** Permitir o acesso ao local **neste dispositivo**. A interface do usuário tem esta aparência:

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Configurações de local em Windows configurações":::

> [!NOTE]
> Se você optar por usar o serviço de localização, isso se aplica somente ao sistema operacional Windows sistema operacional em si. Os aplicativos não têm permissão para usar serviços de localização. Cada usuário pode escolher se permite que os aplicativos acessem sua localização.