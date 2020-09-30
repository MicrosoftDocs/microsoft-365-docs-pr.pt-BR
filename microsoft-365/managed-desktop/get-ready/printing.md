---
title: Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft
description: Etapas importantes para garantir o trabalho sem problemas de impressão
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5198691a38b179a5491a36de95531edb9f32d691
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48322218"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a>Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft

À medida que você estiver pronto para se inscrever na área de trabalho gerenciada da Microsoft, avalie seus requisitos de impressão e determine a abordagem certa para o seu ambiente. Você tem três opções:
 
- Implantar a solução de impressão universal da Microsoft para facilitar a descoberta de impressoras pelos dispositivos de área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [o que é impressão universal](https://docs.microsoft.com/universal-print/fundamentals/universal-print-whatis).
- Implantar impressoras diretamente usando um script do PowerShell personalizado. Siga as etapas na seção [configurar impressoras locais](#set-up-local-printers) para fazer isso.
- Use uma solução de impressão em nuvem que não seja da Microsoft que seja compatível com dispositivos Windows 10 que fazem parte de um domínio do Azure Active Directory. A solução deve atender aos requisitos de software para a área de trabalho gerenciada da Microsoft. Para obter mais informações, consulte [requisitos de aplicativos de área de trabalho gerenciada da Microsoft](../service-description/mmd-app-requirements.md).
 
Em todos os casos, se os drivers da impressora não estiverem disponíveis no Microsoft Update ou na Microsoft Store, você terá que obtê-los e disponibilizá-los para implantação em seus dispositivos de área de trabalho gerenciada da Microsoft com o Microsoft Intune. Para saber mais, confira [Intune autônomo-gerenciamento de aplicativos Win32](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)

## <a name="set-up-local-printers"></a>Configurar impressoras locais

Se você decidiu implantar impressoras usando um script personalizado do PowerShell e preparou os recursos de impressão, siga estas etapas para ter impressoras compartilhadas implantadas:

1.  Navegue até o portal de área de trabalho gerenciada da Microsoft.
2.  Envie uma solicitação com rótulo de *implantação de impressora* na seção solicitações de suporte de > de **suporte** do portal de administração, fornecendo estes detalhes:
    - Todos os caminhos UNC para locais de impressora compartilhados que precisarão ser implantados para dispositivos de área de trabalho gerenciada da Microsoft
    - Grupos de usuários que exigem acesso a essas impressoras compartilhadas
3.  Usando o portal de administração, vamos informar quando a solicitação foi concluída. Inicialmente, implantaremos apenas a configuração para dispositivos no grupo de implantação de teste.
4.  Você deve testar e confirmar se a configuração funciona conforme o esperado. Responda usando a guia **discussão** na solicitação de suporte para nos informar quando você concluiu o teste.
5.  Em seguida, implantaremos a configuração para outros grupos de implantação.
