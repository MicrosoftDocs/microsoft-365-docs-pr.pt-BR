---
title: Trabalhar com o controle de aplicativo
description: ''
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917635"
---
# <a name="work-with-app-control"></a>Trabalhar com o controle de aplicativo

Depois que o controle do aplicativo é implantado em seu ambiente, você e Área de Trabalho Gerenciada da Microsoft operações têm responsabilidades contínuas. Por exemplo, talvez você queira adicionar um novo aplicativo ao ambiente ou adicionar (ou remover) um signante confiável. Para melhorar a segurança, todos os aplicativos devem ser assinados com código antes de liberá-los para os usuários. Os detalhes do editor de um aplicativo incluem informações sobre o signante.


## <a name="add-a-new-app"></a>Adicionar um novo aplicativo

Para adicionar um novo aplicativo, siga estas etapas:

1. Adicione o aplicativo a [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).
2. Implante o aplicativo em qualquer dispositivo no anel de teste. 
3. Teste seu aplicativo de acordo com seus processos comerciais padrão. 
4. Verifique o Visualizador de Eventos em Logs de Aplicativos e **Serviços\Microsoft\Windows\AppLocker**, procurando eventos **8003** ou **8006.** Esses eventos indicam que o aplicativo seria bloqueado. Para obter mais informações sobre todos os eventos do App Locker e seus significados, consulte [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
5. Se você encontrar qualquer um desses eventos, abra uma solicitação de signatária com Área de Trabalho Gerenciada da Microsoft Operations.

## <a name="add-or-remove-a-trusted-signer"></a>Adicionar (ou remover) um signante confiável

Ao abrir uma solicitação de signante, você precisará fornecer alguns detalhes importantes do editor primeiro. Em seguida, siga estas etapas:

1. [Reunir detalhes do editor](#gather-publisher-details).
2. Abra um tíquete com Área de Trabalho Gerenciada da Microsoft Operações para solicitar a regra do signante e inclua os seguintes detalhes:  
    - Nome do aplicativo 
    - Versão do aplicativo 
    - Descrição 
    - Tipo de alteração ("adicionar" ou "remover")  
    - Publisher detalhes (por exemplo: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Para remover a confiança de um aplicativo, siga as mesmas etapas, mas de definir **o tipo de alteração** para *remover*.

As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:


|Grupo de implantação  |Tipo de política  |Tempo  |
|---------|---------|---------|
|Testar     |  Auditoria       |  Dia 0       |
|Primeiro     | Enforced        | 1º dia        |
|Rápida     | Enforced        |  2º dia       |
|Amplas     | Enforced        |  3º dia       |


Você pode pausar ou reverter a implantação a qualquer momento durante a distribuição. Para fazer isso, abra outra solicitação de serviço com Operações.

> [!NOTE]
> Se você pausar o lançamento de uma regra de signante, essa regra deverá ser retorda ou concluída antes que outra versão possa ser iniciada.

## <a name="gather-publisher-details"></a>Reunir detalhes do editor

Para acessar os dados do editor de um aplicativo, siga estas etapas:

1. Encontre um Área de Trabalho Gerenciada da Microsoft no anel de teste que tenha uma política de Modo de Auditoria aplicada. 
2. Tente instalar o aplicativo no dispositivo.
3. Abra o Visualizador de Eventos nesse dispositivo. 
4. No Visualizador de Eventos, navegue até Logs de Aplicativos e **Serviços\Microsoft\Windows** e selecione **AppLocker**. 
5. Encontre qualquer **evento 8003** ou **8006** e copie informações do evento: 
    - Nome do aplicativo 
    - Versão do aplicativo 
    - Descrição 
    - Publisher detalhes (por exemplo: "O= <publisher name> , L= <location> , S=State, C=Country")