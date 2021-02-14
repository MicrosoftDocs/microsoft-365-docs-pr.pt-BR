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
ms.openlocfilehash: 0b76a14a30caeb75cfdcb8acc5715fe6710e0625
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289454"
---
# <a name="work-with-app-control"></a>Trabalhar com o controle de aplicativo

Depois que o controle de aplicativo tiver sido implantado em seu ambiente, você e as Operações de Área de Trabalho Gerenciada da Microsoft terão responsabilidades contínuas. Por exemplo, talvez você queira adicionar um novo aplicativo no ambiente ou adicionar (ou remover) um signante confiável. Para melhorar a segurança, todos os aplicativos devem ser assinados por código antes de liberá-los aos usuários. Os detalhes do editor de um aplicativo incluem informações sobre o signante.


## <a name="add-a-new-app"></a>Adicionar um novo aplicativo

Para adicionar um novo aplicativo, siga estas etapas:

1. Adicione o aplicativo ao [Microsoft Intune.](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)
2. Implante o aplicativo em qualquer dispositivo no anel de teste. 
3. Teste seu aplicativo de acordo com seus processos empresariais padrão. 
4. Verifique o Visualizador de Eventos em Logs de Aplicativos e **Serviços\Microsoft\Windows\AppLocker**, procurando eventos **8003** ou **8006.** Esses eventos indicam que o aplicativo seria bloqueado. Para obter mais informações sobre todos os eventos do App Locker e seus significados, consulte Usando o Visualizador de [Eventos com o AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)
5. Se você encontrar qualquer um desses eventos, abra uma solicitação de signante com as Operações da Área de Trabalho Gerenciada da Microsoft.

## <a name="add-or-remove-a-trusted-signer"></a>Adicionar (ou remover) um signante confiável

Ao abrir uma solicitação de signante, você precisará primeiro fornecer alguns detalhes importantes do editor. Em seguida, siga estas etapas:

1. [Coletar detalhes do editor.](#gather-publisher-details)
2. Abra um tíquete com as Operações da Área de Trabalho Gerenciada da Microsoft para solicitar a regra signante e inclua os seguintes detalhes:  
    - Nome do aplicativo 
    - Versão do aplicativo 
    - Descrição 
    - Tipo de alteração ("adicionar" ou "remover")  
    - Detalhes do editor (por exemplo: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Para remover a confiança de um aplicativo, siga as mesmas etapas, mas de acordo **com o tipo de alteração** a ser *removido.*

As operações implantarão progressivamente políticas em grupos de implantação seguindo este cronograma:


|Grupo de implantação  |Tipo de política  |Tempo  |
|---------|---------|---------|
|Testar     |  Auditoria       |  Dia 0       |
|Primeiro     | Enforced        | 1º dia        |
|Rápida     | Enforced        |  2º dia       |
|Amplas     | Enforced        |  3º dia       |


Você pode pausar ou reverter a implantação a qualquer momento durante a distribuição. Para fazer isso, abra outra solicitação de serviço com o Operations.

> [!NOTE]
> Se você pausar o lançamento de uma regra signante, essa regra deverá ser retordenada ou concluída antes que outra liberação possa começar.

## <a name="gather-publisher-details"></a>Coletar detalhes do editor

Para acessar os dados do editor de um aplicativo, siga estas etapas:

1. Encontre um dispositivo de Área de Trabalho Gerenciada da Microsoft no anel teste que tenha uma política de Modo de Auditoria aplicada. 
2. Tente instalar o aplicativo no dispositivo.
3. Abra o Visualizador de Eventos nesse dispositivo. 
4. No Visualizador de Eventos, navegue até Logs de Aplicativos e **Serviços\Microsoft\Windows** e selecione **AppLocker**. 
5. Encontre qualquer **evento 8003** ou **8006** e copie as informações do evento: 
    - Nome do aplicativo 
    - Versão do aplicativo 
    - Descrição 
    - Detalhes do editor (por exemplo: "O= <publisher name> , L= <location> , S=State, C=Country") 
