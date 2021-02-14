---
title: Impressão Digital de Documento
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: Os funcionários de TI em sua organização lidam com vários tipos de informações confidenciais em um dia comum. A Impressão Digital de Documento facilita a proteção dessas informações identificando formas padrão usadas em sua organização. Este tópico descreve os conceitos por trás da Impressão Digital de Documento e como criar um usando o PowerShell.
ms.openlocfilehash: 0c1fb86e4176c042a6ed772b2a18fc14ca81efcd
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547137"
---
# <a name="document-fingerprinting"></a>Impressão Digital de Documento

Os funcionários de TI em sua organização lidam com vários tipos de informações confidenciais em um dia comum. No Centro de Conformidade de Segurança, a Impressão Digital de Documento facilita a proteção das informações identificando formulários padrão usados em &amp; toda a organização. Este tópico descreve os conceitos por trás da Impressão Digital de Documento e como criar um usando o PowerShell.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Cenário básico da Impressão Digital de Documento

A Impressão Digital de Documento é um recurso de Prevenção contra Perda de Dados (DLP) que converte um formulário padrão em um tipo de informação confidenciais, que você pode usar nas regras de suas políticas de DLP. Por exemplo, você pode criar uma impressão digital de documento com base em um modelo de patente em branco e, então, criar uma política DLP que detecta e bloqueia todos os modelos de patente de saída com conteúdo confidencial. Opcionalmente, você pode [](use-notifications-and-policy-tips.md) configurar dicas de política para notificar os remetentes de que eles podem estar enviando informações confidenciais, e o remetente deve verificar se os destinatários estão qualificados para receber as patentes. Esse processo funciona com qualquer formulário baseado em texto usado em sua organização. Exemplos adicionais de formulários que você pode carregar incluem:
  
- Formulários governamentais
- Formulários compatíveis com a Lei americana HIPAA (Health Insurance Portability Accountability Act, Lei de responsabilidade sobre portabilidade de seguro saúde)  
- Formulários de informação sobre funcionários para departamentos de Recursos Humanos
- Formulários personalizados criados especificamente para sua organização

Idealmente, sua organização já tem uma prática comercial estabelecida sobre o uso de determinados formulários para transmitir informações confidenciais. Depois de carregar um formulário vazio a ser convertido em uma impressão digital de documento e configurar uma política correspondente, a DLP detectará todos os documentos no email de saída que correspondam a essa impressão digital.

## <a name="how-document-fingerprinting-works"></a>Funcionamento da Impressão Digital de Documento

Provavelmente você já sabe que os documentos não têm impressões digitais reais, mas o nome ajuda a explicar o recurso. Da mesma maneira que as impressões digitais de uma pessoa têm padrões exclusivos, os documentos têm padrões de palavra exclusivos. Quando você carrega um arquivo, a DLP identifica o padrão de palavra exclusivo no documento, cria uma impressão digital de documento com base nesse padrão e usa essa impressão digital de documento para detectar documentos de saída contendo o mesmo padrão. É por isso que o carregamento de um formulário ou de um modelo cria o tipo mais eficaz de impressão digital de documento. Todos que preenchem um formulário usam o mesmo conjunto de palavras do original e, então, adicionam suas próprias palavras ao documento. Desde que o documento de saída não seja protegido por senha e contenha todo o texto do formulário original, a DLP poderá determinar se o documento corresponde à impressão digital de documento.

> [!IMPORTANT]
> Por enquanto, a DLP pode usar a impressão digital de documento como um método de detecção somente no Exchange Online.

O exemplo a seguir mostra o que acontecerá se você criar uma impressão digital de documento com base em um modelo de patente, mas você pode usar qualquer formulário como base para a criação de uma impressão digital de documento.
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a>Exemplo de um documento de patente correspondente a uma impressão digital de documento de um modelo de patente

![Document-Fingerprinting-diagram.png](../media/Document-Fingerprinting-diagram.png)
  
O modelo de patente contém os campos em branco "Título de patente", "Inventários" e "Descrição" e descrições para cada um desses campos — esse é o padrão da palavra. Quando você carrega o modelo de patente original, ele está em um dos tipos de arquivo com suporte e em texto sem formato. A DLP converte esse padrão de palavra em uma impressão digital de documento, que é um pequeno arquivo XML Unicode que contém um valor de hash exclusivo que representa o texto original, e a impressão digital é salva como uma classificação de dados no Active Directory. (Como medida de segurança, o próprio documento original não é armazenado no serviço; somente o valor de hash é armazenado e o documento original não pode ser reconstruído do valor de hash.) A impressão digital de patente se torna um tipo de informação confidenciais que você pode associar a uma política de DLP. Depois de associar a impressão digital a uma política de DLP, a DLP detecta todos os emails de saída que contêm documentos que corresponderem à impressão digital de patente e lida com eles de acordo com a política da sua organização. 

Por exemplo, talvez você queira configurar uma política de DLP que impeça que funcionários regulares enviem mensagens de saída contendo patentes. A DLP usará a impressão digital de patente para detectar patentes e bloquear esses emails. Como alternativa, talvez você queira permitir que seu departamento jurídico seja capaz de enviar patentes para outras organizações porque ele tem uma necessidade comercial de fazer isso. Você pode permitir que departamentos específicos enviem informações confidenciais criando exceções para esses departamentos em sua política de DLP ou pode permitir que eles substituam uma dica de política por uma justificativa comercial.
  
### <a name="supported-file-types"></a>Tipos de arquivo compatíveis

A Impressão Digital de Documento dá suporte aos mesmos tipos de arquivo com suporte em regras de fluxo de emails (também conhecidas como regras de transporte). Para uma lista de tipos de arquivo com suporte, consulte Tipos de arquivo com suporte para inspeção de conteúdo de regra de fluxo [de email.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection) Uma observação rápida sobre tipos de arquivo: nem as regras de fluxo de emails nem a Impressão Digital de Documento são compatíveis com o tipo de arquivo .dotx, o que pode ser confuso porque é um arquivo de modelo no Word. Quando você vir a palavra "modelo" neste e em outros tópicos sobre Impressão Digital de Documento, ela se referirá a um documento já estabelecido como um formulário padrão, e não ao tipo de arquivo de modelo.
  
#### <a name="limitations-of-document-fingerprinting"></a>Limitações da impressão digital de documento

A Impressão Digital de Documento não detectará informações confidenciais nos seguintes casos:
  
- Arquivos protegidos por senha
- Arquivos que contenham somente imagens
- Documentos que não contenham todo o texto do formulário original usado para criar a impressão digital de documento

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Usar o PowerShell para criar um pacote de regras de classificação com base na impressão digital de documento

Observe que você só pode criar uma impressão digital de documento usando o PowerShell no Centro de Conformidade &amp; de Segurança. Para se conectar, [confira Conectar-se ao PowerShell do Centro](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)& Segurança e Conformidade.

A DLP usa pacotes de regras de classificação para detectar conteúdo sensível. Para criar um pacote de regras de classificação com base em uma impressão digital de documento, use os cmdlets **New-DlpFingerprint** e **New-DlpSensitiveInformationType.** Como os resultados de **New-DlpFingerprint** não são armazenados fora da regra de classificação de dados, você sempre **executará New-DlpFingerprint** e **New-DlpSensitiveInformationType** ou **Set-DlpSensitiveInformationType** na mesma sessão do PowerShell. Este exemplo cria uma nova impressão digital de documento baseada no arquivo CC:\My Documents\Contoso Employee Template.docx. Armazene a nova impressão digital como uma variável para poder usá-la com o cmdlet **New-DlpSensitiveInformationType** na mesma sessão do PowerShell.
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

Este exemplo cria uma nova regra de classificação de dados chamada "Contoso Employee Confidential" que usa as impressões digitais de documento do arquivo C:\My Documents\Contoso Customer Information Form.docx.
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

Agora você pode usar o cmdlet **Get-DlpSensitiveInformationType** para encontrar todos os pacotes de regras de classificação de dados de DLP e, neste exemplo, "Contoso Customer Confidential" faz parte da lista de pacotes de regras de classificação de dados. 
  
Por fim, adicione o pacote de regras de classificação de dados "Contoso Customer Confidential" a uma política de DLP no Centro de Conformidade &amp; de Segurança. Este exemplo adiciona uma regra a uma política de DLP existente chamada "ConfidentialPolicy".

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

Você também pode usar o pacote de regras de classificação de dados em regras de fluxo de emails no Exchange Online, conforme mostrado no exemplo a seguir. Para executar esse comando, primeiro você precisa [se conectar ao PowerShell do Exchange Online.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) Observe também que leva tempo para que o pacote de regras seja sincronizado do Centro de Conformidade &amp; de Segurança para o Centro de administração do Exchange.
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

A DLP agora detecta documentos que corresponderem à impressão digital Form.docx de documento da Contoso.
  
Para obter informações sobre sintaxe e parâmetros, consulte:

- [New-DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/Get-DlpSensitiveInformationType)
