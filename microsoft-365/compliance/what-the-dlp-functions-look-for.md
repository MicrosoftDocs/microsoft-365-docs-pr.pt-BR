---
title: O que as funções de prevenção de perda de dados (DLP) procuram
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Saiba o que as funções de prevenção de perda de dados (DLP) procuram.
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536306"
---
# <a name="what-the-dlp-functions-look-for"></a>O que as funções DLP procuram

A prevenção de perda de dados (DLP) inclui tipos de informações confidenciais, como número de cartão de crédito e número de cartão de débito da UE, que estão prontos para uso nas suas políticas de DLP. Esses tipos de informação confidencial procuram por um padrão específico e o confirmam, garantindo a formatação adequada, impondo as somas de verificação e procurando palavras-chave relevantes ou outras informações. Algumas dessas funcionalidades são realizadas por funções internas. Por exemplo, o tipo de informação confidencial de Número de Cartão de Crédito usa uma função para procurar datas formatadas como uma data de expiração, para ajudar a corroborar que um número é um número de cartão de crédito.
  
Este artigo explica o que essas funções procuram para ajudá-lo a entender como funcionam os tipos de informações confidenciais predefinidos. Para mais informações, consulte [definições de entidade de tipo de informação confidencial](sensitive-information-type-entity-definitions.md)
  
## <a name="func_us_date"></a>Func_us_date

Essa função procura uma data no formato comumente usado nos EUA. Isso inclui os formatos "mês/dia/ano", "mês-dia-ano" e "ano dia do mês". Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas. 
  
Exemplos:
  
- 2 de dezembro de 2016
    
- 2 de dezembro de 2016
    
- Dec 02 2016
    
- 12/2/2016
    
- 12/02/16
    
- Dec-2-2016
    
- 12-2-16
    
Nomes de meses aceitos:
  
- English
    
  - Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro
    
  - Jan. Fev. mar. abr. Maio de 1º de julho de agosto de setembro. Dec.
    
## <a name="func_eu_date"></a>Func_eu_date

Essa função procura uma data no formato comumente usado na UE (e a maioria dos lugares fora dos EUA), como "dia/mês/ano", "dia-mês-ano" e "ano do mês do dia". Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.
  
Exemplos:
  
- 2 Dec 2016
    
- 02 de dezembro de 2016
    
- 2 de dezembro de 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dez-2016
    
- 2-12-16
    
Nomes de meses aceitos:
  
- English
    
  - Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro
    
  - Jan. Fev. mar. abr. Maio de 1º de julho de agosto de setembro. Dec.
    
- Dutch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan fevereiro de maart de abril de Mei jun jul setembro de agosto de dezembro de Okt de Nov
    
- French
    
  - Janvier, Février, Mars, Avril, Mai, Juin Juillet, Août, Septembre, outubro, Novembre, décembre
    
  - janv. févr. Mars Avril Mai Juin Juil. Août set. Outubro. Nov. déc.
    
- German
    
  - jänuar, februar, März, abril, Mai, Juni Juli, agosto, setembro, Oktober, novembro de Dezember
    
  - Jan./Jän. Fev. März abr. Mai Juni Juli ago. set. Okt. Nov. dez.
    
- Italian
    
  - gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre
    
  - genn. febbr. mar. abr. magg. giugno Luglio AG. definida. ott. Nov. DIC.
    
- Português
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan fev mar abr mai jun jul atrás Set out nov dez
    
- Spanish
    
  - enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre
    
  - Enero Fev. Marzo abr. Mayo Jun. Jul. agosto set./set. Outubro. Nov. DIC.
    
## <a name="func_eu_date1-deprecated"></a>Func_eu_date1 (preterido)

> [!NOTE]
> Essa função foi preterida porque dá suporte apenas a nomes de meses em Português, que agora estão incluídos na `Func_eu_date` função acima. 
  
Essa função procura uma data no formato comumente usado em português. O formato dessa função é o mesmo que `Func_eu_date` , diferente somente no idioma usado.
  
Exemplos:
  
- 2 dez 2016
    
- 02 dez 2016
    
- 2 dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dez-2016
    
- 2-12-16
    
Nomes de meses aceitos:
  
- Português
    
  - janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro
    
  - Jan fev mar abr mai jun jul atrás Set out nov dez
    
## <a name="func_eu_date2-deprecated"></a>Func_eu_date2 (preterido)

> [!NOTE]
> Essa função foi preterida porque dá suporte apenas a nomes de meses em Holandês, que agora estão incluídos na `Func_eu_date` função acima. 
  
Essa função procura uma data no formato comumente usado em holandês. O formato dessa função é o mesmo que `Func_eu_date` , diferente somente no idioma usado.
  
Exemplos:
  
- 2 Mei 2016
    
- 02 Mei 2016
    
- 2 Mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-Mei-2016
    
- 2-12-16
    
Nomes de meses aceitos:
  
- Dutch
    
  - januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December
    
  - Jan Fev maart Apr Mei jun jul ago set out Okt Nov
    
## <a name="func_expiration_date"></a>Func_expiration_date

Essa função procura uma data nos formatos usados por cartões de crédito e débito, que exclui os dias e usa os meses. Essa função coincidirá datas no formato de "mês/ano", "Mês-Year", "[month Name] Year" e "[month abreviation] Year". Os nomes ou as abreviações de meses não diferenciam maiúsculas de minúsculas.
  
Exemplos:
  
- MM/AA -- por exemplo, 01/11 ou 1/11
    
- MM/AAAA -- por exemplo, 01/2011 ou 1/2011
    
- MM-AA -- por exemplo, 01-22 ou 1-11
    
- MM-AAAA -- por exemplo, 01-2000 ou 1-2000
    
Os seguintes formatos dão suporte a AA ou AAAA:
  
- Month-aaaa--por exemplo Jan-2010 ou Janeiro-2010 ou Jan-10 ou janeiro-10
    
- Mês AAAA – por exemplo, 'janeiro 2010' ou 'jan 2010' ou 'janeiro 10' ou 'jan 10'
    
- MêsAAAA – por exemplo, 'janeiro2010' ou 'Jan2010' ou 'janeiro10' ou 'Jan10'
    
- Month/aaaa--por exemplo, ' Janeiro/2010 ' ou ' Jan/2010 ' ou ' janeiro/10 ' ou ' Jan/10 '
    
Nomes de meses aceitos:
  
- English
    
  - Janeiro, fevereiro, março, abril, maio, junho de julho, agosto, setembro, outubro, novembro de dezembro
    
  - Jan fev mar de junho de julho de agosto de agosto de abril de dezembro
    
## <a name="func_us_address"></a>Func_us_address

Essa função procura um nome de estado americano ou abreviatura de postal seguida de um código postal válido, exatamente como eles são usados em endereços postais. O CEP deve ser um dos CEPs corretos associados ao nome ou sigla do estado americano. O nome do estado americano e o CEP não podem ser separados por pontos ou letras.
  
Exemplos:
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

