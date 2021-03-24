---
title: Gerenciar indicadores
ms.reviewer: ''
description: Gerencie indicadores para um hash de arquivo, endereço IP, URLs ou domínios que definem a detecção, a prevenção e a exclusão de entidades.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 6edb4ddf764788a11ea3b6f1863dd95e694f1849
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054271"
---
# <a name="manage-indicators"></a>Gerenciar indicadores

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. No painel de navegação, selecione **Indicadores de**  >  **Configurações**.

2. Selecione a guia do tipo de entidade que você gostaria de gerenciar.  

3. Atualize os detalhes do indicador e clique em **Salvar** ou clique no botão **Excluir** se quiser remover a entidade da lista.

## <a name="import-a-list-of-iocs"></a>Importar uma lista de IoCs

Você também pode optar por carregar um arquivo CSV que define os atributos dos indicadores, a ação a ser tomada e outros detalhes.

Baixe o CSV de exemplo para saber os atributos de coluna com suporte.

1. No painel de navegação, selecione **Indicadores de**  >  **Configurações**.

2. Selecione a guia do tipo de entidade para o qual você gostaria de importar indicadores.

3. Selecione **Importar**  >  **Escolher arquivo**. 

4. Selecione **Importar**. Faça isso para todos os arquivos que você gostaria de importar. 

5. Selecione **Concluído**.

A tabela a seguir mostra os parâmetros com suporte.

Parâmetro | Tipo    |   Descrição
:---|:---|:---
indicatorType | Enum | Tipo do indicador. Os valores possíveis são: "FileSha1", "FileSha256", "IpAddress", "DomainName" e "Url". **Required**
indicatorValue | Cadeia de caracteres | Identidade da entidade [Indicator.](ti-indicator.md) **Required**
ação | Enum | A ação que será tomada se o indicador for descoberto na organização. Os valores possíveis são: "Alert", "AlertAndBlock" e "Allowed". **Required**
title | Cadeia de caracteres | Título de alerta de indicador. **Required**
descrição | Cadeia de caracteres |  Descrição do indicador. **Required**
expirationTime | DateTimeOffset | O tempo de expiração do indicador no formato a seguir YYYY-MM-DDTHH:MM:SS.0Z. **Opcional**
severity | Enum | A gravidade do indicador. Os valores possíveis são: "Informacional", "Baixo", "Médio" e "Alto". **Opcional**
recommendedActions | Cadeia de caracteres | Ações recomendadas do alerta de ti. **Opcional**
rbacGroupNames | Cadeia de caracteres | Lista separada por vírgulas de nomes de grupo do RBAC aos que o indicador seria aplicado. **Opcional**
category | Cadeia de caracteres | Categoria do alerta. Exemplos incluem: execução e acesso de credenciais. **Opcional**
mitretechniques| Cadeia de caracteres | Código/id de técnicas MITRE (vírgula separada). Para obter mais informações, consulte [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/). **Opcional** É recomendável adicionar um valor na categoria quando uma técnica MITRE.

Para obter mais informações, consulte Categorias de alerta do Microsoft Defender for Endpoint agora estão alinhadas com [o MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).


## <a name="see-also"></a>Confira também
- [Criar indicadores](manage-indicators.md)
- [Criar indicadores para arquivos](indicator-file.md)
- [Criar indicadores para IPs e URLs/domínios](indicator-ip-domain.md)
- [Criar indicadores com base em certificados](indicator-certificates.md)
