---
title: Como o Exchange Online protege seus segredos de email
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Além da central de confiabilidade do Office 365, que fornece informações de segurança, privacidade e conformidade do Office 365, você pode querer saber como o Office 365 ajuda a proteger os segredos que você fornece em seus datacenters. Usamos uma tecnologia chamada DKM (Distributed Key Manager).
ms.openlocfilehash: 8350785968c68b22c58be17ec68d94ff908c95d9
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37072646"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="208b9-104">Como o Exchange Online protege seus segredos de email</span><span class="sxs-lookup"><span data-stu-id="208b9-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="208b9-105">Este artigo descreve como a Microsoft protege seus segredos de email em seus datacenters.</span><span class="sxs-lookup"><span data-stu-id="208b9-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="208b9-106">Como protegemos as informações secretas fornecidas por você?</span><span class="sxs-lookup"><span data-stu-id="208b9-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="208b9-107">Além da central de confiabilidade do Office 365, que fornece [informações de segurança, privacidade e conformidade do office 365](https://go.microsoft.com/fwlink/?linkid=874644), você pode querer saber como o Office 365 ajuda a proteger os segredos que você fornece em seus datacenters.</span><span class="sxs-lookup"><span data-stu-id="208b9-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Office 365 helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="208b9-108">Usamos uma tecnologia chamada DKM (Distributed Key Manager).</span><span class="sxs-lookup"><span data-stu-id="208b9-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="208b9-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) é uma funcionalidade do lado do cliente que usa um conjunto de chaves secretas para criptografar e descriptografar informações.</span><span class="sxs-lookup"><span data-stu-id="208b9-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="208b9-110">Somente os membros de um grupo de segurança específico nos Serviços de Domínio Active Directory podem acessar essas chaves para descriptografar os dados criptografados pelo DKM.</span><span class="sxs-lookup"><span data-stu-id="208b9-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="208b9-111">No Exchange Online, apenas certas contas de serviço, sob as quais os processos do Exchange são executados, fazem parte do grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="208b9-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="208b9-112">Como parte do procedimento operacional padrão no datacenter, nenhum humano recebe credenciais que fazem parte deste grupo de segurança e, portanto, nenhuma pessoa tem acesso às chaves que podem descriptografar esses segredos.</span><span class="sxs-lookup"><span data-stu-id="208b9-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="208b9-p104">Para fins de depuração, solução de problemas ou auditoria, um administrador de datacenter deve solicitar acesso elevado para obter credenciais temporárias que fazem parte do grupo de segurança. Esse processo requer vários níveis de aprovação legal. Se o acesso for concedido, toda as atividades são registradas e auditadas. Além disso, o acesso é concedido apenas por um tempo definido, expirando automaticamente após esse período.</span><span class="sxs-lookup"><span data-stu-id="208b9-p104">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group. This process requires multiple levels of legal approval. If access is granted, all activity is logged and audited. In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="208b9-117">Para maior proteção, a tecnologia do DKM inclui a sobreposição de chave e o arquivamento automatizados.</span><span class="sxs-lookup"><span data-stu-id="208b9-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="208b9-118">Isso também garante que você pode continuar acessando seu conteúdo antigo sem depender da mesma chave indefinidamente.</span><span class="sxs-lookup"><span data-stu-id="208b9-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="208b9-119">Em que circunstâncias o Exchange Online usa o DKM?</span><span class="sxs-lookup"><span data-stu-id="208b9-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="208b9-120">A Microsoft usa o [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) para criptografar seus segredos nos datacenters do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="208b9-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="208b9-121">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="208b9-121">For example:</span></span>
  
- <span data-ttu-id="208b9-122">Credenciais da conta de email para contas conectadas.</span><span class="sxs-lookup"><span data-stu-id="208b9-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="208b9-123">As contas conectadas são contas de terceiros, como hotmail, Gmail e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="208b9-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="208b9-124">contas de email.</span><span class="sxs-lookup"><span data-stu-id="208b9-124">mail accounts.</span></span>
    
- <span data-ttu-id="208b9-125">Chave do cliente.</span><span class="sxs-lookup"><span data-stu-id="208b9-125">Customer key.</span></span> <span data-ttu-id="208b9-126">Se você estiver usando a [chave do cliente no Office 365](controlling-your-data-using-customer-key.md), você usará o [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) para proteger seus segredos.</span><span class="sxs-lookup"><span data-stu-id="208b9-126">If you are using [Customer Key in Office 365](controlling-your-data-using-customer-key.md), you'll use [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="208b9-127">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="208b9-127">Related topics</span></span>

[<span data-ttu-id="208b9-128">Criptografia no Office 365</span><span class="sxs-lookup"><span data-stu-id="208b9-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="208b9-129">Detalhes de referências técnicas sobre a criptografia no Office 365</span><span class="sxs-lookup"><span data-stu-id="208b9-129">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="208b9-130">Garantia de serviço no centro de conformidade &amp; de segurança do Office 365</span><span class="sxs-lookup"><span data-stu-id="208b9-130">Service assurance in the Office 365 Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

