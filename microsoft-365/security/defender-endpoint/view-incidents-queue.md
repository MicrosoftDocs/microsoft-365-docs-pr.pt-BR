---
title: Exibir e organizar a Fila de incidentes
ms.reviewer: ''
description: Consulte a lista de incidentes e saiba como aplicar filtros para limitar a lista e obter uma exibição mais focada.
keywords: exibir, organizar, incidentes, agregar, investigações, fila, ttp
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93aa685f12e0241758bf86d3aa956717db052e5f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499931"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a>Exibir e organizar a fila do Microsoft Defender para Incidentes de Ponto de Extremidade

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Aplica-se a:**
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

A **fila Incidentes** mostra uma coleção de incidentes que foram sinalizados de dispositivos em sua rede. Isso ajuda a classificar incidentes e criar uma decisão de resposta de segurança cibernética embasada.

Por padrão, a fila exibe incidentes vistos nos últimos 30 dias, com o incidente mais recente sendo exibido na parte superior da lista, ajudando você a ver os incidentes mais recentes primeiro.

Há várias opções que você pode escolher para personalizar o exibição de fila de incidentes. 

Na navegação superior, você pode:
- Personalizar colunas para adicionar ou remover colunas 
- Modificar o número de itens para exibição por página
- Selecione os itens a mostrar por página
- Selecione em lotes os incidentes a atribuir 
- Navegar entre páginas
- Aplicar filtros

![Imagem da fila de incidentes](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a>Classificar e filtrar a fila de incidentes
Você pode aplicar os filtros a seguir para limitar a lista de incidentes e obter uma exibição mais focada.

### <a name="severity"></a>Severity

Gravidade do incidente | Descrição
:---|:---
Alto </br>(Vermelho) | Ameaças frequentemente associadas a ameaças persistentes avançadas (APT). Esses incidentes indicam um alto risco devido à gravidade dos danos que podem causar em dispositivos.
Médio </br>(Laranja) | Ameaças raramente observadas na organização, como alteração anômala do Registro, execução de arquivos suspeitos e comportamentos observados típicos de estágios de ataque.
Baixo </br>(Amarelo) | Ameaças associadas a malwares e ferramentas de hackers predominantes que não indicam necessariamente uma ameaça avançada direcionando a organização.
Informações </br>(Cinza) | Incidentes informacionais podem não ser considerados prejudiciais para a rede, mas podem ser bons para acompanhar.

## <a name="assigned-to"></a>Atribuído a
Você pode optar por filtrar a lista selecionando não atribuir a ninguém ou os que estão atribuídos a você.

### <a name="category"></a>Categoria
Os incidentes são categorizados com base na descrição do estágio em que a cadeia de crimes de segurança cibernética está. Essa exibição ajuda o analista de ameaças a determinar a prioridade, a urgência e a estratégia de resposta correspondente a ser implantada com base no contexto.

### <a name="status"></a>Status
Você pode optar por limitar a lista de incidentes exibidos com base em seu status para ver quais estão ativos ou resolvidos.

### <a name="data-sensitivity"></a>Confidencialidade de dados
Use este filtro para mostrar incidentes que contêm rótulos de sensibilidade.

## <a name="incident-naming"></a>Nomeação de incidente

Para entender rapidamente o escopo do incidente, os nomes de incidentes são gerados automaticamente com base em atributos de alerta, como o número de pontos de extremidade afetados, usuários afetados, fontes de detecção ou categorias.

Por exemplo: *incidente em vários estágios em vários pontos de extremidade relatados por várias fontes.*

> [!NOTE]
> Incidentes que existiam antes da adoção da nomenização automática de incidentes manterão seu nome.


## <a name="see-also"></a>Confira também
- [Fila de incidentes](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [Gerenciar incidentes](manage-incidents.md)
- [Investigar incidentes](investigate-incidents.md)

