---
title: Visão geral de arquivamento ilimitado
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Saiba mais sobre o arquivamento de expansão automática, que fornece armazenamento de arquivo morto ilimitado para Exchange Online caixas de correio.
ms.openlocfilehash: d61d3649ed65a93298928cced21180bbeca6aa95
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476262"
---
# <a name="overview-of-unlimited-archiving"></a>Visão geral de arquivamento ilimitado

Em Office 365, as caixas de correio de arquivo morto fornecem aos usuários espaço de armazenamento de caixa de correio adicional. Depois que a caixa de correio de arquivo morto de um usuário é habilitada, até 100 GB de armazenamento adicional estará disponível. No passado, quando a cota de armazenamento de 100 GB era atingida, as organizações tinham que entrar em contato com a Microsoft para solicitar espaço de armazenamento adicional para uma caixa de correio de arquivo morto. Esse não é mais o caso.

O recurso de arquivamento ilimitado no Microsoft 365 (chamado arquivamento de expansão automática *)* fornece armazenamento adicional em caixas de correio de arquivo morto. Quando a cota de armazenamento na caixa de correio de arquivo morto é atingida, o Microsoft 365 aumenta automaticamente o tamanho do arquivo morto, o que significa que os usuários não ficarão sem espaço de armazenamento de caixa de correio e os administradores não terão que solicitar armazenamento adicional para caixas de correio de arquivo morto.

Para obter instruções passo a passo para ativar o arquivamento de expansão automática, consulte [Enable unlimited archiving](enable-unlimited-archiving.md).

> [!NOTE]
> A expansão automática do arquivamento também oferece suporte às caixas de correio compartilhadas. Para habilitar o arquivo morto para uma caixa de correio compartilhada, é necessária uma licença Exchange Online Plano 2 ou uma licença Exchange Online Plano 1 com uma Arquivamento do Exchange Online de usuário.

## <a name="how-auto-expanding-archiving-works"></a>Como funciona o arquivamento de expansão automática

Conforme explicado anteriormente, o espaço de armazenamento de caixa de correio adicional é criado quando a caixa de correio de arquivo morto do usuário está habilitada. Quando o arquivamento de expansão automática está habilitado, Microsoft 365 verifica periodicamente o tamanho da caixa de correio de arquivo morto. Quando uma caixa de correio de arquivo morto se aproxima do limite de armazenamento, Microsoft 365 cria automaticamente espaço de armazenamento adicional para o arquivo morto. Se o usuário ficar sem esse espaço de armazenamento adicional, Microsoft 365 adiciona mais espaço de armazenamento ao arquivo morto do usuário. Esse processo acontece automaticamente, o que significa que os administradores não têm que solicitar armazenamento de arquivo morto adicional ou gerenciar o arquivamento de expansão automática.

Aqui está uma visão geral rápida do processo.

![Visão geral do processo de arquivamento de expansão automática](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. O arquivamento está habilitado para uma caixa de correio de usuário ou uma caixa de correio compartilhada. Uma caixa de correio de arquivo morto com 100 GB de espaço de armazenamento é criada e a cota de aviso para a caixa de correio de arquivo morto é definida como 90 GB.

2. Um administrador habilita o arquivamento de expansão automática para a caixa de correio. Quando a caixa de correio de arquivo morto (incluindo a pasta Itens Recuperáveis) atinge 90 GB, ela é convertida em um arquivo morto em expansão automática e Microsoft 365 adiciona espaço de armazenamento ao arquivo morto. Pode levar até 30 dias para que o espaço de armazenamento adicional seja provisionado.

   > [!NOTE]
   > Se uma caixa de correio for colocada em retenção ou atribuída a uma política de retenção, a cota de armazenamento da caixa de correio de arquivo morto será aumentada para 110 GB quando o arquivamento de expansão automática estiver habilitado. Da mesma forma, a cota de aviso de arquivo morto é aumentada para 100 GB.

3. Microsoft 365 adiciona automaticamente mais espaço de armazenamento quando necessário.

> [!IMPORTANT]
> O arquivamento de expansão automática só é suportado para caixas de correio usadas para usuários individuais (ou caixas de correio compartilhadas) com uma taxa de crescimento que não excede 1 GB por dia. A caixa de correio de arquivo morto de um usuário destina-se somente a esse usuário. Não é permitido usar o diário, as regras de transporte ou o encaminhamento automático de regras para copiar mensagens para uma caixa de correio de arquivo morto. A Microsoft se reserva o direito de negar o arquivamento ilimitado em instâncias em que a caixa de correio de arquivo morto de um usuário é usada para armazenar dados de arquivo morto para outros usuários ou em outros casos de uso inadequado.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>O que é movido para o espaço de armazenamento de arquivo morto adicional?

Para fazer uso eficiente do armazenamento de arquivo morto de expansão automática, as pastas podem ser movidas. Microsoft 365 determina quais pastas serão movidas quando o armazenamento adicional for adicionado ao arquivo morto. Às vezes, quando uma pasta é movida, uma ou mais subpastas são criadas automaticamente e os itens da pasta original são distribuídos para essas pastas para facilitar o processo de movimentação. Ao exibir a parte de arquivo morto da lista de pastas Outlook, essas subpastas são exibidas na pasta original.  A convenção de nomenis Microsoft 365 usa para nomear essas subpastas é _yyyy (Criada em **\<folder name\> mmm dd, yyyy h_mm)**, onde:

- **yyyy é** o ano em que as mensagens na pasta foram recebidas.

- **mmm dd, yyyy h_m** é a data e a hora em que a subpasta foi criada pelo Office 365, no formato UTC, com base no fuso horário do usuário e nas configurações regionais no Outlook.

As capturas de tela a seguir mostram uma lista de pastas antes e depois que as mensagens são movidas para um arquivo morto expandido automaticamente.

 **Antes que o armazenamento adicional seja adicionado**

![Lista de pastas da caixa de correio de arquivo morto antes da expansão automática do arquivo morto ser provisionada](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **Depois que o armazenamento adicional é adicionado**

![Lista de pastas da caixa de correio de arquivo morto após a expansão automática do arquivo morto ser provisionada](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> Conforme descrito anteriormente, o Microsoft 365 move itens para subpastas (e os nomeia usando a convenção de nomenlicação descrita acima) para ajudar a distribuir conteúdo para um arquivo morto auxiliar. Mas a mudança de itens para subpastas pode nem sempre ser o caso. Às vezes, uma pasta inteira pode ser movida para um arquivo morto auxiliar. Nesse caso, a pasta manterá seu nome original.  Não será aparente na lista de pastas na Outlook que a pasta foi movida para um arquivo morto auxiliar.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Outlook requisitos para acessar itens em um arquivo morto expandido automaticamente

Para acessar mensagens armazenadas em um arquivo morto expandido automaticamente, os usuários têm que usar um dos seguintes Outlook clientes:

- Outlook 2016 ou Outlook 2019 para Windows

- Outlook na Web

- Outlook 2016 ou Outlook 2019 para Mac

Aqui estão algumas coisas a considerar ao usar Outlook ou Outlook na Web para acessar mensagens armazenadas em um arquivo morto expandido automaticamente.

- Você pode acessar qualquer pasta em sua caixa de correio de arquivo morto, incluindo as que foram movidas para a área de armazenamento expandida automaticamente.

- A pesquisa de arquivamento expandido automaticamente está disponível Outlook web (OWA). Semelhante ao Arquivo Morto Online, você pode pesquisar itens que foram movidos para uma área de armazenamento adicional. Quando o arquivo morto é selecionado como o escopo de pesquisa no OWA, todos os arquivos (incluindo arquivos expandidos automaticamente) e suas subpastas correspondentes serão pesquisados.

- A pesquisa de arquivo morto expandido automaticamente está disponível Outlook Área de Trabalho no Canal Atual (Visualização). Nesta visualização, o escopo Caixa de Correio Atual está disponível, permitindo que você pesquise o arquivo morto expandido automaticamente. Para obter mais informações sobre isso e outros recursos de suporte à Pesquisa da Microsoft, consulte [How Outlook for Windows connected to Exchange Online use Microsoft Search](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045). 

- As contagens de itens Outlook contagens de leitura/não lidas (em Outlook e Outlook na Web) em um arquivo morto expandido automaticamente podem não ser precisas.

- Você pode excluir itens em uma subpasta que aponta para uma área de armazenamento expandida automaticamente, mas a pasta em si não pode ser excluída.

- Não é possível usar o recurso Recuperar Itens Excluídos para recuperar um item que foi excluído de uma área de armazenamento expandida automaticamente.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>Arquivamento de expansão automática e outros recursos de conformidade

Esta seção explica a funcionalidade entre o arquivamento de expansão automática e outros recursos de conformidade e governança de dados.

- **Descoberta eDiscovery:** Quando você usa uma ferramenta de Descoberta Automática, como Pesquisa de Conteúdo ou In-Place Descoberta In-Place, as áreas de armazenamento adicionais em um arquivo morto expandido automaticamente também são pesquisadas.

- **Retenção:** Quando você coloca uma caixa de correio em espera usando ferramentas como Retenção de Litígio no Exchange Online ou políticas de retenção e retenção de caso de Descoberta Automática no centro de segurança e conformidade, o conteúdo localizado em um arquivo morto expandido automaticamente também é colocado em espera.

- **Gerenciamento de registros de mensagens (MRM):** Se você usar políticas de exclusão mrm no Exchange Online excluir permanentemente itens de caixa de correio expirados, os itens expirados localizados no arquivo morto expandido automaticamente também serão excluídos.

- **Serviço de importação:** Você pode usar o serviço Office 365 Import para importar arquivos PST para o arquivo morto expandido automaticamente do usuário. Você pode importar até 100 GB de dados de arquivos PST para a caixa de correio de arquivo morto do usuário.

## <a name="more-information"></a>Mais informações

Para obter mais detalhes técnicos sobre o arquivamento de expansão automática, [consulte Microsoft 365: Perguntas frequentes](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)sobre arquivos em expansão automática.
