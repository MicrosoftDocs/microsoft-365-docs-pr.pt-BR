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
ms.openlocfilehash: 1c31c0d5524370fd417460fbacf3695df4fa0102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632236"
---
# <a name="service-encryption"></a><span data-ttu-id="b1c06-103">Criptografia de serviço</span><span class="sxs-lookup"><span data-stu-id="b1c06-103">Service Encryption</span></span>

<span data-ttu-id="b1c06-104">Além de usar a criptografia no nível do volume, o Exchange Online, o Skype for Business, o SharePoint Online e o OneDrive for Business também usam a criptografia de serviço para criptografar os dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="b1c06-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="b1c06-105">A criptografia de serviço permite duas opções de gerenciamento de chave:</span><span class="sxs-lookup"><span data-stu-id="b1c06-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="b1c06-106">A Microsoft gerencia todas as chaves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="b1c06-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="b1c06-107">(Essa opção está atualmente disponível no SharePoint Online, no OneDrive for Business e no Skype for Business).</span><span class="sxs-lookup"><span data-stu-id="b1c06-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="b1c06-108">Sua organização fornece as chaves raiz.</span><span class="sxs-lookup"><span data-stu-id="b1c06-108">Your organization supplies the root keys.</span></span> <span data-ttu-id="b1c06-109">Você gerencia essas chaves usando o Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="b1c06-109">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="b1c06-110">Essa opção é chamada de chave do cliente.</span><span class="sxs-lookup"><span data-stu-id="b1c06-110">This option is called Customer Key.</span></span> <span data-ttu-id="b1c06-111">A chave do cliente está disponível atualmente para os arquivos do Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business e Teams.</span><span class="sxs-lookup"><span data-stu-id="b1c06-111">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="b1c06-112">Se você usar a chave do cliente, essas chaves substituirão chaves gerenciadas pela Microsoft para criptografar seus dados.</span><span class="sxs-lookup"><span data-stu-id="b1c06-112">If you use Customer Key, these keys replace Microsoft-managed keys to encrypt your data.</span></span>

<span data-ttu-id="b1c06-113">A criptografia de serviço oferece vários benefícios.</span><span class="sxs-lookup"><span data-stu-id="b1c06-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="b1c06-114">Por exemplo, chave de cliente:</span><span class="sxs-lookup"><span data-stu-id="b1c06-114">For example, Customer Key:</span></span>

- <span data-ttu-id="b1c06-115">Fornece recursos de gerenciamento e proteção de direitos na parte superior da proteção de criptografia forte.</span><span class="sxs-lookup"><span data-stu-id="b1c06-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="b1c06-116">Inclui uma opção de chave do cliente que permite que os serviços de vários locatários forneçam gerenciamento de chave por locatário.</span><span class="sxs-lookup"><span data-stu-id="b1c06-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="b1c06-117">Fornece separação entre os administradores do sistema operacional Windows e o acesso aos dados do cliente armazenados ou processados pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="b1c06-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="b1c06-118">Aprimora a capacidade do Microsoft 365 de atender às demandas de clientes que têm requisitos de conformidade referentes à criptografia.</span><span class="sxs-lookup"><span data-stu-id="b1c06-118">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="b1c06-119">Chave de Cliente</span><span class="sxs-lookup"><span data-stu-id="b1c06-119">Customer Key</span></span>

<span data-ttu-id="b1c06-120">Usando a chave de cliente, você pode gerar suas próprias chaves criptográficas usando um módulo de serviço de hardware local (HSM) ou o Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="b1c06-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="b1c06-121">Independentemente de como você gerar a chave, use o AKV para controlar e gerenciar as chaves criptográficas usadas pelo Office 365.</span><span class="sxs-lookup"><span data-stu-id="b1c06-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="b1c06-122">Depois que as chaves são armazenadas no AKV, elas podem ser usadas como a raiz de um dos cadeias de chaves que criptografam seus arquivos ou dados de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="b1c06-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="b1c06-123">Outro benefício da chave do cliente é o controle que você tem sobre a capacidade da Microsoft de processar seus dados.</span><span class="sxs-lookup"><span data-stu-id="b1c06-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="b1c06-124">Se você deseja remover dados do Office 365, como se você deseja encerrar o serviço com a Microsoft ou remover uma parte dos seus dados armazenados na nuvem, é possível fazer isso e usar a chave do cliente como um controle técnico.</span><span class="sxs-lookup"><span data-stu-id="b1c06-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="b1c06-125">Isso garante que ninguém, incluindo a Microsoft, possa acessar ou processar os dados.</span><span class="sxs-lookup"><span data-stu-id="b1c06-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="b1c06-126">A chave do cliente é adicional e complementar à Lockbox do cliente que você usa para controlar o acesso aos seus dados pela equipe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b1c06-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="b1c06-127">Para saber como configurar a chave do cliente para o Microsoft 365 para Exchange Online, Skype for Business, SharePoint Online, incluindo sites de equipe e OneDrive for Business, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="b1c06-127">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="b1c06-128">Criptografia de serviço com a chave do cliente</span><span class="sxs-lookup"><span data-stu-id="b1c06-128">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="b1c06-129">Configurar a chave do cliente</span><span class="sxs-lookup"><span data-stu-id="b1c06-129">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="b1c06-130">Gerenciar chave do cliente</span><span class="sxs-lookup"><span data-stu-id="b1c06-130">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="b1c06-131">Rolar ou girar uma chave do cliente ou uma chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b1c06-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="b1c06-132">Entender a chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="b1c06-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
