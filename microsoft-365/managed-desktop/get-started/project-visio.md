---
title: Instalar o Microsoft Project ou o Microsoft Visio em dispositivos da Área de Trabalho Gerenciada da Microsoft
description: Informações sobre como instalar o Microsoft Project ou o Microsoft Visio em dispositivos da Área de Trabalho Gerenciada da Microsoft
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950527"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Instalar o Microsoft Project ou o Microsoft Visio em dispositivos da Área de Trabalho Gerenciada da Microsoft

O Microsoft Project e o Microsoft Visio exigem que etapas específicas sejam instaladas em dispositivos da Área de Trabalho Gerenciada da Microsoft. Este tópico documenta os pré-requisitos e o processo de instalação desses aplicativos.

## <a name="prerequisites"></a>Pré-requisitos

Os administradores devem verificar se atendem a esses pré-requisitos:
- **Quantidades de** licenças - a quantidade correta de licenças do Microsoft Project e do Microsoft Visio deve estar disponível para seus usuários. A Área de Trabalho Gerenciada da Microsoft atualmente só dá suporte a versões de 64 bits desses aplicativos. 
- **Nomes de licença** - Os nomes de licença apropriados para esses aplicativos são:
    - **Microsoft Project** - Project Online Professional ou Project Online Premium
    - **Microsoft Visio** - Plano 2 do Visio Online
- **Portal da** Empresa - O Portal da Empresa deve estar disponível em seu locatário para que os usuários instalem esses aplicativos. Se o Portal da Empresa não estiver implantado em seu locatário, consulte [o Portal da Empresa.](company-portal.md)

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Implantar o Project e o Visio para dispositivos da Área de Trabalho Gerenciada da Microsoft
A Área de Trabalho Gerenciada da Microsoft adicionará o Microsoft Project e o Microsoft Visio como dois Aplicativos Win32 no Microsoft Intune. Também criaremos dois grupos no Azure Active Directory que serão atribuídos ao aplicativo correspondente com a intenção "Disponível". 

**Para implantar o Project e o Visio** Adicione o usuário ao grupo apropriado e o aplicativo ficará disponível no Portal da Empresa. Pode levar alguns minutos para sincronizar, mas os usuários podem instalar os aplicativos do Portal da Empresa. 

Nome do grupo do Azure AD | Quais usuários atribuir?   
 --- | ---
Modern Workplace-Office-Project_Install | Usuários que precisam do Project
Modern Workplace-Office-Visio_Install | Usuários que precisam do Visio

## <a name="communicate-changes"></a>Comunicar alterações
É importante que os administradores de IT saibam aos usuários como instalar o Project e o Visio. Isso inclui: 
- Notificar os usuários quando esses aplicativos estão disponíveis para eles. 
- Instruções sobre como instalar esses aplicativos do Portal da Empresa.
