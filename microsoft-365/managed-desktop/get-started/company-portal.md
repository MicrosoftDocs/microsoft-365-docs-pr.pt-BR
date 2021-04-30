---
title: Instalar Portal da Empresa do Intune em dispositivos
description: Informações sobre como instalar o aplicativo portal da empresa em Área de Trabalho Gerenciada da Microsoft dispositivos
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, Portal da Empresa
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086680"
---
# <a name="install-intune-company-portal-on-devices"></a>Instalar Portal da Empresa do Intune em dispositivos

Área de Trabalho Gerenciada da Microsoft requer que os administradores dem Portal da Empresa do Intune para seus usuários com Área de Trabalho Gerenciada da Microsoft dispositivos. Aqui estão alguns benefícios para sua organização:
- Os usuários têm um local para navegar e instalar aplicativos disponíveis. 
- Os administradores de IT podem organizar aplicativos por categorias para seus usuários.  
- Alguns aplicativos (como Microsoft Project e Microsoft Visio) exigem Portal da Empresa para implantar com Área de Trabalho Gerenciada da Microsoft.
- Os administradores de IT podem personalizar Portal da Empresa para sua organização. Isso inclui imagens de marca, adição de contatos de suporte local e muito mais. Para obter mais informações, [consulte How to Configure the Microsoft Intune Portal da Empresa app](/intune/company-portal-app).   

Este tópico documenta o processo de implantação do Portal da Empresa do Intune para seus Área de Trabalho Gerenciada da Microsoft usuários. O processo geral tem esta aparência:
1. Comprar Portal da Empresa do Microsoft Store para Empresas e sincronizar com o Intune
2. Atribuir Portal da Empresa aos usuários
3. Comunicar a alteração aos usuários

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Etapa 1 - Comprar Portal da Empresa de Microsoft Store para Empresas sincronizar com o Intune
Para obter informações sobre como comprar os aplicativos e sincronizar com o Intune, consulte [Microsoft Store para Empresas aplicativos](deploy-apps.md#msfb-apps) em *Implantar aplicativos para Área de Trabalho Gerenciada da Microsoft dispositivos*.

Este tópico fornece informações sobre como: 
- Comprar Portal da Empresa de Microsoft Store para Empresas 
- Forçar a sincronização entre o Intune e Microsoft Store para Empresas
- Verificar a sincronização ativa entre o Intune e o Microsoft Store para Empresas 

## <a name="step-2---assign-company-portal-to-your-users"></a>Etapa 2 - Atribuir Portal da Empresa aos usuários
Após seu registro no Área de Trabalho Gerenciada da Microsoft, implantaremos automaticamente Portal da Empresa seu locatário e instalaremos o aplicativo em Área de Trabalho Gerenciada da Microsoft dispositivos em sua organização.

## <a name="step-3---communicate-change-to-your-users"></a>Etapa 3 - Comunicar alterações aos usuários
Como administrador de IT da sua organização, é importante que os usuários saibam como usar Portal da Empresa em sua organização. Área de Trabalho Gerenciada da Microsoft recomenda:
- Etapas sobre a instalação de aplicativos do Portal da Empresa. Para obter mais informações, [consulte Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).
- Como enviar solicitações aos administradores de IT para aplicativos que não estão disponíveis no momento. Para obter mais informações, [consulte Solicitar um aplicativo para trabalho ou escola.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar a Área de Trabalho Gerenciada da Microsoft

1. [Adicionar e verificar contatos do administrador no portal de Administração](add-admin-contacts.md)
2. [Ajustar o acesso condicional](conditional-access.md)
3. [Atribuir licenças](assign-licenses.md)
4. Implantar Portal da Empresa do Intune (este tópico)
5. [Habilitar Roaming de Estado da Empresa](enterprise-state-roaming.md)
6. [Configurar dispositivos](set-up-devices.md)
7. [Preparar usuários para o uso dos dispositivos](get-started-devices.md)
8. [Implantar aplicativos](deploy-apps.md)
