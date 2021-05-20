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
description: Saiba como planejar os Tópicos do Microsoft Viva
ms.openlocfilehash: de7534ce58a7888ac822826ef4ef1b4934ed8cb1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583107"
---
# <a name="plan-for-microsoft-viva-topics"></a>Planejar tópicos do Microsoft Viva

Você está no controle de como os tópicos são experimentado em sua organização. Suas decisões de planejamento para Tópicos garantem que os tópicos de alta qualidade sejam mostrados aos usuários e que eles tenham as permissões certas para consumir e contribuir com conhecimento.

Neste artigo, examinaremos essas decisões de planejamento:

- Quais SharePoint sites que você deseja rastrear para tópicos
- Quais tópicos, se algum, você deseja excluir das experiências de tópico
- Para quais usuários você deseja tornar os tópicos visíveis
- Quais usuários você deseja dar permissões para gerenciar tópicos no centro de tópicos
- Quais usuários você deseja dar permissões para criar ou editar tópicos no centro de tópicos
- Qual nome você deseja dar ao centro de tópicos

A segurança e a privacidade de seus dados são respeitadas, e as experiências de tópico não concedem aos usuários acesso adicional aos arquivos aos que eles não têm direitos. Recomendamos que você também leia a segurança e a privacidade [dos Tópicos](topic-experiences-security-privacy.md) do Microsoft Viva como parte do seu processo de planejamento.

Para saber mais sobre a tecnologia de IA por trás dos Tópicos do Viva, leia a leitura de Alexandria em Tópicos do Microsoft Viva: de [big data a grande conhecimento.](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)

## <a name="requirements"></a>Requisitos

Você deve estar inscrito em [Tópicos](https://www.microsoft.com/microsoft-viva/topics) do Viva e ser um administrador global ou SharePoint para acessar o centro de administração Microsoft 365 e configurar Tópicos.

Todos os usuários que vão usar Tópicos exigem uma **licença experiências de** tópico. A atribuição de licenças é abordada [em Configurar Tópicos do Microsoft Viva.](set-up-topic-experiences.md)

## <a name="topic-discovery"></a>Descoberta de tópicos

As configurações de descoberta de tópicos especificam quais sites do Microsoft Office SharePoint Online são usados como fontes de tópicos. Você pode optar por incluir todos os sites do Microsoft Office SharePoint Online, uma lista específica de sites ou nenhum site. Recomendamos que você escolha todos os sites para que as experiências de tópico possam descobrir um grande número de tópicos bons para seus usuários.

Ao configurar tópicos, você pode escolher entre as seguintes opções:

- **Todos os**: todos os sites do Microsoft Office SharePoint Online em sua organização. Isso inclui sites atuais e futuros.
- **Tudo, exceto sites selecionados**: Todos os sites, exceto aqueles que você especificar. Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos. 
- **Somente sites selecionados:** somente os sites especificados. Sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.
- **Nenhum site**: Não incluir sites do Microsoft Office SharePoint Online.

Se você escolher **Todos,** exceto sites selecionados ou Somente **sites** selecionados, poderá carregar um arquivo .csv com uma lista de sites. Essas opções são úteis se você estiver fazendo um piloto e quiser incluir um número limitado de sites para iniciar.

Você pode copiar o modelo .csv abaixo:

``` csv
Site name,URL
```

Não recomendamos escolher **Nenhum site** porque impede que os tópicos são criados ou atualizados automaticamente. No entanto, você pode escolher essa opção se quiser configurar Tópicos e adicionar sites posteriormente.

Recomendamos que você crie um processo para usuários ou gerentes de conhecimento solicitarem que sites individuais sejam removidos da descoberta de tópicos, se necessário em sua organização.

### <a name="multi-geo"></a>Multi-Geo

Se sua organização tiver implantado Microsoft 365 [multi-geo](/microsoft-365/enterprise/microsoft-365-multi-geo), o centro de tópicos será provisionado no local central e somente os sites SharePoint no local central estarão disponíveis para uso como fontes para tópicos. (Se você selecionar **Todos os sites,** os Tópicos do Viva usarão todos os sites no local central.)

Todo o processamento e armazenamento do conteúdo é feito no local central.

## <a name="user-permissions"></a>Permissões do usuário

As permissões de usuário especificadas determinam quais pessoas em sua organização interagem com tópicos e o que podem fazer.

> [!Note] 
> Neste momento, os Tópicos do Viva não suportam o fornecimento de licenças ou permissões de usuário para usuários convidados (externos). 

*Gerenciar tópicos*

Os gerentes de conhecimento supervisionam a qualidade das informações, sua estrutura e outras práticas recomendadas em sua organização. Eles podem confirmar e rejeitar tópicos.

Embora você possa especificar gerentes de tópicos individuais, recomendamos que você crie um grupo de segurança (ou use um existente) que contenha as pessoas que você deseja ser gerentes de conhecimento. Você pode especificar esse grupo de segurança durante o processo de instalação.

*Criar e editar tópicos*

Os colaboradores de tópicos são os campeões e especialistas em assuntos da sua organização. Eles podem criar e editar tópicos. 

Recomendamos que você permita que todos na sua organização criem e editem tópicos porque as experiências de tópico funcionam melhor quando todos os usuários podem compartilhar informações.

Se você quiser limitar a criação e edição de tópicos para pessoas ou grupos específicos, crie um grupo de segurança para eles e especifique-os durante o processo de instalação.

Você pode optar por não permitir que ninguém contribua com tópicos, no entanto, isso não é recomendado. Os gerentes de conhecimento ainda poderão editar e criar tópicos se você escolher essa opção.

*Visualizadores de tópicos*

Os visualizadores de tópicos podem ver informações sobre páginas de tópicos, nos resultados da pesquisa e quando os tópicos são realçados no conteúdo como SharePoint páginas. Os usuários só podem ver tópicos descobertos quando têm acesso aos arquivos e páginas em que o tópico foi descoberto.

Ao configurar os visualizadores de tópicos, você pode escolher entre:

- **Todos na minha organização**
- **Somente pessoas selecionadas ou grupos de segurança**
- **Ninguém**

Recomendamos **Todos na minha organização**, mas se você estiver fazendo um piloto, talvez queira escolher apenas pessoas selecionadas ou grupos de segurança. Você também pode escolher **Ninguém** se quiser configurar Tópicos, mas ainda não permitir que as pessoas vejam tópicos. (Os gerentes de conhecimento ainda terão acesso para permitir que eles exibirem os tópicos e ajudar com a decisão de disponibilizar tópicos amplamente.)

## <a name="knowledge-rules"></a>Regras de conhecimento

Como administrador, você pode excluir determinados tópicos de experiências de tópicos. Isso é útil se você quiser impedir que dados confidenciais apareçam em tópicos. Embora os gerentes de conhecimento possam excluir tópicos no centro de tópicos, os tópicos excluídos pelo administrador não são visíveis para gerentes de conhecimento. (Os gerentes de conhecimento também podem remover tópicos no centro de tópicos após a descoberta.)

Se você quiser excluir tópicos no nível de administrador, você deve adicioná-los a um arquivo .csv e carregar o arquivo. Você pode fazer isso durante a instalação ou posterior.

O .csv deve conter os seguintes parâmetros:

- **Nome**: digite o nome do tópico que você deseja excluir. Há duas maneiras de fazer isso:
- **MatchType-Exact/Partial**: Digite se o nome inserido foi *um tipo de* combinação exato *ou* parcial.
    - Match exato: Você pode incluir o nome exato ou acrônimo (por exemplo, *Contoso* ou *ATL*).
    - Match parcial: você pode excluir todos os tópicos que tenham uma palavra específica nele.  Por exemplo, *o arco* excluirá  todos os tópicos com o arco de palavra nele, como círculo de *arco,* *soldagem* de arco de plasma ou arco *treinamento*. Observe que ele não excluirá tópicos nos quais o texto é incluído como parte de uma palavra, como *Arquitetura*.
- **Significa (opcional)**: (Também conhecido como expansão *)* Se você quiser excluir um acrônimo, digite as palavras que o acrônimo representa.

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

Você pode copiar o modelo csv abaixo:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Administração

Quando você configura Tópicos, como parte do processo de instalação, um centro de tópicos é criado automaticamente. Pense no nome do centro de tópicos e no que deseja que a URL seja. Você pode definir o nome e a URL como parte do processo de instalação e alterar o nome (mas não a URL) posteriormente no centro de administração Microsoft 365. Você só pode ter um centro de tópicos.

## <a name="setup-checklist"></a>Lista de verificação de instalação

Ao configurar experiências de tópico, você precisará dos seguintes itens ao passar pelo assistente de instalação:

> [!div class="checklist"]
> * Lista de sites a incluir ou excluir, se não incluir todos os sites para descoberta de tópicos
> * Grupo de segurança para visualizadores de tópicos, se não permitir que todos os usuários visualizem tópicos
> * Grupo de segurança para colaboradores de tópicos, se não permitir que todos os usuários criem e editem tópicos
> * Grupo de segurança para gerentes de conhecimento de tópicos, se não permitir que todos os usuários gerenciem tópicos
> * Lista de tópicos confidenciais a excluir da descoberta de tópicos
> * Um nome para seu site central de tópicos

## <a name="see-also"></a>Confira também

[Configurar Experiências de tópico](set-up-topic-experiences.md)

[Gerenciar a descoberta de tópicos no Microsoft 365](topic-experiences-discovery.md)

[Gerenciar visibilidade de tópicos no Microsoft 365](topic-experiences-knowledge-rules.md)

[Gerenciar permissões de tópico em Microsoft 365](topic-experiences-user-permissions.md)

[Alterar o nome do centro de tópicos no Microsoft 365](topic-experiences-administration.md)
