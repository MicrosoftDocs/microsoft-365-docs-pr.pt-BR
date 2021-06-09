---
title: Criptografia de Serviço
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
description: 'Resumo: Entenda a resiliência de dados no Microsoft Office 365.'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058544"
---
# <a name="service-encryption"></a><span data-ttu-id="04e4a-103">Criptografia de Serviço</span><span class="sxs-lookup"><span data-stu-id="04e4a-103">Service Encryption</span></span>

<span data-ttu-id="04e4a-104">Além de usar criptografia de nível de volume, Exchange Online, Microsoft Teams, SharePoint Online e OneDrive for Business também usam a Criptografia de Serviço para criptografar dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="04e4a-104">In addition to using volume-level encryption, Exchange Online, Microsoft Teams, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="04e4a-105">A Criptografia de Serviço permite duas opções principais de gerenciamento:</span><span class="sxs-lookup"><span data-stu-id="04e4a-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="04e4a-106">Chaves gerenciadas pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="04e4a-106">Microsoft-managed keys</span></span>
<span data-ttu-id="04e4a-107">A Microsoft gerencia todas as chaves criptográficas, incluindo as chaves raiz para criptografia de serviço.</span><span class="sxs-lookup"><span data-stu-id="04e4a-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="04e4a-108">Essa opção está habilitada por padrão para Exchange Online, SharePoint Online, OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="04e4a-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="04e4a-109">As chaves gerenciadas pela Microsoft fornecem criptografia de serviço padrão, a menos que você decida fazer a integração usando a Chave do Cliente.</span><span class="sxs-lookup"><span data-stu-id="04e4a-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="04e4a-110">Se, em uma data posterior, você decidir parar de usar a Chave do Cliente sem seguir o caminho de limpeza de dados, seus dados permanecerão criptografados usando as chaves gerenciadas pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04e4a-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="04e4a-111">Seus dados são sempre criptografados nesse nível padrão no mínimo.</span><span class="sxs-lookup"><span data-stu-id="04e4a-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="04e4a-112">Chave de Cliente</span><span class="sxs-lookup"><span data-stu-id="04e4a-112">Customer Key</span></span>
<span data-ttu-id="04e4a-113">Você fornece chaves raiz usadas com criptografia de serviço e gerencia essas chaves usando o Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="04e4a-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="04e4a-114">A Microsoft gerencia todas as outras chaves.</span><span class="sxs-lookup"><span data-stu-id="04e4a-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="04e4a-115">Essa opção é chamada de Chave do Cliente e está disponível atualmente para Exchange Online, SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="04e4a-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="04e4a-116">(Anteriormente conhecido como Criptografia Avançada com BYOK.</span><span class="sxs-lookup"><span data-stu-id="04e4a-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="04e4a-117">Consulte [Aprimorando a transparência e o controle para Office 365 clientes](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) para o comunicado original.)</span><span class="sxs-lookup"><span data-stu-id="04e4a-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="04e4a-118">A criptografia de serviço oferece vários benefícios:</span><span class="sxs-lookup"><span data-stu-id="04e4a-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="04e4a-119">Fornece uma camada adicional de proteção sobre BitLocker.</span><span class="sxs-lookup"><span data-stu-id="04e4a-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="04e4a-120">Fornece a separação Windows administradores do sistema operacional do acesso aos dados do aplicativo armazenados ou processados pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="04e4a-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="04e4a-121">Inclui uma opção de Chave do Cliente que permite que os serviços de vários locatários forneçam gerenciamento de chaves por locatário.</span><span class="sxs-lookup"><span data-stu-id="04e4a-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="04e4a-122">Aprimora a capacidade de Microsoft 365 atender às demandas dos clientes que têm requisitos de conformidade específicos em relação à criptografia.</span><span class="sxs-lookup"><span data-stu-id="04e4a-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="04e4a-123">Usando a Chave do Cliente, você pode gerar suas próprias chaves criptográficas usando um HSM (Hardware Service Module) local ou a Azure Key Vault (AKV).</span><span class="sxs-lookup"><span data-stu-id="04e4a-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="04e4a-124">Independentemente de como você gera a chave, você usa o AKV para controlar e gerenciar as chaves criptográficas usadas por Office 365.</span><span class="sxs-lookup"><span data-stu-id="04e4a-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="04e4a-125">Depois que suas chaves são armazenadas no AKV, elas podem ser usadas como a raiz de um dos chaveiros que criptografa seus dados ou arquivos de caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="04e4a-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="04e4a-126">Outro benefício da Chave do Cliente é o controle que você tem sobre a capacidade da Microsoft de processar seus dados.</span><span class="sxs-lookup"><span data-stu-id="04e4a-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="04e4a-127">Se você deseja remover dados do Office 365, como se deseja encerrar o serviço com a Microsoft ou remover uma parte dos dados armazenados na nuvem, você pode fazer isso e usar a Chave do Cliente como um controle técnico.</span><span class="sxs-lookup"><span data-stu-id="04e4a-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="04e4a-128">Remover dados garante que ninguém, incluindo a Microsoft, possa acessar ou processar os dados.</span><span class="sxs-lookup"><span data-stu-id="04e4a-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="04e4a-129">A Chave do Cliente é além e complementar ao Customer Lockbox que você usa para controlar o acesso aos seus dados pela equipe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="04e4a-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="04e4a-130">Para saber como configurar a Chave do Cliente para Microsoft 365 para Exchange Online, Microsoft Teams, SharePoint Online, incluindo Sites de Equipe e OneDrive for Business, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="04e4a-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Microsoft Teams, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="04e4a-131">Criptografia do serviço com a Chave de Cliente</span><span class="sxs-lookup"><span data-stu-id="04e4a-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="04e4a-132">Configurar a Chave do Cliente</span><span class="sxs-lookup"><span data-stu-id="04e4a-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="04e4a-133">Gerenciar Chave do Cliente</span><span class="sxs-lookup"><span data-stu-id="04e4a-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="04e4a-134">Rolar ou girar uma chave do cliente ou uma chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="04e4a-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="04e4a-135">Compreender a chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="04e4a-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
