---
title: Suporte de APIs do Microsoft Defender para Ponto de Extremidade
ms.reviewer: ''
description: Saiba mais sobre as entidades específicas com suporte do Microsoft Defender para Endpoint para as quais você pode criar chamadas de API.
keywords: apis, apis com suporte, ator, alertas, dispositivo, usuário, domínio, ip, arquivo, consultas avançadas, busca avançada
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 61c7c8022ed89a4d10e5737e2dcdf92a4375bedd
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770404"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Suporte de APIs do Microsoft Defender para Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="endpoint-uri-and-versioning"></a>URI de ponto de extremidade e versão

### <a name="endpoint-uri"></a>URI do ponto de extremidade

> O URI de base de serviço é: [https://api.securitycenter.microsoft.com](https://api.securitycenter.microsoft.com)
>
> Os OData baseados em consultas têm o prefixo '/api'. Por exemplo, para obter Alertas, você pode enviar solicitação GET para [https://api.securitycenter.microsoft.com/api/alerts](https://api.securitycenter.microsoft.com/api/alerts)

### <a name="versioning"></a>Controle de versão

> A API dá suporte ao versioning.
>
> A versão atual é **V1.0**.
>
> Para usar uma versão específica, use este formato: `https://api.securitycenter.microsoft.com/api/{Version}` . Por exemplo: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
>
> Se você não especificar nenhuma versão (por exemplo), você `https://api.securitycenter.microsoft.com/api/alerts` obterá a versão mais recente.

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Saiba mais sobre as entidades com suporte individual para as quais você pode executar chamadas de API e detalhes, como valores de solicitação HTTP, cabeçalhos de solicitação e respostas esperadas.

## <a name="in-this-section"></a>Nesta seção

Tópico | Descrição
:---|:---
[Busca Avançada](run-advanced-query-api.md) | Execute consultas da API.
[Métodos e propriedades de alerta](alerts.md) | Execute chamadas de API, como \- obter alertas, criar alerta, atualizar alerta e muito mais.
[Exportar métodos e propriedades de avaliação por dispositivo](get-assessmnt-1methods-properties.md) | Execute chamadas de API, como \- avaliação de configuração segura de exportação, avaliação de inventário de software e avaliação de vulnerabilidades de software de exportação.
[Métodos e propriedades de Investigação Automatizada](investigation.md) | Execute chamadas de API, como \- obter coleção de Investigação.
[Obter alertas relacionados ao domínio](get-domain-related-alerts.md) | Execute chamadas de API, como \- obter dispositivos relacionados ao domínio, estatísticas de domínio e muito mais.
[Métodos e propriedades de arquivo](files.md) | Execute chamadas de API, como \- obter informações de arquivo, alertas relacionados a arquivos, dispositivos relacionados a arquivos e estatísticas de arquivo.
[Métodos e propriedades de indicadores](ti-indicator.md) | Execute uma chamada de API, como \- obter Indicadores, criar Indicador e excluir Indicadores.
[Obter alertas relacionados ao IP](get-ip-related-alerts.md) | Execute chamadas de API, como \- obter alertas relacionados a IP e obter estatísticas de IP.
[Métodos e propriedades de computadores](machine.md) | Execute chamadas de API, como obter dispositivos, obter dispositivos por ID, informações sobre \- usuários conectados, editar marcas e muito mais.
[Métodos e propriedades de Ação do Computador](machineaction.md) | Execute uma chamada de API, como \- Isolamento, Executar verificação antivírus e muito mais.
[Métodos e propriedades da recomendação](recommendation.md) | Execute chamadas de API, como \- obter recomendação por ID.
[Propriedades e métodos de atividade de correção](get-remediation-methods-properties.md) | Execute uma chamada de API, como obter todas as tarefas de correção, obter tarefas de correção de dispositivos expostos e obter uma tarefa de correção \- por id.
[Métodos e propriedades de pontuação](score.md) | Execute chamadas de API, como \- obter pontuação de exposição ou obter pontuação segura do dispositivo.
[Métodos e propriedades de software](software.md) | Execute chamadas de API, como \- vulnerabilidades de lista por software.
[Métodos do usuário](user.md) | Execute chamadas de API, como \- obter alertas relacionados ao usuário e dispositivos relacionados ao usuário.
[Métodos e propriedades da vulnerabilidade](vulnerability.md) | Execute chamadas de API, como \- dispositivos de lista por vulnerabilidade.

## <a name="see-also"></a>Confira também

- [APIs do Microsoft Defender para Ponto de Extremidade](apis-intro.md)

- [Notas de versão da API do Microsoft Defender para Ponto de Extremidade](api-release-notes.md)
