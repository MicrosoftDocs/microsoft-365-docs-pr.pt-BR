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
# <a name="troubleshoot-autopilot-device-errors"></a>Solucionar problemas de dispositivo do AutoPilot

## <a name="device-file-error-messages"></a>Mensagens de erro de arquivo de dispositivo

Aqui estão as informações sobre alguns dos erros que você pode ver ao trabalhar com arquivos de dispositivo do AutoPilot em Microsoft 365 Business Premium. 
  
|**Código de erro**|**Corrigir para tentar**|
|:-----|:-----|
|Corpo de solicitação inválido  <br/> |Esse erro deve acontecer raramente, se você vir esse erro, tente a operação novamente.  <br/> |
|O valor de hash de hardware para um dispositivo não está correto.  <br/> |Se você vir esse erro, significa que o valor fornecido no arquivo CSV para o hash de hardware de um dispositivo não está correto. Primeiro, verifique se o valor foi digitado corretamente. Se você acha que o valor está correto, mas esse erro ainda está acontecendo, peça ajuda ao fornecedor de hardware.  <br/> |
|Dispositivo atribuído a outro locatário  <br/> |Se você vir esse erro, significa que o valor fornecido no arquivo CSV para o número de série ou a chave do produto de um ou mais dispositivos não está correto. Primeiro, verifique se o valor foi digitado corretamente. Se você acha que o valor está correto, mas esse erro ainda está acontecendo, peça ajuda ao fornecedor de hardware.  <br/> |
|O arquivo CSV contém um número de série inválido ou uma chave de produto  <br/> |Se você vir esse erro, isso significa que o dispositivo que você está tentando registrar já está registrado por outra organização. Para corrigir esse erro, peça ajuda ao fornecedor de hardware.  <br/> |
|Este dispositivo não tem suporte para instalação usando o AutoPilot  <br/> | Esse erro significa que o dispositivo não atendem aos requisitos de implantação do AutoPilot. Os dispositivos precisam atender a esses requisitos:  <br/>  Windows 10, versão 1703 ou posteriores.  <br/>  Novos dispositivos que não passaram por Windows experiência completa.  <br/> |
|Dispositivo não encontrado  <br/> |Esse erro significa que um ou mais dispositivos no arquivo CSV não estão registrados na sua organização. Para corrigir isso, peça ajuda ao fornecedor de hardware.  <br/> |
