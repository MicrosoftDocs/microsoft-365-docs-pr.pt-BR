---
title: Criptografia de serviço do Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumo: entenda a resiliência de dados no Microsoft Office 365.'
ms.openlocfilehash: ec7f794a62a910fadaece890cf73451644d44109
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071108"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="cdffc-103">Criptografia de serviço do Office 365</span><span class="sxs-lookup"><span data-stu-id="cdffc-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="cdffc-104">Além de usar a criptografia no nível do volume, o Exchange Online, o Skype for Business, o SharePoint Online e o OneDrive for Business também usam a criptografia de serviço para criptografar os dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="cdffc-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="cdffc-105">A criptografia de serviço permite duas opções de gerenciamento de chave:</span><span class="sxs-lookup"><span data-stu-id="cdffc-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="cdffc-106">A Microsoft gerencia todas as chaves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="cdffc-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="cdffc-107">(Essa opção está atualmente disponível no SharePoint Online, no OneDrive for Business e no Skype for Business).</span><span class="sxs-lookup"><span data-stu-id="cdffc-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="cdffc-108">O cliente fornece as chaves raiz usadas com a criptografia de serviço e o cliente gerencia essas chaves usando o Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="cdffc-108">The customer supplies root keys used with service encryption and the customer manages these keys using Azure Key Vault.</span></span> <span data-ttu-id="cdffc-109">A Microsoft gerencia todas as outras chaves.</span><span class="sxs-lookup"><span data-stu-id="cdffc-109">Microsoft manages all other keys.</span></span> <span data-ttu-id="cdffc-110">Essa opção é chamada de chave do cliente e está disponível atualmente para o Exchange Online, o SharePoint Online e o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="cdffc-110">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="cdffc-111">(Conhecido anteriormente como criptografia avançada com o BYOK.</span><span class="sxs-lookup"><span data-stu-id="cdffc-111">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="cdffc-112">Consulte [aprimorando a transparência e o controle para clientes do Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para o anúncio original.</span><span class="sxs-lookup"><span data-stu-id="cdffc-112">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="cdffc-113">A criptografia de serviço oferece vários benefícios.</span><span class="sxs-lookup"><span data-stu-id="cdffc-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="cdffc-114">Por exemplo, chave de cliente:</span><span class="sxs-lookup"><span data-stu-id="cdffc-114">For example, Customer Key:</span></span>

- <span data-ttu-id="cdffc-115">Fornece recursos de gerenciamento e proteção de direitos na parte superior da proteção de criptografia forte.</span><span class="sxs-lookup"><span data-stu-id="cdffc-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="cdffc-116">Inclui uma opção de chave do cliente que permite que os serviços de vários locatários forneçam gerenciamento de chave por locatário.</span><span class="sxs-lookup"><span data-stu-id="cdffc-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="cdffc-117">Fornece separação entre os administradores do sistema operacional Windows e o acesso aos dados do cliente armazenados ou processados pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="cdffc-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="cdffc-118">Aprimora a capacidade do Office 365 de atender às demandas de clientes que têm requisitos de conformidade referentes à criptografia.</span><span class="sxs-lookup"><span data-stu-id="cdffc-118">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="cdffc-119">Chave de Cliente</span><span class="sxs-lookup"><span data-stu-id="cdffc-119">Customer Key</span></span>

<span data-ttu-id="cdffc-120">Usando a chave de cliente, você pode gerar suas próprias chaves criptográficas usando um módulo de serviço de hardware local (HSM) ou o Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="cdffc-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="cdffc-121">Independentemente de como você gerar a chave, use o AKV para controlar e gerenciar as chaves criptográficas usadas pelo Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdffc-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="cdffc-122">Depois que as chaves são armazenadas no AKV, elas podem ser usadas como a raiz de um dos cadeias de chaves que criptografam seus arquivos ou dados de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="cdffc-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="cdffc-123">Outro benefício da chave do cliente é o controle que você tem sobre a capacidade da Microsoft de processar seus dados.</span><span class="sxs-lookup"><span data-stu-id="cdffc-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="cdffc-124">Se você deseja remover dados do Office 365, como se você deseja encerrar o serviço com a Microsoft ou remover uma parte dos seus dados armazenados na nuvem, é possível fazer isso e usar a chave do cliente como um controle técnico.</span><span class="sxs-lookup"><span data-stu-id="cdffc-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="cdffc-125">Isso garante que ninguém, incluindo a Microsoft, possa acessar ou processar os dados.</span><span class="sxs-lookup"><span data-stu-id="cdffc-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="cdffc-126">A chave do cliente é adicional e complementar à Lockbox do cliente que você usa para controlar o acesso aos seus dados pela equipe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cdffc-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="cdffc-127">Para saber como configurar a chave do cliente para o Office 365 para o Exchange Online, o Skype for Business, o SharePoint Online, incluindo sites de equipe e o OneDrive for Business, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="cdffc-127">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="cdffc-128">Criptografia de serviço com a chave do cliente no Office 365</span><span class="sxs-lookup"><span data-stu-id="cdffc-128">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="cdffc-129">Configurar a chave do cliente para o Office 365</span><span class="sxs-lookup"><span data-stu-id="cdffc-129">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="cdffc-130">Gerenciar a chave do cliente para o Office 365</span><span class="sxs-lookup"><span data-stu-id="cdffc-130">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="cdffc-131">Rolar ou girar uma chave do cliente ou uma chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="cdffc-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="cdffc-132">Entender a chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="cdffc-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
