---
title: Instalar Microsoft Project microsoft Visio em Área de Trabalho Gerenciada da Microsoft dispositivos
description: Informações sobre como instalar o Microsoft Project ou o Microsoft Visio em Área de Trabalho Gerenciada da Microsoft dispositivos
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
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Instalar Microsoft Project microsoft Visio em Área de Trabalho Gerenciada da Microsoft dispositivos

Microsoft Project e o Microsoft Visio exigem etapas específicas para serem instaladas em Área de Trabalho Gerenciada da Microsoft dispositivos. Este tópico documenta os pré-requisitos e o processo de instalação desses aplicativos.

## <a name="prerequisites"></a>Pré-requisitos

Os administradores devem verificar se atendem a esses pré-requisitos:
- **Quantidades de** licença - A quantidade correta de Microsoft Project e licenças do Microsoft Visio devem estar disponíveis para seus usuários. Área de Trabalho Gerenciada da Microsoft atualmente suporta apenas versões de 64 bits desses aplicativos. 
- **Nomes de licença** - Os nomes de licença apropriados para esses aplicativos são:
    - **Microsoft Project** - Project Online Professional ou Project Online Premium
    - **Microsoft Visio** - Visio Plano Online 2
- **Portal da Empresa** - o Portal da Empresa deve estar disponível em seu locatário para que os usuários instalem esses aplicativos. Se o Portal da Empresa não for implantado em seu locatário, [consulte Portal da Empresa](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Implantar Project e Visio para Área de Trabalho Gerenciada da Microsoft dispositivos
Área de Trabalho Gerenciada da Microsoft adicionará Microsoft Project microsoft Visio como dois aplicativos Win32 no Microsoft Intune. Também criaremos dois grupos em Azure Active Directory que serão atribuídos ao aplicativo correspondente com a intenção "Disponível". 

**Para implantar Project e Visio** Adicione o usuário ao grupo apropriado e o aplicativo ficará disponível no Portal da Empresa. Pode levar alguns minutos para sincronizar, mas os usuários podem instalar os aplicativos Portal da Empresa. 

Nome do grupo do Azure AD | Quais usuários atribuir?   
 --- | ---
Modern Workplace-Office-Project_Install | Usuários que precisam de Project
Modern Workplace-Office-Visio_Install | Usuários que precisam de Visio

## <a name="communicate-changes"></a>Comunicar alterações
É importante que os administradores de IT saibam aos usuários como instalar Project e Visio. Isso inclui: 
- Notificando os usuários quando esses aplicativos estão disponíveis para eles. 
- Instruções sobre como instalar esses aplicativos do Portal da Empresa.
