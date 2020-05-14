---
title: Pesquisar e localizar dados pessoais
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 2/7/2018
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Aprenda a pesquisar e encontrar dados pessoais sujeitos a Regulamentações Gerais de Proteção de Dados (RGPD) no Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0d29697a28221b5ff998f5ce923c143bf7a0804
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214575"
---
# <a name="search-for-and-find-personal-data"></a>Pesquisar e localizar dados pessoais

A grosso modo, o RGPD define dados pessoais como qualquer dado relativo a uma pessoa física identificada ou identificável que seja residente da União Europeia (UE).

Artigo 4 – Definições

> "dados pessoais" são todas as informações relativas a uma pessoa física identificada ou identificável ("titular dos dados"); uma pessoa física identificável é alguém que pode ser identificado, direta ou indiretamente, em especial por referência a um identificador como um nome, um número de identificação, dados de localização, um identificador online ou por um ou mais elementos específicos da identidade física, fisiológica, genética, mental, econômica, cultural ou social dessa pessoa física;

Este artigo demonstra como localizar dados pessoais armazenados no SharePoint Online e no OneDrive for Business (que inclui os sites de todos os grupos do Microsoft 365 e Microsoft Teams).

A localização de dados pessoais sujeitos ao GDPR se baseia no uso de tipos de informações confidenciais no Office 365. Eles definem como o processo automatizado reconhece os tipos de informações específicas, como números de serviços de saúde e cartão de crédito. Você pode usar as políticas de prevenção contra perda de dados para localizar dados pessoais no email enquanto está em trânsito. Você pode usar os tipos de informações confidenciais que deseja para o RGPD localizar e proteger as informações pessoais conforme elas são enviadas por email. Confira também, [Solicitações de entidades de dados GDPR gerenciados com a ferramenta de caso DSR no Centro de Conformidade & Segurança](https://docs.microsoft.com/microsoft-365/compliance/manage-gdpr-data-subject-requests-with-the-dsr-case-tool).

## <a name="use-content-search-to-find-personal-data"></a>Usar a Pesquisa de Conteúdo para localizar dados pessoais

A Microsoft recomenda uma abordagem em três etapas para localizar dados pessoais no Office 365. O restante deste tópico orienta sobre cada uma dessas etapas.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Etapa</strong></th>
<th align="left"><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>1. Pesquisar tipos de informações confidenciais</p></td>
<td align="left"><p>Inicie usando os tipos de informações confidenciais para localizar dados pessoais. Crie uma consulta de Pesquisa de Conteúdo para cada tipo de informação confidencial. Execute a consulta e analise os resultados.</p>
Se necessário, adicione parâmetros às consultas para reduzir os falsos positivos: <li>Intervalo de contagem</li>
    <li>Intervalo de confiança</li>
    <li>Outras propriedades ou operadores para consultas mais complexas</li>
<p>Se necessário, modifique um tipo de informação confidencial para aprimorar o refinamento para a sua organização:</p>
<p><li>Ajuste o nível de confiança diretamente no XML.</li></p>
<p><li>Adicione palavras-chave.</li></p>
<p><li>Ajuste os requisitos de proximidade das palavras-chave.</li></p></td>
</tr>
<tr class="even">
<td align="left"><p>2. Usar a Keyword Query Language (KQL) para localizar dados pessoais adicionais em seu ambiente</p></td>
<td align="left"><p>Para localizar dados não incluídos nos tipos de informações confidenciais, use a linguagem de consulta KQL para desenvolver consultas personalizadas.</p>
<p>Teste os resultados da pesquisa e ajuste a cadeia de caracteres de consulta da KQL até atingir o resultado esperado.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>3. Criar novos tipos de informações confidenciais personalizados usando consultas KQL</p></td>
<td align="left">Após otimizar as consultas KQL para localizar os dados de destino, crie novos tipos de informações confidenciais personalizados usando essas consultas. Em seguida, você pode usar esses tipos de informações confidenciais personalizados com a Pesquisa de Conteúdo, com as políticas DLP e outras ferramentas e em outras consultas KQL.</td>
</tr>
</tbody>
</table>


## <a name="search-for-sensitive-information-types-using-content-search"></a>Buscar tipos de informações confidenciais usando a Pesquisa de Conteúdo

Começar a pesquisar dados pessoais usando os tipos de informações confidenciais incluídas no Office 365. Eles estão listados em Classificação no centro de segurança e no centro de conformidade.

Este tópico inclui uma lista de alguns tipos de informações confidenciais que se aplicam a cidadãos na União Europeia. Verifique o centro de segurança ou centro de conformidade para novas adições que podem ajudar com a conformidade GDPR.

Confira também este artigo: [Lista de tipos de informações confidenciais e para que serve cada um](https://docs.microsoft.com/microsoft-365/compliance/content-search).

Os tipos de informações confidenciais definem como o processo automatizado reconhecerá tipos específicos de informação, como números de contas bancárias, números de serviços de saúde e de cartões de crédito. Os tipos de informações confidenciais também são conhecidos como condições. Um tipo de informação confidencial se define por um padrão que pode ser identificado por uma expressão regular ou uma função. Além disso, podem-se usar evidências de comprovação como palavras-chave e somas de verificação para identificar um tipo de informação confidencial. Também se usa o nível de confiança e de proximidade no processo de avaliação.

No momento, os tipos de informações confidenciais não podem ser usados para localizar dados em repouso nas caixas de correio.

### <a name="using-content-search-with-sensitive-information-types"></a>Usar a Pesquisa de Conteúdo com os tipos de informações confidenciais

<table>
<thead>
<tr class="header">
<th align="left"><strong>Etapa</strong></th>
<th align="left"><strong>Mais informações</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd"><td align="left"><p>Acessar a Pesquisa de Conteúdo no Centro de Conformidade e Segurança</p></td>
<td align="left"><p>No painel esquerdo do Centro de Conformidade e Segurança, clique em **Pesquisa&amp; investigação** &gt; **Pesquisa de Conteúdo**.</p>
<p>Confira <a href="https://support.office.com/article/Run-a-Content-Search-in-the-Office-365-Security-Compliance-Center-61852fd9-fe8a-4880-a339-cb19ed3bff4a">Executar uma Pesquisa de Conteúdo no Centro de Conformidade e &amp; Segurança</a>.</p></td>
</tr>
<tr class="even">
<td align="left"><p>Criar um novo item de pesquisa para cada tipo de informação confidencial</p></td>
<td align="left"><p>Use a seguinte sintaxe:</p>
<blockquote>
<p>SensitiveType:"&lt;tipo&gt;"</p>
</blockquote>
<p>Por exemplo:</p>
<blockquote>
<p>SensitiveType:&quot;Número de passaporte francês&quot;</p>
</blockquote>
<p>Amplie a pesquisa para o SharePoint (inclui o OneDrive for Business). A sintaxe deve ser exata e não deve haver erros de digitação ou espaços extras.</p>
<p>Confira <a href="https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites">Criar uma consulta para localizar dados confidenciais armazenados em sites</a>.</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Examinar os resultados de cada pesquisa</p></td>
<td align="left"><p>Identifique esses tipos de problemas para determinar se a precisão da consulta está adequada:</p>
<p><li>Muitos falsos positivos</li></p>
<p><li>Falta de instâncias de dados conhecidos</li></p>
<p>Confira <a href="https://docs.microsoft.com/microsoft-365/compliance/export-search-results">Exportar os resultados da Pesquisa de Conteúdo do &amp;Centro de Conformidade e Segurança</a>.</p>
<p>Observação: se estiver usando o Mozilla Firefox ou o Chrome, pode ser preciso baixar antes os relatórios usando o Internet Explorer ou o Microsoft Edge para instalar o suplemento necessário.</p></td>
</tr>
</tbody>
</table>

## <a name="sensitive-information-types-for-eu-citizen-data"></a>Tipos de informações confidenciais para os dados de cidadãos da União Europeia

Comece com esses tipos de informações confidenciais, muitos outros chegarão em breve para os dados pessoais na União Europeia.

> Número nacional belga
>
> Número de Cartão de Crédito
>
> Número da carteira de identidade croata
>
> Número de identificação pessoal (NIB) croata
>
> Número da carteira nacional de identidade tcheca
>
> Número de identificação pessoal dinamarquês
>
> Número de cartão de débito da UE
>
> RG nacional finlandês
>
> Número de passaporte finlandês
>
> Número da carteira de motorista francesa
>
> Carteira nacional de identidade francesa (CNI)
>
> Número de passaporte francês
>
> Número da segurança social francesa (INSEE)
>
> Número de carteira de motorista da Alemanha
>
> Número da carteira de identidade alemã
>
> Número de passaporte alemão
>
> Carteira nacional de identidade grega
>
> Número internacional de conta bancária (IBAN)
>
> Endereço IP
>
> Número de serviço público pessoal (PPS) irlandês
>
> Número de carteira de motorista italiana
>
> Número do Serviço do Cidadão (BSN) da Países Baixos
>
> Número de identidade norueguesa
>
> Carteira de identidade polonesa
>
> RG nacional polonês (PESEL)
>
> Passaporte polonês
>
> Número do cartão do cidadão português
>
> Número da segurança social espanhola (SSN)
>
> RG nacional sueco
>
> Número de passaporte sueco
>
> Número de carteira de motorista do Reino Unido
>
> Número do título de eleitor britânico
>
> Número do serviço nacional de saúde britânico
>
> Número do seguro nacional britânico (NINO)
>
> Número de passaporte americano/britânico

## <a name="add-parameters-to-a-sensitive-information-type-query-to-hone-the-results"></a>Adicionar parâmetros a uma consulta de tipo de informação confidencial para refinar os resultados

É possível adicionar esses parâmetros a uma consulta de tipo de informação confidencial:

-   Intervalo de contagem: define o número de ocorrências de informações confidenciais que um documento precisa conter para ser incluído nos resultados da consulta.

-   Intervalo de confiança: o nível de confiança a que o tipo confidencial detectado realmente corresponde, como 85% (85%).

Sintaxe:

-   SensitiveType:"\<tipo\>|\<intervalo de contagem\>|\<intervalo de confiança\>"

Exemplos:

-   SensitiveType:"Número de cartão de crédito|5" (retornará apenas os documentos que contenham exatamente cinco números de cartão de crédito)

-   SensitiveType:"Número de cartão de crédito|\*|85.." (o intervalo de confiança é 85% ou mais)

Observação: "SensitiveType" diferencia maiúsculas e minúsculas, mas o restante da consulta não.

Também é possível usar operadores e propriedades para ilustrar como você pode refinar suas consultas. Para obter mais informações e exemplos, confira [Criar uma consulta para localizar dados confidenciais armazenados em sites](https://docs.microsoft.com/microsoft-365/compliance/form-a-query-to-find-sensitive-data-stored-on-sites).
