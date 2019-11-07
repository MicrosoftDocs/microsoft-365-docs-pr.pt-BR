---
title: Instalar o portal da empresa do Intune em dispositivos
description: Informações sobre a instalação do aplicativo portal da empresa em dispositivos de área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, portal da empresa
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 121771dd2474d58e7bd6a0d56218563c8785d4bf
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "38011952"
---
# <a name="install-intune-company-portal-on-on-devices"></a>Instalar o portal da empresa do Intune em dispositivos

O Microsoft Managed desktop exige que os administradores de ti instalem o portal da empresa do Intune para seus usuários com dispositivos de área de trabalho gerenciada da Microsoft Veja alguns benefícios da sua organização:
- Os usuários têm um local para procurar e instalar aplicativos disponíveis. 
- Os administradores de ti podem organizar os aplicativos por categorias para seus usuários.  
- Alguns aplicativos (como o Microsoft Project e o Microsoft Visio) exigem que o portal da empresa implante com a área de trabalho gerenciada da Microsoft.
- Os administradores de ti podem personalizar o portal da empresa para sua organização. Isso inclui imagens de marca, adição em contatos de suporte local e muito mais. Para obter mais informações, consulte [como configurar o aplicativo do portal da empresa do Microsoft Intune](https://docs.microsoft.com/intune/company-portal-app).   

Este tópico documenta o processo de implantação do portal da empresa do Intune em seus usuários de área de trabalho gerenciada da Microsoft. O processo geral tem a seguinte aparência:
1. Comprar portal da empresa da Microsoft Store para empresas e sincronizar com o Intune
2. Atribuir portal da empresa aos usuários
3. Comunicar alterações para seus usuários

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Etapa 1: comprar o portal da empresa da Microsoft Store para empresas e sincronizar com o Intune
Para obter informações sobre como comprar os aplicativos e sincronizar com o Intune, consulte [Microsoft Store para aplicativos comerciais](deploy-apps.md#msfb-apps) em *implantar aplicativos em dispositivos de área de trabalho gerenciada da Microsoft*.

Este tópico fornece informações sobre como: 
- Comprar portal da empresa da Microsoft Store para empresas 
- Forçar sincronização entre o Intune e a Microsoft Store para empresas
- Verificar a sincronização ativa entre o Intune e a Microsoft Store para empresas 

## <a name="step-2---assign-company-portal-to-your-users"></a>Etapa 2-atribuir o portal da empresa aos seus usuários
Envie uma solicitação de suporte para operações de área de trabalho gerenciada da Microsoft por meio do portal de administração do Microsoft Managed desktop. Na solicitação de suporte, solicite que o portal da empresa seja atribuído aos seus usuários. O Microsoft Managed desktop implantará o portal da empresa em seu locatário e instalará o aplicativo em dispositivos de área de trabalho gerenciada da Microsoft em sua organização.

Para obter mais informações sobre como enviar solicitações de suporte com a área de trabalho gerenciada da Microsoft, consulte [admin support for Microsoft Managed desktop](../working-with-managed-desktop/admin-support.md).

## <a name="step-3---communicate-change-to-your-users"></a>Etapa 3-comunicar alterações para seus usuários
Como administrador de ti da sua organização, é importante permitir que os usuários saibam como usar o portal da empresa em sua organização. O Microsoft Managed desktop recomenda:
- Etapas de instalação de aplicativos do portal da empresa. Para obter mais informações, consulte [Install and share apps in your Device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).
- Como enviar solicitações para os administradores de ti para aplicativos que não estão disponíveis no momento.

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar a usar a área de trabalho gerenciada da Microsoft

1. [Adicionar e verificar contatos de administrador no portal de administração](add-admin-contacts.md)
2. [Ajustar o acesso condicional](conditional-access.md)
3. [Atribuir licenças](assign-licenses.md)
4. Implantar o portal da empresa do Intune (este tópico)
5. [Habilitar roaming de estado corporativo](enterprise-state-roaming.md)
6. [Configurar dispositivos](set-up-devices.md)
7. [Preparar usuários para o uso dos dispositivos](get-started-devices.md)
8. [Implantar aplicativos](deploy-apps.md)