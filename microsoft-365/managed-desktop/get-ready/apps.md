---
title: Preparando aplicativos para a área de trabalho gerenciada da Microsoft
description: ''
keywords: Área de trabalho gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289057"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Preparando aplicativos para a área de trabalho gerenciada da Microsoft

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Os clientes de área de trabalho gerenciada da Microsoft e da Microsoft têm responsabilidades igualmente diferentes em relação aos aplicativos usados com a área de trabalho gerenciada da Microsoft.

## <a name="microsoft-responsibilities"></a>Responsabilidades da Microsoft
**Aplicativos do Office 365** A Microsoft fornecerá serviço completo para a implantação, atualização e suporte de aplicativos específicos do Office 365. Todos os usuários receberão o conjunto base do Office 365 clique para executar, versão de 64 bits de aplicativos incluídos na imagem do dispositivo para que um usuário possa se tornar produtivo rapidamente. Os aplicativos do Project e do Visio no pacote do Office 365 são licenciados separadamente.  A área de trabalho gerenciada da Microsoft fornecerá grupos de implantação que permitem ao administrador de ti gerenciar licenças e implantar esses aplicativos apropriadamente para sua organização. A Microsoft dará suporte aos usuários finais desses aplicativos por meio dos canais de suporte do Microsoft Managed desktop.

**Aplicativos de linha de negócios** A Microsoft fornece ferramentas para que os administradores de ti gerenciem e implantem seus aplicativos de linha de negócios (LOB) para os usuários finais como parte do produto do Intune. A Microsoft dará suporte a problemas de implantação de aplicativos, conforme detalhado em [aplicativos de linha de negócios](#line-of-business-applications) 

**Implantar com o Intune** O Intune será vinculado à **Microsoft Store para empresas** durante a integração da área de trabalho gerenciada da Microsoft, permitindo que aplicativos adquiridos sejam implantados por meio do Intune. A Microsoft também implantará o aplicativo portal da empresa da Microsoft Store para os usuários finais, de modo que os administradores de ti possam fornecer uma experiência de autoatendimento para seus usuários finais.

**Gerenciamento de aplicativos** A Microsoft pode identificar aplicativos restritos que não são adequados para o local de trabalho moderno devido ao impacto do sistema. Quando um aplicativo é identificado, a Microsoft notificará o cliente e esse aplicativo deverá ser removido do locatário. 

Para obter mais informações sobre comportamentos de aplicativo restritos e requisitos de aplicativos, consulte [requisitos do aplicativo de área de trabalho gerenciado da Microsoft](../service-description/mmd-app-requirements.md)

## <a name="customer-responsibilities"></a>Responsabilidades do cliente
O pacote do Office 365 é essencial para ofertas de produtividade da Microsoft e está incluído na licença do Microsoft 365 para todos os usuários do Microsoft Managed desktop. Enquanto a Microsoft implanta, atualiza e dá suporte a aplicativos do Office para dispositivos de área de trabalho gerenciada da Microsoft, ainda há algumas áreas nas quais o cliente é responsável.
- **Atribuir licenças** -os clientes são responsáveis por atribuir as licenças apropriadas aos usuários finais do Office 365. 
- **Adicionar usuários a grupos de segurança** -para clientes com usuários que precisam do Project ou do Visio, o administrador de ti deve adicionar esses usuários aos grupos de implantação apropriados. Os administradores de ti também são responsáveis por gerenciar o fim da vida útil desses usuários. 
- **Implantar os complementos do office 365** -os clientes são responsáveis pela implantação de qualquer plug-in no pacote do Office 365 que são considerados necessários. 

Como os aplicativos de linha de negócios (LOB) são exclusivos para cada cliente, os clientes são responsáveis por gerenciar todos os aplicativos em sua organização não implantados pela Microsoft. Isso inclui:
- Decidir quais aplicativos são necessários e quem precisa deles
- Atribuindo aplicativos a esses usuários
- Criar e manter grupos do Azure Active Directory (AD) para gerenciar atribuições de aplicativos 

O cliente deve carregar aplicativos LOB no Intune. Eles são, então, responsáveis pela implantação, atualização e encerramento desses aplicativos sobre seus respectivos ciclos de vida, além de gerenciar o suporte para esses aplicativos para seus usuários.

## <a name="office-applications"></a>Aplicativos do Office
Como parte da licença do Microsoft 365 e5, o Office 365 Standard Suite (64 bit) é implantado pela Microsoft. 

Para obter detalhes, consulte [tecnologias de área de trabalho gerenciaDa da Microsoft](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>Aplicativos de linha de negócios
Esta tabela resume as responsabilidades em diferentes fases para aplicativos de linha de negócios (LOB). 

Itens de trabalho do aplicativo |    Cliente    | Microsoft
--- | --- | ---
**Aplicativos de integração** |  |
Identificar aplicativos necessários para grupos de usuários de destino   | ![sim](images/checkmark.png)  |
Criar e gerenciar grupos do Azure AD para implantação de aplicativos | ![sim](images/checkmark.png) |   
**Pacote de aplicativos** |  |
Empacotar aplicativos para atender aos padrões de implantação do Intune |  ![sim](images/checkmark.png) |  
Carregar aplicativos no Intune | ![sim](images/checkmark.png)     |
Testar aplicativos no ambiente de área de trabalho gerenciada da Microsoft |    ![sim](images/checkmark.png) |  
Testar aplicativos com usuários finais    | ![sim](images/checkmark.png) |    
**Implantação** | |
Gerenciar e atribuir usuários aos aplicativos  | ![sim](images/checkmark.png)  |
As ferramentas de implantação do Intune fornecem aplicativos para clientes remotos| |   ![sim](images/checkmark.png)
Identificar e implantar atualizações de aplicativos por meio do Intune | ![sim](images/checkmark.png)    |
Desinstalar e remover aplicativos quando eles tiverem sido desativados    | ![sim](images/checkmark.png) |    
**Gerenciamento** | |
Adquirir e atribuir licenças |   ![sim](images/checkmark.png)     |
Fornecer suporte ao usuário final para aplicativos de linha de negócios  | ![sim](images/checkmark.png) |
Gerenciar as configurações do aplicativo remotamente    | ![sim](images/checkmark.png) |

Para obter informações sobre requisitos de aplicativos LOB, consulte [requisitos de aplicativos de área de trabalho gerenciaDa da Microsoft](../service-description/mmd-app-requirements.md)


## <a name="intune-application-deployment"></a>Implantação de aplicativo do Intune
O gerenciamento de aplicativos pode ser manipulado pelo portal de administração de área de trabalho gerenciada da Microsoft ou por meio do portal do Intune. O portal de gerenciamento de aplicativos do Intune mostra aplicativos implantados para Windows, Android e iOS. O portal de administração do Microsoft Managed desktop limita o modo de exibição aos aplicativos do Windows 10. Ambos estão disponíveis por meio do portal do Azure. 
* [Noções básicas do gerenciamento de aplicativos do Intune](https://docs.microsoft.com/intune/app-management)
* [Adicionar aplicativos ao Intune](https://docs.microsoft.com/intune/app-management)
   * [Adicionar um aplicativo de linha de negócios](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Adicionar aplicativos Win32 ao Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Adicionar aplicativos Web](https://docs.microsoft.com/intune/web-app)
* [Implantar aplicativos](https://docs.microsoft.com/intune/apps-deploy)
   * [Implantar aplicativos no Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Portal da empresa
   * [Implantar o portal da empresa](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configurar o aplicativo do portal da empresa](https://docs.microsoft.com/intune/company-portal-app)
