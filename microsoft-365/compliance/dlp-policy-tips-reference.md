---
title: Referência de dicas de política de Prevenção contra Perda de Dados
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: Saiba como adicionar uma dica de política a uma política de prevenção contra perda de dados (DLP) notificar um usuário de que está trabalhando com conteúdo que conflita com uma política de DLP.
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 36e4d4f96146b51e0b31731c9e93222eed767045
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903797"
---
# <a name="data-loss-prevention-policy-tips-reference"></a>Referência de dicas de política de Prevenção contra Perda de Dados

As dicas de política de DLP no Outlook Web Access têm suporte para todas as condições, exceções e ações aplicáveis à carga de trabalho do Exchange em uma política de DLP, exceto o seguinte:

**Condições:**

- Remetente é
- Domínio remetente é
- Recipient é membro do
- O header contém palavras ou frases
- O header corresponde aos padrões
- Tamanho do documento é igual ou maior do que
- Tipo de mensagem é
- A importância da mensagem é
- Conjunto de caracteres de conteúdo contém palavras
- Assunto ou corpo contém palavras ou frases
- Assunto ou corpo corresponde aos padrões
- Conjunto de caracteres de conteúdo contém palavras
- O conteúdo é recebido de
- O remetente substituiu a dica de política
- Tamanho da mensagem é igual ou maior do que
- Atributo AD do Remetente contém palavras ou frases
- Atributo Sender AD corresponde a padrões
- O conteúdo do documento contém palavras ou frases
- O conteúdo do documento corresponde aos padrões

**Ações:**

- Encaminhar a mensagem para aprovação ao gerente do remetente
- Encaminhar a mensagem para aprovação para aprovações específicas
- Redirecionar a mensagem para usuários específicos
- Adicionar destinatários à caixa Para
- Adicionar destinatários à Caixa Cc
- Adicionar destinatários à Caixa Cc
- Adicionar o gerente do remetente como destinatário
- Adicionar aviso de isenção de responsabilidade HTML
- Assunto de email de pré-envio
- Remover a criptografia de mensagens O365 e a proteção de direitos

## <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions"></a>O Outlook 2013 e posterior oferece suporte para mostrar dicas de política apenas para algumas condições e exceções

Atualmente, o Outlook 2013 e posterior oferece suporte para mostrar dicas de política para políticas que não contêm nenhuma condição ou exceção além das condições abaixo mencionadas e exceções correspondentes:

- O conteúdo contém (funciona apenas para tipos de informações confidenciais. Rótulos de sensibilidade não são suportados)
- O conteúdo é compartilhado

Observe que todas as condições funcionam para emails de autoria no aplicativo cliente do Outlook, onde eles corresponderão ao conteúdo e imporão ações de proteção ao conteúdo. No entanto, não há suporte para mostrar dicas de política aos usuários para quaisquer condições que sejam usadas além das mencionadas acima.

## <a name="outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types"></a>Outlook 2013 e posterior e suporte a aplicativos do Office na Área de Trabalho mostrando dicas de política para apenas alguns tipos de informações confidenciais

A lista de tipos de informações confidenciais que serão detectados para mostrar dicas de política de DLP no Outlook na Área de Trabalho (2013 e posterior) e aplicativos do Office (Word, Excel, PowerPoint) na Área de Trabalho são as seguintes:

- Número de roteamento ABA
- Número de Identidade Nacional (DNI) da Argentina
- Número de conta de banco da Austrália
- Número de conta médica da Austrália
- Número de passaporte da Austrália
- Número de imposto de renda da Austrália
- Chave Auth do Azure DocumentDB  
- Cadeia de conexão de banco de dados iaas do Azure e cadeia de SQL conexão do Azure  
- Cadeia de conexão do Azure IoT  
- Senha de configuração de publicação do Azure  
- Cadeia de conexão de cache do Azure Redis  
- Azure SAS  
- Cadeia de conexão de barramento de serviço do Azure  
- Chave da conta de armazenamento do Azure  
- Chave de Conta de Armazenamento do Azure (Genérico)  
- Número nacional belga
- Número de CPF do Brasil
- Número de Pessoa Jurídica (CNPJ) do Brasil
- 	Cartão de Identidade Nacional (RG) do Brasil
- Número de conta bancária do Canadá
- Número de carteira de motorista do Canadá
- Número de serviço de saúde do Canadá
- Número de passaporte do Canadá
- Número de identificação pessoal de saúde do Canadá (PHIN)
- Número de seguro social do Canadá
- 	Número do Cartão de Identidade do Chile
- 	Número do Cartão de Identidade de Residentes (PRC) da China
- Número de Cartão de Crédito
- Número da carteira de identidade croata  
- Número de identificação pessoal (NIB) croata  
- Número da identidade pessoal tcheca  
- Número de identificação pessoal dinamarquês
- Número da Drug Enforcement Agency (DEA)
- Número de cartão de débito da UE
- Número da licença de motorista da UE  
- Número de Identificação Nacional da UE  
- Número do passaporte da UE  
- Número de Segurança Social da UE (SSN) ou ID Equivalente  
- Número de Identificação Fiscal da UE (TIN)  
- RG nacional finlandês
- Número de passaporte finlandês
- Número da carteira de motorista francesa
- Carteira nacional de identidade francesa (CNI)
- Número de passaporte francês
- Número da segurança social francesa (INSEE)
- Número de carteira de motorista da Alemanha
- Número de passaporte alemão
- Número da carteira de identidade alemã
- Carteira nacional de identidade grega  
- Número do Cartão de Identidade de Hong Kong (HKID)
- Número da Conta Permanente da Índia (PAN)
- Número de Identificação Exclusivo da Índia (Aadhaar)
- Número do Cartão de Identidade da Indonésia (KTP)
- Número internacional de conta bancária (IBAN)
- Classificação Internacional de Doença (ICD-10-CM)  
- Classificação Internacional de Doença (ICD-9-CM)  
- Endereço IP
- Número de serviço público pessoal (PPS) irlandês 
- Número de conta bancária de Israel
- ID nacional de Israel
- Número de carteira de motorista da Itália
- Número de conta bancária do Japão
- Número de carteira de motorista do Japão
- Número de passaporte do Japão
- Número de registro de residente do Japão
- Número de seguro social do Japão (SIN)
- Número do cartão de residência japonês
- Número do Cartão de Identidade da Malásia
- Número do Serviço do Cidadão (BSN) da Países Baixos  
- Número do Ministério da Saúde da Nova Zelândia
- Número de identidade norueguesa  
- Número de Identificação Multiuso Unificada das Filipinas
- Carteira de identidade polonesa
- RG nacional polonês (PESEL)
- Passaporte polonês
- Número do cartão do cidadão português
- ID nacional da Arábia Saudita
- Número do Cartão de Identidade do Registro Nacional (NRIC) de Cingapura
- Número de Identificação da África do Sul  
- Número do Registro de Residentes da Coreia do Sul
- Número da segurança social espanhola (SSN)
- SQL Server de conexão  
- RG nacional sueco
- Número de passaporte sueco
- Código SWIFT
- ID nacional de Taiwan
- 	Número de passaporte de Taiwan
- Certificado de Residente de Taiwan (ARC/TARC)
- Código de Identificação da População Tailandesa
- Número de Identificação Nacional Turco
- Número de carteira de motorista do Reino Unido
- Número do título de eleitor britânico
- Número do serviço nacional de saúde britânico
- Número do seguro nacional britânico (NINO)
- EUA / Reino Unido. Passport Number
- Número de conta bancária dos EUA
- Número de carteira de motorista dos EUA
- Número de identificação de contribuinte individual (ITIN) dos EUA
- Número de seguridade social dos EUA (SSN)

Observe que os tipos de informações confidenciais personalizados também são suportados para dicas de política de DLP, além dos tipos de informações confidenciais externas acima.

## <a name="data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types"></a>Prevenção contra Perda de Dados em dispositivos de ponto de extremidade oferece suporte a dicas de política apenas para alguns tipos de informações confidenciais

A lista de tipos de informações confidenciais que serão detectados em documentos que residem em dispositivos de ponto de extremidade são os seguintes:

- Número de roteamento ABA 
- Número de Identidade Nacional (DNI) da Argentina 
- Número de conta de banco da Austrália 
- Número de conta médica da Austrália 
- Número de passaporte da Austrália 
- Número de imposto de renda da Austrália 
- Número comercial australiano 
- Número da empresa australiana 
- Número da Carteira de Motorista da Áustria 
- Cartão de Identidade da Áustria 
- Número do Passaporte da Áustria 
- Número da Previdência Social da Áustria 
- Número de Identificação Fiscal da Áustria 
- Número do Imposto sobre o Valor Adicionado (IVA) da Áustria 
- Chave Auth do Azure DocumentDB 
- Cadeia de conexão de banco de dados iaas do Azure e cadeia de SQL conexão do Azure 
- Cadeia de conexão do Azure IoT 
- Senha de configuração de publicação do Azure 
- Cadeia de conexão de cache do Azure Redis 
- Azure SAS 
- Cadeia de conexão de barramento de serviço do Azure 
- Chave da conta de armazenamento do Azure 
- Chave de Conta de Armazenamento do Azure (Genérico) 
- Número da carteira de motorista belga 
- Número nacional belga 
- Número do Passaporte belga 
- Número de imposto adicionado ao valor belga 
- Número de CPF do Brasil 
- Número de Pessoa Jurídica (CNPJ) do Brasil 
- 	Cartão de Identidade Nacional (RG) do Brasil 
- Número da Licença de Motorista da Bulgária 
- Número do Passaporte da Bulgária 
- Número Civil Uniforme da Bulgária 
- Número de conta bancária do Canadá 
- Número de carteira de motorista do Canadá 
- Número de serviço de saúde do Canadá 
- Número de passaporte do Canadá 
- Número de identificação pessoal de saúde do Canadá (PHIN) 
- Número de seguro social do Canadá 
- 	Número do Cartão de Identidade do Chile 
- 	Número do Cartão de Identidade de Residentes (PRC) da China 
- Número de Cartão de Crédito 
- Número da Carteira de Motorista da Croácia 
- Número da carteira de identidade croata 
- Número do cartão de identificação nacional da Croácia 
- Número do Passaporte croata 
- Número de identificação pessoal (NIB) croata 
- CSCAN-AZURE0060 Azure Storage Account Shared Access Signature 
- Chave Simétrica Geral CSCAN-GENERAL0140 
- Número da Licença de Motorista de Chipre 
- Chipre Identity Card 
- Número do Passaporte chipre 
- Número de identificação fiscal de Chipre 
- Número da carteira de motorista tcheca 
- Número da identidade pessoal tcheca 
- Número do Passaporte da República Tcheca 
- Número da Carteira de Motorista da Dinamarca 
- Número do Passaporte da Dinamarca 
- Número de identificação pessoal dinamarquês 
- Número da Drug Enforcement Agency (DEA) 
- Número da Carteira de Motorista da Estônia 
- Número do Passaporte da Estônia 
- Código de Identificação Pessoal da Estônia 
- Número de cartão de débito da UE 
- Número da licença de motorista da UE 
- Número de Identificação Nacional da UE 
- Número do passaporte da UE 
- Número de Segurança Social da UE (SSN) ou ID Equivalente 
- Número de Identificação Fiscal da UE (TIN) 
- Número da Carteira de Motorista da Finlândia 
- Número do Seguro de Saúde da Finlândia 
- RG nacional finlandês 
- Número de passaporte finlandês 
- Número da carteira de motorista francesa 
- Número do Seguro de Saúde da França 
- Carteira nacional de identidade francesa (CNI) 
- Número de passaporte francês 
- Número da segurança social francesa (INSEE) 
- Número de Identificação Fiscal da França (NUMÉRO SPI.) 
- Número de imposto adicionado ao valor da França 
- Número de carteira de motorista da Alemanha 
- Número de passaporte alemão 
- Número da carteira de identidade alemã 
- Número de Identificação Fiscal da Alemanha 
- Número de imposto adicionado ao valor da Alemanha 
- Número da carteira de motorista da Grécia 
- Carteira nacional de identidade grega 
- Número do Passaporte Grécia 
- Número de Segurança Social da Grécia (AMKA) 
- Número de identificação de imposto grego 
- Número do Cartão de Identidade de Hong Kong (HKID) 
- Número de Seguro Social húngaro (TAD) 
- Número de imposto adicionado ao valor húngaro 
- Número da Licença de Motorista da Hungria 
- Número do Passaporte da Hungria 
- Número de Identificação Pessoal da Hungria 
- Número de identificação do Imposto da Hungria 
- Número da Conta Permanente da Índia (PAN) 
- Número de Identificação Exclusivo da Índia (Aadhaar) 
- Número do Cartão de Identidade da Indonésia (KTP) 
- Número internacional de conta bancária (IBAN) 
- Classificação Internacional de Doença (ICD-10-CM) 
- Classificação Internacional de Doença (ICD-9-CM) 
- Endereço IP 
- Número da Carteira de Motorista da Irlanda 
- Número do Passaporte da Irlanda 
- Número de serviço público pessoal (PPS) irlandês 
- Número de conta bancária de Israel 
- ID nacional de Israel 
- Número de carteira de motorista da Itália 
- Código Fiscal da Itália 
- Número do Passaporte da Itália 
- Número de imposto de valor adicionado da Itália 
- Número de conta bancária do Japão 
- Número de carteira de motorista do Japão 
- Número de passaporte do Japão 
- Número de registro de residente do Japão 
- Número de seguro social do Japão (SIN) 
- Japonês Meu Número Corporativo 
- Japonês Meu Número Pessoal 
- Número do cartão de residência japonês 
- Número da Carteira de Motorista da Letônia 
- Número do Passaporte da Letônia 
- Código Pessoal da Letônia 
- Número da Carteira de Motorista da Lituânia 
- Número do Passaporte lituano 
- Código Pessoal da Lituânia 
- Número da Carteira de Motorista de Luxemburgo 
- Número de Identificação Nacional de Luxemburgo (Pessoas naturais) 
- Número de Identificação Nacional de Luxemburgo (pessoas não naturais) 
- Número do Passaporte de Luxemburgo 
- Número do Cartão de Identidade da Malásia 
- Número da Licença de Motorista de Malta 
- Número do Cartão de Identidade de Malta 
- Número do Passaporte de Malta 
- Número da ID de Imposto de Malta 
- Número do Serviço do Cidadão (BSN) da Países Baixos 
- Número da carteira de motorista dos Países Baixos 
- Número do passaporte holandês 
- Número de identificação fiscal dos Países Baixos 
- Número de imposto adicionado ao valor holandês 
- Número da conta bancária da Nova Zelândia 
- Número da Licença de Driver da Nova Zelândia 
- Número da Receita do Interior da Nova Zelândia 
- Número do Ministério da Saúde da Nova Zelândia 
- Número de Assistência Social da Nova Zelândia 
- Número de identidade norueguesa 
- Número de Identificação Multiuso Unificada das Filipinas 
- Número da Carteira de Motorista da Polônia 
- Carteira de identidade polonesa 
- RG nacional polonês (PESEL) 
- Passaporte polonês 
- Número de identificação fiscal da Polônia 
- Número REGON polonês 
- Número do cartão do cidadão português 
- Número da Carteira de Motorista de Portugal 
- Número do Passaporte de Portugal 
- Número de Identificação Fiscal de Portugal 
- Número da Carteira de Motorista da Romênia 
- Número do Passaporte da Romênia 
- CNP (Código Numérico Pessoal da Romênia) 
- Número do Passaporte Russo (Doméstico) 
- Número de Passaporte Russo (Internacional) 
- ID nacional da Arábia Saudita 
- Número do Cartão de Identidade do Registro Nacional (NRIC) de Cingapura 
- Número da carteira de motorista da Eslováquia 
- Número do Passaporte da Eslováquia 
- Número pessoal da Eslováquia 
- Número da carteira de motorista da Eslovênia 
- Número do Passaporte da Eslovênia 
- Número de identificação fiscal da Eslovênia 
- Número de cidadão mestre exclusivo da Eslovênia 
- Número de Identificação da África do Sul 
- Número do Registro de Residentes da Coreia do Sul 
- DNI da Espanha 
- Número da Carteira de Motorista da Espanha 
- Número do Passaporte da Espanha 
- Número da segurança social espanhola (SSN) 
- Número de Identificação Fiscal da Espanha 
- SQL Server de conexão 
- Número da Carteira de Motorista da Suécia 
- RG nacional sueco 
- Número de passaporte sueco 
- Número de Identificação Fiscal da Suécia 
- Código SWIFT 
- Número da Previdência Social Suíça AHV 
- ID nacional de Taiwan 
- 	Número de passaporte de Taiwan 
- Certificado de Residente de Taiwan (ARC/TARC) 
- Código de Identificação da População Tailandesa 
- Número de Identificação Nacional Turco 
- Número de carteira de motorista do Reino Unido 
- Número do título de eleitor britânico 
- Número do serviço nacional de saúde britânico 
- Número do seguro nacional britânico (NINO) 
- Reino Unido Número de referência exclusivo do contribuinte 
- EUA / Reino Unido. Passport Number 
- Número de conta bancária dos EUA 
- Número de carteira de motorista dos EUA 
- Número de identificação de contribuinte individual (ITIN) dos EUA 
- Número de seguridade social dos EUA (SSN) 
- Número do Passaporte da Ucrânia (Doméstico) 
- Número do Passaporte da Ucrânia (Internacional) 
 
Observe que os tipos de informações confidenciais personalizados também serão detectados, além dos tipos de informações confidenciais de saída da caixa acima

## <a name="support-matrix-for-dlp-policy-tips-across-microsoft-apps"></a>Matriz de Suporte para dicas de política de DLP em aplicativos microsoft

|**Aplicativo e plataforma**|**Suporte à dica de política DLP**|**Tipos de informações confidenciais suportados**|**Predicados e ações com suporte**|**Comentário**|
|:--|:--|:--|:--|:--|
|**Outlook Web Access**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Todos|Subset|Consulte [Referência de dicas de política de prevenção contra](#data-loss-prevention-policy-tips-reference) perda de dados|
|**Outlook Win32 (Outlook 2013 e além)**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|Subset|Consulte [o Outlook 2013](#outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions-and-exceptions) e mais tarde oferece suporte para mostrar dicas de política para apenas algumas condições e exceções e [o Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) e posteriores e aplicativos do Office na Área de Trabalho mostrando dicas de política para apenas alguns tipos de informações confidenciais para obter detalhes sobre o suporte a tipos de informações confidenciais e condições de DLP e ações com suporte para mostrar dicas de política de DLP no Outlook Win32.|
|**Outlook Mobile (iOS, Android)/Outlook Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nenhum|Nenhum|Dicas de política de DLP não são suportadas no Outlook Mobile|
|**Cliente Web do Sharepoint Online/One Drive for Business**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Todos|Todos os predicados e ações do SPO/ODB em DLP||
|**Cliente Do Sharepoint Win32/ One Drive for Business Win32**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nenhum|Nenhum|As dicas de política de DLP não são suportadas em aplicativos cliente da área de trabalho do Sharepoint ou do OneDrive|
|**Word, Excel, PowerPoint Web Client**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Todos|Todos os predicados e ações do SPO/ODB em DLP|A dica de política de DLP é suportada se o documento estiver hospedado no aplicativo Web SPO ou ODB e a política DLP já estiver carimbada.|
|**Word, Excel, PowerPoint Mobile Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nenhum|Nenhum|As dicas de política de DLP não são suportadas em aplicativos móveis para Office.|
|**Teams Web/ Teams Desktop/ Teams Mobile/ Teams Mac**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Todos|Todos os predicados do Teams na política de DLP|As dicas de política mostrarão quando uma mensagem for sinalizada como "Esta mensagem foi sinalizada. O que posso fazer?" Ao clicar no link, o usuário pode revisar os tipos de informações confidenciais detectados e substituir ou relatar um problema, se permitido pelo administrador. Observe que nenhuma dica de política é mostrada para arquivos. Quando o destinatário tenta acessar o documento, ele pode ter acesso negado se não for permitido.|
|**Dispositivos de ponto de extremidade Win32**|:::image type="icon" source="../media/rightmrk.png" border="false":::|Subset|Todos os predicados de DLP de ponto de extremidade e ações na política de DLP|Consulte [Prevenção contra Perda de Dados no Ponto de](#data-loss-prevention-on-endpoint-devices-supports-policy-tips-for-only-some-sensitive-information-types) Extremidade oferece suporte a dicas de política apenas para alguns tipos de informações confidenciais|
|**Dispositivos Mac**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nenhum|Nenhum|Políticas de prevenção contra perda de dados não são impositivas em dispositivos Mac hoje|
|**Aplicativos de nuvem de terceiros**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nenhum|Nenhum|Dicas de política de prevenção contra perda de dados não são suportadas em aplicativos de nuvem de terceiros|
|**On-prem**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Nenhum|Nenhum||
|**Word, Excel, PowerPoint Win32 Client**|:::image type="icon" source="../media/crsmrk.png" border="false":::|Subset|Subset|Confira [Outlook 2013](#outlook-2013-and-later-and-office-apps-on-desktop-support-showing-policy-tips-for-only-some-sensitive-information-types) e posterior e suporte a aplicativos do Office na Área de Trabalho mostrando dicas de política para apenas alguns tipos de informações confidenciais para a lista de tipos de informações confidenciais com suporte</br></br>As dicas de política para aplicativos cliente WXP funcionarão para documentos armazenados em Sites do Sharepoint Online ou do One Drive for Business para todas as políticas de DLP que tenham exatamente o abaixo ou um subconjunto de condições ou ações na política DLP:</br> <ul><li>O conteúdo contém tipos de informações confidenciais</li><li>Escopo do Access (o conteúdo é compartilhado internamente/externamente)</li><li>Notificar o usuário (dicas de política/notificações do usuário)</li><li>Bloquear todos</li><li>Relatórios de incidentes</li></ul></br> Se qualquer outra condição ou ação estiver presente, a dica de política DLP para essa política não aparecerá nos aplicativos de área de trabalho do Word, Excel ou PowerPoint.</br>Confira [Dicas de política no Excel, PowerPoint e Word](use-notifications-and-policy-tips.md#policy-tips-in-excel-powerpoint-and-word) para obter mais detalhes|
||||||
