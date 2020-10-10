---
title: Detalhes e resultados de uma investigação automatizada
description: Durante e após uma investigação automática, você pode exibir os resultados e as principais descobertas
keywords: automatização, investigação, resultados, análise, detalhes, correção, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 96fa036d3154b15499303623efe027e4d340c98a
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48413621"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Detalhes e resultados de uma investigação automatizada

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Proteção contra Ameaças da Microsoft

Quando uma investigação automatizada ocorrer na Proteção Contra Ameaças da Microsoft, os detalhes dessa investigação estarão disponíveis durante e após o processo de investigação automática. Se você tiver as [permissões necessárias](mtp-action-center.md#required-permissions-for-action-center-tasks), poderá exibir esses detalhes na exibição de detalhes da investigação. A exibição de detalhes da investigação fornece o status atualizado e a capacidade de aprovar as ações pendentes. 

![Detalhes da investigação](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>Abrir a exibição de detalhes da investigação

Você pode abrir a exibição de detalhes da investigação usando um destes métodos:
- [Selecionar um item na central de Ações](#select-an-item-in-the-action-center)
- [Selecionar uma investigação em uma página de detalhes do incidente](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Selecionar um item na central de Ações

Use a central de ações para exibir as ações que estão pendentes (na guia **Pendente**) ou que já foram aprovadas (na guia **Histórico**). 

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 

2. No painel de navegação, escolha **Central de ações**. 

3. Na guia **Pendente**ou **Histórico**, selecione um item. Se você tiver as [permissões necessárias](mtp-action-center.md#required-permissions-for-action-center-tasks), poderá aprovar (ou rejeitar) ações pendentes.

### <a name="open-an-investigation-from-an-incident-details-page"></a>Abrir uma investigação em uma página de detalhes do incidente

Use uma página de detalhes do incidente para exibir informações detalhadas sobre um incidente, incluindo os alertas que foram disparados com informações sobre os dispositivos afetados, contas de usuários ou caixas de correio.

1. Vá para [https://security.microsoft.com](https://security.microsoft.com) e entre. 

2. No painel de navegação, escolha **Incidentes**. 

3. Selecione um item na lista para abrir a exibição de detalhes do incidente.<br/>![Detalhes do incidente](../../media/mtp-incidentdetails-tabs.png)

4. Na guia **Investigações**, selecione uma investigação na lista.

## <a name="investigation-details"></a>Detalhes da investigação

Use o modo de exibição de detalhes da investigação para ver as atividades antigas, atuais e pendentes referentes a uma investigação. A exibição de detalhes de investigação se parece com a seguinte imagem:

![Detalhes da investigação](../../media/mtp-air-investdetails.png)

Na exibição de detalhes da investigação, você pode ver as informações nas guias **Gráfico de Investigação**, **Alertas**, **Dispositivos**, **Identidades**, **Principais descobertas**, **Entidades**,**Log** e **Ações pendentes**, descritas na tabela a seguir.

|Guia    |Descrição |
|--------|--------|
|Gráficos de investigação    |Oferece uma representação visual da investigação. Descreve entidades e lista as ameaças encontradas, juntamente com os alertas, e se as ações estão aguardando aprovação.<br/>Você pode clicar em um item no gráfico para exibir mais detalhes. Por exemplo, clicar no ícone **Ameaças encontradas** o levará para a guia **Principais conclusões**. |
|Alertas |Lista os alertas associados à investigação. Os alertas podem ser de recursos de proteção contra ameaças no computador de um usuário, em aplicativos do Office, Cloud app Security e outros recursos de Proteção Contra Ameaças da Microsoft 365.|
|Dispositivos|Lista os computadores incluídos na investigação, juntamente com o nível de correção.|
|Conclusões principais   |Lista os resultados da investigação, juntamente com o status e as ações realizadas ou pendentes. Você pode aprovar as ações pendentes para dispositivos e identidades na guia.|
|Entidades   |Lista as atividades do usuário, os arquivos, os processos, os serviços, os endereços IP, drivers, e os métodos de persistência associados à investigação, juntamente com o status e as ações realizadas.|
|Log    |Fornece uma exibição detalhada de todas as etapas realizadas durante a investigação, juntamente com o status.|
|Ações pendentes    |Lista os itens que exigem aprovação para prosseguir.|

## <a name="next-steps"></a>Próximas etapas

- [Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas](mtp-autoir-actions.md)

