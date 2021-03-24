---
title: Planejar versões de software e software de fim de suporte
description: Descubra e planeje versões de software e software que não são mais suportadas e não receberão atualizações de segurança.
keywords: gerenciamento de ameaças e vulnerabilidades, recomendação de segurança de tvm mdatp, recomendação de segurança cibernética, recomendação de segurança a ação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7a1ee326540ec4baab19a266a4e570fd6a364306
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054520"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a>Planejar versões de software e software de fim de suporte com gerenciamento de ameaças e vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**

- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

O fim do suporte (EOS), também conhecido como EOL (fim da vida útil), para versões de software ou software significa que eles não serão mais suportados ou atendidos e não receberão atualizações de segurança. Quando você usa versões de software ou software com suporte final, você está expondo sua organização a vulnerabilidades de segurança, riscos legais e financeiros.

É fundamental que os administradores de segurança e DES trabalhem juntos e garantam que o inventário de software da organização seja configurado para obter resultados ideais, conformidade e um ecossistema de rede saudável. Eles devem examinar as opções para remover ou substituir aplicativos que chegaram às versões de fim de suporte e atualização que não são mais suportadas. É melhor criar e implementar um plano **antes do** final das datas de suporte.

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a>Encontre versões de software ou software que não são mais suportadas

1. No menu gerenciamento de ameaças e vulnerabilidades, navegue até [**Recomendações de segurança.**](tvm-security-recommendation.md)
2. Vá para o **painel Filtros** e procure a seção marcas. Selecione uma ou mais opções de marca EOS. Em **seguida, aplique**.

    ![Marcas de captura de tela que dizem software EOS, versões do EOS e versões futuras do EOS.](images/tvm-eos-tag.png)

3. Você verá uma lista de recomendações relacionadas ao software com suporte final, versões de software que são o fim do suporte ou versões com o próximo fim do suporte. Essas marcas também estão visíveis na [página de inventário de software.](tvm-software-inventory.md)

    ![Recomendações com a marca EOS.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a>Lista de versões e datas

Para exibir uma lista de versões que chegaram ao fim do suporte, fim ou suporte em breve, e essas datas, siga as etapas a seguir:

1. Uma mensagem aparecerá no sobrevoo de recomendação de segurança para software com versões que chegaram ao fim do suporte ou chegarão ao fim do suporte em breve.

    ![Captura de tela do link de distribuição de versão.](images/eos-upcoming-eos.png)

2. Selecione o link **de distribuição** de versão para ir para a página de análise de software. Lá, você pode ver uma lista filtrada de versões com marcas que as identificam como fim do suporte ou o próximo fim do suporte.

    ![Captura de tela da página de detalhamento de software com o fim do software de suporte.](images/software-drilldown-eos.png)

3. Selecione uma das versões na tabela a ser aberta. Por exemplo, versão 10.0.18362.1. Um flyout aparecerá com a data de término do suporte.

    ![Captura de tela da data de término do suporte.](images/version-eos-date.png)

Depois de identificar quais versões de software e software são vulneráveis devido ao status de fim de suporte, você deve decidir se as atualizará ou removerá da sua organização. Isso reduzirá a exposição de suas organizações a vulnerabilidades e ameaças persistentes avançadas.

## <a name="related-topics"></a>Tópicos relacionados

- [Visão geral do gerenciamento de ameaças e vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Recomendações de segurança](tvm-security-recommendation.md)
- [Inventário de software](tvm-software-inventory.md)
