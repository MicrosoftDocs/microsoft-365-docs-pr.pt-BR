---
title: Configurar coleção de certificados virtuais no Exchange Online para validar S/MIME
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Os administradores podem aprender a criar uma coleção de certificados virtuais que será usada para validar certificados S/MIME no Exchange Online.
ms.openlocfilehash: e19d6791ee2045771be23c6693a8a11943280483
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866563"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Configurar coleção de certificados virtuais no Exchange Online para validar S/MIME

Como administrador, você precisará configurar uma coleção de certificados virtuais no Exchange Online que será usada para validar certificados S/MIME. Essa coleção de certificados virtuais é configurada como um repositório de certificados com uma extensão de nome de arquivo SST. O arquivo SST contém todos os certificados raiz e intermediários usados na validação de um certificado S/MIME.

## <a name="create-and-save-an-sst"></a>Criar e salvar um SST

Você pode criar esse arquivo de repositório de certificados SST exportando os certificados de uma máquina confiável usando o cmdlet **Export-Certificate** no Windows PowerShell e especificando o valor _Type_ como SST. Para obter instruções, consulte [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).

Depois de ter o arquivo de repositório de certificados SST, use a sintaxe a seguir no PowerShell do Exchange Online para salvar o conteúdo do arquivo SST no repositório de certificados virtual do Exchange Online. Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

Este exemplo importa o arquivo SST C:\Meus Documents\Exported Certificate Store. SST.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Garantir que um certificado seja válido

No Exchange Online, somente o SST é usado para validação de certificado.

## <a name="more-information"></a>Mais informações

[S/MIME para assinatura e criptografia de mensagens](s-mime-for-message-signing-and-encryption.md)

[Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig)
