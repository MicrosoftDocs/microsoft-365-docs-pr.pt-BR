---
title: Solucionar problemas de dispositivo do AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Saiba como solucionar erros que você pode ver ao trabalhar com arquivos de dispositivo do AutoPilot Microsoft 365 Business Premium.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578078"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="f97d1-103">Solucionar problemas de dispositivo do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="f97d1-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="f97d1-104">Mensagens de erro de arquivo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="f97d1-104">Device file error messages</span></span>

<span data-ttu-id="f97d1-105">Aqui estão as informações sobre alguns dos erros que você pode ver ao trabalhar com arquivos de dispositivo do AutoPilot em Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="f97d1-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="f97d1-106">**Código de erro**</span><span class="sxs-lookup"><span data-stu-id="f97d1-106">**Error code**</span></span>|<span data-ttu-id="f97d1-107">**Corrigir para tentar**</span><span class="sxs-lookup"><span data-stu-id="f97d1-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f97d1-108">Corpo de solicitação inválido</span><span class="sxs-lookup"><span data-stu-id="f97d1-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="f97d1-109">Esse erro deve acontecer raramente, se você vir esse erro, tente a operação novamente.</span><span class="sxs-lookup"><span data-stu-id="f97d1-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="f97d1-110">O valor de hash de hardware para um dispositivo não está correto.</span><span class="sxs-lookup"><span data-stu-id="f97d1-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="f97d1-111">Se você vir esse erro, significa que o valor fornecido no arquivo CSV para o hash de hardware de um dispositivo não está correto.</span><span class="sxs-lookup"><span data-stu-id="f97d1-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="f97d1-112">Primeiro, verifique se o valor foi digitado corretamente.</span><span class="sxs-lookup"><span data-stu-id="f97d1-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="f97d1-113">Se você acha que o valor está correto, mas esse erro ainda está acontecendo, peça ajuda ao fornecedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="f97d1-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="f97d1-114">Dispositivo atribuído a outro locatário</span><span class="sxs-lookup"><span data-stu-id="f97d1-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="f97d1-115">Se você vir esse erro, significa que o valor fornecido no arquivo CSV para o número de série ou a chave do produto de um ou mais dispositivos não está correto.</span><span class="sxs-lookup"><span data-stu-id="f97d1-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="f97d1-116">Primeiro, verifique se o valor foi digitado corretamente.</span><span class="sxs-lookup"><span data-stu-id="f97d1-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="f97d1-117">Se você acha que o valor está correto, mas esse erro ainda está acontecendo, peça ajuda ao fornecedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="f97d1-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="f97d1-118">O arquivo CSV contém um número de série inválido ou uma chave de produto</span><span class="sxs-lookup"><span data-stu-id="f97d1-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="f97d1-119">Se você vir esse erro, isso significa que o dispositivo que você está tentando registrar já está registrado por outra organização.</span><span class="sxs-lookup"><span data-stu-id="f97d1-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="f97d1-120">Para corrigir esse erro, peça ajuda ao fornecedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="f97d1-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="f97d1-121">Este dispositivo não tem suporte para instalação usando o AutoPilot</span><span class="sxs-lookup"><span data-stu-id="f97d1-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="f97d1-122">Esse erro significa que o dispositivo não atendem aos requisitos de implantação do AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="f97d1-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="f97d1-123">Os dispositivos precisam atender a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="f97d1-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="f97d1-124">Windows 10, versão 1703 ou posteriores.</span><span class="sxs-lookup"><span data-stu-id="f97d1-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="f97d1-125">Novos dispositivos que não passaram por Windows experiência completa.</span><span class="sxs-lookup"><span data-stu-id="f97d1-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="f97d1-126">Dispositivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="f97d1-126">Device not found</span></span>  <br/> |<span data-ttu-id="f97d1-127">Esse erro significa que um ou mais dispositivos no arquivo CSV não estão registrados na sua organização.</span><span class="sxs-lookup"><span data-stu-id="f97d1-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="f97d1-128">Para corrigir isso, peça ajuda ao fornecedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="f97d1-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
