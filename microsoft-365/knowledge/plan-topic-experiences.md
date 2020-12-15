---
title: Planejar experiências de tópico no Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba como planejar experiências de tópico no Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668084"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a>Planejar experiências de tópico no Microsoft 365

Você está no controle de como os tópicos são experientes em sua organização. Suas decisões de planejamento para experiências de tópicos garantem que tópicos de alta qualidade sejam mostrados para seus usuários e que tenham as permissões corretas para consumir e contribuir com conhecimento.

Neste artigo, examinaremos estas decisões de planejamento:

- Quais sites do SharePoint você deseja rastrear para tópicos.
- Quais tópicos, se houver, você deseja excluir das experiências de tópico
- Para quais usuários você deseja tornar os tópicos visíveis.
- Quais usuários você deseja dar permissões para gerenciar tópicos no centro de tópicos.
- Quais usuários você deseja dar permissões para criar ou editar tópicos no centro de tópicos.
- Que nome você deseja dar à sua central de tópicos.

A segurança e a privacidade de seus dados são respeitadas, e a experiência do tópico não concede aos usuários acesso adicional aos arquivos aos quais eles não têm direitos. Recomendamos que você também leia o [tópico segurança e privacidade das experiências](topic-experiences-security-privacy.md) como parte do seu processo de planejamento.

## <a name="requirements"></a>Requirements

Você deve ser um administrador global ou administrador do SharePoint para acessar o centro de administração do Microsoft 365 e configurar experiências de tópico.

Todos os usuários que vão usar experiências de tópico exigem uma licença de **experiência do tópico** . A atribuição de licenças é abordada em [experiências de tópicos de configuração](set-up-topic-experiences.md).

## <a name="topic-discovery"></a>Descoberta de tópicos

As configurações de descoberta de tópico especificam quais sites do SharePoint são usados como fontes para tópicos. Você pode optar por incluir todos os sites do SharePoint, uma lista específica de sites ou nenhum site. Recomendamos que você escolha todos os sites para que a experiência do tópico possa descobrir um grande número de tópicos bons para seus usuários.

Ao configurar experiências de tópico, você pode escolher entre as seguintes opções:

- **Todos os sites**: todos os sites do SharePoint em sua organização. Isso inclui sites atuais e futuros.
- **Todos, exceto sites selecionados**: todos os sites, exceto aqueles que você especificar. Os sites criados no futuro serão incluídos como fontes para descoberta de tópicos. 
- **Somente sites selecionados**: somente os sites que você especificar. Os sites criados no futuro não serão incluídos como fontes para descoberta de tópicos.
- **Nenhum site**: não inclua nenhum site do SharePoint.

Se você escolher **todos, exceto os sites selecionados** ou **apenas sites selecionados**, poderá carregar um arquivo. csv com uma lista de sites. Essas opções são úteis se você estiver fazendo um piloto e quiser incluir um número limitado de sites para iniciar.

Você pode copiar o modelo. csv abaixo:

``` csv
Site name,URL
```

Não é recomendável escolher **nenhum site** porque impede que os tópicos sejam criados ou atualizados automaticamente. No entanto, você pode escolher esta opção se quiser configurar experiências de tópico e, em seguida, adicionar sites mais tarde.

Recomendamos que você crie um processo para usuários ou gerentes de conhecimento para solicitar que sites individuais sejam removidos da descoberta de tópicos, se necessário em sua organização.

## <a name="user-permissions"></a>Permissões do usuário

As permissões de usuário que você especifica determinam quais pessoas da sua organização interagem com os tópicos e o que eles podem fazer.

*Gerenciar tópicos*

Os gerentes de conhecimento supervisionam a qualidade das informações, a forma como as práticas recomendadas e as demais em sua organização. Eles podem confirmar e rejeitar tópicos.

Embora você possa especificar gerentes de tópico individuais, recomendamos que você crie um grupo de segurança (ou use um existente) que contenha as pessoas que você deseja que sejam gerentes de conhecimento. Você pode especificar esse grupo de segurança durante o processo de instalação.

*Criar e editar tópicos*

Os colaboradores do tópico são especialistas e especialistas no assunto da sua organização. Eles podem criar e editar tópicos. 

Recomendamos que você permita que todas as pessoas em sua organização criem e editem tópicos porque as experiências de tópico funcionam melhor quando todos os usuários podem compartilhar informações.

Se quiser limitar a criação e edição de tópicos a pessoas ou grupos específicos, crie um grupo de segurança para eles e especifique-o durante o processo de instalação.

Você pode optar por não permitir que qualquer pessoa possa contribuir para tópicos, no entanto, isso não é recomendado. Os gerentes de conhecimento ainda poderão editar e criar tópicos.

*Visualizadores de tópicos*

Os visualizadores de tópicos podem ver informações sobre páginas de tópicos, nos resultados da pesquisa e quando os tópicos estão realçados no conteúdo como páginas do SharePoint. Os usuários só podem ver os tópicos detectados quando têm acesso aos arquivos e às páginas nas quais o tópico foi descoberto.

Ao configurar os visualizadores de tópicos, você pode escolher:

- **Todos na minha organização**
- **Apenas pessoas ou grupos de segurança selecionados**
- **Ninguém**

Recomendamos **todos em minha organização**, mas se você estiver fazendo um piloto, convém escolher apenas pessoas ou grupos de segurança selecionados. Você também pode escolher **não um** se quiser configurar experiências de tópico, mas não permitir que as pessoas vejam tópicos ainda. (Os gerentes de conhecimento ainda terão acesso para permitir que eles exibam os tópicos e ajudem na decisão de disponibilizar experiências de tópicos amplamente disponíveis.)

## <a name="knowledge-rules"></a>Regras de conhecimento

Como administrador, você pode excluir determinados tópicos de experiências de tópico. Isso é útil se você deseja manter dados confidenciais de aparecerem nos tópicos. Embora os gerentes de conhecimento possam excluir tópicos no centro de tópicos, os tópicos excluídos pelo administrador não estão mesmo visíveis aos gerentes de conhecimento. (Os gerentes de conhecimento também podem remover tópicos no centro de tópicos após a descoberta.)

Se você deseja excluir tópicos no nível de administrador, você deve adicioná-los a um arquivo. csv e carregar o arquivo. Você pode fazer isso durante a instalação ou posterior.

O arquivo. csv deve conter os seguintes parâmetros:

- **Name**: digite o nome do tópico que você deseja excluir. Há duas maneiras de fazer isso:
- **MatchType-Exact/partial**: digite se o nome inserido foi um tipo de correspondência *exata* ou *parcial* .
    - Correspondência exata: você pode incluir o nome exato ou o acrônimo (por exemplo, *contoso* ou *ATL*).
    - Correspondência parcial: você pode excluir todos os tópicos que possuem uma palavra específica.  Por exemplo, o *arco* excluirá todos os tópicos com a palavra *arco* nele, como *círculo de arco*, solda de arco de *plasma* ou arco de *treinamento*. Observe que ele não excluirá tópicos nos quais o texto está incluído como parte de uma palavra, como *arquitetura*.
- **Significa (opcional)**: (também conhecido como *expansão*) se você quiser excluir um acrônimo, digite as palavras que o acrônimo significa.

    ![Excluir tópicos no modelo CSV](../media/exclude-topics-csv.png) 

Você pode copiar o modelo CSV abaixo:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Administração

Quando você configura experiências de tópico, como parte do processo de instalação, uma central de tópicos é criada automaticamente. Considere o que você deseja que seja o nome do centro do tópico e o que você deseja que a URL seja. É possível definir o nome e a URL como parte do processo de instalação, e você pode alterar o nome (mas não a URL) mais tarde no centro de administração do Microsoft 365. Você só pode ter uma central de tópicos.

## <a name="setup-checklist"></a>Lista de verificação de configuração

Ao configurar experiências de tópico, você precisará dos seguintes itens à medida que passar pelo assistente de configuração:

> [!div class="checklist"]
> * Lista de sites a incluir ou excluir se não incluir todos os sites para descoberta de tópico
> * Grupo de segurança para visualizadores de tópico se não permitir que todos os usuários exibam tópicos
> * Grupo de segurança para colaboradores de tópico se não permitir que todos os usuários criem e editem tópicos
> * Grupo de segurança para gerentes de conhecimento do tópico se não permitir que todos os usuários gerenciem tópicos
> * Lista de tópicos confidenciais a serem excluídos da descoberta de tópicos
> * Um nome para o seu site do centro de tópicos

## <a name="see-also"></a>Também consulte

[Configurar experiências de tópico](set-up-topic-experiences.md)

[Gerenciar descoberta de tópicos no Microsoft 365](topic-experiences-discovery.md)

[Gerenciar a visibilidade de tópicos no Microsoft 365](topic-experiences-knowledge-rules.md)

[Gerenciar permissões de tópico no Microsoft 365](topic-experiences-user-permissions.md)

[Alterar o nome da central de tópicos no Microsoft 365](topic-experiences-administration.md)
