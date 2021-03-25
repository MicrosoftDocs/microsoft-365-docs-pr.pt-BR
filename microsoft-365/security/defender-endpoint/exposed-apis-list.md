---
title: Microsoft Defender para APIs de Ponto de Extremidade com suporte
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
ms.technology: mde
ms.openlocfilehash: 77491620f7efa88f8ab249c2b76cd2532ba679dd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198312"
---
# <a name="supported-microsoft-defender-for-endpoint-apis"></a>Microsoft Defender para APIs de Ponto de Extremidade com suporte

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)

- Deseja experimentar o Microsoft Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

## <a name="endpoint-uri-and-versioning"></a>URI de ponto de extremidade e versão

### <a name="endpoint-uri"></a>Ponto de extremidade URI:            

> O URI de base de serviço é: https://api.securitycenter.microsoft.com
> 
> Os OData baseados em consultas têm o prefixo '/api'. Por exemplo, para obter Alertas, você pode enviar solicitação GET para https://api.securitycenter.microsoft.com/api/alerts

### <a name="versioning"></a>Versão:

> A API dá suporte ao versioning.
> 
> A versão atual é **V1.0**.
> 
> Para usar uma versão específica, use este formato: `https://api.securitycenter.microsoft.com/api/{Version}` . Por exemplo: `https://api.securitycenter.microsoft.com/api/v1.0/alerts`
> 
> Se você não especificar nenhuma versão (por exemplo), você https://api.securitycenter.microsoft.com/api/alerts obterá a versão mais recente.


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


Saiba mais sobre as entidades com suporte individual para as quais você pode executar chamadas de API e detalhes, como valores de solicitação HTTP, cabeçalhos de solicitação e respostas esperadas.

## <a name="in-this-section"></a>Nesta seção

Tópico | Descrição
:---|:---
Busca Avançada | Execute consultas da API.
Alertas | Execute chamadas de API, como obter alertas, criar alerta, atualizar alerta e muito mais.
Domínios | Execute chamadas de API, como obter dispositivos relacionados ao domínio, estatísticas de domínio e muito mais.
Arquivos | Execute chamadas de API, como obter informações de arquivo, alertas relacionados a arquivos, dispositivos relacionados a arquivos e estatísticas de arquivo.
IPs | Execute chamadas de API, como obter alertas relacionados a IP e obter estatísticas de IP.
Máquinas | Execute chamadas de API, como obter dispositivos, obter dispositivos por ID, informações sobre usuários conectados, editar marcas e muito mais.
Ações do computador | Execute uma chamada de API, como Isolamento, Executar verificação antivírus e muito mais.
Indicadores | Execute uma chamada de API, como criar Indicador, obter Indicadores e excluir Indicadores.
Usuários | Execute chamadas de API, como obter alertas relacionados ao usuário e dispositivos relacionados ao usuário.
Pontuação | Execute chamadas de API, como obter pontuação de exposição ou obter pontuação segura do dispositivo.
Software | Execute chamadas de API, como vulnerabilidades de lista por software.
Vulnerabilidade | Execute chamadas de API, como dispositivos de lista por vulnerabilidade.
Recomendação | Execute chamadas de API, como Obter recomendação por ID.

## <a name="see-also"></a>Confira também
- [APIs do Microsoft Defender para Ponto de Extremidade](apis-intro.md)
