---
title: Configurar recursos automatizados de investigação e correção
description: Configurar seus recursos automatizados de investigação e correção no Microsoft Defender para Ponto de Extremidade.
keywords: configurar, configurar, automatizar, investigação, detecção, alertas, correção, resposta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: bd86458749db4019bb247a3664748b9891965754
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841325"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Configurar recursos automatizados de investigação e correção no Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Se sua organização estiver usando o [Microsoft Defender para Ponto](/windows/security/threat-protection/) de Extremidade (Defender para Ponto de Extremidade), os recursos automatizados de investigação e correção podem economizar tempo e esforço da equipe de operações de segurança. [](/microsoft-365/security/defender-endpoint/automated-investigations) Conforme descrito nesta [postagem de blog,](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)esses recursos imitam as etapas ideais que um analista de segurança toma para investigar e remediar ameaças. [Saiba mais sobre investigação e correção automatizadas.](/microsoft-365/security/defender-endpoint/automated-investigations) 

Para configurar a investigação e a correção automatizadas,
1. [Ativar os recursos;](#turn-on-automated-investigation-and-remediation) e 
2. [Configurar grupos de dispositivos](#set-up-device-groups).

## <a name="turn-on-automated-investigation-and-remediation"></a>Ativar investigação e correção automatizadas

1. Como administrador global ou administrador de segurança, vá para o Central de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) e entre.
2. No painel de navegação, escolha **Configurações**.
3. Na seção **Geral,** selecione **Recursos avançados**.
4. Acione a **Investigação Automatizada e** resolva **automaticamente os alertas**.

## <a name="set-up-device-groups"></a>Configurar grupos de dispositivos

1. No Central de Segurança do Microsoft Defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ), na  página Configurações, em **Permissões,** selecione Grupos **de dispositivos**.
2. Selecione **+ Adicionar grupo de dispositivos**.
3. Crie pelo menos um grupo de dispositivos, da seguinte forma:
   - Especifique um nome e uma descrição para o grupo de dispositivos.
   - Na lista **Nível de automação,** selecione um nível, como **Full – correção de ameaças automaticamente**. O nível de automação determina se as ações de correção são realizadas automaticamente ou somente após a aprovação. Para saber mais, confira [Níveis de automação em investigação e correção automatizadas.](automation-levels.md)
   - Na seção **Membros,** use uma ou mais condições para identificar e incluir dispositivos.
   - Na guia **Acesso ao** usuário, selecione os grupos [Azure Active Directory que](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) devem ter acesso ao grupo de dispositivos que você está criando.
4. Selecione **Concluído** quando terminar de configurar o grupo de dispositivos.

## <a name="next-steps"></a>Próximas etapas

- [Visite o Centro de Ações para exibir ações pendentes e concluídas de correção](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Revisar e aprovar ações pendentes](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>Confira também

- [Endereços falsos positivos/negativos no Microsoft Defender para Ponto de Extremidade](defender-endpoint-false-positives-negatives.md)
