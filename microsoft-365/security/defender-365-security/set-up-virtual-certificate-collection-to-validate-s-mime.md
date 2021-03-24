---
title: Configurar coleção de certificados virtuais - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Os administradores podem aprender a criar uma coleção de certificados virtuais que será usada para validar certificados S/MIME no Exchange Online.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2a5dad897ce58b8496551535cc28e03c7a1fa964
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053463"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Configurar o conjunto de certificados virtuais no Exchange Online para validar o S/MIME

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Como administrador, você precisará configurar um conjunto de certificados virtuais no Exchange Online que será usado para validar certificados S/MIME. Essa coleção de certificados virtuais é configurada como um armazenamento de certificados com uma extensão de nome de arquivo SST. O arquivo SST contém todos os certificados raiz e intermediários usados na validação de um certificado S/MIME.

## <a name="create-and-save-an-sst"></a>Criar e salvar um SST

Você pode criar esse arquivo de armazenamento de certificados SST exportando os certificados de um computador confiável usando o cmdlet **Export-Certificate** no Windows PowerShell e especificando o valor _Type_ como SST. Para obter instruções, consulte [Export-Certificate](/powershell/module/pkiclient/export-certificate).

Depois de ter o arquivo de armazenamento de certificados SST, use a seguinte sintaxe no PowerShell do Exchange Online para salvar o conteúdo do arquivo SST no armazenamento de certificados virtuais do Exchange Online. Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

Este exemplo importa o arquivo SST C:\My Documents\Exported Certificate Store.sst.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Garantir que um certificado seja válido

No Exchange Online, somente o SST é usado para validação de certificado.

## <a name="more-information"></a>Informações adicionais

[S/MIME para assinatura e criptografia de mensagens](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](/powershell/module/exchange/get-smimeconfig)