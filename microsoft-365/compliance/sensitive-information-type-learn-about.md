---
title: Aprenda sobre os tipos de informações confidenciais
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 7e99198e0713a1940f094c3875293b2590f31e3f
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256850"
---
# <a name="learn-about-sensitive-information-types"></a>Aprenda sobre os tipos de informações confidenciais

Identificar e classificar itens confidenciais que estão sob o controle de suas organizações é a primeira etapa da disciplina [proteção de informações.](./information-protection.md)  Microsoft 365 fornece três maneiras de identificar itens para que possam ser classificados:

- manualmente pelos usuários
- reconhecimento de padrão automatizado, como tipos de informações confidenciais
- [machine learning](classifier-learn-about.md)

Os tipos de informações confidenciais são classificadores baseados em padrão. Eles detectam informações confidenciais, como previdência social, cartão de crédito ou números de conta bancária para identificar itens confidenciais, consulte [Definições de entidades](sensitive-information-type-entity-definitions.md) de tipos de informações confidenciais

## <a name="sensitive-information-types-are-used-in"></a>Tipos de informações confidenciais são usados em

- [Políticas de prevenção contra perda de dados](dlp-learn-about-dlp.md) 
- [Rótulos de confidencialidade](sensitivity-labels.md)
- [Rótulos de retenção](retention.md)
- [Gerenciamento de riscos insider](insider-risk-management.md)
- [Conformidade em comunicações](communication-compliance.md)
- [Políticas de rotulagem automática](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Partes fundamentais de um tipo de informação confidenciais

Todas as entidades de tipo de informação confidenciais são definidas por esses campos:

- name: como o tipo de informação sensível é chamado
- description: descreve o que o tipo de informação confidenciais está procurando
- padrão: um padrão define o que um tipo de informação sensível detecta. Ele consiste nos seguintes componentes
    - Elemento principal – o elemento principal que o tipo de informação sensível está procurando. Pode ser uma expressão **regular com** ou sem uma validação de verificação, uma lista de palavras-chave **,** um dicionário de palavras-chave **ou** uma **função**.
    - Elemento de suporte – elementos que atuam como evidências de suporte que ajudam a aumentar a confiança da partida. Por exemplo, palavra-chave "SSN" na proximidade de um número SSN. Pode ser uma expressão regular com ou sem uma validação de verificação, lista de palavras-chave, dicionário de palavras-chave.
    - Nível de confiança - níveis de confiança (alto, médio, baixo) refletem a quanta evidência de suporte foi detectada juntamente com o elemento principal. Quanto mais evidências de suporte um item contiver, maior será a confiança de que um item matched contém as informações confidenciais que você está procurando.
    - Proximidade – Número de caracteres entre o elemento principal e o elemento de suporte

![Diagrama da janela de proximidade e evidências comprobatórias](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Saiba mais sobre níveis de confiança neste vídeo


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>Exemplo de tipo de informação confidenciais


## <a name="argentina-national-identity-dni-number"></a>Número DNI (identidade nacional da Argentina)

### <a name="format"></a>Formatar

Oito dígitos separados por pontos

### <a name="pattern"></a>Padrão

Oito dígitos:
- dois dígitos
- um ponto
- três dígitos
- um ponto
- três dígitos

### <a name="checksum"></a>Soma de verificação

Não

### <a name="definition"></a>Definição

Uma política de DLP tem confiança média de que detectou esse tipo de informação confidenciais se, dentro de uma proximidade de 300 caracteres:
- A expressão regular Regex_argentina_national_id encontra conteúdo que corresponde ao padrão.
- Uma palavra-chave Keyword_argentina_national_id é encontrada.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Número de Identidade Nacional da Argentina 
- Identidade 
- Identificação do Cartão de Identidade Nacional 
- DNI 
- Registro Nacional de Pessoas da NIC 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>Mais sobre níveis de confiança

Em uma definição de entidade de tipo de informação **confidenciais,** o nível de confiança reflete a quanta evidência de suporte é detectada além do elemento principal. Quanto mais evidências de suporte um item contiver, maior será a confiança de que um item matched contém as informações confidenciais que você está procurando. Por exemplo, as combinações com um alto nível de confiança conterão mais evidências de suporte na proximidade do elemento principal, enquanto as combinações com um nível de confiança baixo conteriam pouca ou nenhuma evidência de suporte próxima. 

Um nível de confiança alto retorna o menor número de falsos positivos, mas pode resultar em mais falsos negativos. Níveis de confiança baixos ou médios retornam mais falsos positivos, mas poucos a zero falsos negativos.

- **baixa confiança**: o valor de 65 itens matched conterá o menor número de falsos negativos, mas os mais falsos positivos. Baixa confiança retorna todas as partidas de baixa, média e alta confiança.
- **confiança média**: Valor de 75, itens matched conterão uma quantidade média de falsos positivos e falsos negativos. A confiança média retorna todas as combinações médias e de alta confiança.  
- **alta confiança**: o valor de 85 itens matched conterá o menor número de falsos positivos, mas os mais falsos negativos. A alta confiança só retorna as partidas de alta confiança.  

Você deve usar padrões de alto nível de confiança com contagens baixas, digamos cinco a dez e padrões de baixa confiança com contagens mais altas, digamos 20 ou mais.

> [!NOTE]
> Se você tiver políticas existentes ou SITs (tipos de informações confidenciais personalizados) definidos usando níveis de confiança baseados em número (também sabem como precisão), eles serão automaticamente mapeados para os três níveis de confiança discretos; baixa confiança, confiança média e alta confiança na interface do usuário do Centro de Conformidade e Segurança.
> - Todas as políticas com precisão mínima ou padrões SIT personalizados com níveis de confiança entre 76 e 100 serão mapeadas para alta confiança. 
> - Todas as políticas com precisão mínima ou padrões SIT personalizados com níveis de confiança entre 66 e 75 serão mapeadas para confiança média.
> - Todas as políticas com precisão mínima ou padrões SIT personalizados com níveis de confiança menores ou iguais a 65 serão mapeadas para baixa confiança. 

## <a name="creating-custom-sensitive-information-types"></a>Criando tipos de informações confidenciais personalizadas

Para criar tipos de informações confidenciais personalizadas no Centro de Conformidade e Segurança, você pode escolher entre várias opções:

- **Usar a interface do usuário** Você pode configurar um tipo de informações confidenciais personalizadas usando o a interface do usuário do Centro de Conformidade e Segurança. Com esse método, você pode usar expressões comuns, palavras-chave e dicionários de palavras-chave. Para saber mais, confira [Criar um tipo de informações confidenciais personalizadas](create-a-custom-sensitive-information-type.md).

- **Use EDM** Você pode configurar tipos de informações confidenciais personalizadas usando a classificação baseada em EDM (Exact Data Match). Esse método permite criar um tipo de informações confidenciais dinâmico usando um banco de dados seguro que você pode atualizar periodicamente. Confira [Criar um tipo de informações confidenciais personalizadas com classificação baseada em Exact Data Match](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Use o PowerShell** Você pode configurar tipos de informações confidenciais personalizadas usando o PowerShell. Embora esse método seja mais complexo do que usar a interface do usuário, você tem mais opções de configuração. Consulte [Criar um tipo de informações confidenciais personalizadas no Centro de Conformidade e Segurança do PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).



> [!NOTE]
> Níveis de confiança aprimorados estão disponíveis para uso imediato na Prevenção contra Perda de Dados para serviços Microsoft 365, Proteção de Informações da Microsoft para serviços Microsoft 365, Conformidade de Comunicação, Governança de Informações e Gerenciamento de Registros.
> Microsoft 365 A Proteção de Informações agora dá suporte a idiomas de conjunto de caracteres de byte duplo para:
> - Chinês (simplificado)
> - Chinês (tradicional)
> - Coreano
> - Japonês
> 
> Este suporte está disponível para tipos de informações confidenciais. Para obter mais informações, confira [Suporte à proteção de informações para notas de versão de conjuntos de caracteres de byte duplo (visualização)](mip-dbcs-relnotes.md).

> [!TIP]
> Para detectar padrões que contêm caracteres chineses/japoneses e caracteres de byte único ou para detectar padrões que contenham chinês/japonês e inglês, defina duas variantes da palavra-chave ou regex. Por exemplo, para detectar uma palavra-chave como "机密的document", use duas variantes da palavra-chave; um com um espaço entre o texto japonês e inglês e outro sem um espaço entre o texto japonês e o inglês. Portanto, as palavras-chave a serem adicionadas ao SIT devem ser "机密的 documento" e "机密的document". Da mesma forma, para detectar uma frase "東京オリ ピック2020", duas variantes devem ser usadas; "東京オリ ピック 2020" e "東京オリ ピック2020".
> 
> Ao criar um regex usando um hífen de byte duplo ou um período de byte duplo, certifique-se de escapar de ambos os caracteres como um escaparia de um hífen ou ponto em um regex. Aqui está um exemplo de regex para referência:
>    - (?<!\d) ([4][0-9] {3} [ \- ?\-\t]*[0-9]{4}
>
> Recomendamos usar a combinação de cadeia de caracteres em vez de corresponder a palavras em uma lista de palavras-chave.

## <a name="for-further-information"></a>Para obter mais informações
- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
- [Criar um tipo de informação confidencial personalizado](create-a-custom-sensitive-information-type.md)
- [Criar um tipo personalizado de informações confidenciais no PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

Para saber como usar tipos de informações confidenciais para estar em conformidade com os regulamentos de privacidade de dados, consulte [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
