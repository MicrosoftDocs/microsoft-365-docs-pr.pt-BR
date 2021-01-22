---
title: Microsoft 365 Defender
description: Configurar seu laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender para experimentar e experimentar a solução de segurança projetada para proteger dispositivos, identidade, dados e aplicativos em sua organização.
keywords: Avaliação da Proteção contra Ameaças da Microsoft, experimente a Proteção contra Ameaças da Microsoft, avalie a Proteção contra Ameaças da Microsoft, laboratório de avaliação da Proteção contra Ameaças da Microsoft, piloto da Proteção contra Ameaças da Microsoft, segurança cibernética, ameaça persistente avançada, segurança corporativa, dispositivos, identidade, usuários, dados, aplicativos, incidentes, investigação e correção automatizadas, busca avançada
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6735817a71f9fb50843acad3a13596ec247aa407
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930205"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Criar um laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


Este guia ajuda você a trabalhar na configuração de um ambiente de laboratório com usuários e grupos e, em seguida, orienta você na configuração dos recursos no Microsoft 365 Defender para que você possa imitar um ataque de ameaça e obter um resultado de avaliação significativo. 

O objetivo da criação deste laboratório de avaliação ou ambiente piloto é ilustrar os recursos abrangentes e integrados do Microsoft 365 Defender. Experimente como essa solução de segurança inteligente detecta, impede, investiga automaticamente e responde a ameaças avançadas à sua organização. 


Você será orientado pelas etapas para iniciar a avaliação do Microsoft 365 Defender com base nos caminhos de implantação recomendados. O objetivo é ajudá-lo a configurar a solução de segurança em um ambiente de laboratório com uma conta de avaliação ou em um ambiente piloto em produção com uma licença completa. Preparar seu laboratório de avaliação ou ambiente piloto pode ajudá-lo a apresentar casos de uso da operação de segurança para tomadores de decisão em sua organização. Quando terminar de executar suas simulações de ataque e estiver satisfeito com os resultados, você poderá implantá-la e operacionalizá-la totalmente em sua organização com a ajuda dos Profissionais de Vendas Técnicos da Microsoft ou de especialistas em sua organização. 

Este guia ajudará você a:
- Configurar seu servidor de laboratório e computadores
- Configurar o Active Directory com usuários e grupos
- Configurar e configurar o Microsoft Defender para Identidade, o Microsoft Defender para Office 365, o Microsoft Defender para Ponto de Extremidade e o Microsoft Cloud App Security
- Configurar políticas locais para seu servidor e computadores
- Simular um ataque de ameaça para gerar um incidente de teste ou alerta no Microsoft 365 Defender

>[!IMPORTANT]
>Para obter os melhores resultados, siga as instruções de configuração do laboratório o mais próximo possível.


## <a name="deployment-phases"></a>Fases de implantação

Há três fases na criação de um ambiente de laboratório de avaliação do Microsoft 365 Defender.

![Fases de implantação: preparar, configurar, integração](../../media/evaluation-guide-phases.png)

|Fase | Descrição | 
|:-------|:-----|
|[Fase 1: Preparar](prepare-mtpeval.md)| Saiba o que você precisa considerar ao implantar o Microsoft 365 Defender em um laboratório de avaliação ou ambiente piloto: <br><br>- Participantes e aprovação <br> - Considerações sobre o ambiente <br>- Acesso <br>- Configuração do Azure Active Directory <br> - Ordem de configuração
|[Fase 2: Instalação](setup-mtpeval.md)|  Tome as etapas iniciais para acessar a Central de Segurança do Microsoft 365 para configurar seu laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender. Você será orientado a:<br><br>- Inscreva-se na avaliação do Microsoft 365 E5 <br>  - Configurar domínio<br>- Atribuir licenças do Microsoft 365 E5<br>– Conclua o assistente de configuração no portal|
|[Fase 3: Configurar o & Onboard](config-mtpeval.md) | Configure cada pilar do Microsoft 365 Defender e pontos de extremidade de integração. Você será orientado a:<br><br>- Configurar o Microsoft Defender para Office 365<br>- Configurar o Microsoft Cloud App Security<br>- Configurar o Microsoft Defender para Identidade<br>- Configurar o Microsoft Defender para o Ponto de Extremidade


Depois de concluir este guia, você teria identificado as partes envolvidas e as aprovações necessárias, ter as permissões de acesso corretas, se inscreveu para avaliação, configurar domínios e cada um dos pilares do Microsoft 365 Defender, e seus pontos de extremidade serão integrados ao serviço.

## <a name="key-capabilities"></a>Principais recursos

Embora o Microsoft 365 Defender fornece muitos recursos, o objetivo principal deste guia de implantação é começar a trabalhar com dispositivos de integração. Além da integração, essas diretrizes orientam você começa com os seguintes recursos.


Funcionalidade | Descrição 
:---|:---
Obter o Microsoft Defender para Office 365 | Ajuda a proteger toda a sua empresa do Office 365 contra ameaças atuais
Microsoft Defender para Identidade? | Identifica e detecta ameaças em identidades comprometidas e ações internas mal-intencionadas.
Microsoft Cloud App Security | Fornece visibilidade rica, controle o deslocamento de dados e detecte ameaças cibernéticas em serviços de nuvem.
Microsoft Defender para Ponto de Extremidade | Impede, detecta e fornece recursos de resposta a ameaças avançadas com segurança abrangente do ponto de extremidade.


## <a name="in-scope"></a>No escopo

As seguintes tarefas estão no escopo deste guia:
-   Configurar o Azure Active Directory
-   Configurar o Microsoft 365 Defender
    -   Inscreva-se na avaliação do Microsoft 365 E5 ou use sua licença completa se estiver executando um piloto
    -   Configurar domínio
    -   Atribuir licenças do Microsoft 365 E5
    -   Concluindo o assistente de configuração no portal
-   Configurar todos os pilares do Microsoft 365 Defender com base nas práticas recomendadas
    -   Obter o Microsoft Defender para Office 365
    -   Microsoft Defender para Identidade?
    -   Microsoft Cloud App Security
    -   Microsoft Defender para Ponto de Extremidade

## <a name="out-of-scope"></a>Fora do escopo

Os seguintes estão fora do escopo deste guia de implantação:

-   Configuração de soluções de terceiros que podem se integrar ao Microsoft 365 Defender
-   Teste de penetração no ambiente de produção

## <a name="next-step"></a>Próxima etapa
[Fase 1: Preparar](prepare-mtpeval.md) 
<br> Preparar seu laboratório de avaliação ou ambiente piloto do Microsoft 365 Defender
