---
title: Usar consultas compartilhadas Microsoft 365 busca avançada do Defender
description: Comece a rastrear ameaças imediatamente com consultas predefinidas e compartilhadas. Compartilhe suas consultas com o público em geral ou com a sua organização.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, detecções personalizadas, esquema, kusto, repo github, minhas consultas, consultas compartilhadas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952579"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Usar consultas compartilhadas na busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender
- Microsoft Defender para Ponto de Extremidade



[Buscas avançadas](advanced-hunting-overview.md) consultas podem ser compartilhadas entre usuários na mesma organização. Você também pode encontrar consultas compartilhadas publicamente no GitHub. Essas consultas permitem que você pesquise rapidamente cenários de busca específica de ameaças sem ter que escrever consultas do zero.

![Imagem de consultas compartilhadas](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Salvar, modificar e compartilhar uma consulta
Você pode salvar uma consulta nova ou existente para que ela possa ser acessada ou apenas por você ou então compartilhada com outros usuários em sua organização. 

1. Criar ou modificar uma consulta. 

2. Clique no botão suspenso **Salvar consulta** e selecione **Salvar como**.
    
3. Digite um nome para a consulta. 

   ![Imagem de salvamento de uma consulta](../../media/advanced-hunting-save-query.png)

4. Selecione a pasta em que você deseja salvar a consulta.
    - **Consultas compartilhadas** — compartilhadas com todos os usuários da organização
    - **Minhas consultas** — acessíveis somente para você
    
5. Selecione **Salvar**. 

## <a name="delete-or-rename-a-query"></a>Excluir ou renomear uma consulta
1. Clique com o botão direito do mouse em uma consulta que você deseja renomear ou excluir.

    ![Imagem da exclusão de consulta](../../media/advanced_hunting_delete_rename.png)

2. Selecione **Exclua** e confirme a exclusão. Ou selecione **Renomear** e forneça um novo nome para a consulta.

## <a name="create-a-direct-link-to-a-query"></a>Criar um link direto para uma consulta
Para gerar um link que abra sua consulta diretamente no editor de consulta de busca avançada, finalize sua consulta e selecione **Compartilhar link**.

## <a name="access-queries-in-the-github-repository"></a>Acessar consultas no repositório do GitHub  
Os pesquisadores de segurança da Microsoft compartilham regularmente consultas avançadas em um [repositório público designado no GitHub](https://aka.ms/hunting-queries). Esse repositório está aberto para a contribuições. Para contribuir, acesse [integrar o GitHub gratuitamente](https://github.com/).

>[!tip]
>Os pesquisadores de segurança da Microsoft também oferecem consultas avançadas para que você possa localizar atividades e indicadores associados a ameaças emergentes. Essas consultas são fornecidas como parte dos relatórios de [análise de ameaças](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) da Central de Segurança do Microsoft Defender.

>[!NOTE]
>Algumas tabelas neste artigo podem não estar disponíveis no Microsoft Defender para Ponto de Extremidade. [A Microsoft 365 Defender para](m365d-enable.md) procurar ameaças usando mais fontes de dados. Você pode mover seus fluxos de trabalho de busca avançados do Microsoft Defender para o Endpoint para o Microsoft 365 Defender seguindo as etapas em Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de [Extremidade.](advanced-hunting-migrate-from-mde.md)

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Buscar em dispositivos, e-mails, aplicativos e identidades](advanced-hunting-query-emails-devices.md)
- [Compreender o esquema](advanced-hunting-schema-tables.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)