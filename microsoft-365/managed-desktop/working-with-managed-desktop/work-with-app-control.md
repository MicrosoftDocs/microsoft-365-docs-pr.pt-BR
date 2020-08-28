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

Depois que o controle de aplicativos é implantado em seu ambiente, você e as operações de área de trabalho gerenciada da Microsoft têm responsabilidades contínuas. Por exemplo, você pode querer adicionar um novo aplicativo no ambiente ou adicionar (ou remover) um signatário confiável. Para melhorar a segurança, todos os aplicativos devem ser assinados por código antes de você liberá-los aos usuários. Os detalhes do fornecedor do aplicativo incluem informações sobre o Assinante.


## <a name="add-a-new-app"></a>Adicionar um novo aplicativo

Para adicionar um novo aplicativo, siga estas etapas:

1. Adicione o aplicativo ao [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management).
2. Implante o aplicativo em qualquer dispositivo no anel de teste. 
3. Teste seu aplicativo de acordo com seus processos de negócios padrão. 
4. Verifique o Visualizador de eventos em **aplicativos e serviços Logs\Microsoft\Windows\AppLocker**, procurando qualquer evento **8003** ou **8006** . Esses eventos indicam que o aplicativo seria bloqueado. Para obter mais informações sobre todos os eventos do bloqueador de aplicativos e seus significados, consulte [usando o Visualizador de eventos com AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
5. Se você encontrar qualquer um desses eventos, abra uma solicitação de signatário com operações de área de trabalho gerenciada da Microsoft.

## <a name="add-or-remove-a-trusted-signer"></a>Adicionar (ou remover) um signatário confiável

Ao abrir uma solicitação de signatário, você precisará fornecer alguns detalhes importantes do Publisher. Siga estas etapas:

1. [Coletar detalhes do editor](#gather-publisher-details).
2. Abra uma permissão com operações de área de trabalho gerenciada da Microsoft para solicitar a regra de signatário e incluir os seguintes detalhes:  
    - Nome do aplicativo 
    - Versão do aplicativo 
    - Descrição 
    - Tipo de alteração ("Adicionar" ou "remover")  
    - Detalhes do editor (por exemplo: "O = <publisher name> , L = <location> , S = estado, C = país") 

> [!NOTE]
> Para remover a confiança de um aplicativo, siga as mesmas etapas, mas defina o **tipo de alteração** como *remover*.

As operações implantarão progressivamente políticas em grupos de implantação seguindo esta programação:


|Grupo de implantação  |Tipo de política  |Tempo  |
|---------|---------|---------|
|Testar     |  Auditoria       |  Dia 0       |
|Primeiro     | Enforced        | 1º dia        |
|Rápida     | Enforced        |  2º dia       |
|Amplas     | Enforced        |  3º dia       |


Você pode pausar ou reverter a implantação a qualquer momento durante a distribuição. Para fazer isso, abra outra solicitação de serviço com operações.

> [!NOTE]
> Se você pausar o lançamento de uma regra de signatário, essa regra deverá ser revertida ou concluída para que outra distribuição possa ser iniciada.

## <a name="gather-publisher-details"></a>Coletar detalhes do editor

Para acessar os dados do editor de um aplicativo, siga estas etapas:

1. Encontre um dispositivo de área de trabalho gerenciada da Microsoft no anel de teste que tem uma política de modo de auditoria aplicada. 
2. Tente instalar o aplicativo no dispositivo.
3. Abra o Visualizador de eventos nesse dispositivo. 
4. No Visualizador de eventos, navegue até **aplicativo e serviços Logs\Microsoft\Windows**e, em seguida, selecione **AppLocker**. 
5. Encontre qualquer evento **8003** ou **8006** e, em seguida, copie informações do evento: 
    - Nome do aplicativo 
    - Versão do aplicativo 
    - Descrição 
    - Detalhes do editor (por exemplo: "O = <publisher name> , L = <location> , S = estado, C = país") 
