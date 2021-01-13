---
title: Exceções ao plano de serviço
description: Como solicitar exceções ao plano de serviço padrão
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 97fe3fe1734908c46dcfff4acd76ce9ae5b8b1a5
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841262"
---
# <a name="exceptions-to-the-service-plan"></a>Exceções ao plano de serviço

A Área de Trabalho Gerenciada da Microsoft fornece uma lista de dispositivos gerenciada, configurações de dispositivo padrão, [requisitos](device-policies.md)de aplicativos e [determinadas](../working-with-managed-desktop/config-setting-overview.md)configurações configuráveis, tudo projetado para fornecer uma experiência segura, produtiva e agradável para os usuários. É melhor sempre permanecer com o serviço conforme fornecido. No entanto, reconhecemos que alguns detalhes do serviço podem não se ajustar exatamente às necessidades da sua organização. Se você acha que precisa alterar o serviço de alguma forma, é importante seguir os seguintes processos para solicitar essas alterações.
 
## <a name="types-of-exceptions"></a>Tipos de exceções

Uma exceção é qualquer adição ou alteração na configuração base da Área de Trabalho Gerenciada da Microsoft; os exemplos variam desde a configuração de portas USB até a implantação de um novo driver de dispositivo. Agrupamos várias exceções da seguinte forma:

|Tipo  |Descrição  |
|---------|---------|
|Software de produtividade     |  Software em primeiro plano necessário para os usuários, restrito pelos requisitos [do aplicativo](mmd-app-requirements.md)       |
|Agentes de & VPNs     |  Software usado para proteger, monitorar ou alterar o comportamento do dispositivo ou da rede       |
|Monitoramento de experiência digital     |  Software usado para rastrear dados no dispositivo de um usuário para relatar à IT       |
|Drivers de hardware ou software     |   Drivers de dispositivo, restritos pelos [requisitos do aplicativo](mmd-app-requirements.md)      |
|Políticas     | Configurações do Windows 10 ou do Microsoft 365 Apps para empresas em um dispositivo gerenciado        |
|Dispositivos     | Dispositivos que não estão na lista de dispositivos da Área de [Trabalho Gerenciada da](device-list.md) Microsoft        |
|Outros     |  Qualquer coisa não coberta pelas outras áreas       |
 
## <a name="request-an-exception"></a>Solicitar uma exceção

Envie solicitações por meio do Portal de Administração da Área de Trabalho Gerenciada da Microsoft criando uma solicitação de alteração. Certifique-se de incluir estes detalhes:

-   Tipo de isenção: qual é a categoria de exceção? (consulte a tabela anterior)
-   Requisito: qual é o requisito comercial específico para a exceção?
-   Proposta: qual solução sua empresa está solicitando?
-   Linha do tempo: quanto tempo você deseja que essa exceção dura? 

## <a name="how-we-assess-an-exception-request"></a>Como avaliamos uma solicitação de exceção

Quando revisarmos as solicitações de exceção, avaliamos esses fatores nesta ordem:
 
1.  Alguns aplicativos e políticas que a Área de Trabalho Gerenciada da Microsoft implanta em todos os dispositivos não são indististíveis, portanto, sua solicitação não deve afetá-los. Consulte [Configuração do dispositivo](device-policies.md) para obter mais informações.
2.  O software de produtividade restrito exigido por um usuário para fazer seu trabalho provavelmente será aprovado. 
3.  Se atendermos aos seus requisitos usando a tecnologia da Microsoft, provavelmente aprovaremos sua solicitação para um período de migração de exceção de três a 12 meses (dependendo do escopo do projeto).
4.  Se não atendermos aos seus requisitos usando a tecnologia da Microsoft, provavelmente aprovaremos sua solicitação, a menos que ela viole uma das condições abaixo.  

Esses princípios garantem que a Área de Trabalho Gerenciada da Microsoft sempre possa atender às suas necessidades enquanto rastreia os desvios do nosso modelo padrão. 

## <a name="key-conditions"></a>Condições principais

Analisamos as exceções para garantir que elas não violem nenhuma destas condições:

-   Uma exceção não deve afetar negativamente a segurança do sistema. 
-   Manter a exceção não deve incorrer em um custo significativo para operações ou suporte da Área de Trabalho Gerenciada da Microsoft.
-   Uma exceção não deve afetar a estabilidade do sistema, por exemplo, causando falhas ou travamentos no modo kernel.
-   A alteração não deve nos restringir a operar o serviço ou conflitar com a tecnologia principal da Área de Trabalho Gerenciada da Microsoft.

Essas condições podem mudar no futuro. Se fizermos essas alterações, forneceremos um aviso de 30 dias antes dessas condições entrarem em vigor.  Se a Área de Trabalho Gerenciada da Microsoft oferecer uma maneira alternativa de atender a uma exceção aprovada, a Área de Trabalho Gerenciada da Microsoft notificará o cliente caso a Área de Trabalho Gerenciada da Microsoft altere a maneira de dar suporte à exceção. 

## <a name="revoking-approval-for-an-exception"></a>Revogar aprovação para uma exceção

Depois que uma exceção solicitada é aprovada e implantada, é possível que descubramos problemas que violam as principais condições que não eram evidentes quando aprovamos a alteração em primeiro lugar. Nessa situação, talvez seja preciso revogar a aprovação da exceção.
 
Se isso acontecer, notificaremos você usando o portal de administração da Área de Trabalho Gerenciada da Microsoft. A partir da primeira vez que o notificarmos, você terá 90 dias para remover a exceção antes que os dispositivos com exceção não sejam mais vinculados aos contratos de nível de serviço da Área de Trabalho Gerenciada da Microsoft. Enviaremos várias notificações de acordo com uma linha do tempo estrita. No entanto, um incidente ou ameaça grave pode exigir que mudemos a linha do tempo ou nossas decisões sobre uma exceção. Não removeremos uma *exceção* sem seu consentimento, mas qualquer dispositivo com uma exceção revogada não estará mais vinculado ao nosso contrato de nível de serviço. Esta é a linha do tempo das notificações que enviaremos a você:

- **Primeiro aviso:** Fornecemos o primeiro aviso de nossa decisão de revogar a aprovação, incluindo informações sobre por que a revogamos, as ações que aconselhamos você a tomar, a data limite para essas ações e as etapas a serem seguidas se você quiser invocar a decisão. Esse aviso ocorre com 90 dias de antecedência antes que a exceção precise ser removida de todos os dispositivos. 
- **Segundo aviso (30 dias depois):** Fornecemos um segundo aviso, incluindo as mesmas informações fornecidas no primeiro aviso. 
- **Terceiro aviso (60 dias após o primeiro aviso):** Fornecemos um terceiro aviso, incluindo as mesmas informações fornecidas no primeiro aviso. 
- **Aviso final (uma semana antes do prazo de 90 dias):** Fornecemos um quarto aviso, incluindo as mesmas informações fornecidas no primeiro aviso.
- **90 dias após o primeiro aviso:** Os contratos de nível de serviço da Área de Trabalho Gerenciada da Microsoft não se aplicam mais a dispositivos que tenham a exceção revogada. A qualquer momento, você pode desafio a decisão e fornecer informações adicionais para consideração, incluindo atualização, alterações de configuração ou alteração de software. 


