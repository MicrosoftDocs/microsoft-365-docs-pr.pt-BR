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
ms.openlocfilehash: b6e809505fed8b1f84eb502dc08751ad1f0b587c
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841394"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft

À medida que você se preparar para se inscrever na Área de Trabalho Gerenciada da Microsoft, avalie seus requisitos de impressão e determine a abordagem correta para seu ambiente. Você tem três opções:
 
- Implante a solução Microsoft Universal Print para facilitar a descoberta de impressoras por dispositivos da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [O que é Impressão Universal.](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis)
- Implante impressoras diretamente usando um script personalizado do PowerShell. Siga as etapas na [seção Configurar impressoras](#set-up-local-printers) locais.
- Use uma solução de impressão em nuvem que não seja da Microsoft compatível com dispositivos Windows 10 que fazem parte de um domínio do Azure Active Directory. A solução deve atender aos requisitos de software da Área de Trabalho Gerenciada da Microsoft. Para obter mais informações, consulte [Requisitos de aplicativo da Área de Trabalho Gerenciada da Microsoft.](../service-description/mmd-app-requirements.md)
 
Em todos os casos, se os drivers de impressora não estão disponíveis no Microsoft Update ou na Microsoft Store, você terá que obtém-los por conta própria e empacotá-los para implantação em seus dispositivos da Área de Trabalho Gerenciada da Microsoft com o Microsoft Intune. Para saber mais, confira [o Gerenciamento de aplicativos do Intune Autônomo - Win32](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurar impressoras locais

Se você decidiu implantar impressoras usando um script personalizado do PowerShell e preparou os recursos de impressão, siga estas etapas para implantar impressoras compartilhadas:

1.  Navegue até o portal da Área de Trabalho Gerenciada da Microsoft.
2.  Envie uma solicitação *rotulada* implantação de impressora na seção **solicitações de** suporte > suporte do Portal de Administração, fornecendo estes detalhes:
    - Todos os caminhos UNC para locais de impressora compartilhados que precisarão ser implantados para dispositivos da Área de Trabalho Gerenciada da Microsoft
    - Grupos de usuários que exigem acesso a essas impressoras compartilhadas
3.  Usando o Portal de Administração, nós o mostraremos quando a solicitação for concluída. Inicialmente, implantaremos apenas a configuração em dispositivos no grupo de implantação Teste.
4.  Você deve testar e confirmar se a configuração funciona como esperado. Responda usando a guia **Discussão** na solicitação de Suporte para nos dizer quando você concluiu o teste.
5.  Em seguida, implantaremos a configuração em outros grupos de implantação.
