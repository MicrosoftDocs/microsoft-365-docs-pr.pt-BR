---
title: Solucionar problemas de dispositivo do AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Saiba como solucionar erros de arquivo de dispositivo piloto automático.
ms.openlocfilehash: 9d4a47f78c38d8c076f5b3876a36b6bf46eaaaf3
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279829"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="ccae6-103">Solucionar problemas de dispositivo do AutoPilot</span><span class="sxs-lookup"><span data-stu-id="ccae6-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="ccae6-104">Mensagens de erro de arquivo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="ccae6-104">Device file error messages</span></span>

<span data-ttu-id="ccae6-105">Veja a seguir informações sobre alguns dos erros que você pode ver enquanto estiver trabalhando com arquivos de dispositivo do autoPilot no Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="ccae6-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="ccae6-106">**Código de erro**</span><span class="sxs-lookup"><span data-stu-id="ccae6-106">**Error code**</span></span>|<span data-ttu-id="ccae6-107">**Correção para tentar**</span><span class="sxs-lookup"><span data-stu-id="ccae6-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ccae6-108">Corpo de solicitação inválido</span><span class="sxs-lookup"><span data-stu-id="ccae6-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="ccae6-109">Esse erro deve acontecer raramente, se você vir esse erro, tente a operação novamente.</span><span class="sxs-lookup"><span data-stu-id="ccae6-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="ccae6-110">O valor de hash de hardware para um dispositivo não está correto.</span><span class="sxs-lookup"><span data-stu-id="ccae6-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="ccae6-111">Se você vir esse erro, significa que o valor que você forneceu no arquivo CSV para o hash de hardware de um dispositivo não está correto.</span><span class="sxs-lookup"><span data-stu-id="ccae6-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="ccae6-112">Primeiro, verifique se o valor foi digitado corretamente.</span><span class="sxs-lookup"><span data-stu-id="ccae6-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="ccae6-113">Se você achar que o valor está correto, mas esse erro ainda está ocorrendo, peça ajuda ao fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="ccae6-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ccae6-114">Dispositivo atribuído a outro locatário</span><span class="sxs-lookup"><span data-stu-id="ccae6-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="ccae6-115">Se você vir esse erro, significa que o valor que você forneceu no arquivo CSV para o número de série ou a chave de produto de um ou mais dispositivos está incorreto.</span><span class="sxs-lookup"><span data-stu-id="ccae6-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="ccae6-116">Primeiro, verifique se o valor foi digitado corretamente.</span><span class="sxs-lookup"><span data-stu-id="ccae6-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="ccae6-117">Se você achar que o valor está correto, mas esse erro ainda está ocorrendo, peça ajuda ao fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="ccae6-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ccae6-118">O arquivo CSV contém um número de série ou chave de produto inválida</span><span class="sxs-lookup"><span data-stu-id="ccae6-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="ccae6-119">Se você vir esse erro, significa que o dispositivo que você está tyring a registrar já está registrado por outra organização.</span><span class="sxs-lookup"><span data-stu-id="ccae6-119">If you see this error it means that the device you are tyring to register is already registered by an other organization.</span></span> <span data-ttu-id="ccae6-120">Para corrigir isso, peça ajuda ao fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="ccae6-120">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ccae6-121">Este dispositivo não tem suporte para a instalação usando o autoPilot</span><span class="sxs-lookup"><span data-stu-id="ccae6-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="ccae6-122">Este erro significa que o dispositivo não atende aos requisitos de implantação do piloto automático.</span><span class="sxs-lookup"><span data-stu-id="ccae6-122">This error means the device does not meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="ccae6-123">Os dispositivos precisam atender a esses requisitos:</span><span class="sxs-lookup"><span data-stu-id="ccae6-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="ccae6-124">Windows 10, versão 1703 ou posteriores.</span><span class="sxs-lookup"><span data-stu-id="ccae6-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="ccae6-125">Novos dispositivos que ainda não passaram pela configuração inicial pelo usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="ccae6-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="ccae6-126">Dispositivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="ccae6-126">Device not found</span></span>  <br/> |<span data-ttu-id="ccae6-127">Esse erro significa que um ou mais dispositivos no seu arquivo CSV não estão registrados na sua organização.</span><span class="sxs-lookup"><span data-stu-id="ccae6-127">This error means that one or more devices in your CSV file is not registered to your organization.</span></span> <span data-ttu-id="ccae6-128">Para corrigir isso, peça ajuda ao fornecedor do hardware.</span><span class="sxs-lookup"><span data-stu-id="ccae6-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
