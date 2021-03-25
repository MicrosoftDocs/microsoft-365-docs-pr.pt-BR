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
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203379"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="b807d-103">Configurar o conjunto de certificados virtuais no Exchange Online para validar o S/MIME</span><span class="sxs-lookup"><span data-stu-id="b807d-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b807d-104">Como administrador, você precisará configurar um conjunto de certificados virtuais no Exchange Online que será usado para validar certificados S/MIME.</span><span class="sxs-lookup"><span data-stu-id="b807d-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="b807d-105">Essa coleção de certificados virtuais é configurada como um armazenamento de certificados com uma extensão de nome de arquivo SST.</span><span class="sxs-lookup"><span data-stu-id="b807d-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="b807d-106">O arquivo SST contém todos os certificados raiz e intermediários usados na validação de um certificado S/MIME.</span><span class="sxs-lookup"><span data-stu-id="b807d-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="b807d-107">Criar e salvar um SST</span><span class="sxs-lookup"><span data-stu-id="b807d-107">Create and save an SST</span></span>

<span data-ttu-id="b807d-108">Você pode criar esse arquivo de armazenamento de certificados SST exportando os certificados de um computador confiável usando o cmdlet **Export-Certificate** no Windows PowerShell e especificando o valor _Type_ como SST.</span><span class="sxs-lookup"><span data-stu-id="b807d-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="b807d-109">Para obter instruções, consulte [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="b807d-109">For instructions, see [Export-Certificate](/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="b807d-110">Depois de ter o arquivo de armazenamento de certificados SST, use a seguinte sintaxe no PowerShell do Exchange Online para salvar o conteúdo do arquivo SST no armazenamento de certificados virtuais do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b807d-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="b807d-111">Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b807d-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="b807d-112">Este exemplo importa o arquivo SST C:\My Documents\Exported Certificate Store.sst.</span><span class="sxs-lookup"><span data-stu-id="b807d-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="b807d-113">Para obter informações detalhadas sobre sintaxes e parâmetros, consulte [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="b807d-113">For detailed syntax and parameter information, see [Set-SmimeConfig](/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="b807d-114">Garantir que um certificado seja válido</span><span class="sxs-lookup"><span data-stu-id="b807d-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="b807d-115">No Exchange Online, somente o SST é usado para validação de certificado.</span><span class="sxs-lookup"><span data-stu-id="b807d-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="b807d-116">Informações adicionais</span><span class="sxs-lookup"><span data-stu-id="b807d-116">More Information</span></span>

[<span data-ttu-id="b807d-117">S/MIME para assinatura e criptografia de mensagens</span><span class="sxs-lookup"><span data-stu-id="b807d-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="b807d-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="b807d-118">Get-SmimeConfig</span></span>](/powershell/module/exchange/get-smimeconfig)