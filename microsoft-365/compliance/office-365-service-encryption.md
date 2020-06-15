---
title: Criptografia de serviço
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
ms.openlocfilehash: e69d35f08070e1fe092ca8a9b4aef6d179711121
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717342"
---
# <a name="service-encryption"></a><span data-ttu-id="cf01b-103">Criptografia de serviço</span><span class="sxs-lookup"><span data-stu-id="cf01b-103">Service Encryption</span></span>

<span data-ttu-id="cf01b-104">Além de usar a criptografia no nível do volume, o Exchange Online, o Skype for Business, o SharePoint Online e o OneDrive for Business também usam a criptografia de serviço para criptografar os dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="cf01b-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="cf01b-105">A criptografia de serviço permite duas opções de gerenciamento de chave:</span><span class="sxs-lookup"><span data-stu-id="cf01b-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="cf01b-106">Chaves gerenciadas pela Microsoft:</span><span class="sxs-lookup"><span data-stu-id="cf01b-106">Microsoft managed keys:</span></span> 
<span data-ttu-id="cf01b-107">A Microsoft gerencia todas as chaves criptográficas, incluindo as chaves raiz para a criptografia de serviço.</span><span class="sxs-lookup"><span data-stu-id="cf01b-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="cf01b-108">Essa opção está atualmente disponível no SharePoint Online e no OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="cf01b-108">This option is currently available in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="cf01b-109">Essa opção está sendo distribuída no momento para o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="cf01b-109">This option is currently being rolled out for Exchange Online.</span></span> <span data-ttu-id="cf01b-110">As chaves gerenciadas pela Microsoft fornecem criptografia de serviço padrão, a menos que você decida usar a chave do cliente.</span><span class="sxs-lookup"><span data-stu-id="cf01b-110">Microsoft managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="cf01b-111">Se, mais tarde, você optar por parar de usar a chave do cliente sem seguir o caminho de limpeza de dados, seus dados permanecerão criptografados usando as chaves gerenciadas pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf01b-111">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft managed keys.</span></span> <span data-ttu-id="cf01b-112">Seus dados são sempre criptografados no nível padrão no mínimo.</span><span class="sxs-lookup"><span data-stu-id="cf01b-112">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="cf01b-113">Chave do cliente:</span><span class="sxs-lookup"><span data-stu-id="cf01b-113">Customer Key:</span></span> 
<span data-ttu-id="cf01b-114">Você fornece chaves raiz usadas com a criptografia de serviço e gerencia essas chaves usando o Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="cf01b-114">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="cf01b-115">A Microsoft gerencia todas as outras chaves.</span><span class="sxs-lookup"><span data-stu-id="cf01b-115">Microsoft manages all other keys.</span></span> <span data-ttu-id="cf01b-116">Essa opção é chamada de chave do cliente e está disponível atualmente para o Exchange Online, o SharePoint Online e o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="cf01b-116">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="cf01b-117">(Conhecido anteriormente como criptografia avançada com o BYOK.</span><span class="sxs-lookup"><span data-stu-id="cf01b-117">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="cf01b-118">Consulte [aprimorando a transparência e o controle para clientes do Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para o anúncio original.</span><span class="sxs-lookup"><span data-stu-id="cf01b-118">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="cf01b-119">A criptografia de serviço oferece vários benefícios.</span><span class="sxs-lookup"><span data-stu-id="cf01b-119">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="cf01b-120">Por exemplo, chave de cliente:</span><span class="sxs-lookup"><span data-stu-id="cf01b-120">For example, Customer Key:</span></span>

- <span data-ttu-id="cf01b-121">Fornece recursos de gerenciamento e proteção de direitos na parte superior da proteção de criptografia forte.</span><span class="sxs-lookup"><span data-stu-id="cf01b-121">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="cf01b-122">Inclui uma opção de chave do cliente que permite que os serviços de vários locatários forneçam gerenciamento de chave por locatário.</span><span class="sxs-lookup"><span data-stu-id="cf01b-122">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="cf01b-123">Fornece separação entre os administradores do sistema operacional Windows e o acesso aos dados do cliente armazenados ou processados pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="cf01b-123">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="cf01b-124">Aprimora a capacidade do Microsoft 365 de atender às demandas de clientes que têm requisitos de conformidade referentes à criptografia.</span><span class="sxs-lookup"><span data-stu-id="cf01b-124">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="cf01b-125">Usando a chave de cliente, você pode gerar suas próprias chaves criptográficas usando um módulo de serviço de hardware local (HSM) ou o Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="cf01b-125">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="cf01b-126">Independentemente de como você gerar a chave, use o AKV para controlar e gerenciar as chaves criptográficas usadas pelo Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf01b-126">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="cf01b-127">Depois que as chaves são armazenadas no AKV, elas podem ser usadas como a raiz de um dos cadeias de chaves que criptografam seus arquivos ou dados de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="cf01b-127">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="cf01b-128">Outro benefício da chave do cliente é o controle que você tem sobre a capacidade da Microsoft de processar seus dados.</span><span class="sxs-lookup"><span data-stu-id="cf01b-128">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="cf01b-129">Se você deseja remover dados do Office 365, como se você deseja encerrar o serviço com a Microsoft ou remover uma parte dos seus dados armazenados na nuvem, é possível fazer isso e usar a chave do cliente como um controle técnico.</span><span class="sxs-lookup"><span data-stu-id="cf01b-129">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="cf01b-130">Isso garante que ninguém, incluindo a Microsoft, possa acessar ou processar os dados.</span><span class="sxs-lookup"><span data-stu-id="cf01b-130">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="cf01b-131">A chave do cliente é adicional e complementar à Lockbox do cliente que você usa para controlar o acesso aos seus dados pela equipe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cf01b-131">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="cf01b-132">Para saber como configurar a chave do cliente para o Microsoft 365 para Exchange Online, Skype for Business, SharePoint Online, incluindo sites de equipe e OneDrive for Business, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="cf01b-132">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="cf01b-133">Criptografia de serviço com a chave do cliente</span><span class="sxs-lookup"><span data-stu-id="cf01b-133">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="cf01b-134">Configurar a chave do cliente</span><span class="sxs-lookup"><span data-stu-id="cf01b-134">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="cf01b-135">Gerenciar chave do cliente</span><span class="sxs-lookup"><span data-stu-id="cf01b-135">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="cf01b-136">Rolar ou girar uma chave do cliente ou uma chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="cf01b-136">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="cf01b-137">Entender a chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="cf01b-137">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

