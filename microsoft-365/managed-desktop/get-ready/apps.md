---
title: Preparar os aplicativos para o Microsoft gerenciados a área de trabalho
description: ''
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b46e3de4a4cfe2140574ab9fc589e3a738bd2e17
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864882"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Preparar os aplicativos para o Microsoft gerenciados a área de trabalho

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Clientes de Microsoft e Microsoft Desktop gerenciados igualmente têm responsabilidades críticas, embora seja diferentes em torno de aplicativos usados com o Microsoft Desktop gerenciados.

## <a name="microsoft-responsibilities"></a>Responsabilidades da Microsoft
**Aplicativos do Office 365** Microsoft fornecerá o serviço completo para a implantação, atualização e suporte de aplicativos específicos do Office 365. Todos os usuários receberão o conjunto de base do Office 365 clique para executar a versão de 64 bits dos aplicativos incluídos na imagem do dispositivo, de forma que um usuário pode se tornar produtivo rapidamente. Os aplicativos de projeto e o Visio do pacote Office 365 são licenciados separadamente.  Microsoft Desktop gerenciados fornecerá os grupos de implantação, permitindo que o administrador de TI gerenciar licenças e implantar esses aplicativos de forma adequada para sua organização. Microsoft dará suporte a usuários finais desses aplicativos por meio de canais Microsoft Desktop gerenciados suporte.

**Aplicativos de linha de negócios** A Microsoft fornece ferramentas para os administradores de TI a gerenciar e implantar seus aplicativos do linha de negócios (LOB) aos usuários finais como parte do produto Intune. A Microsoft oferecerá suporte a problemas de implantação de aplicativo conforme detalhado nos [aplicativos de linha de negócios](#line-of-business-applications) 

**Implantar com Intune** Durante a inclusão de Microsoft Desktop gerenciados, permitindo que aplicativos adquiridos a serem implantados por meio de Intune Intune será vinculado no **Armazenamento da Microsoft para a empresa** . Microsoft também implantar a versão baseada na web do Portal da empresa aos usuários finais para que os administradores de TI pode fornecer uma experiência de autoatendimento para usuários finais.

**Gerenciamento de aplicativo** Microsoft pode identificar aplicativos restritos que não são adequados para o local de trabalho moderno por causa impacto sobre o seu sistema. Quando esse aplicativo é identificado Microsoft notificará o cliente e desse aplicativo precisará ser removido do inquilino. 

Para obter mais informações em requisitos de aplicativo e comportamentos de app restrita, consulte [requisitos de app do Microsoft Desktop gerenciados](../service-description/mmd-app-requirements.md)

## <a name="customer-responsibilities"></a>Responsabilidades do cliente
Pacote Office 365 são fundamentais para as ofertas de produtividade da Microsoft e está incluso na licença Microsoft 365 para todos os usuários do Microsoft Desktop gerenciados. Enquanto o Microsoft implanta, atualiza e oferece suporte a aplicativos do Office para os dispositivos de área de trabalho gerenciada da Microsoft ainda há algumas áreas para o qual o cliente é responsável.
- **Atribuir licenças** - os clientes são responsáveis para atribuir as licenças apropriadas aos usuários finais para o Office 365. 
- **Adicionar usuários a grupos de segurança** - para clientes com usuários que precisam de projeto ou do Visio, o administrador de TI deve adicionar esses usuários para os grupos de implantação apropriado. Os administradores de TI também estão responsáveis pelo gerenciamento do fim da vida útil para os usuários. 
- **Implantar o Office 365 complementos** - clientes são responsáveis pela implantação qualquer plug-ins para o pacote do Office 365 que serão considerados necessárias. 

Como os aplicativos de linha de negócios (LOB) são exclusivos para cada cliente, os clientes estão responsáveis pelo gerenciamento de todos os aplicativos dentro de sua organização não implantado pela Microsoft. Isso inclui:
- Decidindo quais aplicativos são necessários e quem precisa-los
- Atribuindo aplicativos aos usuários
- Criar e manter os grupos do Windows Azure AD (Active Directory) para gerenciar as atribuições de aplicativo 

O cliente deve carregar aplicativos LOB para Intune. Eles são então responsáveis por implantando, atualização e encerrando esses aplicativos durante seus respectivos ciclos, bem como gerenciar o suporte para esses aplicativos para seus usuários.

## <a name="office-applications"></a>Aplicativos do Office
Como parte da licença do Microsoft 365 E5, o Office 365 Standard Suite (64 bits) é implantado pela Microsoft. 

Para obter detalhes, consulte [tecnologias Microsoft Desktop gerenciados](../intro/technologies.md)<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a>Aplicativos de linha de negócios
Esta tabela resume as responsabilidades entre as fases diferentes para aplicativos de linha de negócios (LOB). 

Itens de trabalho do aplicativo |    Cliente    | Microsoft
--- | --- | ---
**Inclusão de aplicativos** |  |
Identificar aplicativos necessários para grupos de usuários de destino   | ![sim](images/checkmark.png)  |
Criar e gerenciar grupos do Azure AD para implantação de aplicativo | ![sim](images/checkmark.png) |   
**Empacotamento de aplicativo** |  |
Pacote de aplicativos para cumprir os padrões de implantação Intune |  ![sim](images/checkmark.png) |  
Carregar os aplicativos Intune | ![sim](images/checkmark.png)     |
Aplicativos de teste no ambiente de área de trabalho gerenciada do Microsoft |    ![sim](images/checkmark.png) |  
Teste de aplicativos com usuários finais    | ![sim](images/checkmark.png) |    
**Implantação** | |
Gerenciar e atribuir usuários a aplicativos  | ![sim](images/checkmark.png)  |
Ferramentas de implantação Intune fornece o aplicativo aos clientes remotos| |   ![sim](images/checkmark.png)
Identificar e implantar atualizações de aplicativos por meio de Intune | ![sim](images/checkmark.png)    |
Desinstala e remova os aplicativos quando eles foram retirados    | ![sim](images/checkmark.png) |    
**Gerenciamento** | |
Adquirir e atribuir licenças |   ![sim](images/checkmark.png)     |
Oferecer suporte ao usuário final para aplicativos de linha de negócios  | ![sim](images/checkmark.png) |
Gerenciar configurações de aplicativo remotamente    | ![sim](images/checkmark.png) |

Para obter informações sobre os requisitos de aplicativos LOB, consulte [requisitos de aplicativos de área de trabalho gerenciada do Microsoft](../service-description/mmd-app-requirements.md)


## <a name="intune-application-deployment"></a>Implantação de aplicativos Intune
Gerenciamento de aplicativos pode ser manipulado através do portal de administração de área de trabalho gerenciada da Microsoft ou por meio do portal Intune. Portal de gerenciamento de aplicativo do Intune mostra aplicativos implantados para Windows, Android e iOS. Portal de administração de área de trabalho gerenciada do Microsoft limita o modo de exibição para aplicativos do Windows 10. Ambos estão disponíveis por meio do Portal do Windows Azure. 
* [Noções básicas do gerenciamento de aplicativo Intune](https://docs.microsoft.com/intune/app-management)
* [Como adicionar aplicativos ao Intune](https://docs.microsoft.com/intune/app-management)
   * [Adicionar um aplicativo de linha de negócios](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Como adicionar aplicativos do Win32 ao Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Adicionar aplicativos web](https://docs.microsoft.com/intune/web-app)
* [Implantar aplicativos](https://docs.microsoft.com/intune/apps-deploy)
   * [Implantar aplicativos Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Portal da empresa
   * [Implantar o Portal da empresa](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configurar o aplicativo de Portal da empresa](https://docs.microsoft.com/intune/company-portal-app)
