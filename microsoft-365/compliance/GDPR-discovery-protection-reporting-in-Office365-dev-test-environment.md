---
title: Descoberta de RGPD, proteção e relatórios no ambiente de desenvolvimento/teste
description: Demonstre recursos de RGPD no Microsoft 365.
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 6a16f48948cd40ea39f8d066471e902d2b5a6bf0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632336"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-devtest-environment"></a>Descoberta de RGPD, proteção e relatórios no ambiente de desenvolvimento/teste

 **Resumo:** demonstre recursos de RGPD no Microsoft 365. 
  
Este artigo descreve como configurar e demonstrar a descoberta, a proteção e o relatório de informações de identificação pessoal (PII), para a Regulamentação Geral sobre a Proteção de Dados (RGPD) em um ambiente de desenvolvimento/teste do Microsoft 365.
  
## <a name="phase-1-create-and-configure-your-trial-microsoft-365-subscription"></a>Fase 1: Criar e configurar a sua assinatura de avaliação do Microsoft 365

Primeiro, siga as etapas no artigo em [Fase 2 do ambiente de desenvolvimento/teste do Microsoft 365](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription).

Em seguida, use estas etapas para configurar o gerente de Descoberta Eletrônica:

1. Entre no locatário de avaliação do Microsoft 365 com sua conta de administrador global.
2. Na home page do Microsoft 365, clique em **segurança e conformidade**.
3. Na nova guia Segurança e Conformidade, clique em **Permissões** > **Gerenciador de Descoberta Eletrônica**.
4. Clique em **Editar** para o Gerenciador de Descoberta Eletrônica e clique em **Escolher o Gerenciador de Descoberta Eletrônica**.
5. Clique em **+ Adicionar**, procure o nome da sua conta do administrador global e adicione sua conta de administrador global como um Gerente de Descoberta Eletrônica.
6. Clique em **Concluir** > **Salvar** > **Fechar**.
  
## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a>Fase 2: Adicionar as informações de identificação pessoal ao seu locatário

Nesta fase, crie um documento com PII para um conjunto de exemplo de números de contas bancárias internacionais (IBANs) e armazene-o em um site do SharePoint Online no ambiente de desenvolvimento/teste do Microsoft 365.

1. Abra o Microsoft Word no computador.
2. Cole a tabela a seguir no arquivo do Word e salve-a como ‘IBANs.docx’ no computador local.
    
    Número  |País  |Código |IBAN  |
    |---------|---------|---------|---------|
    |1     |  SEPA Áustria      | AT            |AT611904300234573201       |
    |2     |  SEPA Bulgária       |BG    |BG80BNBG96611020345678      |
    |3     |  SEPA Dinamarca      |   DK      |DK5000400440116243      |
    |4     |  SEPA Finlândia      |   FI      |FI2112345600000785         |
    |5     |  SEPA França       |   FR      |FR1420041010050500013M02606         |
    |6     |  SEPA Alemanha      |   DE      |DE89370400440532013000         |
    |7     |  SEPA Grécia       |   GA      |GR1601101250000000012300695         |
    |8     |  SEPA Itália       |    IT     |GR1601101250000000012300695         |
    |9     |  SEPA Países Baixos      |   NL      |    NL91ABNA0417164300     |
    |10     | SEPA Polônia       |  PL       | PL27114020040000300201355387        |

Observação:- este conjunto de dados de amostra é derivado de informações publicamente disponíveis e destina-se a ser usado somente para fins de teste.

3. Em uma nova guia do navegador, digite: **https://**\<NomeDoLocatário\>**.sharepoint.com**
4. Clique em **documentos** para abrir a biblioteca de documentos para esse site. Se você for solicitado a realizar um novo tour de experiência de lista, clique em **avançar** até terminar.
5.  Clique em **Carregar** > **Arquivos** e selecione o IBANs.docx criado na etapa 2.

  
## <a name="phase-3-demonstrate-data-discovery"></a>Fase 3: Demonstrar a descoberta de dados

Nesta fase, você demonstra a pesquisa para localizar o documento criado e armazenado na Fase 2, com base em seu conteúdo com IBANs.

1. Na guia Segurança e Conformidade, clique em **Página Inicial**, em seguida, clique em **Pesquisa e Investigação** > **Pesquisa de Conteúdo**.
2. Crie um novo item de pesquisa clicando em **+**.
3. Em uma nova janela, forneça as informações a seguir:  
    a. Nome: pesquisa de IBAN  
    b. Onde deseja que seja feita a pesquisa?: **Escolha sites específicos para procurar** (clique em **+**) e insira a URL do site: **https://**\<NomeDoLocatário\>**.sharepoint.com/**  
    c. Clique em **Adicionar**, em seguida, clique em **OK**. Se vir um aviso, clique em **OK**.  
    d. Clique em **Avançar** em uma janela **Nova pesquisa**.  
    e. Para **O que você deseja que procuremos?**: **SensitiveType: "Número internacional de conta bancária (IBAN)"**, em seguida, clique em **Pesquisar**.

4. Você deverá ver pelo menos um item listado nos resultados da **Pesquisa de IBAN**.


## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a>Fase 4: Criar um tipo de informação confidencial personalizado via PowerShell

Nesta fase, você pode criar um tipo personalizado de informações confidenciais para a fictícia Contoso Corporation usando o Microsoft PowerShell. A Contoso usa um número de clientes (CCN) para identificar cada cliente em seu banco de dados. Um CCN tem a seguinte estrutura:
- Dois dígitos para representar o ano em que o registro foi criado.
    - A Contoso foi fundada em 2002; portanto, o menor valor possível seria 02. 
- Três dígitos para representar o órgão responsável pela criação do registro.
    - O intervalo de valores possível do órgão vai de 000 a 999. 
- Um caractere alfabético para representar a linha de negócios.
    - Os valores possíveis são a-z e devem diferenciar maiúsculas de minúsculas.
- Um número de série de quatro dígitos. 
    - O intervalo de valores possível de um número de série que vai de 0000 a 9999.   

A Contoso sempre se refere aos clientes usando um CCN nas correspondências interna e externa, em documentos e outras formas. A Contoso precisa de um tipo de item confidencial personalizado para detectar o uso do CCN em conteúdo do Microsoft 365 e assim aplicar proteção no uso desse formulário de informações de identificação pessoal.

1. Siga as instruções em [Conectar-se ao PowerShell do Centro de Conformidade e Segurança usando a autenticação multifator](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) e conecte-se ao Centro de Conformidade e Segurança com o UPN da sua conta de administrador global.
2. Execute os seguintes comandos do PowerShell.

     ```
    #Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName
    ```
3. Execute os seguintes comandos do PowerShell e copie os GUIDs gerados para uma instância aberta do Bloco de Notas no computador na ordem em que estão listados.
    ```
    #Generate three unique GUIDs
    Write-Host "GUID1 = "([guid]::NewGuid().Guid)
    Write-Host "GUID2 = "([guid]::NewGuid().Guid)
    Write-Host "GUID3 = "([guid]::NewGuid().Guid)
    ```
4. No computador local, abra outra instância do Bloco de Notas e cole o seguinte conteúdo:

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"> 
    <RulePack id="GUID1">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="GUID2" />
    <Details defaultLangCode="en"> 
    <LocalizedDetails langcode="en"> 
    <PublisherName>Contoso Ltd.</PublisherName> 
    <Name>Contoso Rule Package</Name> 
    <Description>Defines Contoso's custom set of classification rules</Description>
    </LocalizedDetails>
    </Details>
    </RulePack>
    <Rules>
    <!-- Contoso Customer Number (CCN) -->
    <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
    <IdMatch idRef="Regex_contoso_ccn" />
    <Match idRef="Keyword_contoso_ccn" />
    <Match idRef="Regex_eu_date" />
    </Pattern>
    </Entity>
    <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
    <Keyword id="Keyword_contoso_ccn">
    <Group matchStyle="word">
    <Term caseSensitive="false">customer number</Term>
    <Term caseSensitive="false">customer no</Term>
    <Term caseSensitive="false">customer #</Term>
    <Term caseSensitive="false">customer#</Term>
    <Term caseSensitive="false">Contoso customer</Term>
    </Group>
    </Keyword>
    <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
    <LocalizedStrings>
    <Resource idRef="GUID3">
    <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
    <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
    </Resource>
    </LocalizedStrings>
    </Rules>
    </RulePackage>
    ```
5. Substitua os valores de GUID1, GUID2 e GUID3 no texto XML da etapa 4 pelos valores da etapa 3 e salve o conteúdo no computador local com o nome ContosoCCN.xml.
6. Preencha o caminho para o arquivo ContosoCCN.xml e execute os comandos a seguir.
    ```
    #Create new Sensitive Information Type
    $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
    ```
7. Na guia Segurança e Conformidade, clique em **Classificações** > **Tipos de informação confidencial**. Você verá o número de clientes da Contoso (CCN) na lista.

## <a name="phase-5-demonstrate-data-protection"></a>Fase 5: Demonstrar a proteção de dados

A proteção de informações pessoais no Microsoft 365 inclui o uso de recursos de prevenção contra perda de dados (DLP).  Com as políticas de DLP, é possível proteger automaticamente informações confidenciais no Microsoft 365.

Há várias maneiras de aplicar a proteção. Instruindo e aumentar a conscientização sobre onde os dados de residentes da UE estão armazenados em seu ambiente e como os seus funcionários têm permissão para gerenciá-los representa um nível de proteção de informações usando a DLP do Office 365.

Nesta fase, você cria uma nova política DLP e demonstra como ela é aplicada a arquivos IBANs.docx armazenados no SharePoint Online na fase 2 e quando você tenta enviar um email com IBANs.

1. Na guia Segurança e Conformidade do navegador, clique em **Página Inicial**.
2. Clique em **Prevenção contra perda de dados** > **Política**.
3. Clique em **+ Criar uma política**.
4. Em **Iniciar com um modelo ou criar uma política personalizada**, clique em **Personalizado** > **Política personalizada** > **Avançar**.
5. Em **Nomear sua política**, forneça os seguintes detalhes e clique em **Avançar**: a. Nome: **Política de PII de cidadão da UE** b Descrição: **Proteger as informações de identificação pessoal de cidadãos europeus**
6. Em **escolher locais**, selecione **todos os locais no Microsoft 365**. Isso inclui conteúdo no email do Exchange e documentos do OneDrive e do SharePoint. E, em seguida, clique em **avançar**.
7. Em **Personalizar o tipo de conteúdo que deseja proteger**, clique em **Encontrar conteúdo que contém:** e clique em **Editar**.
8. Em **Escolher os tipos de conteúdo para proteger**, clique em **Adicionar** > **Tipos de informações confidenciais**.
9. Em **Tipos de informações confidenciais**, clique em **+ Adicionar**.
10. Em **Tipos de informações confidenciais**, pesquise **IBAN**, marque a caixa de seleção **Número internacional de conta bancária (IBAN)** e, em seguida, clique em **Adicionar**.
11. Confirme se o tipo de informações confidenciais do **Número internacional de conta bancária (IBAN)** foi adicionado e clique em **Concluído**.
12. Em **O conteúdo contém**, confirme que os tipos de informação confidencial foram adicionados e clique em **Salvar**.
13. Em **Personalize o tipo de conteúdo que deseja proteger**, confirme **Localizar conteúdo com:** o **Número internacional de conta bancária (IBAN)** e, em seguida, clique em **Avançar**.
14. Em **Detectar quando o conteúdo que está sendo compartilhado contém:**, altere o valor de **10** para **1** e clique em **Avançar**.
15. Em **Deseja ativar a política ou testar primeiro?**, escolha as configurações a seguir e clique em **Avançar**.  
    a. Escolha a opção para **Gostaria de testá-lo primeiro**  
    b. Marque a caixa de seleção **Mostrar dicas de política em modo teste** 
16. Em **Analisar as configurações**, clique em **Criar** depois de analisar as configurações. Observação: depois de criar uma nova política DLP, pode levar algum tempo para ela entrar em vigor.
17. No computador local, abra uma instância privada do navegador.
18. Na barra de endereços, digite **https://**\<NomeDoLocatário\>**.sharepoint.com** e entre usando sua conta de administrador global.
19. Clique em **Documentos**.
20. Clique no arquivo chamado "IBANs.docx". Você verá "Dica de política para IBANs.docx". O arquivo IBANs.docx foi compartilhado com destinatários externos, o que viola a política DLP. 
21. Na barra de endereços, digite: `https://outlook.office365.com`
22. Clique em **Novo** - **Email** e forneça o seguinte:  
    - **Para:** \<um endereço de email pessoal\>  
    - **Assunto:** Teste de RGPD  
    - **Corpo:** Cópia na tabela de valores mostrados abaixo.
  
        |Número  |País  |Código |IBAN  |
        |---------|---------|---------|---------|
        |1     |  SEPA Áustria      | AT            |AT611904300234573201       |
        |2     |  SEPA Bulgária       |BG    |BG80BNBG96611020345678      |
        |3     |  SEPA Dinamarca      |   DK      |DK5000400440116243      |
        |4     |  SEPA Finlândia      |   FI      |FI2112345600000785         |
        |5     |  SEPA França       |   FR      |FR1420041010050500013M02606         |
        |6     |  SEPA Alemanha      |   DE      |DE89370400440532013000         |
        |7     |  SEPA Grécia       |   GA      |GR1601101250000000012300695         |
        |8     |  SEPA Itália       |    IT     |GR1601101250000000012300695         |
        |9     |  SEPA Países Baixos      |   NL      |   NL91ABNA0417164300      |
        |10     | SEPA Polônia       |  PL       | PL27114020040000300201355387        |

Observação:- este conjunto de dados de amostra é derivado de informações publicamente disponíveis e destina-se a ser usado somente para fins de teste.

23. Você verá que a política DLP reconheceu que o corpo do email contém IBANs e informa a dica de política na parte superior da janela da mensagem.
24. Feche a instância privada do navegador.


## <a name="phase-6-demonstrate-reporting"></a>Etapa 6: Demonstrar relatórios
 
Nesta fase, você demonstra relatórios do Microsoft 365 com base na política DLP configurada na fase 5.

   1. Na guia Segurança e Conformidade do navegador, clique em **Página Inicial**.
   2. Clique em **Relatórios** > **Painel** > **Correspondências de políticas DLP**.
   3. Sua política DLP ajuda a identificar e proteger informações confidenciais da organização. Por exemplo, no relatório, você verá que a política identificou o documento que contém IBANs armazenados no SharePoint Online.
  
## <a name="see-also"></a>Confira também

[Proteção de informações do Office 365 para o RGPD](office-365-information-protection-for-gdpr.md)

[RGPD do Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/gdpr?toc=/microsoft-365/enterprise/toc.json)
