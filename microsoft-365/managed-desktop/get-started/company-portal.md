---
title: Instalar o Portal da Empresa do Intune em dispositivos
description: Informações sobre a instalação do aplicativo portal da empresa em dispositivos da Área de Trabalho Gerenciada da Microsoft
keywords: Microsoft Managed Desktop, Microsoft 365, Portal da Empresa
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4c5d20529a210207e225d4a2b46d5935ae112c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925769"
---
# <a name="install-intune-company-portal-on-devices"></a>Instalar o Portal da Empresa do Intune em dispositivos

A Área de Trabalho Gerenciada da Microsoft exige que os administradores de IT instalem o Portal da Empresa do Intune para seus usuários com dispositivos da Área de Trabalho Gerenciada da Microsoft. Aqui estão alguns benefícios para sua organização:
- Os usuários têm um local para navegar e instalar aplicativos disponíveis. 
- Os administradores de IT podem organizar aplicativos por categorias para seus usuários.  
- Alguns aplicativos (como o Microsoft Project e o Microsoft Visio) exigem que o Portal da Empresa implante com a Área de Trabalho Gerenciada da Microsoft.
- Os administradores de IT podem personalizar o Portal da Empresa para sua organização. Isso inclui imagens de marca, adição de contatos de suporte local e muito mais. Para obter mais informações, [consulte How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).   

Este tópico documenta o processo de implantação do Portal da Empresa do Intune para seus usuários da Área de Trabalho Gerenciada da Microsoft. O processo geral tem esta aparência:
1. Comprar o Portal da Empresa na Microsoft Store para Empresas e sincronizar com o Intune
2. Atribuir Portal da Empresa aos seus usuários
3. Comunicar a alteração aos usuários

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Etapa 1 - Comprar Portal da Empresa da Microsoft Store para Empresas e sincronizar com o Intune
Para obter informações sobre como comprar os aplicativos e sincronizar com o Intune, consulte [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in Deploy apps to Microsoft Managed Desktop *devices*.

Este tópico fornece informações sobre como: 
- Comprar o Portal da Empresa da Microsoft Store para Empresas 
- Forçar a sincronização entre o Intune e a Microsoft Store para Empresas
- Verificar a sincronização ativa entre o Intune e a Microsoft Store para Empresas 

## <a name="step-2---assign-company-portal-to-your-users"></a>Etapa 2 - Atribuir Portal da Empresa aos seus usuários
Após seu registro na Área de Trabalho Gerenciada da Microsoft, as Operações de Área de Trabalho Gerenciada da Microsoft implantarão automaticamente o Portal da Empresa em seu locatário e instalarão o aplicativo em dispositivos da Área de Trabalho Gerenciada da Microsoft em sua organização.

## <a name="step-3---communicate-change-to-your-users"></a>Etapa 3 - Comunicar alterações aos usuários
Como administrador de IT da sua organização, é importante que os usuários saibam como usar o Portal da Empresa em sua organização. A Área de Trabalho Gerenciada da Microsoft recomenda:
- Etapas sobre a instalação de aplicativos do Portal da Empresa. Para obter mais informações, [consulte Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).
- Como enviar solicitações aos administradores de IT para aplicativos que não estão disponíveis no momento. Para obter mais informações, [consulte Solicitar um aplicativo para trabalho ou escola.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar com a Área de Trabalho Gerenciada da Microsoft

1. [Adicionar e verificar contatos do administrador no portal de Administração](add-admin-contacts.md)
2. [Ajustar o acesso condicional](conditional-access.md)
3. [Atribuir licenças](assign-licenses.md)
4. Implantar o Portal da Empresa do Intune (este tópico)
5. [Habilitar Roaming de Estado da Empresa](enterprise-state-roaming.md)
6. [Configurar dispositivos](set-up-devices.md)
7. [Preparar usuários para o uso dos dispositivos](get-started-devices.md)
8. [Implantar aplicativos](deploy-apps.md)