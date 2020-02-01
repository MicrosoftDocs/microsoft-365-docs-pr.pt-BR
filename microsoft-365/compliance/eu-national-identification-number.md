---
title: Número de identificação nacional da UE
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação nacional da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: f001d23ec3d6d8a2b3aa9575d4a9d602c4315e13
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592232"
---
# <a name="eu-national-identification-number"></a>Número de identificação nacional da UE

Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação nacional da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
  
## <a name="austria"></a>Áustria

### <a name="format"></a>Formatar

Uma combinação de 24 caracteres de letras, dígitos e caracteres especiais
  
### <a name="pattern"></a>Padrão

24 caracteres:
  
-  22 letras (não diferencia maiúsculas de minúsculas), dígitos, barras invertidas, barras encaminhadas ou sinais de adição 
    
- Duas letras (não diferencia maiúsculas de minúsculas), dígitos, barras invertidas, barras invertidas, sinais de adição ou sinais de igual
    
### <a name="checksum"></a>Soma de verificação

Não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_austria_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_austria_eu_national_id_card` chave de foi encontrada. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_austria_eu_national_id_card"></a>Keywords_austria_eu_national_id_card

número de identidade austríaca
  
número de identidade nacional
  
número de identidade
  
national id
  
personalausweis republik österreich
  
## <a name="belgium"></a>Bélgica

Para obter detalhes, consulte a seção "número nacional da Bélgica" em o [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="bulgaria"></a>Bulgária

### <a name="format"></a>Formatar

Dez dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Dez dígitos sem espaços e delimitadores
  
-  Seis dígitos que correspondem à data de nascimento (AAMMDD) 
    
- Dois dígitos que correspondem à ordem de nascimento
    
- Um dígito que corresponde ao gênero: um dígito par para macho e um dígito estranho para o fêmea
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_bulgaria_national_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_bulgaria_national_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_bulgaria_national_number` localiza conteúdo que corresponde ao padrão. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_bulgaria_national_number"></a>Keywords_bulgaria_national_number

egn
  
egn #
  
número nacional búlgaro
  
número nacional
  
social security number
  
nationalnumber #
  
es #
  
es
  
nationalnumber
  
bnn #
  
bnn
  
número de identificação pessoal
  
personalidnumber #
  
единен граждански номер
  
edinen grazhdanski de nome
  
егн
  
егн #
  
## <a name="croatia"></a>Croácia

Para obter detalhes, consulte a seção "número de identidade da Croácia" em o [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formatar

Dez dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

 Dez dígitos 
  
### <a name="checksum"></a>Soma de verificação

Não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_cyprus_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_cyprus_eu_national_id_card` chave de foi encontrada. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_cyprus_eu_national_id_card"></a>Keywords_cyprus_eu_national_id_card

número do cartão de identificação
  
national identification number
  
número de identificação pessoal
  
número do cartão de identidade
  
ταυτοτητασ
  
## <a name="czech-republic"></a>República Tcheca

Para obter detalhes, consulte a seção "número de identidade nacional tcheco" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="denmark"></a>Dinamarca

Para obter detalhes, consulte a seção "Dinamarca Personal Identification Number" em o [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="estonia"></a>Estônia

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos:
  
- Um dígito que corresponde ao sexo e ao século de nascimento (número ímpar masculino, mesmo número fêmea; 1-2:19 Century; 3-4:20 Century; 5-6:21 século)
    
- Seis dígitos que correspondem à data de nascimento (AAMMDD)
    
- Três dígitos que correspondem a um número de série separando as pessoas que nasceu na mesma data
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_estonia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_estonia_eu_national_id_card` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_estonia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_estonia_eu_national_id_card"></a>Keywords_estonia_eu_national_id_card

código de identificação pessoal
  
número de identificação pessoal
  
national identification number
  
número nacional
  
número de identificação pessoal
  
personalidnumber #
  
IKMover
  
isikukood
  
ID-kaart
  
## <a name="finland"></a>Finlândia

Para obter detalhes, consulte a seção "ID nacional da Finlândia" em o [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="france"></a>França

Para obter detalhes, consulte a seção "CNI (cartão de ID nacional da França)" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="germany"></a>Alemanha

Para obter detalhes, consulte a seção "número do cartão de identidade da Alemanha" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="greece"></a>Grécia

Para obter detalhes, consulte a seção "cartão de ID nacional da Grécia" em [que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="hungary"></a>Hungria

### <a name="format"></a>Formatar

11 dígitos
  
### <a name="pattern"></a>Padrão

11 dígitos:
  
-  Um dígito que corresponde ao gênero (1-macho, 2-fêmea, outros números também são possíveis para o cidadãos nasceu antes 1900 ou cidadãos com cidadania dupla) 
    
- Seis dígitos que correspondem à data de nascimento (AAMMDD)
    
- Três dígitos que correspondem a um número de série
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_hungary_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_hungary_eu_national_id_card` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_hungary_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_hungary_eu_national_id_card"></a>Keywords_hungary_eu_national_id_card

número de identificação pessoal
  
identification number
  
número de identificação pessoal
  
személyazonosító igazolvány
  
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formatar

Uma combinação de letras, dígitos e um espaço no padrão especificado de nove caracteres
  
### <a name="pattern"></a>Padrão

Uma combinação de letras, dígitos e um espaço no padrão especificado de nove caracteres
  
De 1º de janeiro de 2013 até agora:
  
-  Sete dígitos  
    
- Um dígito de verificação
    
- Um espaço ou a letra maiúscula "W" (diferencia maiúscula de minúscula)
    
Antes de 1º de janeiro de 2013:
  
-  Sete dígitos  
    
- Um dígito de verificação
    
- Um espaço ou uma letra maiúscula (diferencia maiúscula de minúscula)
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função localiza conteúdo que corresponde ao padrão.
    
- Uma palavra-chave de foi encontrada.
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função localiza conteúdo que corresponde ao padrão.
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_ireland_eu_national_id_card"></a>Keywords_ireland_eu_national_id_card

número de serviço público pessoal
  
PPS não
  
número da receita e do seguro social
  
RSI não
  
número de identificação pessoal
  
identification number
  
número de identificação pessoal
  
uimhir phearsanta seirbhíse poiblí
  
uimh. PSP
  
## <a name="italy"></a>Itália

### <a name="format"></a>Formatar

Uma combinação de 16 caracteres de letras e dígitos no padrão especificado
  
### <a name="pattern"></a>Padrão

Uma combinação de letras e dígitos de 16 caracteres:
  
- Três letras que correspondem às três primeiras consoantes no nome da família
    
- Três letras que correspondem à primeira, terceira e quarta consoantes no primeiro nome
    
- Dois dígitos que correspondem aos últimos dígitos do ano de nascimento
    
- Uma letra que corresponde à carta para o mês de nascimento-as letras são usadas em ordem alfabética, mas apenas as letras de a a E, H, L, M, P, R a T são usadas (dessa forma, Janeiro é A e outubro é R)
    
- Dois dígitos que correspondem ao dia do mês de nascimento — para diferenciar entre sexos, 40 é adicionado ao dia de nascimento para mulheres
    
- Quatro dígitos que correspondem ao código de área específico do município onde a pessoa nasceu (códigos de todo o país são usados para países estrangeiros)
    
- Um dígito de paridade
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_italy_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_italy_eu_national_id_card` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_italy_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_italy_eu_national_id_card"></a>Keywords_italy_eu_national_id_card

código pessoal
  
número de código pessoal
  
número do certificado pessoal
  
código fiscal
  
personalcodeno #
  
número de identificação pessoal
  
código de ID pessoal
  
pessoal do Codice
  
numero certificato pessoal
  
pessoal do numero
  
pessoal da ID numero
  
pessoal da ID codice
  
fiscalização codice
  
## <a name="latvia"></a>Letônia

### <a name="format"></a>Formatar

11 dígitos e um hífen no formato especificado
  
### <a name="pattern"></a>Padrão

11 dígitos e um hífen:
  
-  Seis dígitos que correspondem à data de nascimento (DDMMAA) 
    
- Um hífen
    
- Um dígito que corresponde ao século de nascimento ("0" para o século 19, "1" para o século 20 e "2" para o século 21)
    
- Quatro dígitos, gerados aleatoriamente
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_latvia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_latvia_eu_national_id_card` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_latvia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_latvia_eu_national_id_card"></a>Keywords_latvia_eu_national_id_card

código pessoal
  
número de código pessoal
  
número do certificado pessoal
  
personalcodeno #
  
número de identificação pessoal
  
código de ID pessoal
  
Kods personas
  
## <a name="lithuania"></a>Lituânia

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos sem espaços e delimitadores:
  
- Um dígito que corresponde ao sexo da pessoa e ao século de nascimento
    
-  Seis dígitos que correspondem à data de nascimento (AAMMDD) 
    
- Três dígitos que correspondem ao número de série da data de nascimento
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_lithuania_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_lithuania_eu_national_id_card` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_lithuania_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_lithuania_eu_national_id_card"></a>Keywords_lithuania_eu_national_id_card

código numérico pessoal
  
número de identificação exclusivo
  
número do serviço do cidadão
  
número de identidade exclusivo
  
uniqueidentityno #
  
código pessoal.
  
asmeninis skaitmeninis kodas
  
unikalus identifikavimo numeris
  
piliečio paslaugos numeris
  
unikalus identifikavimo kodas
  
kodas.
  
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos
  
- Um dígito que corresponde ao sexo da pessoa e ao século de nascimento
    
-  Seis dígitos que correspondem à data de nascimento (AAMMDD) 
    
- Três dígitos que correspondem ao número de série da data de nascimento
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_luxemburg_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_luxemburg_eu_national_id_card` chave de foi encontrada. 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_luxemburg_eu_national_id_card"></a>Keywords_luxemburg_eu_national_id_card

ID pessoal
  
número de identificação pessoal
  
personalidno #
  
número de identificação exclusivo
  
personalidnumber #
  
chave de ID exclusiva
  
código de ID pessoal
  
uniqueidkey #
  
código individual
  
ID individual
  
ID eindeutige-Nummer
  
ID eindeutige
  
ID personnelle
  
Numéro d'identification
  
idpersonnelle #
  
persönliche identifikationsnummer
  
eindeutigeid #
  
## <a name="malta"></a>Malta

### <a name="format"></a>Formatar

Sete dígitos seguidos de uma letra
  
### <a name="pattern"></a>Padrão

Sete dígitos seguidos de uma letra:
  
-  Sete dígitos  
    
- Uma letra maiúscula (diferencia maiúsculas de minúsculas)
    
### <a name="checksum"></a>Soma de verificação

Não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_malta_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_malta_eu_national_id_card` chave de foi encontrada. 
    
Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_malta_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_malta_eu_national_id_card"></a>Keywords_malta_eu_national_id_card

código numérico pessoal
  
número de identificação exclusivo
  
número do serviço do cidadão
  
número de identidade exclusivo
  
uniqueidentityno #
  
Kodiċi numerali pessoali
  
numru ta ' identifikazzjoni uniku
  
numru tas-servizz taċ-ċittadin
  
numru ta ' Identità uniku
  
## <a name="netherlands"></a>Países Baixos

### <a name="format"></a>Formatar

Nove dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_netherlands_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra-chave de foi encontrada.
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_netherlands_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_netherlands_eu_national_id_card"></a>Keywords_netherlands_eu_national_id_card

código numérico pessoal
  
número de identificação exclusivo
  
número do serviço do cidadão
  
número de identidade exclusivo
  
uniqueidentityno #
  
BSN
  
BSN #
  
código de numerieke persoonlijke
  
uniek identificatienummer
  
burgerservicenummer
  
uniek identiteitsnummer
  
## <a name="poland"></a>Polônia

Para obter detalhes, consulte a seção "ID nacional da Polônia (PESEL)" em [que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
## <a name="portugal"></a>Portugal

Para obter detalhes, consulte a seção "número de cartão de cidadão da Portugal" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="romania"></a>Romênia

### <a name="format"></a>Formatar

13 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

13 dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_romania_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_romania_eu_national_id_card` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_romania_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_romania_eu_national_id_card"></a>Keywords_romania_eu_national_id_card

código numérico pessoal
  
número de identificação exclusivo
  
cnp
  
cnp #
  
pessoal
  
pessoal #
  
número de seguro
  
insurancenumber #
  
número de identidade exclusivo
  
uniqueidentityno #
  
c.o.d. numérico pessoal
  
identificare de c.o.d. pessoal
  
UNIC de c.o.d. identificare
  
număr pessoal do UNIC
  
număr identitate
  
număr identificare pessoal
  
număridentitate #
  
codnumericpersonal #
  
numărpersonalunic #
  
## <a name="slovakia"></a>Eslováquia

### <a name="format"></a>Formatar

Dez dígitos contendo uma barra invertida
  
### <a name="pattern"></a>Padrão

Dez dígitos contendo uma barra invertida:
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_slovakia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_slovakia_eu_national_id_card` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_slovakia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovakia_eu_national_id_card"></a>Keywords_slovakia_eu_national_id_card

número de nascimento
  
national identification number
  
número de identificação pessoal
  
social security number
  
nationalnumber #
  
es #
  
es
  
número nacional
  
número de identificação pessoal
  
personalidnumber #
  
rč
  
rodné číslo
  
rodne cislo
  
## <a name="slovenia"></a>Eslovênia

### <a name="format"></a>Formatar

13 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

13 dígitos no padrão especificado:
  
-  Sete dígitos que correspondem à data de nascimento (DDMMLLL), onde "LLL" corresponde aos últimos três dígitos do ano de nascimento 
    
- Dois dígitos que correspondem à área de nascimento
    
- Três dígitos que correspondem a uma combinação de sexo e número de série para pessoas nasceu no mesmo dia (000-499 para macho e 500-999 para fêmea)
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_slovenia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_slovenia_eu_national_id_card` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_slovenia_eu_national_id_card` localiza conteúdo que corresponde ao padrão. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovenia_eu_national_id_card"></a>Keywords_slovenia_eu_national_id_card

código numérico pessoal
  
número de identificação exclusivo
  
número de registro exclusivo
  
número de identidade exclusivo
  
uniqueidentityno #
  
número de cidadão mestre exclusivo
  
edinstvena identifikacijska številka
  
uniqueidentityno #
  
edinstvena številka glavnega državljana
  
emšo
  
## <a name="spain"></a>Espanha

### <a name="format"></a>Formatar

Sete dígitos seguidos de um caractere
  
### <a name="pattern"></a>Padrão

Sete dígitos seguidos de um caractere
  
- Sete dígitos 
    
- Um dígito ou letra (não diferencia maiúsculas de minúsculas)
    
### <a name="checksum"></a>Soma de verificação

Não aplicável
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_spain_eu_national_id_card` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_spain_eu_national_id_card"` chave de foi encontrada. 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_spain_eu_national_id_card"></a>Keywords_spain_eu_national_id_card

dni
  
national identification number
  
número de identidade nacional
  
número de seguro
  
número de identificação pessoal
  
identidade nacional
  
identidade pessoal não
  
número de identidade exclusivo
  
nationalidno #
  
UniqueId #
  
dni #
  
nationalid #
  
nie #
  
nie
  
nienúmero #
  
Nie número
  
documento nacional de Identidad
  
identidad único
  
número nacional identidad
  
DNI número
  
dninúmero #
  
identidadúnico #
  
## <a name="sweden"></a>Suécia

Para obter detalhes, consulte a seção "ID nacional da Suécia" em [o que os tipos de informações confidenciais buscam](what-the-sensitive-information-types-look-for.md).
  
## <a name="see-also"></a>Confira também

[O que os tipos de informação confidencial procuram](what-the-sensitive-information-types-look-for.md)

