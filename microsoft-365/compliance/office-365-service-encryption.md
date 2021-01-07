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
ms.openlocfilehash: fbd2672986046a4f6d25c47b011eaef0a87d90e1
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777044"
---
# <a name="service-encryption"></a><span data-ttu-id="c6595-103">Criptografia de serviço</span><span class="sxs-lookup"><span data-stu-id="c6595-103">Service Encryption</span></span>

<span data-ttu-id="c6595-104">Além de usar a criptografia no nível do volume, o Exchange Online, o Skype for Business, o SharePoint Online e o OneDrive for Business também usam a criptografia de serviço para criptografar os dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="c6595-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="c6595-105">A criptografia de serviço permite duas opções de gerenciamento de chave:</span><span class="sxs-lookup"><span data-stu-id="c6595-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="c6595-106">Chaves gerenciadas pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="c6595-106">Microsoft-managed keys</span></span>
<span data-ttu-id="c6595-107">A Microsoft gerencia todas as chaves criptográficas, incluindo as chaves raiz para a criptografia de serviço.</span><span class="sxs-lookup"><span data-stu-id="c6595-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="c6595-108">Atualmente, essa opção está habilitada por padrão para o Exchange Online, o SharePoint Online, o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="c6595-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="c6595-109">As chaves gerenciadas pela Microsoft fornecem criptografia de serviço padrão, a menos que você decida usar a chave do cliente.</span><span class="sxs-lookup"><span data-stu-id="c6595-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="c6595-110">Se, posteriormente, você optar por parar de usar a chave do cliente sem seguir o caminho de limpeza de dados, seus dados permanecerão criptografados usando as chaves gerenciadas pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6595-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="c6595-111">Seus dados são sempre criptografados no nível padrão no mínimo.</span><span class="sxs-lookup"><span data-stu-id="c6595-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="c6595-112">Chave de Cliente</span><span class="sxs-lookup"><span data-stu-id="c6595-112">Customer Key</span></span>
<span data-ttu-id="c6595-113">Você fornece chaves raiz usadas com a criptografia de serviço e gerencia essas chaves usando o Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="c6595-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="c6595-114">A Microsoft gerencia todas as outras chaves.</span><span class="sxs-lookup"><span data-stu-id="c6595-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="c6595-115">Essa opção é chamada de chave do cliente e está disponível atualmente para o Exchange Online, o SharePoint Online e o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="c6595-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="c6595-116">(Conhecido anteriormente como criptografia avançada com o BYOK.</span><span class="sxs-lookup"><span data-stu-id="c6595-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="c6595-117">Consulte [aprimorando a transparência e o controle para clientes do Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para o anúncio original.</span><span class="sxs-lookup"><span data-stu-id="c6595-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="c6595-118">A criptografia de serviço oferece vários benefícios:</span><span class="sxs-lookup"><span data-stu-id="c6595-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="c6595-119">Fornece uma camada adicional de proteção na parte superior do BitLocker.</span><span class="sxs-lookup"><span data-stu-id="c6595-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="c6595-120">Fornece separação entre os administradores do sistema operacional Windows e o acesso aos dados do aplicativo armazenados ou processados pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c6595-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="c6595-121">Inclui uma opção de chave do cliente que permite que os serviços de vários locatários forneçam gerenciamento de chave por locatário.</span><span class="sxs-lookup"><span data-stu-id="c6595-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="c6595-122">Aprimora a capacidade do Microsoft 365 de atender às demandas de clientes que têm requisitos de conformidade específicos relacionados à criptografia.</span><span class="sxs-lookup"><span data-stu-id="c6595-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="c6595-123">Usando a chave de cliente, você pode gerar suas próprias chaves criptográficas usando um módulo de serviço de hardware local (HSM) ou o Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="c6595-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="c6595-124">Independentemente de como você gerar a chave, use o AKV para controlar e gerenciar as chaves criptográficas usadas pelo Office 365.</span><span class="sxs-lookup"><span data-stu-id="c6595-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="c6595-125">Depois que as chaves são armazenadas no AKV, elas podem ser usadas como a raiz de um dos cadeias de chaves que criptografam seus arquivos ou dados de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="c6595-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="c6595-126">Outro benefício da chave do cliente é o controle que você tem sobre a capacidade da Microsoft de processar seus dados.</span><span class="sxs-lookup"><span data-stu-id="c6595-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="c6595-127">Se você deseja remover dados do Office 365, como se você deseja encerrar o serviço com a Microsoft ou remover uma parte dos seus dados armazenados na nuvem, é possível fazer isso e usar a chave do cliente como um controle técnico.</span><span class="sxs-lookup"><span data-stu-id="c6595-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="c6595-128">A remoção de dados garante que ninguém, incluindo a Microsoft, possa acessar ou processar os dados.</span><span class="sxs-lookup"><span data-stu-id="c6595-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="c6595-129">A chave do cliente é adicional e complementar à Lockbox do cliente que você usa para controlar o acesso aos seus dados pela equipe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6595-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="c6595-130">Para saber como configurar a chave do cliente para o Microsoft 365 para Exchange Online, Skype for Business, SharePoint Online, incluindo sites de equipe e OneDrive for Business, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="c6595-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="c6595-131">Criptografia do serviço com a Chave de Cliente</span><span class="sxs-lookup"><span data-stu-id="c6595-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="c6595-132">Configurar a chave do cliente</span><span class="sxs-lookup"><span data-stu-id="c6595-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="c6595-133">Gerenciar chave do cliente</span><span class="sxs-lookup"><span data-stu-id="c6595-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="c6595-134">Rolar ou girar uma chave do cliente ou uma chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c6595-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="c6595-135">Entender a chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="c6595-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

