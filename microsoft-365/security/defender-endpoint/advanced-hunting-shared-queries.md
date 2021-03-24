---
title: Usar consultas compartilhadas na busca avançada
description: Comece a rastrear ameaças imediatamente com consultas predefinidas e compartilhadas. Compartilhe suas consultas com o público em geral ou com a sua organização.
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, detecções personalizadas, esquema, kusto, repo github, minhas consultas, consultas compartilhadas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9788594eaab29aba54c634e79c7aa00d6148aacd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054202"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Usar consultas compartilhadas na busca avançada

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

[Buscas avançadas](advanced-hunting-overview.md) consultas podem ser compartilhadas entre usuários na mesma organização. Você também pode encontrar consultas compartilhadas publicamente no GitHub. Essas consultas permitem que você pesquise rapidamente cenários de busca específica de ameaças sem ter que escrever consultas do zero.

![Imagem de consultas compartilhadas](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Salvar, modificar e compartilhar uma consulta
Você pode salvar uma consulta nova ou existente para que ela possa ser acessada ou apenas por você ou então compartilhada com outros usuários em sua organização.

1. Digite uma nova consulta ou carregue uma existente em **Consultas compartilhadas** ou **Minhas consultas**.

2. Selecione **Salvar** ou **Salvar como** nas opções de salvar. Para evitar a substituição de uma consulta existente, escolha **Salvar como**.

3. Digite um nome para a consulta.

   ![Imagem de salvamento de uma consulta](images/advanced-hunting-save-query.png)

4. Selecione a pasta em que você deseja salvar a consulta.
    - **Consultas compartilhadas** — compartilhadas com todos os usuários em sua organização
    - **Minhas consultas** — acessíveis somente para você
    
5. Selecione **Salvar**.

## <a name="delete-or-rename-a-query"></a>Excluir ou renomear uma consulta
1. Clique com o botão direito do mouse em uma consulta que você deseja renomear ou excluir.

    ![Imagem da exclusão de consulta](images/atp_advanced_hunting_delete_rename.png)

2. Selecione **Exclua** e confirme a exclusão. Ou selecione **Renomear** e forneça um novo nome para a consulta.

## <a name="create-a-direct-link-to-a-query"></a>Criar um link direto para uma consulta
Para gerar um link que abra sua consulta diretamente no editor de consulta de busca avançada, finalize sua consulta e selecione **Compartilhar link**.

## <a name="access-queries-in-the-github-repository"></a>Acessar consultas no repositório do GitHub  
Os pesquisadores de segurança da Microsoft compartilham regularmente consultas avançadas em um [repositório público designado no GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries). Esse repositório está aberto para a contribuições. Para contribuir, acesse [integrar o GitHub gratuitamente](https://github.com/). 

>[!TIP]
>Os pesquisadores de segurança da Microsoft também oferecem consultas avançadas para que você possa localizar atividades e indicadores associados a ameaças emergentes. Essas consultas são fornecidas como parte dos relatórios de [análise de ameaças](threat-analytics.md) da Central de Segurança do Microsoft Defender.

## <a name="related-topics"></a>Tópicos relacionados
- [Visão geral da busca avançada](advanced-hunting-overview.md)
- [Aprender a linguagem de consulta](advanced-hunting-query-language.md)
- [Trabalhar com os resultados da consulta](advanced-hunting-query-results.md)
- [Compreender o esquema](advanced-hunting-schema-reference.md)
- [Aplicar práticas recomendadas de consulta](advanced-hunting-best-practices.md)
- [Visão geral de detecções personalizadas](overview-custom-detections.md)
