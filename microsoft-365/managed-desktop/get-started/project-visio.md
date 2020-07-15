---
title: Instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft
description: Informações sobre como instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126822"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Instalar o Microsoft Project ou o Microsoft Visio em dispositivos de área de trabalho gerenciada da Microsoft

O Microsoft Project e o Microsoft Visio exigem que etapas específicas sejam instaladas em dispositivos de área de trabalho gerenciada da Microsoft. Este tópico documenta os pré-requisitos e o processo de instalação desses aplicativos.

## <a name="prerequisites"></a>Pré-requisitos

Os administradores devem verificar se eles atendem a estes pré-requisitos:
- **Quantidade de licenças** -a quantidade correta de licenças do Microsoft Project e do Microsoft Visio deve estar disponível para os usuários. Atualmente, a área de trabalho gerenciada da Microsoft dá suporte apenas a versões de 64 bits desses aplicativos. 
- **Nomes de licença** : os nomes de licença apropriados para esses aplicativos são:
    - **Microsoft Project** -Project online Professional ou Project Online Premium
    - **Microsoft Visio** -Visio online plano 2
- **Portal da empresa** -o portal da empresa deve estar disponível em seu locatário para que os usuários instalem esses aplicativos. Se o portal da empresa não estiver implantado em seu locatário, confira [portal da empresa](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Implantar o Project e o Visio para dispositivos de área de trabalho gerenciada da Microsoft
A área de trabalho gerenciada da Microsoft adicionará o Microsoft Project e o Microsoft Visio como dois aplicativos Win32 no Microsoft Intune. Também criaremos dois grupos no Azure Active Directory que serão atribuídos ao aplicativo correspondente com a intenção "disponível". 

**Para implantar o Project e o Visio** Adicione o usuário ao grupo apropriado e o aplicativo ficará disponível no portal da empresa. Pode levar alguns minutos para sincronizar, mas os usuários podem instalar os aplicativos do portal da empresa. 

Nome do grupo do Azure AD | Quais usuários serão atribuídos?   
 --- | ---
Área de trabalho moderna-Office-Project_Install | Usuários que precisam de projeto
Área de trabalho moderna-Office-Visio_Install | Usuários que precisam do Visio

## <a name="communicate-changes"></a>Comunicar alterações
É importante para os administradores de ti permitir que seus usuários saibam como instalar o Project e o Visio. Isso inclui: 
- Notificar os usuários quando esses aplicativos estiverem disponíveis para eles. 
- Instruções sobre como instalar esses aplicativos do portal da empresa.
