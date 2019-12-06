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
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="7f69e-103">Configurar coleção de certificados virtuais no Exchange Online para validar S/MIME</span><span class="sxs-lookup"><span data-stu-id="7f69e-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="7f69e-104">Como administrador, você precisará configurar uma coleção de certificados virtuais no Exchange Online que será usada para validar certificados S/MIME.</span><span class="sxs-lookup"><span data-stu-id="7f69e-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="7f69e-105">Essa coleção de certificados virtuais é configurada como um repositório de certificados com uma extensão de nome de arquivo SST.</span><span class="sxs-lookup"><span data-stu-id="7f69e-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="7f69e-106">O arquivo SST contém todos os certificados raiz e intermediários usados na validação de um certificado S/MIME.</span><span class="sxs-lookup"><span data-stu-id="7f69e-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="7f69e-107">Criar e salvar um SST</span><span class="sxs-lookup"><span data-stu-id="7f69e-107">Create and save an SST</span></span>

<span data-ttu-id="7f69e-108">Você pode criar esse arquivo de repositório de certificados SST exportando os certificados de uma máquina confiável usando o cmdlet **Export-Certificate** no Windows PowerShell e especificando o valor _Type_ como SST.</span><span class="sxs-lookup"><span data-stu-id="7f69e-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="7f69e-109">Para obter instruções, consulte [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span><span class="sxs-lookup"><span data-stu-id="7f69e-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="7f69e-110">Depois de ter o arquivo de repositório de certificados SST, use a sintaxe a seguir no PowerShell do Exchange Online para salvar o conteúdo do arquivo SST no repositório de certificados virtual do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7f69e-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="7f69e-111">Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="7f69e-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="7f69e-112">Este exemplo importa o arquivo SST C:\Meus Documents\Exported Certificate Store. SST.</span><span class="sxs-lookup"><span data-stu-id="7f69e-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="7f69e-113">Para informações detalhadas de sintaxes e de parâmetros, consulte [set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span><span class="sxs-lookup"><span data-stu-id="7f69e-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="7f69e-114">Garantir que um certificado seja válido</span><span class="sxs-lookup"><span data-stu-id="7f69e-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="7f69e-115">No Exchange Online, somente o SST é usado para validação de certificado.</span><span class="sxs-lookup"><span data-stu-id="7f69e-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="7f69e-116">Mais informações</span><span class="sxs-lookup"><span data-stu-id="7f69e-116">More Information</span></span>

[<span data-ttu-id="7f69e-117">S/MIME para assinatura e criptografia de mensagens</span><span class="sxs-lookup"><span data-stu-id="7f69e-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="7f69e-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="7f69e-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig)
