---
title: Solucionar problemas do dispositivo AutoPilot
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Saiba como solucionar erros de arquivo do dispositivo de piloto automático.
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26864859"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="6ab2a-103">Solucionar problemas do dispositivo AutoPilot</span><span class="sxs-lookup"><span data-stu-id="6ab2a-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="6ab2a-104">Mensagens de erro do arquivo de dispositivo</span><span class="sxs-lookup"><span data-stu-id="6ab2a-104">Device file error messages</span></span>

<span data-ttu-id="6ab2a-105">Info aqui está em alguns dos erros que você pode ver ao trabalhar com arquivos de dispositivo de piloto automático no Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="6ab2a-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="6ab2a-106">**Código de erro**</span><span class="sxs-lookup"><span data-stu-id="6ab2a-106">**Error code**</span></span>|<span data-ttu-id="6ab2a-107">**Corrigir tentar**</span><span class="sxs-lookup"><span data-stu-id="6ab2a-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6ab2a-108">Corpo de solicitação inválida</span><span class="sxs-lookup"><span data-stu-id="6ab2a-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="6ab2a-109">Esse erro deve acontecer raramente, se você vir esse erro, tente a operação novamente.</span><span class="sxs-lookup"><span data-stu-id="6ab2a-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="6ab2a-110">Valor de hash de hardware para um dispositivo não está correto.</span><span class="sxs-lookup"><span data-stu-id="6ab2a-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="6ab2a-p101">Se você vir esse erro, significa que o valor fornecido no arquivo CSV para o hash de hardware de um dispositivo não estiverem correto. Primeiro, verifique se o valor foi digitado corretamente. Se você achar que o valor está correto, mas esse erro ainda está ocorrendo, peça ajuda ao seu fornecedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="6ab2a-p101">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="6ab2a-114">Dispositivo atribuído ao outro locatário</span><span class="sxs-lookup"><span data-stu-id="6ab2a-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="6ab2a-p102">Se você vir esse erro, significa que o valor fornecido no seu arquivo CSV para o número de série ou a chave de produto de um ou mais dispositivos não estiverem correto. Primeiro, verifique se o valor foi digitado corretamente. Se você achar que o valor está correto, mas esse erro ainda está ocorrendo, peça ajuda ao seu fornecedor de hardware.</span><span class="sxs-lookup"><span data-stu-id="6ab2a-p102">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="6ab2a-118">O arquivo CSV contém um número de série inválido ou a chave do produto</span><span class="sxs-lookup"><span data-stu-id="6ab2a-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="6ab2a-p103">Se você vir esse erro significa que o dispositivo que você está ao registrar tentar já está registrado por uma outra organização. Para corrigir esse problema, peça ao seu fornecedor de hardware para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="6ab2a-p103">If you see this error it means that the device you are tyring to register is already registered by an other organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="6ab2a-121">Este dispositivo não é suportado para a instalação usando o piloto automático</span><span class="sxs-lookup"><span data-stu-id="6ab2a-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="6ab2a-p104">Este erro indica que o dispositivo não atende aos requisitos de implantação do piloto automático. Dispositivos precisam atender a estes requisitos:</span><span class="sxs-lookup"><span data-stu-id="6ab2a-p104">This error means the device does not meet AutoPilot deployment requirements. Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="6ab2a-124">Windows 10, versão 1703 ou posteriores.</span><span class="sxs-lookup"><span data-stu-id="6ab2a-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="6ab2a-125">Novos dispositivos que ainda não passaram pela configuração inicial pelo usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="6ab2a-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="6ab2a-126">Dispositivo não encontrado</span><span class="sxs-lookup"><span data-stu-id="6ab2a-126">Device not found</span></span>  <br/> |<span data-ttu-id="6ab2a-p105">Este erro indica que um ou mais dispositivos em seu arquivo CSV não é registrado para sua organização. Para corrigir esse problema, peça ao seu fornecedor de hardware para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="6ab2a-p105">This error means that one or more devices in your CSV file is not registered to your organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
