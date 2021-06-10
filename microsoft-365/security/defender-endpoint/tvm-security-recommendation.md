---
title: Recomendações de segurança por Gerenciamento de Ameaças e Vulnerabilidades
description: Obter recomendações de segurança ativas priorizadas por ameaça, probabilidade de violação e valor, em Gerenciamento de Ameaças e Vulnerabilidades.
keywords: Gerenciamento de Ameaças e Vulnerabilidades, recomendação de segurança de TV do Microsoft Defender para Endpoint, recomendação de segurança cibernética, recomendação de segurança a ação
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
ms.openlocfilehash: af22bac911339de9c2e02df24a77c1889a33d43a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933728"
---
# <a name="security-recommendations---threat-and-vulnerability-management"></a>Recomendações de segurança - Gerenciamento de Ameaças e Vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Ameaça e Gerenciamento de Vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

As deficiências de segurança cibernética identificadas em sua organização são mapeadas para recomendações de segurança ativas e priorizadas pelo impacto. Recomendações priorizadas ajudam a reduzir o tempo para mitigar ou remediar vulnerabilidades e impulsionar a conformidade.

Cada recomendação de segurança inclui etapas de correção ativas. Para ajudar no gerenciamento de tarefas, a recomendação também pode ser enviada usando Microsoft Intune e Microsoft Endpoint Configuration Manager. Quando o cenário de ameaças muda, a recomendação também muda conforme coleta informações continuamente do seu ambiente.

>[!TIP]
>Para obter emails sobre novos eventos de vulnerabilidade, consulte [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)

## <a name="how-it-works"></a>Como funciona

Cada dispositivo na organização é pontuado com base em três fatores importantes para ajudar os clientes a se concentrarem nas coisas certas no momento certo.

- **Ameaça** - Características das vulnerabilidades e explorações nos dispositivos de suas organizações e no histórico de violações. Com base nesses fatores, as recomendações de segurança mostram os links correspondentes para alertas ativos, campanhas de ameaças em andamento e seus relatórios de análise de ameaças correspondentes.

- **Probabilidade de violação** - Postura de segurança e resiliência da sua organização contra ameaças

- **Valor comercial** - ativos, processos críticos e propriedades intelectuais da sua organização

## <a name="navigate-to-the-security-recommendations-page"></a>Navegue até a página Recomendações de segurança

Acesse a página Recomendações de segurança de algumas maneiras diferentes:

- Menu de Gerenciamento de Vulnerabilidades de navegação no [Central de Segurança do Microsoft Defender](portal-overview.md)
- Principais recomendações de segurança no painel [Gerenciamento de Ameaças e Vulnerabilidades painel](tvm-dashboard-insights.md)

Exibir recomendações de segurança relacionadas nos seguintes locais:

- Página de software
- Página do dispositivo

### <a name="navigation-menu"></a>Menu de navegação

Vá para o menu Gerenciamento de Ameaças e Vulnerabilidades de navegação e selecione **Recomendações de segurança.** A página contém uma lista de recomendações de segurança para as ameaças e vulnerabilidades encontradas em sua organização.

### <a name="top-security-recommendations-in-the-threat-and-vulnerability-management-dashboard"></a>Principais recomendações de segurança no painel Gerenciamento de Ameaças e Vulnerabilidades painel

Em um determinado dia como Administrador de Segurança, [](tvm-dashboard-insights.md) você pode dar uma [](tvm-exposure-score.md) olhada no painel Gerenciamento de Ameaças e Vulnerabilidades para ver sua pontuação de exposição lado a lado com sua Pontuação Segura da [Microsoft para Dispositivos.](tvm-microsoft-secure-score-devices.md) O objetivo é **reduzir** a exposição da sua  organização contra vulnerabilidades e aumentar a segurança do dispositivo da sua organização para ser mais resiliente contra ataques de ameaças de segurança cibernética. A lista de recomendações de segurança principais pode ajudá-lo a atingir essa meta.

![Exemplo de cartão de principais recomendações de segurança, com quatro recomendações de segurança.](images/top-security-recommendations350.png)

As principais recomendações de segurança listam as oportunidades de melhoria priorizadas com base nos fatores importantes mencionados na seção anterior : ameaça, probabilidade de violação e valor. Selecionar uma recomendação levará você para a página de recomendações de segurança com mais detalhes.

## <a name="security-recommendations-overview"></a>Visão geral das recomendações de segurança

Recomendações de exibição, o número de pontos fracos encontrados, componentes relacionados, insights de ameaças, número de dispositivos expostos, status, tipo de correção, atividades de correção, impacto na pontuação de exposição e Pontuação Segura da Microsoft para Dispositivos e marcas associadas.

A cor do gráfico **de dispositivos expostos** muda conforme a tendência muda. Se o número de dispositivos expostos estiver em alta, a cor será muda para vermelho. Se houver uma diminuição no número de dispositivos expostos, a cor do gráfico mudará para verde.

>[!NOTE]
>A ameaça e Gerenciamento de Vulnerabilidades mostra dispositivos que estavam em uso até **30 dias** atrás. Isso é diferente do restante do Microsoft Defender para Ponto de Extremidade, onde se um dispositivo não estiver em uso há mais de 7 dias, ele terá um status 'Inativo'.

![Exemplo da página inicial para recomendações de segurança.](images/tvmsecrec-updated.png)

### <a name="icons"></a>Ícones

Ícones úteis também chamam sua atenção rapidamente:
- ![seta atingindo um destino](images/tvm_alert_icon.png) possíveis alertas ativos
- ![bug vermelho](images/tvm_bug_icon.png) explorações públicas associadas
- ![lâmpada](images/tvm_insight_icon.png) insights de recomendação

### <a name="explore-security-recommendation-options"></a>Explorar opções de recomendação de segurança

Selecione a recomendação de segurança que você deseja investigar ou processar.

![Exemplo de uma página de recomendação de segurança.](images/secrec-flyouteolsw.png)

No sobrevoo, você pode escolher qualquer uma das seguintes opções:

- **Abra a página de** software - Abra a página de software para obter mais contexto sobre o software e como ele é distribuído. As informações podem incluir contexto de ameaça, recomendações associadas, pontos fracos descobertos, número de dispositivos expostos, vulnerabilidades descobertas, nomes e detalhes de dispositivos com o software instalado e distribuição de versão.

- [**Opções de correção**](tvm-remediation.md) - Envie uma solicitação de correção para abrir um tíquete no Microsoft Intune para que o administrador de IT escolha e endereço. Acompanhe a atividade de correção na página Correção.

- [**Opções de**](tvm-exception.md) exceção - Envie uma exceção, forneça justificativa e desembaixe a duração da exceção se você ainda não puder remediar o problema.

>[!NOTE]
>Quando uma alteração de software é feita em um dispositivo, normalmente leva 2 horas para que os dados sejam refletidos no portal de segurança. No entanto, às vezes isso pode levar mais tempo. As alterações de configuração podem levar de 4 a 24 horas.

### <a name="investigate-changes-in-device-exposure-or-impact"></a>Investigar alterações na exposição ou impacto do dispositivo

Se houver um grande salto no número de dispositivos expostos ou um aumento acentuado no impacto na pontuação de exposição da sua organização e na Pontuação Segura da Microsoft para Dispositivos, essa recomendação de segurança vale a pena investigar.

1. Selecione a página de recomendação e **abrir software**
2. Selecione a **guia Linha do tempo** do evento para exibir todos os eventos impactados relacionados a esse software, como novas vulnerabilidades ou novas explorações públicas. [Saiba mais sobre a linha do tempo do evento](threat-and-vuln-mgt-event-timeline.md)
3. Decida como resolver o aumento ou a exposição da sua organização, como enviar uma solicitação de correção

## <a name="request-remediation"></a>Solicitar correção

O Gerenciamento de Ameaças e Vulnerabilidades de correção faz a ponte entre os administradores de Segurança e DES por meio do fluxo de trabalho de solicitação de correção. Os administradores de segurança como você podem solicitar que o Administrador de TI correção de uma vulnerabilidade da página de recomendação **de** segurança para o Intune. [Saiba mais sobre opções de correção](tvm-remediation.md)

### <a name="how-to-request-remediation"></a>Como solicitar correção

Selecione uma recomendação de segurança que você gostaria de solicitar correção e selecione **Opções de correção.** Preencha o formulário e selecione **Enviar solicitação**. Vá para a [**página Correção**](tvm-remediation.md) para exibir o status da sua solicitação de correção. [Saiba mais sobre como solicitar correção](tvm-remediation.md#request-remediation)

## <a name="file-for-exception"></a>Arquivo para exceção

Como alternativa a uma solicitação de correção quando uma recomendação não é relevante no momento, você pode criar exceções para recomendações. [Saiba mais sobre exceções](tvm-exception.md)

Somente usuários com permissões de "tratamento de exceções" podem adicionar exceção. [Saiba mais sobre funções RBAC](user-roles.md).

Quando uma exceção é criada para uma recomendação, a recomendação não está mais ativa. O estado de recomendação mudará para **Exceção Total** ou **Parcial** (por grupo de dispositivos).

### <a name="how-to-create-an-exception"></a>Como criar uma exceção

Selecione uma recomendação de segurança para a que você gostaria de criar uma exceção e selecione **Opções de exceção.**  

![Mostrando onde o botão para "opções de exceção" está localizado em um flyout de recomendação de segurança.](images/tvm-exception-options.png)

Preencha o formulário e envie. Para exibir todas as exceções (atuais e [](tvm-remediation.md) passadas), navegue até a página Correção  no menu Gerenciamento de Vulnerabilidades & Ameaça e selecione **a** guia [Exceções.](tvm-exception.md#create-an-exception) Saiba mais sobre como criar uma exceção

## <a name="report-inaccuracy"></a>Imprecisão de relatório

Você pode relatar um falso positivo quando vir qualquer informação de recomendação de segurança impreciso, impreciso, incompleta ou já remediada.

1. Abra a recomendação segurança.

2. Selecione os três pontos ao lado da recomendação de segurança que você deseja relatar e selecione **Relatar imprecisão**.

    ![Mostrando onde o botão "Relatar imprecisão" está em um sub-relatório de recomendação de segurança.](images/report-inaccuracy500.png)

3. No painel submenu, selecione a categoria impreciso no menu suspenso, preencha seu endereço de email e detalhes sobre a imprecisão.

4. Selecione **Enviar**. Seus comentários são enviados imediatamente aos especialistas Gerenciamento de Ameaças e Vulnerabilidades segurança.

## <a name="related-articles"></a>Artigos relacionados

- [Visão geral Gerenciamento de Vulnerabilidades ameaça](next-gen-threat-and-vuln-mgt.md)
- [Painel](tvm-dashboard-insights.md)
- [Pontuação de exposição](tvm-exposure-score.md)
- [Microsoft Secure Score para dispositivos](tvm-microsoft-secure-score-devices.md)
- [Correção de vulnerabilidades](tvm-remediation.md)
- [Criar e exibir exceções para recomendações de segurança](tvm-exception.md)
- [Cronograma do evento](threat-and-vuln-mgt-event-timeline.md)
