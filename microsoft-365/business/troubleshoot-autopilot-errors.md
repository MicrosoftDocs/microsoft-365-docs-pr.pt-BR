---
title: Solucionar problemas de dispositivo do AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Saiba como solucionar erros que você pode ver ao trabalhar com arquivos de dispositivo piloto no Microsoft 365 Business.
ms.openlocfilehash: 7569f18097a1f5959b3dd491958c78886e1e05d6
ms.sourcegitcommit: 41c0bc5cf50f4ca63b4286d1ea0f58ab82984b7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547462"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="d45ae-103">Solucionar problemas de dispositivo do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="d45ae-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="d45ae-104">Mensagens de erro de arquivo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="d45ae-104">Device file error messages</span></span>

<span data-ttu-id="d45ae-105">Veja a seguir informações sobre alguns dos erros que você pode ver enquanto estiver trabalhando com arquivos de dispositivo do AutoPilot no Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="d45ae-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="d45ae-106">**Código de erro**</span><span class="sxs-lookup"><span data-stu-id="d45ae-106">**Error code**</span></span>|<span data-ttu-id="d45ae-107">**Correção para tentar**</span><span class="sxs-lookup"><span data-stu-id="d45ae-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d45ae-108">Corpo de solicitação inválido</span><span class="sxs-lookup"><span data-stu-id="d45ae-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="d45ae-109">Esse erro deve acontecer raramente, se você vir esse erro, tente a operação novamente.</span><span class="sxs-lookup"><span data-stu-id="d45ae-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="d45ae-110">O valor de hash de hardware para um dispositivo não está correto.</span><span class="sxs-lookup"><span data-stu-id="d45ae-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="d45ae-111">Se você vir esse erro, significa que o valor que você forneceu no arquivo CSV para o hash de hardware de um dispositivo não está correto.</span><span class="sxs-lookup"><span data-stu-id="d45ae-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="d45ae-112">Primeiro, verifique se o valor foi digitado corretamente.</span><span class="sxs-lookup"><span data-stu-id="d45ae-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="d45ae-113">Se você achar que o valor está correto, mas esse erro ainda está ocorrendo, peça ajuda ao fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="d45ae-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="d45ae-114">Dispositivo atribuído a outro locatário</span><span class="sxs-lookup"><span data-stu-id="d45ae-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="d45ae-115">Se você vir esse erro, significa que o valor que você forneceu no arquivo CSV para o número de série ou a chave de produto de um ou mais dispositivos está incorreto.</span><span class="sxs-lookup"><span data-stu-id="d45ae-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="d45ae-116">Primeiro, verifique se o valor foi digitado corretamente.</span><span class="sxs-lookup"><span data-stu-id="d45ae-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="d45ae-117">Se você achar que o valor está correto, mas esse erro ainda está ocorrendo, peça ajuda ao fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="d45ae-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="d45ae-118">O arquivo CSV contém um número de série ou chave de produto inválida</span><span class="sxs-lookup"><span data-stu-id="d45ae-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="d45ae-119">Se você vir esse erro, significa que o dispositivo que você está tentando registrar já está registrado por outra organização.</span><span class="sxs-lookup"><span data-stu-id="d45ae-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="d45ae-120">Para corrigir esse erro, peça ajuda ao fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="d45ae-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="d45ae-121">Este dispositivo não tem suporte para a instalação usando o AutoPilot</span><span class="sxs-lookup"><span data-stu-id="d45ae-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="d45ae-122">Este erro significa que o dispositivo não atende aos requisitos de implantação do AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="d45ae-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="d45ae-123">Os dispositivos precisam atender a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="d45ae-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="d45ae-124">Windows 10, versão 1703 ou posteriores.</span><span class="sxs-lookup"><span data-stu-id="d45ae-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="d45ae-125">Novos dispositivos que não foram transferidos pela experiência inicial pelo Windows.</span><span class="sxs-lookup"><span data-stu-id="d45ae-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="d45ae-126">Dispositivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="d45ae-126">Device not found</span></span>  <br/> |<span data-ttu-id="d45ae-127">Esse erro significa que um ou mais dispositivos no seu arquivo CSV não estão registrados na sua organização.</span><span class="sxs-lookup"><span data-stu-id="d45ae-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="d45ae-128">Para corrigir isso, peça ajuda ao fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="d45ae-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
