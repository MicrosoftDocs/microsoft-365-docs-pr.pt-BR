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
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864859"
---
# <a name="troubleshoot-autopilot-device-errors"></a>Solucionar problemas do dispositivo AutoPilot

## <a name="device-file-error-messages"></a>Mensagens de erro do arquivo de dispositivo

Info aqui está em alguns dos erros que você pode ver ao trabalhar com arquivos de dispositivo de piloto automático no Microsoft 365 Business. 
  
|**Código de erro**|**Corrigir tentar**|
|:-----|:-----|
|Corpo de solicitação inválida  <br/> |Esse erro deve acontecer raramente, se você vir esse erro, tente a operação novamente.  <br/> |
|Valor de hash de hardware para um dispositivo não está correto.  <br/> |Se você vir esse erro, significa que o valor fornecido no arquivo CSV para o hash de hardware de um dispositivo não estiverem correto. Primeiro, verifique se o valor foi digitado corretamente. Se você achar que o valor está correto, mas esse erro ainda está ocorrendo, peça ajuda ao seu fornecedor de hardware.  <br/> |
|Dispositivo atribuído ao outro locatário  <br/> |Se você vir esse erro, significa que o valor fornecido no seu arquivo CSV para o número de série ou a chave de produto de um ou mais dispositivos não estiverem correto. Primeiro, verifique se o valor foi digitado corretamente. Se você achar que o valor está correto, mas esse erro ainda está ocorrendo, peça ajuda ao seu fornecedor de hardware.  <br/> |
|O arquivo CSV contém um número de série inválido ou a chave do produto  <br/> |Se você vir esse erro significa que o dispositivo que você está ao registrar tentar já está registrado por uma outra organização. Para corrigir esse problema, peça ao seu fornecedor de hardware para obter ajuda.  <br/> |
|Este dispositivo não é suportado para a instalação usando o piloto automático  <br/> | Este erro indica que o dispositivo não atende aos requisitos de implantação do piloto automático. Dispositivos precisam atender a estes requisitos:  <br/>  Windows 10, versão 1703 ou posteriores.  <br/>  Novos dispositivos que ainda não passaram pela configuração inicial pelo usuário do Windows.  <br/> |
|Dispositivo não encontrado  <br/> |Este erro indica que um ou mais dispositivos em seu arquivo CSV não é registrado para sua organização. Para corrigir esse problema, peça ao seu fornecedor de hardware para obter ajuda.  <br/> |
   
