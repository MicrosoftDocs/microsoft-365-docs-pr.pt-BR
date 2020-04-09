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
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Resumo: entender a criptografia de dados na camada de serviço do Microsoft Office 365.'
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193457"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="68888-103">Criptografia de serviço do Office 365</span><span class="sxs-lookup"><span data-stu-id="68888-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="68888-104">Além de usar o BitLocker para a criptografia no nível do volume, o Exchange Online, o Skype for Business, o SharePoint Online, o OneDrive for Business e o Microsoft Teams também usam a criptografia de serviço para criptografar os dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="68888-104">In addition to using BitLocker for volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="68888-105">A criptografia de serviço permite duas opções de gerenciamento de chave:</span><span class="sxs-lookup"><span data-stu-id="68888-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="68888-106">A Microsoft gerencia todas as chaves criptográficas.</span><span class="sxs-lookup"><span data-stu-id="68888-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="68888-107">No momento, essa opção está disponível no SharePoint Online, no OneDrive for Business, no Skype for Business e em bate-papos do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="68888-107">This option is currently available in SharePoint Online, OneDrive for Business, Skype for Business, and Teams chats.</span></span> <span data-ttu-id="68888-108">Os dados são criptografados por padrão com as chaves gerenciadas pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="68888-108">Your data is encrypted by default with Microsoft managed keys.</span></span>

- <span data-ttu-id="68888-109">Sua organização fornece as chaves raiz.</span><span class="sxs-lookup"><span data-stu-id="68888-109">Your organization supplies the root keys.</span></span> <span data-ttu-id="68888-110">Você gerencia essas chaves usando o Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="68888-110">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="68888-111">Essa opção é chamada de chave do cliente.</span><span class="sxs-lookup"><span data-stu-id="68888-111">This option is called Customer Key.</span></span> <span data-ttu-id="68888-112">A chave do cliente está disponível atualmente para os arquivos do Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business e Teams.</span><span class="sxs-lookup"><span data-stu-id="68888-112">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="68888-113">Se você usar a chave do cliente, essas chaves substituirão as chaves gerenciadas pela Microsoft para criptografar seus dados.</span><span class="sxs-lookup"><span data-stu-id="68888-113">If you use Customer Key, these keys replace Microsoft managed keys to encrypt your data.</span></span>

<span data-ttu-id="68888-114">Independentemente da opção escolhida, a criptografia de serviço oferece vários benefícios:</span><span class="sxs-lookup"><span data-stu-id="68888-114">Regardless of the option you choose, service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="68888-115">Impõe a autenticação do usuário para recuperar e descriptografar dados solicitados por um usuário autorizado.</span><span class="sxs-lookup"><span data-stu-id="68888-115">Enforces user authentication to retrieve and decrypt data requested by an authorized user.</span></span>

- <span data-ttu-id="68888-116">Fornece separação entre os administradores do sistema operacional Windows e o acesso aos dados do cliente armazenados ou processados pelo sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="68888-116">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="68888-117">Aprimora a capacidade do Office 365 de atender às demandas de clientes que têm requisitos de conformidade referentes à criptografia.</span><span class="sxs-lookup"><span data-stu-id="68888-117">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="68888-118">Para saber como configurar a chave do cliente para o Office 365 para o Exchange Online, o Skype for Business, o SharePoint Online, o OneDrive for Business e os arquivos do Teams, consulte estes artigos:</span><span class="sxs-lookup"><span data-stu-id="68888-118">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files, see these articles:</span></span>

- [<span data-ttu-id="68888-119">Criptografia de serviço com a chave do cliente no Office 365</span><span class="sxs-lookup"><span data-stu-id="68888-119">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="68888-120">Configurar a chave do cliente para o Office 365</span><span class="sxs-lookup"><span data-stu-id="68888-120">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="68888-121">Gerenciar a chave do cliente para o Office 365</span><span class="sxs-lookup"><span data-stu-id="68888-121">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="68888-122">Rolar ou girar uma chave do cliente ou uma chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="68888-122">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="68888-123">Entender a chave de disponibilidade</span><span class="sxs-lookup"><span data-stu-id="68888-123">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
