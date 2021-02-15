---
title: Instalar o Portal da Empresa do Intune em dispositivos
description: Informações sobre como instalar o aplicativo de portal da empresa em dispositivos da Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, Portal da Empresa
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939279"
---
# <a name="install-intune-company-portal-on-devices"></a>Instalar o Portal da Empresa do Intune em dispositivos

A Área de Trabalho Gerenciada da Microsoft exige que os administradores de IT instalem o Portal da Empresa do Intune para seus usuários com dispositivos da Área de Trabalho Gerenciada da Microsoft. Aqui estão alguns benefícios para sua organização:
- Os usuários têm um local para procurar e instalar aplicativos disponíveis. 
- Os administradores de IT podem organizar aplicativos por categorias para seus usuários.  
- Alguns aplicativos (como o Microsoft Project e o Microsoft Visio) exigem que o Portal da Empresa seja implantado com a Área de Trabalho Gerenciada da Microsoft.
- Os administradores de IT podem personalizar o Portal da Empresa para sua organização. Isso inclui a imagem da marca, a adição de contatos de suporte local e muito mais. Para obter mais informações, consulte Como configurar o aplicativo portal da empresa [do Microsoft Intune.](https://docs.microsoft.com/intune/company-portal-app)   

Este tópico documenta o processo de implantação do Portal da Empresa do Intune para os usuários da Área de Trabalho Gerenciada da Microsoft. O processo geral tem esta aparência:
1. Adquirir o Portal da Empresa na Microsoft Store para Empresas e sincronizar com o Intune
2. Atribuir o Portal da Empresa aos seus usuários
3. Comunicar a alteração aos usuários

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>Etapa 1: Comprar o Portal da Empresa na Microsoft Store para Empresas e sincronizar com o Intune
Para obter informações sobre como comprar os aplicativos e sincronizar com o Intune, consulte os aplicativos da [Microsoft Store](deploy-apps.md#msfb-apps) para Empresas em Implantar aplicativos em dispositivos da Área de *Trabalho Gerenciada da Microsoft.*

Este tópico fornece informações sobre como: 
- Purchase Company Portal from Microsoft Store for Business 
- Forçar a sincronização entre o Intune e a Microsoft Store para Empresas
- Verificar a sincronização ativa entre o Intune e a Microsoft Store para Empresas 

## <a name="step-2---assign-company-portal-to-your-users"></a>Etapa 2- Atribuir o Portal da Empresa aos seus usuários
Após o registro na Área de Trabalho Gerenciada da Microsoft, as Operações da Área de Trabalho Gerenciada da Microsoft implantarão automaticamente o Portal da Empresa em seu locatário e instalarão o aplicativo em dispositivos da Área de Trabalho Gerenciada da Microsoft em sua organização.

## <a name="step-3---communicate-change-to-your-users"></a>Etapa 3: comunicar as alterações aos usuários
Como administrador de IT da sua organização, é importante que os usuários saibam como usar o Portal da Empresa em sua organização. A Área de Trabalho Gerenciada da Microsoft recomenda:
- Etapas para instalar aplicativos do Portal da Empresa. Para obter mais informações, [consulte Instalar e compartilhar aplicativos em seu dispositivo.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)
- Como enviar solicitações para administradores de IT para aplicativos que não estão disponíveis no momento. Para obter mais informações, [consulte Solicitar um aplicativo para trabalho ou escola.](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Etapas para começar a trabalhar com a Área de Trabalho Gerenciada da Microsoft

1. [Adicionar e verificar contatos do administrador no portal de Administração](add-admin-contacts.md)
2. [Ajustar o acesso condicional](conditional-access.md)
3. [Atribuir licenças](assign-licenses.md)
4. Implantar o Portal da Empresa do Intune (este tópico)
5. [Habilitar Roaming de Estado da Empresa](enterprise-state-roaming.md)
6. [Configurar dispositivos](set-up-devices.md)
7. [Preparar usuários para o uso dos dispositivos](get-started-devices.md)
8. [Implantar aplicativos](deploy-apps.md)
