---
title: Utilize consultas compartilhadas na busca avançada da Proteção contra Ameaças da Microsoft
description: Comece a rastrear ameaças imediatamente com consultas predefinidas e compartilhadas. Compartilhe suas consultas com o público em geral ou com a sua organização.
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, Kusto, repositório do GitHub, minhas consultas, consultas compartilhadas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 64c9b07dad0f109698222d3f3f079a4f3318273a
ms.sourcegitcommit: 5b8e9935fe7bfcb96b8f8356119ce23152bd16a9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2020
ms.locfileid: "41210306"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Usar consultas compartilhadas na busca avançada

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[Buscas avançadas](advanced-hunting-overview.md) consultas podem ser compartilhadas entre usuários na mesma organização. Você também pode encontrar consultas compartilhadas publicamente no GitHub. Essas consultas permitem que você pesquise rapidamente cenários de busca específica de ameaças sem ter que escrever consultas do zero.

![Imagem de consultas compartilhadas](../images/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Salvar, modificar e compartilhar uma consulta
Você pode salvar uma consulta nova ou existente para que ela possa ser acessada ou apenas por você ou então compartilhada com outros usuários em sua organização. 

1. Criar ou modificar uma consulta. 

2. Clique no botão suspenso **Salvar consulta** e selecione **Salvar como**.
    
3. Digite um nome para a consulta. 

   ![Imagem de salvamento de uma consulta](../images/advanced-hunting-save-query.png)

4. Selecione a pasta em que você deseja salvar a consulta.
    - **Consultas compartilhadas** — compartilhadas com todos os usuários da organização
    - **Minhas consultas** — acessíveis somente para você
    
5. Selecione **Salvar**. 

## <a name="delete-or-rename-a-query"></a>Excluir ou renomear uma consulta
1. Clique com o botão direito do mouse em uma consulta que você deseja renomear ou excluir.

    ![Imagem da exclusão de consulta](../images/advanced_hunting_delete_rename.png)

2. Selecione **Exclua** e confirme a exclusão. Ou selecione **Renomear** e forneça um novo nome para a consulta.

## <a name="access-queries-in-the-github-repository"></a>Acessar consultas no repositório do GitHub  
Os pesquisadores de segurança da Microsoft compartilham regularmente consultas avançadas em um [repositório público designado no GitHub](https://github.com/microsoft/MTP-AHQ). Esse repositório está aberto para a contribuições. Para contribuir, acesse [integrar o GitHub gratuitamente](https://github.com/).

>[!tip]
>Os pesquisadores de segurança da Microsoft também oferecem consultas avançadas para que você possa localizar atividades e indicadores associados a ameaças emergentes. Essas consultas são fornecidas como parte dos relatórios de [análise de ameaças](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) da Central de Segurança do Microsoft Defender.

## <a name="related-topics"></a>Tópicos relacionados
- [Buscar proativamente por ameaças](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Buscar por ameaças em dispositivos e emails](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)