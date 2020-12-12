---
title: Avaliar o Microsoft 365 defender
description: Configure seu laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto para experimentar e experimentar a solução de segurança projetada para proteger dispositivos, identidade, dados e aplicativos em sua organização.
keywords: Avaliação de proteção contra ameaças da Microsoft, experimente a proteção contra ameaças da Microsoft, avalie a proteção contra ameaças da Microsoft, laboratório de avaliação de proteção contra ameaças da Microsoft, piloto de proteção contra ameaças da Microsoft, segurança persistente avançada, segurança corporativa, dispositivos, dispositivo, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, caça avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.openlocfilehash: 8504b036203e1f73dc9e0a0d79a228425fb88bfa
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659625"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Criar um laboratório de avaliação do Microsoft 365 defender ou um ambiente piloto 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


Este guia ajuda você a trabalhar com a configuração de um ambiente de laboratório com usuários e grupos e, em seguida, orienta você pela configuração dos recursos no Microsoft 365 defender para que você possa imitar um ataque de ameaça e obter um resultado de avaliação significativo. 

O objetivo de criar este laboratório de avaliação ou ambiente piloto é ilustrar os recursos abrangentes e integrados do Microsoft 365 defender. Experimente como essa solução de segurança inteligente detecta, impede, investiga automaticamente e responde a ameaças avançadas de sua organização. 


Você será orientado pelas etapas para iniciar sua avaliação do Microsoft 365 defender com base nos caminhos de implantação recomendados. O objetivo é ajudá-lo a configurar a solução de segurança em um ambiente de laboratório com uma conta de avaliação ou em um ambiente piloto em produção com uma licença completa. Preparar o laboratório de avaliação ou o ambiente piloto pode ajudá-lo a apresentar casos de uso da operação de segurança para tomadores de decisões em sua organização. Quando você terminar de executar as simulações de ataque e estiver satisfeito com os resultados, você pode implantá-lo e operacionalá-lo completamente em sua organização com a ajuda dos profissionais de vendas ou especialistas da Microsoft em sua organização. 

Este guia ajudará você a:
- Configurar seu servidor de laboratório e computadores
- Configurar o Active Directory com usuários e grupos
- Configurar e configurar o Microsoft defender para identidade, Microsoft defender para Office 365, Microsoft defender para ponto de extremidade e Microsoft Cloud app Security
- Configurar políticas locais para seu servidor e computadores
- Imitar um ataque de ameaça para gerar um incidente de teste ou alerta no Microsoft 365 defender

>[!IMPORTANT]
>Para obter resultados ideais, siga as instruções de configuração do laboratório o mais próximo possível.


## <a name="deployment-phases"></a>Fases de implantação

Há três fases na criação de um ambiente de laboratório de avaliação do Microsoft 365 defender.

![Fases de implantação: preparação, configuração, integração](../../media/evaluation-guide-phases.png)

|Fase | Descrição | 
|:-------|:-----|
|[Fase 1: preparar](prepare-mtpeval.md)| Saiba o que você precisa considerar ao implantar o Microsoft 365 defender em um laboratório de avaliação ou ambiente piloto: <br><br>– Participantes e aprovação <br> -Considerações de ambiente <br>– Acesso <br>-Configuração do Azure Active Directory <br> -Ordem de configuração
|[Fase 2: configuração](setup-mtpeval.md)|  Siga as etapas iniciais para acessar a central de segurança do Microsoft 365 para configurar o laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto. Você será orientado para:<br><br>-Inscrever-se no Microsoft 365 E5 Trial <br>  -Configurar domínio<br>-Atribuir licenças do Microsoft 365 e5<br>– Concluir o assistente de configuração no portal|
|[Fase 3: configurar o & integrado](config-mtpeval.md) | Configure cada Microsoft 365 defender pilar e pontos de extremidade integrados. Você será orientado para:<br><br>– Configurar o Microsoft defender para Office 365<br>– Configurar o Microsoft Cloud app Security<br>– Configurar o Microsoft defender para identidade<br>– Configurar o Microsoft defender para ponto de extremidade


Depois de concluir este guia, você teria identificado os participantes envolvidos e as aprovações necessárias, têm as permissões de acesso corretas, se inscreveram para os domínios de avaliação, configurados e cada um dos pilares do Microsoft 365 defender, e seus pontos de extremidade serão integrados ao serviço.

## <a name="key-capabilities"></a>Principais recursos

Embora o Microsoft 365 defender forneça muitos recursos, o principal objetivo deste guia de implantação é começar a usar dispositivos de integração. Além da integração, esta orientação é iniciada com os seguintes recursos.


Funcionalidade | Descrição 
:---|:---
Obter o Microsoft Defender para Office 365 | Ajuda a proteger todo o Office 365 ambiente das ameaças atuais
O que é o Microsoft Defender para Identidade? | Identifica e detecta ameaças sobre identidades comprometidas e ações mal-intencionadas de insider.
Microsoft Cloud App Security | Fornece visibilidade avançada, controlar dados de viagem e detectar ciberataques nos serviços de nuvem.
Microsoft Defender para Ponto de Extremidade | Impede, detecta e fornece recursos de resposta a ameaças avançadas com segurança de ponto de extremidade abrangente.


## <a name="in-scope"></a>No escopo

As seguintes tarefas estão no escopo deste guia:
-   Configurar o Azure Active Directory
-   Configurar o Microsoft 365 defender
    -   Inscreva-se no Microsoft 365 E5 Trial ou use sua licença completa se estiver executando um piloto
    -   Configurar domínio
    -   Atribuir licenças do Microsoft 365 e5
    -   Concluindo o assistente de configuração no portal
-   Configurar todos os pilares do Microsoft 365 defender com base nas práticas recomendadas
    -   Obter o Microsoft Defender para Office 365
    -   O que é o Microsoft Defender para Identidade?
    -   Microsoft Cloud App Security
    -   Microsoft Defender para Ponto de Extremidade

## <a name="out-of-scope"></a>Fora do escopo

Os itens a seguir estão fora do escopo deste guia de implantação:

-   Configuração de soluções de terceiros que podem ser integradas ao Microsoft 365 defender
-   Teste de penetração no ambiente de produção

## <a name="next-step"></a>Próxima etapa
[Fase 1: preparar](prepare-mtpeval.md) 
<br> Prepare seu laboratório de avaliação do Microsoft 365 defender ou o ambiente piloto
