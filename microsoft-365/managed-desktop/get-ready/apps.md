---
title: Preparar os aplicativos para o Microsoft gerenciados a área de trabalho
description: ''
keywords: Serviço Microsoft Managed Desktop, 365 da Microsoft, documentação
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: ebeb54bd5d1f50cbb6f78b1c8ad4a624c449b8c2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864882"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a>Preparar os aplicativos para o Microsoft gerenciados a área de trabalho

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
Clientes de Microsoft e Microsoft Desktop gerenciados igualmente têm responsabilidades críticas, embora seja diferentes em torno de aplicativos usados com o Microsoft Desktop gerenciados.

## <a name="microsoft-responsibilites"></a>Microsoft responsibilites
**Aplicativos do Office 365** Microsoft fornecerá o serviço completo para a implantação, atualização e suporte de aplicativos específicos do Office 365. Todos os usuários receberão o conjunto de base do Office 365 clique para executar a versão de 64 bits dos aplicativos incluídos na imagem do dispositivo, de forma que um usuário pode se tornar produtivo rapidamente. Os aplicativos de projeto e o Visio do pacote Office 365 são licenciados separadamente.  Microsoft Desktop gerenciados fornecerá os grupos de implantação, permitindo que o administrador de TI gerenciar licenças e implantar esses aplicativos de forma adequada para sua organização. Microsoft dará suporte a usuários finais desses aplicativos por meio de canais Microsoft Desktop gerenciados suporte.

**Aplicativos de linha de negócios** A Microsoft fornece ferramentas para os administradores de TI a gerenciar e implantar seus aplicativos de linha de negócios para os usuários finais como parte do produto Intune. A Microsoft oferecerá suporte a problemas de implantação de aplicativo conforme detalhado nos [aplicativos de linha de negócios](#line-of-business-applications) 

**Implantar com Intune** Durante a inclusão de Microsoft Desktop gerenciados, permitindo que aplicativos adquiridos a serem implantados por meio de Intune Intune será vinculado no **Armazenamento da Microsoft para a empresa** . Microsoft também implantar a versão baseada na web do Portal da empresa aos usuários finais para que os administradores de TI pode fornecer uma experiência de autoatendimento para usuários finais.

**Gerenciamento de aplicativo** Microsoft pode identificar aplicativos restritos que não são adequados para o local de trabalho moderno por causa impacto sobre o seu sistema. Quando esse aplicativo é identificado Microsoft notificará o cliente e desse aplicativo precisará ser removido do inquilino. 

## <a name="customer-responsibilities"></a>Responsabilidades do cliente
Pacote Office 365 são fundamentais para as ofertas de produtividade da Microsoft e está incluso na licença Microsoft 365 para todos os usuários do Microsoft Desktop gerenciados. Enquanto o Microsoft implanta, atualiza e oferece suporte a aplicativos do Office para os dispositivos de área de trabalho gerenciada da Microsoft ainda há algumas áreas para o qual o cliente é responsável.
- **Atribuir licenças** - os clientes são responsáveis para atribuir as licenças apropriadas aos usuários finais para o Office 365. 
- **Adicionar usuários a grupos de segurança** - para clientes com usuários que precisam de projeto ou do Visio, o administrador de TI deve adicionar esses usuários para os grupos de implantação apropriado. Os administradores de TI também estão responsáveis pelo gerenciamento do fim da vida útil para os usuários. 
- **Implantar o Office 365 complementos** - clientes são responsáveis pela implantação qualquer plug-ins para o pacote do Office 365 que serão considerados necessárias. 

Como os aplicativos de linha de negócios (LOB) são exclusivos para cada cliente, os clientes estão responsáveis pelo gerenciamento de todos os aplicativos dentro de sua organização não implantado pela Microsoft. Isso inclui:
- Decidindo quais aplicativos são necessários e quem precisa-los
- Atribuindo aplicativos aos usuários
- Criar e manter os grupos do Windows Azure AD (Active Directory) para gerenciar as atribuições de aplicativo 

Depois que o conjunto básico de aplicativos LOB foi identificado pelos clientes serão adquirir, licenciar, empacotar e testar esses aplicativos no ambiente do Microsoft Desktop gerenciados. O cliente deve carregar e implante aplicativos para Intune para implantar, atualizar e encerrar seus aplicativos LOB. Os clientes estão responsáveis pelo gerenciamento de suporte a aplicativos LOB seus usuários.
 

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

## <a name="resources"></a>Recursos
Enquanto muitos serviços estão fora do escopo para operações de área de trabalho gerenciada do Microsoft há quais ofertas da Microsoft que podem ajudar o cliente a gerenciam os aplicativos de serviços.

### <a name="windows-upgrade-readiness"></a>Preparação para atualização do Windows
Uma parte importante do configurando novos dispositivos Microsoft gerenciados é entender quais aplicativos são necessários para usuários de dispositivo. Preparação de atualização do Windows é uma ferramenta da Microsoft que ajuda as empresas a compreender o cenário do aplicativo dentro da sua empresa e ajuda-los para analisar dados de chave sobre esses aplicativos, tais como:

- **O uso de aplicativos** - dados de telemetria é usado para monitorar o uso do aplicativo.
- **Compatibilidade de aplicativos** - atualizar preparação examina cada aplicativo e vê como amplamente tiver sido implantado na versão mais recente do Windows 10 e avalia como identificar se ele for "Pronto para Windows". Esses dados ajudam foco testando os esforços de aplicativos que não estejam já amplamente adotados.

### <a name="intune-application-deployment"></a>Implantação de aplicativos Intune
Gerenciamento de aplicativos pode ser manipulado através do portal de administração de área de trabalho gerenciada da Microsoft ou por meio do portal Intune. Portal de gerenciamento de aplicativo do Intune mostra aplicativos implantados para Windows, Android e iOS. Portal de administração de área de trabalho gerenciada do Microsoft limita o modo de exibição para aplicativos do Windows 10. Ambos estão disponíveis por meio do Portal do Windows Azure. 
- [Noções básicas do gerenciamento de aplicativo Intune](https://docs.microsoft.com/intune/app-management)
- [Adicionar um aplicativo do Windows 32](https://docs.microsoft.com/intune/lob-apps-windows)
- [Adicionar aplicativos web](https://docs.microsoft.com/intune/web-app)
- [Atribuir e implantar aplicativos para grupos](https://docs.microsoft.com/intune/apps-deploy)

### <a name="application-packaging-standards"></a>Padrões de empacotamento de aplicativo
Para implantar aplicativos do Windows 32 por meio de Intune devem ser empacotados como uma uma única. MSI, um .appx, ou. MSIX. O tipo de pacote mais comum para Intune está no momento. MSI.
