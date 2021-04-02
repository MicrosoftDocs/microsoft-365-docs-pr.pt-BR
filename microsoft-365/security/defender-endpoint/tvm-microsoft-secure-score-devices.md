---
title: Microsoft Secure Score para dispositivos
description: Sua pontuação para dispositivos mostra o estado de configuração de segurança coletiva de seus dispositivos em aplicativos, sistema operacional, rede, contas e controles de segurança.
keywords: Microsoft Secure Score for Devices, mdatp Microsoft Secure Score for Devices, secure score, configuration score, threat and vulnerability management, security controls, improvement opportunities, security configuration score over time, security posture, baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fcf33b309045b9ca763b0d3cabc44fb13505ee0b
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500049"
---
# <a name="microsoft-secure-score-for-devices"></a>Microsoft Secure Score para dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> A pontuação de configuração agora faz parte do gerenciamento de ameaças e vulnerabilidades como Pontuação Segura da Microsoft para Dispositivos.

Sua pontuação para dispositivos está visível no painel de gerenciamento de ameaças e [vulnerabilidades](tvm-dashboard-insights.md) do Centro de Segurança do Microsoft Defender. Uma pontuação segura da Microsoft mais alta para dispositivos significa que seus pontos de extremidade são mais resilientes contra ataques de ameaças de segurança cibernética. Ele reflete o estado de configuração de segurança coletiva de seus dispositivos nas seguintes categorias:

- Aplicativo
- Sistema operacional
- Rede
- Contas
- Controles de segurança

Selecione uma categoria para ir até a página [**Recomendações de**](tvm-security-recommendation.md) segurança e exibir as recomendações relevantes.

## <a name="turn-on-the-microsoft-secure-score-connector"></a>Ativar o conector de Pontuação Segura da Microsoft

Encaminhe o Microsoft Defender para sinais de ponto de extremidade, dando visibilidade da Pontuação Segura da Microsoft para a postura de segurança do dispositivo. Os dados encaminhados são armazenados e processados no mesmo local que seus dados de Pontuação Segura da Microsoft.

As alterações podem levar até algumas horas para refletir no painel.

1. No painel de navegação, acesse **Configurações**  >  **Recursos avançados** 

2. Role para baixo até **Microsoft Secure Score** e alterne a configuração para **On**.

3. Selecione **Salvar preferências**.

## <a name="how-it-works"></a>Como funciona

>[!NOTE]
> A Pontuação Segura da Microsoft para Dispositivos atualmente dá suporte a configurações definidas por meio da Política de Grupo. Devido ao suporte parcial atual do Intune, as configurações que podem ter sido definidas por meio do Intune podem aparecer como mal configuradas. Entre em contato com o administrador de IT para verificar o status real da configuração caso sua organização use o Intune para gerenciamento de configuração seguro.

Os dados no cartão Microsoft Secure Score for Devices são o produto do processo de descoberta de vulnerabilidades meticulosa e contínua. Ele é agregado com avaliações de descoberta de configuração que continuamente:

- Compare as configurações coletadas com os parâmetros de referência coletados para descobrir ativos mal configurados
- Mapear configurações para vulnerabilidades que podem ser remediadas ou parcialmente remediadas (redução de risco)
- Coletar e manter os parâmetros de configuração de práticas (fornecedores, feeds de segurança, equipes de pesquisa internas)
- Coletar e monitorar alterações do estado de configuração do controle de segurança de todos os ativos

## <a name="improve-your-security-configuration"></a>Melhorar sua configuração de segurança

Aprimora sua configuração de segurança, remediando problemas da lista de recomendações de segurança. À medida que você faz isso, a Pontuação Segura da Microsoft para Dispositivos melhora e sua organização se torna mais resiliente contra ameaças e vulnerabilidades de segurança cibernética.

1. No cartão Pontuação Segura da Microsoft para Dispositivos no painel de gerenciamento de ameaças e vulnerabilidades, selecione uma das categorias. Você exibirá a lista de recomendações relacionadas a essa categoria. Ele levará você para a página [**Recomendações de**](tvm-security-recommendation.md) segurança. Se você quiser ver todas as recomendações de segurança, depois de chegar à página Recomendações de segurança, desempure o campo de pesquisa.

2. Selecione um item na lista. O painel de sobremenu será aberto com detalhes relacionados à recomendação. Selecione **Opções de correção**.

   ![Recomendações de segurança relacionadas a controles de segurança](images/tvm_security_controls.png)

3. Leia a descrição para entender o contexto do problema e o que fazer em seguida. Selecione uma data de vencimento, adicione anotações e selecione Exportar todos os dados de atividade de correção para **CSV** para que você possa anexá-los a um email para acompanhamento.

4. **Enviar solicitação**. Você verá uma mensagem de confirmação de que a tarefa de correção foi criada.
   ![Confirmação da criação de tarefas de correção](images/tvm_remediation_task_created.png)

5. Salve seu arquivo CSV.
   ![Salvar arquivo csv](images/tvm_save_csv_file.png)

6. Envie um email de acompanhamento para o administrador de TI e permita o tempo que você aloca para que a correção se propague no sistema.

7. Revise novamente **a Pontuação Segura da Microsoft para** Dispositivos no painel. O número de recomendações de controles de segurança diminuirá. Quando você selecionar **Controles** de  segurança para voltar para a página Recomendações de segurança, o item que você endereça não será mais listado lá. A Pontuação Segura da Microsoft para Dispositivos deve aumentar.

>[!IMPORTANT]
>Para aumentar suas taxas de detecção de avaliação de vulnerabilidade, baixe as seguintes atualizações de segurança obrigatórias e implante-as em sua rede:
>- Clientes 19H1 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
>- Clientes RS5 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
>- Clientes RS4 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
>- Clientes RS3 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
>Para baixar as atualizações de segurança:
>1. Vá para [o Catálogo de Atualizações da Microsoft.](https://www.catalog.update.microsoft.com/home.aspx)
>2. Key-in the security update KB number that you need to download, then click **Search**.  

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Painel](tvm-dashboard-insights.md)
- [Pontuação de exposição](tvm-exposure-score.md)
- [Recomendações de segurança](tvm-security-recommendation.md)
