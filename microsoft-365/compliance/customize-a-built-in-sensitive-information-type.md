---
title: Personalizar um tipo de informação confidencial interno
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Aprenda a criar um tipo de informação sensível personalizado que permitirá que você use regras que atendam às necessidades da sua organização.
ms.openlocfilehash: 79d79a220e0cd8de0755f6cdac99cf7cceb2997f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922655"
---
# <a name="customize-a-built-in-sensitive-information-type"></a>Personalizar um tipo de informação confidencial interno

Ao procurar informações confidenciais no conteúdo, você precisa descrevê-las no que é chamado de *regra*. A Prevenção contra perda de dados (DLP) inclui regras para os tipos de informação confidencial mais comuns que você pode usar imediatamente. Para usar essas regras, você precisa incluí-las em uma política. Se quiser ajustar essas regras internas para atender às necessidades específicas da sua organização, basta criar um tipo de informação confidencial personalizado. Este tópico mostra como personalizar o arquivo XML que contém a coleção de regras existente para detectar um intervalo maior de possíveis informações de cartão de crédito. 
  
Você pode pegar este exemplo e aplicá-lo a outros tipos internos de informações confidenciais. Para obter uma lista dos tipos de informações confidenciais padrão e das definições XML, consulte [Definições da entidade do tipo de informações confidenciais.](sensitive-information-type-entity-definitions.md). 
  
## <a name="export-the-xml-file-of-the-current-rules"></a>Exportar o arquivo XML das regras atuais

Para exportar o XML, é necessário [conectar-se ao Centro de Conformidade e Segurança por meio do PowerShell Remoto.](/powershell/exchange/connect-to-scc-powershell).
  
1. No PowerShell, digite o seguinte para exibir as regras da sua organização na tela. Se você ainda não criou uma, verá apenas o padrão, as regras internas, rotuladas como "Pacote de Regras da Microsoft".

   ```powershell
   Get-DlpSensitiveInformationTypeRulePackage
   ```

2. Armazene as regras da sua organização em uma variável de entrada, digitando o seguinte. Armazenar algo em uma variável o torna facilmente disponível posteriormente em um formato que funciona para comandos remotos do PowerShell.

   ```powershell    
   $ruleCollections = Get-DlpSensitiveInformationTypeRulePackage
   ```
    
3. Crie um arquivo XML formatado com todos os dados digitando o seguinte. `Set-content` faz parte do cmdlet que grava o XML no arquivo. 

   ```powershell
   Set-Content -path C:\custompath\exportedRules.xml -Encoding Byte -Value $ruleCollections.SerializedClassificationRuleCollection
   ```

   > [!IMPORTANT]
   > Use o local do arquivo onde o pacote de regras está realmente armazenado. `C:\custompath\` é um espaço reservado. 
  
## <a name="find-the-rule-that-you-want-to-modify-in-the-xml"></a>Localizar a regra que você deseja modificar no XML

Os cmdlets acima exportam todo o *conjunto de regras*, que inclui as regras padrão fornecidas. Em seguida, será necessário procurar especificamente a regra de Número do cartão de crédito que você deseja modificar. 
  
1. Use um editor de texto para abrir o arquivo XML exportado na seção anterior.
    
2. Role para baixo até a marca `<Rules>`, que é o início da seção que contém as regras DLP. Como esse arquivo XML contém as informações de toda a coleção de regras, ele contém outras informações na parte superior que você precisa rolar para acessar as regras.
    
3. Procure *Func_credit_card* para encontrar a definição de regra de Número do cartão de crédito. No XML, os nomes de regras não podem conter espaços, então geralmente os espaços são substituídos por sublinhados, e às vezes os nomes de regra são abreviados. Um exemplo disto é a regra de números de Previdência Social dos EUA, que é abreviado como _SSN_. O XML da regra de Número do cartão de crédito deve parecer com o exemplo de código a seguir.
    
   ```xml
   <Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085"
          patternsProximity="300" recommendedConfidence="85">
         <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_credit_card" />
           <Any minMatches="1">
             <Match idRef="Keyword_cc_verification" />
             <Match idRef="Keyword_cc_name" />
             <Match idRef="Func_expiration_date" />
           </Any>
         </Pattern>
       </Entity>
   ```

Agora que você localizou a definição de regra de Número do cartão de crédito no XML, é possível personalizar o XML da regra para atender às suas necessidades. Para saber mais sobre as definições de XML, confira o [Glossário de termos](#term-glossary) no final deste tópico.
  
## <a name="modify-the-xml-and-create-a-new-sensitive-information-type"></a>Modificar o XML e criar um novo tipo de informação confidencial

Primeiro, você precisa criar um novo tipo de informações confidenciais, porque você não pode modificar as regras padrão diretamente. Você pode fazer uma grande variedade de coisas com os tipos de informações confidenciais personalizadas que são descritas em [Criar um tipo personalizado de informações confidenciais no Centro de Conformidade e Segurança do PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md). Para esse exemplo, manteremos a simplicidade e apenas removeremos evidências comprobatórias e adicionaremos palavras-chave para a regra de número do cartão de crédito.
  
Todas as definições de regra XML são criadas no modelo geral a seguir. É necessário copiar e colar o XML da definição de Número do cartão de crédito no modelo, modificar alguns valores (observe os espaços reservados ". . ." no exemplo a seguir) e carregar o XML modificado como uma nova regra que pode ser usada nas políticas.
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id=". . .">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id=". . ." /> 
    <Details defaultLangCode=". . .">
      <LocalizedDetails langcode=" . . . ">
         <PublisherName>. . .</PublisherName>
         <Name>. . .</Name>
         <Description>. . .</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
   <!-- Paste the Credit Card Number rule definition here.--> 
      <LocalizedStrings>
         <Resource idRef=". . .">
           <Name default="true" langcode=" . . . ">. . .</Name>
           <Description default="true" langcode=". . ."> . . .</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

Agora, você tem algo parecido com o XML a seguir. Como os pacotes de regras e as regras são identificados pelos GUIDs exclusivos, é necessário gerar dois GUIDs: um para o pacote de regras e outro para substituir o GUID da regra de Número do cartão de crédito. O GUID da ID de entidade no exemplo de código a seguir é aquele da definição de regra interna que você precisa substituir por um novo. Há várias maneiras de gerar GUIDs, mas é possível fazer isso com facilidade no PowerShell digitando **[guid]::NewGuid()**. 
  
```xml
<?xml version="1.0" encoding="utf-16"?>
<RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce">
  <RulePack id="8aac8390-e99f-4487-8d16-7f0cdee8defc">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="8d34806e-cd65-4178-ba0e-5d7d712e5b66" />
    <Details defaultLangCode="en">
      <LocalizedDetails langcode="en">
        <PublisherName>Contoso Ltd.</PublisherName>
        <Name>Financial Information</Name>
        <Description>Modified versions of the Microsoft rule package</Description>
      </LocalizedDetails>
    </Details>
  </RulePack>
  
 <Rules>
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f"
       patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
      <LocalizedStrings>
         <Resource idRef="db80b3da-0056-436e-b0ca-1f4cf7080d1f"> 
<!-- This is the GUID for the preceding Credit Card Number entity because the following text is for that Entity. -->
           <Name default="true" langcode="en-us">Modified Credit Card Number</Name>
           <Description default="true" langcode="en-us">Credit Card Number that looks for additional keywords, and another version of Credit Card Number that doesn't require keywords (but has a lower confidence level)</Description>
         </Resource>
      </LocalizedStrings>
   </Rules>
</RulePackage>
```

## <a name="remove-the-corroborative-evidence-requirement-from-a-sensitive-information-type"></a>Remover o requisito de evidências comprobatórias de um tipo de informação confidencial

Agora que você tem um novo tipo de informações confidenciais que você pode carregar no centro de conformidade &amp; de segurança, a próxima etapa é tornar a regra mais específica. Modificar a regra para que ela só procure um número de 16 dígitos que passa a soma de verificação, mas não exija evidências adicionais (comprobatórias), como palavras-chave. Para fazer isso, é necessário remover a parte do XML que procura por evidências comprobatórias. Evidência comprobatória é muito útil na redução de falsos positivos. Nesse caso, há geralmente determinadas palavras-chave ou uma data de vencimento ao lado do número do cartão de crédito. Se você remover essa evidência, também deverá ajustar a confiança de que encontrou um número de cartão de crédito abaixando a `confidenceLevel`, que é 85 no exemplo.
  
```xml
<Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="300"
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
      </Pattern>
    </Entity>
```

## <a name="look-for-keywords-that-are-specific-to-your-organization"></a>Procurar palavras-chave específicas da sua organização

Talvez você queira exigir evidência comprobatória, mas precise de palavras-chave diferentes ou adicionais, e pode ser que você queira alterar onde procurar essa evidência. Você pode ajustar a `patternsProximity` para expandir ou reduzir a janela de evidência comprobatória para aproximadamente 16 dígitos. Para adicionar as próprias palavras-chave, você precisa definir uma lista de palavras-chave e fazer referência a ela na regra. O XML a seguir adiciona as palavras-chave "cartão da empresa" e "Cartão Contoso" de modo que qualquer mensagem que contenha essas frases em até 150 caracteres de um número de cartão de crédito seja identificada como um número de cartão de crédito.
  
```xml
<Rules>
<! -- Modify the patternsProximity to be "150" rather than "300." -->
    <Entity id="db80b3da-0056-436e-b0ca-1f4cf7080d1f" patternsProximity="150" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
<!-- Add the following XML, which references the keywords at the end of the XML sample. -->
          <Match idRef="My_Additional_Keywords" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
<!-- Add the following XML, and update the information inside the <Term> tags with the keywords that you want to detect. -->
    <Keyword id="My_Additional_Keywords">
      <Group matchStyle="word">
        <Term caseSensitive="false">company card</Term>
        <Term caseSensitive="false">Contoso card</Term>
      </Group>
    </Keyword>
```

## <a name="upload-your-rule"></a>Carregar a regra

Para carregar a regra, é necessário fazer o seguinte.
  
1. Salve como um arquivo .xml com codificação Unicode. Isso é importante porque a regra não funcionará se o arquivo for salvo com uma codificação diferente.
    
2. [Conecte-se ao Centro de Conformidade e Segurança usando o PowerShell Remoto.](/powershell/exchange/connect-to-scc-powershell)
    
3. No PowerShell, digite o seguinte.

   ```powershell    
   New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path "C:\custompath\MyNewRulePack.xml" -Encoding Byte)
   ```
   
   > [!IMPORTANT]
   > Use o local do arquivo onde o pacote de regras está realmente armazenado. `C:\custompath\` é um espaço reservado. 
  
4. Para confirmar, digite S e pressione **Enter**.

5. Verifique se sua nova regra foi carregada e seu nome de exibição digitando:

   ```powershell
   Get-DlpSensitiveInformationType
   ```

Para começar a usar a nova regra para detectar informações confidenciais, é necessário adicionar a regra a uma política DLP. Saiba como adicionar a regra a uma política em [Criar uma política DLP a partir de um modelo](create-a-dlp-policy-from-a-template.md).
  
## <a name="term-glossary"></a>Glossário de termos

Estas são as definições dos termos encontrados durante este procedimento.
  
|**Termo**|**Definição**|
|:-----|:-----|
|Entidade|Entidades são o que chamamos de tipos de informação confidencial, como os números de cartão de crédito. Cada entidade tem um GUID exclusivo como ID. Quando você copia um GUID e pesquisa por ele no XML, encontra a definição de regra XML e todas as traduções localizadas dessa regra XML. Também é possível encontrar essa definição localizando o GUID para a tradução e depois pesquisando por este GUID.|
|Funções|As referências `Func_credit_card` do arquivo XML são uma função no código compilado. Funções são usadas para executar expressões regulares complexas e confirmam se as somas de verificação correspondem às nossas regras internas. Como isso ocorre no código, algumas das variáveis não aparecem no arquivo XML.|
|IdMatch|Esse é o identificador que padrão deverá corresponder — por exemplo, um número de cartão de crédito.|
|Lista de palavras-chave|O arquivo XML também faz referência a `keyword_cc_verification` e a `keyword_cc_name`, que são listas de palavras-chave, nas quais procuramos por correspondência em `patternsProximity` com a entidade. Atualmente elas não são exibidas no XML.|
|Padrão|O padrão contém a lista daquilo que o tipo de informações confidenciais está procurando. Isso inclui palavras-chave, regexes e funções internas, que executam tarefas como verificar somas de verificação. Tipos de informações confidenciais podem ter vários padrões com confianças exclusivas. Isso é útil quando você cria um tipo de informações confidenciais que retorna uma alta confiança se a evidência comprobatórias for encontrada e uma menor confiança se pouca ou nenhuma evidência comprobatórias for encontrada.|
|confidenceLevel padrão|Esse é o nível de confiança que o mecanismo de DLP encontrou na correspondência. Esse nível de confiança está associado a uma correspondência para o padrão se os requisitos do padrão são atendidos. Essa é a medida de confiança que deve ser considerada ao usar as regras de fluxo de emails (também conhecidas como regras de transporte) do Exchange.|
|patternsProximity|Quando encontramos algo que parece um padrão de número de cartão de crédito, o `patternsProximity` é a proximidade em torno desse número, onde procuraremos evidências corroborativas.|
|recommendedConfidence|Esse é o nível de confiança recomendável para esta regra. A confiança recomendada se aplica às entidades e afinidades. Para entidades, esse número nunca é avaliado em relação ao `confidenceLevel` do padrão. É simplesmente uma sugestão para ajudá-lo a escolher um nível de confiança, caso deseje usar um. Com afinidades, o `confidenceLevel` do padrão deve ser maior do que o número de `recommendedConfidence` para uma ação de regra de fluxo de emails ser chamada. A `recommendedConfidence` é o nível de confiança padrão usado em regras de fluxo de emails que chamam uma ação. Se quiser, é possível alterar manualmente a regra de fluxo de emails que será chamada com base no nível de confiança do padrão.  |
   
## <a name="for-more-information"></a>Para obter mais informações

- [Definições da entidade do tipo de informações confidenciais](sensitive-information-type-entity-definitions.md)
    
- [Criar um tipo de informação confidencial personalizado](create-a-custom-sensitive-information-type.md)
    
- [Visão geral das políticas de prevenção contra perda de dados](data-loss-prevention-policies.md)