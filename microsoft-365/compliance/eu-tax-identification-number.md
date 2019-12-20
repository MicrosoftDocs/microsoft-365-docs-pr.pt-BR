---
title: Número de identificação do imposto da UE
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação de imposto da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
ms.openlocfilehash: 0ee76fa46bb22b2754098d053ab769b862fdd3f2
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805844"
---
# <a name="eu-tax-identification-number"></a>Número de identificação do imposto da UE

Este tópico mostra o que uma política de prevenção de perda de dados (DLP) procura quando detecta o tipo de informação confidencial do número de identificação de imposto (TIN) da UE. Esse tipo de informação confidencial define diferentes padrões, palavras-chave e outras evidências para cada país.
  
## <a name="austria"></a>Áustria

### <a name="format"></a>Formatar

Nove dígitos com hífen opcional e barra para frente
  
### <a name="pattern"></a>Padrão

Nove dígitos com hífen opcional e barra para frente:
  
-  Dois dígitos 
    
- Um hífen (opcional)
    
- Três dígitos
    
- Uma barra (opcional)
    
- Quatro dígitos
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_austria_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_austria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_austria_eu_tax_file_number"></a>Keywords_austria_eu_tax_file_number

número do imposto
  
number
  
número de registro de imposto
  
tax id
  
st.nr.
  
steuernummer
  
## <a name="belgium"></a>Bélgica

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos:
  
- Dois dígitos
    
- Um "0" ou "1"
    
- Um dígito
    
- "0" ou "1" ou "2" ou "3" 
    
- Seis dígitos
    
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_belgium_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_belgium_eu_tax_file_number` chave de foi encontrada. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_belgium_eu_tax_file_number"></a>Keywords_belgium_eu_tax_file_number

número do imposto
  
número de Registro Nacional
  
número de registro de imposto
  
tax id
  
nse
  
nse #
  
Numéro de Registro Nacional
  
Numéro d'identification fiscal
  
## <a name="bulgaria"></a>Bulgária

### <a name="format"></a>Formatar

Dez dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

10 dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_bulgaria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_bulgaria_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_bulgaria_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_bulgaria_eu_tax_file_number"></a>Keywords_bulgaria_eu_tax_file_number

bucn
  
número civil uniforme
  
bucn #
  
uniformcivilnumber #
  
ID civil uniforme
  
Nenhum civil uniforme
  
egn
  
número civil uniforme búlgaro
  
uniformcivilno #
  
egn #
  
униформ граждански номер
  
ID униформ
  
ID de граждански униформ
  
униформ граждански не
  
## <a name="croatia"></a>Croácia

### <a name="format"></a>Formatar

11 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos:
  
- Dez dígitos, escolhidos aleatoriamente
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_croatia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_croatia_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_croatia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_croatia_eu_tax_file_number"></a>Keywords_croatia_eu_tax_file_number

número do imposto
  
imposto
  
tax id
  
OID
  
OID #
  
porezni broj
  
## <a name="cyprus"></a>Chipre

### <a name="format"></a>Formatar

Oito dígitos e uma letra no padrão especificado
  
### <a name="pattern"></a>Padrão

Oito dígitos e uma letra:
  
-  Um "0" 
    
- Sete dígitos 
    
- Uma letra (não diferencia maiúsculas de minúsculas)
    
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_cyprus_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_cyprus_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_cyprus_eu_tax_file_number"></a>Keywords_cyprus_eu_tax_file_number

número do imposto
  
imposto
  
tax id
  
código de identificação de imposto
  
tic
  
tic #
  
αριθμός φορολογικού μητρώου
  
φορολογική ταυτότητα
  
κωδικός φορολογικού μητρώου
  
## <a name="czech-republic"></a>República Tcheca

### <a name="format"></a>Formatar

Nove ou dez dígitos com uma barra invertida opcional
  
### <a name="pattern"></a>Padrão

Nove ou dez dígitos com uma barra invertida opcional:
  
- Seis dígitos 
    
- Uma barra invertida (opcional)
    
- Três ou quatro dígitos
    
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_czech_republic_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_czech_republic_eu_tax_file_number` chave de foi encontrada. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_czech_republic_eu_tax_file_number"></a>Keywords_czech_republic_eu_tax_file_number

número do imposto
  
imposto
  
tax id
  
número pessoal
  
daňové číslo
  
osobní číslo
  
## <a name="denmark"></a>Dinamarca

### <a name="format"></a>Formatar

Dez dígitos contendo um hífen
  
### <a name="pattern"></a>Padrão

Dez dígitos contendo um hífen:
  
-  Seis dígitos que correspondem à data de nascimento (DDMMAA) 
    
- Um hífen
    
- Quatro dígitos que correspondem a um número de sequência onde o primeiro dígito corresponde ao século do nascimento e o último dígito corresponde ao sexo da pessoa (ímpar para macho e par para fêmea)
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_denmark_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_denmark_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_denmark_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_denmark_eu_tax_file_number"></a>Keywords_denmark_eu_tax_file_number

número do imposto
  
imposto
  
tax id
  
número de CPR
  
pedir #
  
skat nummer
  
ID Skat
  
## <a name="estonia"></a>Estônia

### <a name="format"></a>Formatar

11 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos:
  
-  Um dígito que corresponde ao gênero e ao século de nascimento onde um número ímpar indica macho e o número par indica fêmea da seguinte maneira: 1, 2 para o século 19; 3, 4 para o século 20; e 5, 6 para o século 21 
    
- Seis dígitos que correspondem à data de nascimento (AAMMDD)
    
- Três dígitos que correspondem a um número de série separando as pessoas que nasceu na mesma data
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_estonia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_estonia_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_estonia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_estonia_eu_tax_file_number"></a>Keywords_estonia_eu_tax_file_number

número do imposto
  
imposto
  
tax id
  
código pessoal
  
maksunumber
  
ID maksu
  
isikukood
  
## <a name="finland"></a>Finlândia

### <a name="format"></a>Formatar

Uma combinação de 11 caracteres de dígitos, letras e sinal de mais e de menos
  
### <a name="pattern"></a>Padrão

Uma combinação de 11 caracteres de dígitos, letras e sinal de mais e menos:
  
- Seis dígitos
    
- Uma das seguintes opções: um sinal de adição, um sinal de menos ou a letra "A" (não diferencia maiúsculas de minúsculas) onde o sinal de mais significa que nasceu entre 1800-1899, o sinal de menos significa que nasceu entre 1900-1999 e "A" significa que nasceu 2000 e depois
    
- Três dígitos
    
- Uma letra ou um número
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_finland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_finland_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_finland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_finland_eu_tax_file_number"></a>Keywords_finland_eu_tax_file_number

identification number
  
ID pessoal
  
número de identidade
  
número de ID nacional da finlandês
  
personalidnumber #
  
national identification number
  
número de identificação
  
n º de ID nacional
  
número de ID nacional
  
ID não
  
tunnistenumero
  
henkilötunnus
  
yksilöllinen henkilökohtainen tunnistenumero
  
ainutlaatuinen henkilökohtainen tunnus
  
identiteetti numero
  
suomen kansallinen henkilötunnus
  
henkilötunnusnumero #
  
kansallisen tunnistenumero
  
tunnusnumero
  
kansallinen tunnus numero
  
## <a name="france"></a>França

### <a name="format"></a>Formatar

13 dígitos para pessoas e nove dígitos para entidades
  
### <a name="pattern"></a>Padrão

13 dígitos para pessoas:
  
- Um dígito que deve ser 0, 1, 2 ou 3
    
- 12 dígitos
    
Nove dígitos para entidades
  
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_france_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_france_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_france_eu_tax_file_number"></a>Keywords_france_eu_tax_file_number

número de identificação do imposto
  
número do imposto
  
tax id
  
Numéro d'identification fiscal
  
## <a name="germany"></a>Alemanha

### <a name="format"></a>Formatar

11 dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos:
  
-  Dez dígitos 
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_germany_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_germany_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_germany_eu_tax_file_number"></a>Keywords_germany_eu_tax_file_number

número do imposto
  
n º do imposto
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
táxi #
  
número de identificação do imposto
  
n º de identificação de imposto
  
steuernummer
  
ID Steuer
  
steueridentifikationsnummer
  
## <a name="greece"></a>Grécia

### <a name="format"></a>Formatar

Nove dígitos sem espaços e delimitadores
  
### <a name="pattern"></a>Padrão

Nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_greece_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_greece_eu_tax_file_number` chave de foi encontrada. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_greece_eu_tax_file_number"></a>Keywords_greece_eu_tax_file_number

AFM
  
Tin
  
n º de ID de imposto
  
ID de imposto não
  
número de identificação do imposto
  
número do registro de imposto
  
n º do registro de impostos
  
AFM #
  
Tin #
  
taxidno #
  
taxregistryno #
  
αριθμός φορολογικού μητρώου
  
aφμ
  
aφμ αριθμός
  
φορολογικού μητρώου νο.
  
τον αριθμό φορολογικού μητρώου
  
## <a name="hungary"></a>Hungria

### <a name="format"></a>Formatar

Dez dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Dez dígitos:
  
-  Um dígito que deve ser "8" 
    
- Cinco dígitos que correspondem ao número de dias entre a data 01/01/1867 e a data do nascimento da pessoa
    
- Três dígitos que correspondem ao número gerado pela chance de diferenciar as pessoas nasceu no mesmo dia
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_hungary_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_hungary_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_hungary_eu_tax_file_number"></a>Keywords_hungary_eu_tax_file_number

número de identificação do imposto húngaro
  
Tin húngaro
  
número de ID do imposto
  
número de IVA
  
autoridade de imposto não
  
número de identidade do imposto ID do imposto
  
taxidnumber #
  
Tin #
  
hungatiantin #
  
identificação de imposto não
  
taxidno #
  
adóazonosító szám
  
adószám
  
adóhatóság szám
  
## <a name="ireland"></a>Irlanda

### <a name="format"></a>Formatar

Sete dígitos seguidos de uma letra sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Sete dígitos seguidos de uma letra:
  
-  Sete dígitos  
    
- Uma letra (não diferencia maiúsculas de minúsculas)
    
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_ireland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_ireland_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_ireland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_ireland_eu_tax_file_number"></a>Keywords_ireland_eu_tax_file_number

serviço público não
  
serviço público pessoal não
  
PPS não
  
serviço pessoal não
  
serviço PPS não
  
ppsno #
  
número do PPS do irlandês
  
publicserviceno #
  
número de serviço público pessoal
  
uimhir phearsanta seirbhíse poiblí
  
PPS uimh
  
uimhir aitheantais phearsanta
  
## <a name="italy"></a>Itália

### <a name="format"></a>Formatar

16 letras e dígitos no padrão especificado
  
### <a name="pattern"></a>Padrão

16 letras e dígitos:
  
-  Três letras que correspondem às três primeiras consoantes no nome da família 
    
- Três letras que correspondem à primeira, terceira e quarta consoantes no primeiro nome
    
- Dois dígitos que correspondem aos últimos dígitos do ano de nascimento
    
- Um dígito que corresponde ao mês de nascimento-as letras são usadas em ordem alfabética, mas apenas as letras de a a E, H, L, M, P, R a T são usadas (portanto, Janeiro é A e outubro é R)
    
- Dois dígitos que correspondem ao dia do mês de nascimento, onde 40 é adicionado ao dia de nascimento de mulheres para diferenciar da homens
    
- Quatro dígitos que correspondem a um código de área específico para o município onde a pessoa nasceu — códigos em todo o país são usados para países estrangeiros
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_italy_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_italy_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_italy_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_italy_eu_tax_file_number"></a>Keywords_italy_eu_tax_file_number

número do imposto
  
n º do imposto
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
táxi #
  
código fiscal
  
fiscalização codice
  
## <a name="latvia"></a>Letônia

### <a name="format"></a>Formatar

11 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos no padrão especificado
  
-  Seis dígitos que correspondem à data de nascimento (DDMMAA) 
    
- Um dígito que corresponde ao século de nascimento onde "0" corresponde ao século 19, "1" corresponde a 20 Century e "2" corresponde ao século 21
    
- Quatro dígitos
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_latvia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_latvia_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_latvia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_latvia_eu_tax_file_number"></a>Keywords_latvia_eu_tax_file_number

número do imposto
  
n º do imposto
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
táxi #
  
número de identificação do imposto
  
n º de identificação de imposto
  
nodokļa numurs
  
nodokļu identifikācijas numurs
  
nodokļu identifikācija numurs
  
## <a name="lithuania"></a>Lituânia

### <a name="format"></a>Formatar

11 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

11 dígitos
  
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_lithuania_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_lithuania_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_lithuania_eu_tax_file_number"></a>Keywords_lithuania_eu_tax_file_number

número do imposto
  
n º do imposto
  
n º do imposto #
  
taxnumber #
  
taxnumber
  
tax id
  
táxi #
  
número de identificação do imposto
  
n º de identificação de imposto
  
ID mokesčių
  
mokesčių numeris
  
mokesčių identifikavimas numeris
  
## <a name="luxemburg"></a>Luxemburg

### <a name="format"></a>Formatar

13 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

13 dígitos:
  
-  11 dígitos 
    
- Dois dígitos de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_luxemburg_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_luxemburg_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_luxemburg_eu_tax_file_number"></a>Keywords_luxemburg_eu_tax_file_number

número do imposto
  
n º do imposto
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
táxi #
  
número de identificação do imposto
  
n º de identificação de imposto
  
steuernummer
  
ID Steuer
  
steueridentifikationsnummer
  
## <a name="malta"></a>Malta

### <a name="format"></a>Formatar

Para as nacionalidades maltês: 7 dígitos e uma letra no padrão especificado
  
Entidades nacionais e Maltês não-maltês: 9 dígitos
  
### <a name="pattern"></a>Padrão

Nacionalidades maltês: 7 dígitos e uma letra
  
-  Sete dígitos  
    
- Uma letra (não diferencia maiúsculas de minúsculas)
    
Entidades nacionais e Maltês não-maltês: 9 dígitos
  
-  Nove dígitos 
    
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_malta_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_malta_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 65% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_malta_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_malta_eu_tax_file_number"></a>Keywords_malta_eu_tax_file_number

número do imposto
  
n º do imposto
  
taxno #
  
taxnumber #
  
taxnumber
  
tax id
  
táxi #
  
número de identificação do imposto
  
n º de identificação de imposto
  
numru tat-taxxa
  
ID tat-taxxa
  
numru ta ' identifikazzjoni tat-taxxa
  
## <a name="netherlands"></a>Países Baixos

### <a name="format"></a>Formatar

Nove dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Nove dígitos 
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_netherlands_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_netherlands_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_netherlands_eu_tax_file_number"></a>Keywords_netherlands_eu_tax_file_number

número de identificação do imposto Holanda
  
identificação de imposto Holanda
  
número de identificação de imposto do Netherland
  
identificação de imposto do Netherland
  
número de identificação do imposto
  
ID de imposto holandês
  
número de identificação do imposto holandês
  
tax id
  
ID de imposto #
  
número do imposto
  
n º do imposto #
  
imposto #
  
Tin
  
Tin #
  
Tin Holanda
  
Tin do Netherland
  
Países Baixos identificatienummer
  
identificatienummer Van é última
  
identificatienummer a última
  
Países Baixos identificatie
  
Países Baixos Nummer ID da última vez
  
Países Baixos belastingnummer
  
btw nummer
  
Nederlandse identificatie
  
## <a name="poland"></a>Polônia

### <a name="format"></a>Formatar

Onze dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Onze dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_poland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_poland_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_poland_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_poland_eu_tax_file_number"></a>Keywords_poland_eu_tax_file_number

número do imposto
  
n º do imposto
  
taxno #
  
taxnumber #
  
taxnumber
  
nip
  
nip #
  
tax id
  
ID de imposto #
  
ID Nip
  
ID Nip #
  
número de identificação do imposto
  
n º de identificação de imposto
  
número de IVA
  
IVA não.
  
vatno #
  
ID de IVA
  
ID de IVA #
  
numer identyfikacji podatkowej
  
polski numer identyfikacji podatkowej
  
numeridentyfikacjipodatkowej #
  
## <a name="portugal"></a>Portugal

### <a name="format"></a>Formatar

Nove dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Nove dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_portugal_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_portugal_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_portugal_eu_tax_file_number"></a>Keywords_portugal_eu_tax_file_number

número do imposto
  
n º do imposto
  
taxno #
  
taxnumber #
  
taxnumber
  
nse
  
nse #
  
fiscal numero
  
número de identificação fiscal
  
## <a name="romania"></a>Romênia

### <a name="format"></a>Formatar

13 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

13 dígitos
  
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_romania_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_romania_eu_tax_file_number` chave de foi encontrada. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_romania_eu_tax_file_number"></a>Keywords_romania_eu_tax_file_number

tax id
  
número de ID do imposto
  
arquivo de imposto não
  
tax file number
  
n º do imposto
  
número do imposto
  
táxi #
  
taxno #
  
ID-UL Taxei
  
numărul de identificare Fiscală
  
## <a name="slovakia"></a>Eslováquia

### <a name="format"></a>Formatar

10 dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

10 dígitos
  
### <a name="checksum"></a>Soma de verificação

Não se aplica
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A expressão `Regex_slovakia_eu_tax_file_number` regular localiza o conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_slovakia_eu_tax_file_number` chave de foi encontrada. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovakia_eu_tax_file_number"></a>Keywords_slovakia_eu_tax_file_number

tax id
  
número de ID do imposto
  
ID do Tin
  
Tin não
  
ID de Tin de eslovaco
  
Tin
  
arquivo de imposto não
  
tax file number
  
n º do imposto
  
número do imposto
  
táxi #
  
taxno #
  
daňové identifikačné číslo
  
daňové číslo
  
daňové číslo súboru
  
## <a name="slovenia"></a>Eslovênia

### <a name="format"></a>Formatar

Oito dígitos sem espaços ou delimitadores
  
### <a name="pattern"></a>Padrão

Oito dígitos
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_slovenia_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_slovenia_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_slovenia_eu_tax_file_number"></a>Keywords_slovenia_eu_tax_file_number

tax id
  
número de ID do imposto
  
ID do Tin
  
Tin não
  
ID de Tin esloveno
  
Tin
  
arquivo de imposto não
  
tax file number
  
n º do imposto
  
número do imposto
  
táxi #
  
taxno #
  
identifikacijska številka davka
  
davčna številka
  
številka davčne datoteke
  
## <a name="spain"></a>Espanha

### <a name="format"></a>Formatar

Sete ou oito dígitos e uma ou duas letras no padrão especificado
  
### <a name="pattern"></a>Padrão

Pessoas naturais do espanhol com um cartão de identidade nacional da Espanha:
  
-  Oito dígitos 
    
- Uma letra maiúscula (diferencia maiúsculas de minúsculas) 
    
Spaniards não residente sem um cartão de identidade nacional da Espanha
  
- Uma letra maiúscula "L" (diferencia maiúsculas de minúsculas)
    
- Sete dígitos 
    
- Uma letra maiúscula (diferencia maiúsculas de minúsculas) 
    
Spaniards residentes sob a idade de 14 anos sem um cartão de identidade nacional da Espanha:
  
- Uma letra maiúscula "K" (diferencia maiúsculas de minúsculas)
    
-  Sete dígitos  
    
- Uma letra maiúscula (diferencia maiúsculas de minúsculas)
    
Foreigners com o número de identificação do estrangeiro
  
- Uma letra maiúscula que é "X", "Y" ou "Z" (diferencia maiúsculas de minúsculas) 
    
- Sete dígitos 
    
- Uma letra maiúscula (diferencia maiúsculas de minúsculas) 
    
Foreigners sem um número de identificação do estrangeiro
  
- Uma letra maiúscula que é "M" (diferencia maiúsculas de minúsculas) 
    
- Sete dígitos 
    
- Uma letra maiúscula (diferencia maiúsculas de minúsculas) 
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_spain_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_spain_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_spain_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_spain_eu_tax_file_number"></a>Keywords_spain_eu_tax_file_number

tax id
  
número de ID do imposto
  
ID de CIF
  
Não CIF
  
ID de CIF espanhol
  
CIF
  
arquivo de imposto não
  
número de CIF espanhol
  
tax file number
  
Não CIF espanhol
  
n º do imposto
  
número do imposto
  
táxi #
  
taxno #
  
cifid #
  
spanishcifid #
  
spanishcifno #
  
número de contribuyente
  
número de impuesto corporativo
  
número de Identificación fiscal
  
número CIF
  
cifnúmero #
  
## <a name="sweden"></a>Suécia

### <a name="format"></a>Formatar

Dez dígitos e um símbolo no padrão especificado
  
### <a name="pattern"></a>Padrão

Dez dígitos e um símbolo:
  
-  Seis dígitos que correspondem à data de nascimento (AAMMDD) 
    
- Um sinal de adição, sinal de menos ou barra invertida
    
- Três dígitos que tornam o número de identificação exclusivo, onde: 
    
  - Para números emitidos antes de 1990, o sétimo e oitavo dígito identificam o Condado de nascimento ou pessoas de nasceu
    
  - O dígito na nona posição indica sexo por tanto ímpar para masculino ou par para fêmea
    
- Um dígito de verificação
    
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 85% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_sweden_eu_tax_file_number` chave de foi encontrada. 
    
Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_sweden_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_sweden_eu_tax_file_number"></a>Keywords_sweden_eu_tax_file_number

tax id
  
n º de ID de imposto
  
número de ID do imposto
  
tax identification
  
identificação de imposto #
  
n º do imposto
  
imposto #
  
táxi #
  
arquivo de imposto
  
arquivo de impostos não.
  
número de identificação pessoal
  
skatt ID Nummer
  
skatt identifikation
  
personnummer
  
## <a name="uk"></a>Reino Unido

### <a name="format"></a>Formatar

Referência de contribuidor exclusivo (UTR): 10 dígitos sem espaços e delimitadores
  
Número de seguro nacional (NINO): para obter detalhes, consulte a seção "Reino Unido Número de seguro nacional (NINO) "em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
### <a name="pattern"></a>Padrão

Referência de contribuidor exclusivo (UTR): 10 dígitos
  
Número de seguro nacional (NINO): para obter detalhes, consulte a seção "Reino Unido Número de seguro nacional (NINO) "em [o que os tipos de informações confidenciais procuram](what-the-sensitive-information-types-look-for.md).
  
### <a name="checksum"></a>Soma de verificação

Sim
  
### <a name="definition"></a>Definição

Uma política de DLP tem 75% de certeza de que ela detectou este tipo de informação confidencial se, dentro de uma proximidade de 300 caracteres:
  
- A função `Func_uk_eu_tax_file_number` localiza conteúdo que corresponde ao padrão. 
    
- Uma palavra- `Keywords_uk_eu_tax_file_number` chave de foi encontrada. 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a>Palavras-chave

#### <a name="keywords_uk_eu_tax_file_number"></a>Keywords_uk_eu_tax_file_number

tax id
  
n º de ID de imposto
  
número de ID do imposto
  
tax identification
  
identificação de imposto #
  
n º do imposto
  
imposto #
  
táxi #
  
arquivo de imposto
  
arquivo de impostos não.
  
## <a name="see-also"></a>Confira também

[O que os tipos de informação confidencial procuram](what-the-sensitive-information-types-look-for.md)

