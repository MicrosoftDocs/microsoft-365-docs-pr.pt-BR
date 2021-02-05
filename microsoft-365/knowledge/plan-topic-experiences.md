---
title: Planejar tópicos do Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Saiba como planejar o planejamento de tópicos do Microsoft Viva
ms.openlocfilehash: 65983f342b3277d33c7bfeb21d8481b1d3d5e817
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107949"
---
# <a name="plan-for-microsoft-viva-topics"></a>Planejar tópicos do Microsoft Viva

Você controla como os tópicos são experientes em sua organização. Suas decisões de planejamento para Tópicos garantem que os tópicos de alta qualidade sejam mostrados aos seus usuários e que eles tenham as permissões corretas para consumir e contribuir com o conhecimento.

Neste artigo, examinaremos estas decisões de planejamento:

- Quais sites do SharePoint você deseja rastrear para tópicos
- Quais tópicos, se algum, você deseja excluir das experiências de tópico
- Para quais usuários você deseja tornar os tópicos visíveis
- Quais usuários você deseja dar permissões para gerenciar tópicos no centro de tópicos
- Quais usuários você deseja dar permissões para criar ou editar tópicos no centro de tópicos
- Qual nome você deseja dar ao seu centro de tópicos

A segurança e a privacidade dos seus dados são respeitadas, e as experiências de tópicos não concedem aos usuários acesso adicional aos arquivos aos que eles não têm direitos. Recomendamos que você leia também a segurança e a privacidade [dos Tópicos](topic-experiences-security-privacy.md) do Microsoft Viva como parte do seu processo de planejamento.

## <a name="requirements"></a>Requisitos

Você deve ser um administrador global ou administrador do SharePoint para acessar o centro de administração do Microsoft 365 e configurar Tópicos.

Todos os usuários que usarão Tópicos exigem uma licença **de Experiências de** Tópico. A atribuição de licenças é [abordada em Configurar tópicos do Microsoft Viva.](set-up-topic-experiences.md)

## <a name="topic-discovery"></a>Descoberta de tópicos

As configurações de descoberta de tópico especificam quais sites do SharePoint são usados como fontes para tópicos. Você pode optar por incluir todos os sites do SharePoint, uma lista específica de sites ou nenhum site. Recomendamos que você escolha todos os sites para que as experiências de tópico possam descobrir um grande número de tópicos bons para seus usuários.

Ao configurar tópicos, você pode escolher entre as seguintes opções:

- **Todos os sites:** todos os sites do SharePoint em sua organização. Isso inclui sites atuais e futuros.
- **Todos, exceto os sites selecionados:** todos os sites, exceto aqueles que você especificar. Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos. 
- **Somente sites selecionados:** somente os sites que você especificar. Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.
- **Nenhum site:** não inclua sites do SharePoint.

Se você escolher **Todos,** exceto sites selecionados ou Apenas **sites** selecionados, poderá carregar um arquivo .csv com uma lista de sites. Essas opções são úteis se você estiver fazendo um piloto e quiser incluir um número limitado de sites para iniciar.

Você pode copiar o modelo .csv abaixo:

``` csv
Site name,URL
```

Não recomendamos escolher **Nenhum site porque** impede que os tópicos são criados ou atualizados automaticamente. No entanto, você pode escolher essa opção se quiser configurar Tópicos e adicionar sites mais tarde.

Recomendamos que você crie um processo para que os usuários ou gerentes de conhecimento solicitem que sites individuais sejam removidos da descoberta de tópicos, se necessário, em sua organização.

## <a name="user-permissions"></a>Permissões do usuário

As permissões de usuário especificadas determinam quais pessoas em sua organização interagem com tópicos e o que elas podem fazer.

*Gerenciar tópicos*

Gerentes de conhecimento supervisionam a qualidade das informações, como ela é estruturada e outras práticas recomendadas em sua organização. Eles podem confirmar e rejeitar tópicos.

Embora você possa especificar gerentes de tópico individuais, recomendamos que você crie um grupo de segurança (ou use um existente) que contenha as pessoas que você deseja que sejam gerentes de conhecimento. Você pode especificar esse grupo de segurança durante o processo de instalação.

*Criar e editar tópicos*

Os colaboradores do tópico são os campeões e especialistas no assunto em sua organização. Eles podem criar e editar tópicos. 

Recomendamos que você permita que todos em sua organização criem e editem tópicos porque as experiências de tópico funcionam melhor quando todos os usuários podem compartilhar informações.

Se você deseja limitar a criação e edição de tópicos a pessoas ou grupos específicos, crie um grupo de segurança para eles e especifique-o durante o processo de configuração.

Você pode optar por não permitir que ninguém contribua com tópicos, no entanto, isso não é recomendado. Os gerentes de conhecimento ainda poderão editar e criar tópicos se você escolher essa opção.

*Visualizadores de tópicos*

Os visualizadores de tópicos podem ver informações em páginas de tópicos, nos resultados da pesquisa e quando os tópicos são realçados no conteúdo, como páginas do SharePoint. Os usuários só podem ver tópicos descobertos quando têm acesso aos arquivos e páginas em que o tópico foi descoberto.

Ao configurar os visualizadores de tópicos, você pode escolher entre:

- **Todos na minha organização**
- **Somente pessoas ou grupos de segurança selecionados**
- **Ninguém**

Recomendamos **Todos na minha organização,** mas se você estiver fazendo um piloto, talvez queira escolher apenas pessoas ou grupos de segurança selecionados. Você também pode **escolher Ninguém se** quiser configurar Tópicos, mas ainda não permitir que as pessoas vejam tópicos. (Os gerentes de conhecimento ainda terão acesso para permitir que eles consultem os tópicos e ajudar na decisão de tornar os Tópicos amplamente disponíveis.)

## <a name="knowledge-rules"></a>Regras de conhecimento

Como administrador, você pode excluir determinados tópicos de experiências de tópicos. Isso será útil se você quiser evitar que dados confidenciais apareçam em tópicos. Embora os gerentes de conhecimento possam excluir tópicos no centro de tópicos, os tópicos excluídos pelo administrador nem mesmo são visíveis para os gerentes de conhecimento. (Os gerentes de conhecimento também podem remover tópicos no centro de tópicos após a descoberta.)

Se quiser excluir tópicos no nível do administrador, você deve adicioná-los a um arquivo .csv e carregar o arquivo. Você pode fazer isso durante a instalação ou posterior.

O arquivo .csv deve conter os seguintes parâmetros:

- **Nome:** digite o nome do tópico que você deseja excluir. Há duas maneiras de fazer isso:
- **MatchType-Exact/Partial**: digite se o nome digitado foi um *tipo de* combinação exato *ou* parcial.
    - Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).
    - Parciais: você pode excluir todos os tópicos que têm uma palavra específica.  Por exemplo, *o arco* excluirá  todos os tópicos com o arco de palavras nele, como Arc *circle*, *Arc arc* ou *Training arc*. Observe que ele não excluirá tópicos nos quais o texto é incluído como parte de uma palavra, *como* Arquitetura .
- **Significa (opcional)**: (também conhecido como expansão) Se você quiser excluir um acrônimo, digite as palavras que o acrônimo representa.

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

Você pode copiar o modelo csv abaixo:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Administração

Quando você configura Tópicos, como parte do processo de configuração, um centro de tópicos é criado automaticamente. Pense em como você deseja nomear o centro de tópicos e o que você deseja que a URL seja. Você pode definir o nome e a URL como parte do processo de instalação e pode alterar o nome (mas não a URL) posteriormente no Centro de administração do Microsoft 365. Você só pode ter um centro de tópicos.

## <a name="setup-checklist"></a>Lista de verificação de instalação

Ao configurar experiências de tópico, você precisará dos seguintes itens ao passar pelo assistente de configuração:

> [!div class="checklist"]
> * Lista de sites a incluir ou excluir se não incluir todos os sites para descoberta de tópicos
> * Grupo de segurança para visualizadores de tópicos se não permitir que todos os usuários consultem tópicos
> * Grupo de segurança para colaboradores de tópicos se não permitir que todos os usuários criem e editem tópicos
> * Grupo de segurança para gerentes de conhecimento de tópicos se não permitir que todos os usuários gerenciem tópicos
> * Lista de tópicos confidenciais a excluir da descoberta de tópicos
> * Um nome para seu site central de tópicos

## <a name="see-also"></a>Confira também

[Configurar Experiências de tópico](set-up-topic-experiences.md)

[Gerenciar a descoberta de tópicos no Microsoft 365](topic-experiences-discovery.md)

[Gerenciar visibilidade do tópico no Microsoft 365](topic-experiences-knowledge-rules.md)

[Gerenciar permissões de tópico no Microsoft 365](topic-experiences-user-permissions.md)

[Alterar o nome do centro de tópicos no Microsoft 365](topic-experiences-administration.md)
