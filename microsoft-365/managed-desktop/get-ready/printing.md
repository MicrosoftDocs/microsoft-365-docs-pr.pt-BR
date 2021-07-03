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
audience: Admin
ms.openlocfilehash: 3f77074aa11e9dc82c8fac9763fdebfd2fc49d99
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287204"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft

À medida que você se prepara para se inscrever no Área de Trabalho Gerenciada da Microsoft, você deve avaliar seus requisitos de impressão e determinar a abordagem correta para seu ambiente. Você tem três opções:

- Implante a solução de Impressão Universal da Microsoft para facilitar a descoberta de Área de Trabalho Gerenciada da Microsoft dispositivos. Para obter mais informações, consulte [O que é Impressão Universal](/universal-print/fundamentals/universal-print-whatis).
- Implante impressoras diretamente usando um script personalizado do PowerShell. Siga as etapas na seção [Configurar impressoras](#set-up-local-printers) locais.
- Use uma solução de impressão em nuvem que não seja da Microsoft que seja compatível com Windows 10 que estão ingressados em um Azure Active Directory domínio. A solução deve atender aos requisitos de software para Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, [consulte Área de Trabalho Gerenciada da Microsoft aplicativos](../service-description/mmd-app-requirements.md).
 
Em todos os casos, se os drivers de impressora não estão disponíveis no Microsoft Update ou no Microsoft Store, você terá que obtém-los por conta própria e empacotá-los para implantação em seus dispositivos Área de Trabalho Gerenciada da Microsoft com Microsoft Intune. Para obter mais, consulte [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurar impressoras locais

Se você decidiu implantar impressoras usando um script personalizado do PowerShell e preparou os recursos de impressão, siga estas etapas para implantar impressoras compartilhadas:

1. Navegue até o Área de Trabalho Gerenciada da Microsoft portal.
2. Envie uma solicitação *rotulada* implantação de Impressora na seção **Solicitações** de Suporte > suporte do Portal de Administração, fornecendo estes detalhes:
    - Todos os caminhos UNC para locais de impressora compartilhado que precisarão ser implantados para Área de Trabalho Gerenciada da Microsoft dispositivos
    - Grupos de usuários que exigem acesso a essas impressoras compartilhadas
3. Usando o Portal de Administração, você saberá quando a solicitação for concluída. Inicialmente, implantaremos apenas a configuração em dispositivos no grupo de implantação de teste.
4. Você deve testar e confirmar se a configuração funciona conforme o esperado. Responda usando a guia **Discussão** na solicitação de Suporte para nos dizer quando você concluiu o teste.
5. Em seguida, implantaremos a configuração nos outros grupos de implantação.

## <a name="steps-to-get-ready"></a>Etapas para se preparar

1. Revise [os pré-requisitos para Área de Trabalho Gerenciada da Microsoft](prerequisites.md).
2. Use [ferramentas de avaliação de preparação.](readiness-assessment-tool.md)
3. [Pré-requisitos para contas de convidado](guest-accounts.md)
4. [Configuração de rede na Área de Trabalho Gerenciada da Microsoft](network.md)
5. [Preparar certificados e perfis de rede da Área de Trabalho Gerenciada da Microsoft](certs-wifi-lan.md)
6. [Preparar o acesso aos recursos locais da Área de Trabalho Gerenciada da Microsoft](authentication.md)
7. [Aplicativos na Área de Trabalho Gerenciada da Microsoft](apps.md)
8. [Preparar unidades mapeadas da Área de Trabalho Gerenciada da Microsoft](mapped-drives.md)
9. [Preparar recursos de impressão para Área de Trabalho Gerenciada da Microsoft](printing.md) (Este artigo)
