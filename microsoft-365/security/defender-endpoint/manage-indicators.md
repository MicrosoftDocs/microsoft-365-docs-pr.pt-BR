---
title: Criar indicadores
ms.reviewer: ''
description: Crie indicadores para um hash de arquivo, endereço IP, URLs ou domínios que definem a detecção, a prevenção e a exclusão de entidades.
keywords: gerenciar, permitido, bloqueado, bloquear, limpar, mal-intencionado, hash de arquivo, endereço ip, urls, domínio
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 481051b74c1be88ba78bbd44e4fc0c174ed0bdad
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470888"
---
# <a name="create-indicators"></a>Criar indicadores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

O indicador de correspondência de comprometimento (IoCs) é um recurso essencial em todas as soluções de proteção de ponto de extremidade. Essa funcionalidade oferece a SecOps a capacidade de definir uma lista de indicadores para detecção e bloqueio (prevenção e resposta).

Crie indicadores que definem a detecção, a prevenção e a exclusão de entidades. Você pode definir a ação a ser tomada, bem como a duração para quando aplicar a ação, bem como o escopo do grupo de dispositivos ao qual aplicá-la.

As fontes atualmente suportadas são o mecanismo de detecção de nuvem do Defender for Endpoint, o mecanismo automatizado de investigação e correção e o mecanismo de prevenção de ponto de extremidade (Microsoft Defender Antivírus).

**Mecanismo de detecção de nuvem**<br>
O mecanismo de detecção de nuvem do Defender para Ponto de Extremidade verifica regularmente os dados coletados e tenta corresponder aos indicadores definidos. Quando houver uma combinação, a ação será tomada de acordo com as configurações especificadas para o IoC.

**Mecanismo de prevenção do ponto de extremidade**<br>
A mesma lista de indicadores é adida pelo agente de prevenção. Ou seja, se o Microsoft Defender AV for o AV principal configurado, os indicadores matched serão tratados de acordo com as configurações. Por exemplo, se a ação for "Alerta e Bloquear", o Microsoft Defender AV impedirá execuções de arquivo (bloquear e remediar) e um alerta correspondente será gerado. Por outro lado, se a Ação estiver definida como "Permitir", o Microsoft Defender AV não detectará nem impedirá que o arquivo seja executado.

**Mecanismo automatizado de investigação e correção**<BR>
A investigação automatizada e a correção se comportam da mesma maneira. Se um indicador for definido como "Permitir", a investigação automatizada e a correção ignorarão um veredito "ruim" para ele. Se definido como "Bloquear", a investigação automatizada e a correção a tratarão como "ruim".

> [!NOTE]
> A configuração EnableFileHashComputation calcula o hash de arquivo para o certificado e o IoC de arquivo durante verificações de arquivo. Ele dá suporte à aplicação IoC de hashes e certificados pertencem a aplicativos confiáveis. Ele será simultaneamente habilitado e desabilitado com a configuração de arquivo permitir ou bloquear. EnableFileHashComputation é habilitado manualmente por meio da Política de Grupo e é desabilitado por padrão.


As ações com suporte atuais são:
- Permitir
- Somente alerta
- Alerta e bloqueio


Você pode criar um indicador para:
- [Files](indicator-file.md)
- [Endereços IP, URLs/domínios](indicator-ip-domain.md)
- [Certificados](indicator-certificates.md)


> [!NOTE]
> Há um limite de 15.000 indicadores por locatário. Os indicadores de arquivo e certificado não bloqueiam [exclusões definidas para o Microsoft Defender Antivírus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus) Os indicadores não são suportados no Microsoft Defender Antivírus quando ele está no modo passivo. 


## <a name="related-topics"></a>Tópicos relacionados

- [Criar IoC contextual](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [Usar a API de indicadores de ponto de extremidade do Microsoft Defender](ti-indicator.md)
- [Usar soluções integradas a parceiros](partner-applications.md)
