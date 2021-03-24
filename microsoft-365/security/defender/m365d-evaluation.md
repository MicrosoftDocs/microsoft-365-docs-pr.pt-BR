---
title: Microsoft 365 Defender
description: Configurar o laboratório de avaliação do Microsoft 365 Defender ou o ambiente piloto para experimentar e experimentar a solução de segurança projetada para proteger dispositivos, identidade, dados e aplicativos em sua organização.
keywords: Avaliação da Proteção contra Ameaças da Microsoft, tente a Proteção contra Ameaças da Microsoft, avalie a Proteção contra Ameaças da Microsoft, laboratório de avaliação da Proteção contra Ameaças da Microsoft, piloto da Proteção contra Ameaças da Microsoft, segurança cibernética, ameaças persistentes avançadas, segurança corporativa, dispositivos, identidade, usuários, dados, aplicativos, incidentes, investigação automatizada e correção, busca avançada
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 2ea829e0e2697facd2522dbf16ced7d620662eee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054499"
---
# <a name="create-a-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Criar um laboratório de avaliação do Microsoft 365 Defender ou um ambiente piloto 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender


Este guia ajuda você a trabalhar na configuração de um ambiente de laboratório com usuários e grupos e, em seguida, orienta você sobre a configuração dos recursos no Microsoft 365 Defender para que você possa imitar um ataque de ameaça e obter um resultado de avaliação significativo. 

O objetivo de criar esse laboratório de avaliação ou ambiente piloto é ilustrar os recursos abrangentes e integrados do Microsoft 365 Defender. Experimente como essa solução de segurança inteligente detecta, impede, investiga automaticamente e responde a ameaças avançadas à sua organização. 


Você será orientado pelas etapas para iniciar sua avaliação do Microsoft 365 Defender com base nos caminhos de implantação recomendados. O objetivo é ajudá-lo a configurar a solução de segurança em um ambiente de laboratório com uma conta de avaliação ou em um ambiente piloto em produção com uma licença completa. Preparar seu laboratório de avaliação ou ambiente piloto pode ajudá-lo a apresentar casos de uso da operação de segurança aos tomadores de decisão em sua organização. Quando terminar de executar suas simulações de ataque e estiver satisfeito com os resultados, você poderá implantá-la e operacionalizá-la totalmente em sua organização com a ajuda de profissionais técnicos de vendas da Microsoft ou especialistas em sua organização. 

Este guia ajudará você:
- Configurar seu servidor de laboratório e computadores
- Configurar o Active Directory com usuários e grupos
- Configurar e configurar o Microsoft Defender para Identidade, o Microsoft Defender para Office 365, o Microsoft Defender para Ponto de Extremidade e o Microsoft Cloud App Security
- Configurar políticas locais para seu servidor e computadores
- Simular um ataque de ameaça para gerar um incidente de teste ou alerta no Microsoft 365 Defender

>[!IMPORTANT]
>Para obter resultados ideais, siga as instruções de instalação do laboratório o mais próximo possível.


## <a name="deployment-phases"></a>Fases de implantação

Há três fases na criação de um ambiente de laboratório de avaliação do Microsoft 365 Defender.

![Fases de implantação: preparar, configurar, integração](../../media/evaluation-guide-phases.png)

|Fase | Descrição | 
|:-------|:-----|
|[Fase 1: Preparar](prepare-m365d-eval.md)| Saiba o que você precisa considerar ao implantar o Microsoft 365 Defender em um laboratório de avaliação ou em um ambiente piloto: <br><br>- Stakeholders e sign-off <br> - Considerações sobre o ambiente <br>- Access <br>- Configuração do Azure Active Directory <br> - Ordem de configuração
|[Fase 2: Instalação](setup-m365deval.md)|  Tome as etapas iniciais para acessar o Centro de Segurança do Microsoft 365 para configurar o laboratório de avaliação do Microsoft 365 Defender ou o ambiente piloto. Você será guiado para:<br><br>- Inscrever-se na avaliação do Microsoft 365 E5 <br>  - Configurar domínio<br>- Atribuir licenças do Microsoft 365 E5<br>– Conclua o assistente de instalação no portal|
|[Fase 3: Configurar o & Onboard](config-m365d-eval.md) | Configure cada pilar do Microsoft 365 Defender e pontos de extremidade de integração. Você será guiado para:<br><br>- Configurar o Microsoft Defender para Office 365<br>- Configurar o Microsoft Cloud App Security<br>- Configurar o Microsoft Defender para Identidade<br>- Configurar o Microsoft Defender para Ponto de Extremidade


Depois de concluir este guia, você identificaria os participantes envolvidos e as aprovações necessárias, teria as permissões de acesso corretas, se inscreveu para avaliação, configurou domínios e cada um dos pilares do Microsoft 365 Defender e seus pontos de extremidade serão integrados ao serviço.

## <a name="key-capabilities"></a>Principais recursos

Embora o Microsoft 365 Defender fornece muitos recursos, o principal objetivo deste guia de implantação é começar a trabalhar com dispositivos de integração. Além da integração, essas diretrizes são iniciadas com os seguintes recursos.


Funcionalidade | Descrição 
:---|:---
Microsoft Defender para Office 365 | Ajuda a proteger todo o seu envrionment do Office 365 contra as ameaças de hoje
Microsoft Defender para Identidade? | Identifica e detecta ameaças em identidades comprometidas e ações internas mal-intencionadas.
Microsoft Cloud App Security | Fornece visibilidade rica, controla a viagem de dados e detecta ameaças cibernéticas em serviços de nuvem.
Microsoft Defender para Ponto de Extremidade | Impede, detecta e fornece recursos de resposta a ameaças avançadas com segurança abrangente do ponto de extremidade.


## <a name="in-scope"></a>No escopo

As seguintes tarefas estão no escopo deste guia:
-   Configurar o Azure Active Directory
-   Configurar o Microsoft 365 Defender
    -   Inscreva-se na Avaliação do Microsoft 365 E5 ou use sua licença completa se estiver executando um piloto
    -   Configurar domínio
    -   Atribuir licenças do Microsoft 365 E5
    -   Concluindo o assistente de instalação no portal
-   Configurar todos os pilares do Microsoft 365 Defender com base nas práticas recomendadas
    -   Microsoft Defender para Office 365
    -   Microsoft Defender para Identidade?
    -   Microsoft Cloud App Security
    -   Microsoft Defender para Ponto de Extremidade

## <a name="out-of-scope"></a>Fora do escopo

Os seguintes estão fora do escopo deste guia de implantação:

-   Configuração de soluções de terceiros que podem se integrar ao Microsoft 365 Defender
-   Testes de penetração no ambiente de produção

## <a name="next-step"></a>Próxima etapa
[Fase 1: Preparar](prepare-m365d-eval.md) 
<br> Preparar seu laboratório de avaliação do Microsoft 365 Defender ou ambiente piloto
