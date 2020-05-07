---
title: Desenvolver um esquema de classificação para dados pessoais
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Determine se a sua organização implementará os rótulos como parte do seu plano da Regulamentação Geral de Proteção de Dados (RGPD).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17484e56206ba8f32db3c779623f2f8d7ed57496
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035163"
---
# <a name="architect-a-classification-schema-for-personal-data"></a>Desenvolver um esquema de classificação para dados pessoais

Outros artigos desta série se concentram no uso de tipos de informações confidenciais para identificar dados pessoais sujeitos ao RGPD. Os tipos de informações confidenciais são uma forma de classificação, que pode ser tudo de que você precisa. No entanto, muitas organizações implementam uma estratégia de governança de dados mais ampla usando rótulos. Use esse tópico para decidir se também desejará implementar os rótulos como parte do seu plano de RGPD. Em caso afirmativo, este tópico dará algumas diretrizes e exemplos.

Observação: definir um esquema de classificação para uma organização e configurar políticas, rótulos e condições requer planejamento e preparação cuidadosos. É importante reforçar que este não é um processo de TI. Trabalhe com sua equipe jurídica e de conformidade para desenvolver uma classificação apropriada e um esquema de rotulação para os dados da sua organização.

## <a name="decide-if-youre-using-labels-in-addition-to-sensitive-data-types"></a>Decidir se vai usar rótulos além dos tipos de dados confidenciais

É possível abordar a classificação de informações pessoais no Microsoft 365 de duas abordagens. Qualquer uma pode ser usada para a proteção de RGPD. Se decidir usar somente tipos de informações confidenciais para classificação, ignore o restante deste tópico.

Selecione uma das opções a seguir.

### <a name="option-1-use-only-microsoft-365-sensitive-information-types"></a>Opção 1: usar somente os tipos de informações confidenciais do Microsoft 365

- Os tipos de informações confidenciais funcionam bem para identificar e proteger os dados pessoais sujeitos ao RGPD e outros tipos de regulamentações.

- Eles são mais simples de usar caso sua organização já não tenha ou planeje implementar um plano de governança de dados mais amplo com uso de rótulos.

- Eles trabalham com regras de DLP (assim como os rótulos do Office).

- Tipos de informações confidenciais funcionam com Segurança de aplicativos de nuvem, assim será possível detectar informações confidenciais em outros aplicativos SaaS.

### <a name="option-2-use-sensitive-information-types--retention-labels"></a>Opção 2: usar os tipos de informações confidenciais + rótulos de retenção

- Será necessário que os tipos de informações confidenciais apliquem rótulos automaticamente aos dados pessoais sujeitos ao RGPD, o que faz deles um pré-requisito.

- Usar a retenção de rótulos permite incluir dados pessoais que são sujeitos ao RGPD em um plano mais amplo de governança de dados para a sua organização.

## <a name="develop-a-label-schema-that-includes-personal-data"></a>Desenvolver um esquema de rotulação que inclui dados pessoais

Antes de usar os recursos técnicos para aplicar rótulos e proteção, primeiro defina na sua organização um esquema de classificação. Ela pode já ter um, o que facilita adicionar dados pessoais. Este tópico inclui um exemplo de esquema de classificação. Você pode usá-lo como ponto de partida, se necessário.

### <a name="getting-started"></a>Introdução

Comece por escolher a quantidade e os nomes dos rótulos a implementar. Faça isso sem se preocupar com a tecnologia a se usar nem com como os rótulos serão aplicados. Aplique esse esquema em toda a organização, incluindo os dados guardados no local e em outros serviços de nuvem.

### <a name="recommendations"></a>Recomendações 

Ao criar e implementar políticas, rótulos e condições, considere essas recomendações:

- Use esquemas de classificação existentes (se houver)&ndash; muitas organizações já estão usando a classificação de dados de alguma forma. Avalie com cuidado o esquema de rotulação existente e, se possível, use-o como está. Usar rótulos familiares reconhecíveis pelo usuário final ajuda na adesão.

- Comece com políticas e rótulos padrão&ndash; todas as soluções vêm com um conjunto de políticas e rótulos predefinidos. Avalie-os com cuidado, de acordo com os requisitos corporativos e jurídicos da organização e considere usar esses em vez de criar outros.

- Comece aos poucos&ndash; não há limites para a quantidade de rótulos que podem ser criados. Contudo, uma quantidade imensa de rótulos e sub-rótulos pode impactar negativamente a adesão. Oferecer muitas opções é quase como não oferecer nenhuma.

- Utilize cenários e casos de uso&ndash; identifique os casos de uso comuns na organização e use os cenários derivados do RGPD para verificar se a configuração pensada para a rotulação e classificação funcionarão na prática.

- Questione cada solicitação por um novo rótulo&ndash; será que cada cenário ou caso de uso precisa mesmo de um novo rótulo ou pode-se usar o que já existe? Manter a quantidade de rótulos no mínimo facilita a adesão.

- Use sub-rótulos para os departamentos principais&ndash; alguns departamentos terão necessidades específicas que exigirão rótulos específicos. Defina esses rótulos como sub-rótulos de um rótulo existente e considere usar políticas com escopo que sejam atribuídas a grupos de usuários em vez de a toda a organização.

- Considere usar políticas com escopo&ndash; políticas direcionadas a subconjuntos de usuários impedirão uma "sobrecarga de rótulos". Uma política com escopo permite atribuir (sub-)rótulos por função ou departamento específico apenas a funcionários que trabalhem para o departamento específico.

- Use nomes significativos para os rótulos&ndash; recomenda-se não usar jargões, padrões ou acrônimos como nomes de rótulos. Tente usar nomes que façam sentido para o usuário final e melhore a adoção. Em vez de usar rótulos como PII, PCI, HIPAA, LBI, MBI e HBI, considere nomes como Não Corporativo, Público, Geral, Confidencial e Altamente Confidencial.

### <a name="example-classification-schema"></a>Exemplo de esquema de classificação

<table>
<thead>
<tr class="header">
<th align="left"><strong>Nome do rótulo</strong></th>
<th align="left"><strong>Descrição</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Pessoal</td>
<td align="left">Dados não corporativos, apenas para uso pessoal.</td>
</tr>
<tr class="even">
<td align="left">Público</td>
<td align="left">Dados corporativos especificamente preparados e aprovados para o público.</td>
</tr>
<tr class="odd">
<td align="left">Dados do cliente</td>
<td align="left">Dados corporativos que contêm informações de identificação pessoal. Exemplos são números de cartão de crédito, de contas bancárias e de cadastros de pessoas físicas.</td>
</tr>
<tr class="even">
<td align="left">Dados de RH</td>
<td align="left">Dados de recursos humanos sobre funcionários da Contoso, como matrícula e salário.</td>
</tr>
<tr class="odd">
<td align="left">Confidencial</td>
<td align="left">Dados corporativos confidenciais que poderiam causar danos à empresa se compartilhados com pessoas não autorizadas. Exemplos incluem contratos, relatórios de segurança, resumos de previsões de mercado e dados de contas de vendas.</td>
</tr>
<tr class="even">
<td align="left">Altamente Confidencial</td>
<td align="left">Dados corporativos altamente confidenciais que poderiam causar danos à empresa se compartilhados com pessoas não autorizadas. Exemplos incluem informações de funcionários e clientes, senhas, códigos-fonte e relatórios financeiros prévios.</td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a>Definir um critério taxonômico e de pesquisa para todos os rótulos

Após desenvolver um esquema de classificação para a sua organização, a próxima etapa é desenvolver critérios taxonômicos e de pesquisa para localizar os dados. Para dados pessoais, você já concluiu esse trabalho identificando os tipos de informações confidenciais e também personalizando ou criando novos tipos de informações confidenciais para o ambiente.

A tabela a seguir oferece um exemplo de esquema de critério taxonômico e de pesquisa para uma organização. Os rótulos são ordenados por nível de confidencialidade, do menos afetado ao mais importante, para garantir que os dados que atendam a várias condições de rotulação recebam o rótulo apropriado.

Observação: o exemplo de configuração tem fins meramente ilustrativos e não deve ser considerado referência ou orientação de implantação.

A lição mais importante é que o esforço que você fizer para classificar os dados pessoais para estar em conformidade com o RGPD esteja alinhado aos objetivos de toda a organização.

### <a name="example-schema-taxonomy-and-search-criteria"></a>Exemplo de esquema de critério taxonômico e de pesquisa

<table>
<thead>
<tr class="header">
<th align="left"><strong>Rótulo</strong></th>
<th align="left"><strong>Taxonomia</strong></th>
<th align="left"><strong>Método</strong></th>
<th align="left"><strong>Sintaxe de pesquisa</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Pessoal</td>
<td align="left">Documentos rotulados manualmente como pessoais pelo usuário final.</td>
<td align="left">Manual</td>
<td align="left">Documentos rotulados manualmente como pessoais pelo usuário final.</td>
</tr>
<tr class="even">
<td align="left">Público</td>
<td align="left">Documentos que contenham a frase aprovado, independente da capitalização, para o lançamento público ##/### em que # representa qualquer dígito.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL – Aprovado para lançamento público*</p>
<p>RegEx — (?i)(\bAprovado para Publicação \d{2}\/\d{4}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Dados do cliente</td>
<td align="left">Tipos de informações confidenciais para dados de cidadãos da UE.</td>
<td align="left">Tipos de informações confidenciais</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Recursos humanos – dados de funcionários</td>
<td align="left">Documentos que incluam a identificação do funcionário, que diferenciam maiúsculas de minúsculas, no formato CONTOSO-9##### em que # representa qualquer dígito.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL – CONTOSO-9*</p>
<p>RegEx — (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Recursos humanos – dados salariais</td>
<td align="left">Documentos que incluam a palavra-chave Contoso (com diferenciação de maiúsculas e minúsculas) E tanto a palavra-chave Salário (sem diferenciação de maiúsculas e minúsculas) OU Remuneração</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL – Contoso E (Salário OU Remuneração)</p>
<p>RegEx — (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="even">
<td align="left">Confidencial</td>
<td align="left">Documentos que contenham a frase (com diferenciação de maiúsculas e minúsculas) Contoso Confidencial.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL – Contoso Confidencial</p>
<p>RegEx — (?i)(\bContoso Confidencial\b)</p></td>
</tr>
<tr class="odd">
<td align="left">Altamente Confidencial</td>
<td align="left">Documentos que incluam a frase Contoso Secreto (com diferenciação de maiúsculas e minúsculas) ou Secreto-C#### em que # representa qualquer dígito.</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL – Contoso Secreto OU o Secreto-C*</p>
<p>RegEx — (?i)(\bContoso Secreto\b)|(\bSecreto-C\d\{4}\b)</p></td>
</tr>
</tbody>
</table>
