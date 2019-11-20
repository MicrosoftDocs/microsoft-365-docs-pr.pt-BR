---
title: Solucionar problemas de dispositivo do AutoPilot
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Saiba como solucionar erros de arquivo de dispositivo piloto automático.
ms.openlocfilehash: 1b5358bd6686c2548e82ec5297ac0ad675835718
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2019
ms.locfileid: "38718690"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Solucionar problemas de dispositivo do AutoPilot

## <a name="device-file-error-messages"></a>Mensagens de erro de arquivo de dispositivo

Veja a seguir informações sobre alguns dos erros que você pode ver enquanto estiver trabalhando com arquivos de dispositivo do AutoPilot no Microsoft 365 Business. 
  
|**Código de erro**|**Correção para tentar**|
|:-----|:-----|
|Corpo de solicitação inválido  <br/> |Esse erro deve acontecer raramente, se você vir esse erro, tente a operação novamente.  <br/> |
|O valor de hash de hardware para um dispositivo não está correto.  <br/> |Se você vir esse erro, significa que o valor que você forneceu no arquivo CSV para o hash de hardware de um dispositivo não está correto. Primeiro, verifique se o valor foi digitado corretamente. Se você achar que o valor está correto, mas esse erro ainda está ocorrendo, peça ajuda ao fornecedor do hardware.  <br/> |
|Dispositivo atribuído a outro locatário  <br/> |Se você vir esse erro, significa que o valor que você forneceu no arquivo CSV para o número de série ou a chave de produto de um ou mais dispositivos está incorreto. Primeiro, verifique se o valor foi digitado corretamente. Se você achar que o valor está correto, mas esse erro ainda está ocorrendo, peça ajuda ao fornecedor do hardware.  <br/> |
|O arquivo CSV contém um número de série ou chave de produto inválida  <br/> |Se você vir esse erro, significa que o dispositivo que você está tentando registrar já está registrado por outra organização. Para corrigir esse erro, peça ajuda ao fornecedor do hardware.  <br/> |
|Este dispositivo não tem suporte para a instalação usando o AutoPilot  <br/> | Este erro significa que o dispositivo não atende aos requisitos de implantação do AutoPilot. Os dispositivos precisam atender a esses requisitos:  <br/>  Windows 10, versão 1703 ou posteriores.  <br/>  Novos dispositivos que não foram transferidos pela experiência inicial pelo Windows.  <br/> |
|Dispositivo não encontrado  <br/> |Esse erro significa que um ou mais dispositivos no seu arquivo CSV não estão registrados na sua organização. Para corrigir isso, peça ajuda ao fornecedor do hardware.  <br/> |
