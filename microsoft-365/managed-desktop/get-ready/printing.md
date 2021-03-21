---
title: Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft
description: Etapas importantes para garantir que a impressão funcione sem problemas
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 3decc7d67decc5557e7921e68108e2ddb447f0fd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924547"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft

À medida que você se prepara para se inscrever na Área de Trabalho Gerenciada da Microsoft, você deve avaliar seus requisitos de impressão e determinar a abordagem correta para seu ambiente. Você tem três opções:
 
- Implante a solução de Impressão Universal da Microsoft para facilitar a descoberta de impressoras para dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [O que é Impressão Universal](/universal-print/fundamentals/universal-print-whatis).
- Implante impressoras diretamente usando um script personalizado do PowerShell. Siga as etapas na seção [Configurar impressoras](#set-up-local-printers) locais.
- Use uma solução de impressão em nuvem que não seja da Microsoft compatível com dispositivos Windows 10 que estão ingressados em um domínio do Azure Active Directory. A solução deve atender aos requisitos de software para a Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).
 
Em todos os casos, se os drivers de impressora não estão disponíveis no Microsoft Update ou na Microsoft Store, você terá que obtém-los por conta própria e empacotá-los para implantação em seus dispositivos da Área de Trabalho Gerenciada da Microsoft com o Microsoft Intune. Para obter mais, consulte [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurar impressoras locais

Se você decidiu implantar impressoras usando um script personalizado do PowerShell e preparou os recursos de impressão, siga estas etapas para implantar impressoras compartilhadas:

1.  Navegue até o portal da Área de Trabalho Gerenciada da Microsoft.
2.  Envie uma solicitação *rotulada* implantação de Impressora na seção **Solicitações** de Suporte > suporte do Portal de Administração, fornecendo estes detalhes:
    - Todos os caminhos UNC para locais de impressora compartilhado que precisarão ser implantados para dispositivos da Área de Trabalho Gerenciada da Microsoft
    - Grupos de usuários que exigem acesso a essas impressoras compartilhadas
3.  Usando o Portal de Administração, você saberá quando a solicitação for concluída. Inicialmente, implantaremos apenas a configuração em dispositivos no grupo de implantação de teste.
4.  Você deve testar e confirmar se a configuração funciona conforme o esperado. Responda usando a guia **Discussão** na solicitação de Suporte para nos dizer quando você concluiu o teste.
5.  Em seguida, implantaremos a configuração nos outros grupos de implantação.