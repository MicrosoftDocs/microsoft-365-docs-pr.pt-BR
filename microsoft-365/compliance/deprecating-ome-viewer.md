---
title: Reprovando o aplicativo visualizador de criptografia de mensagens do Office 365
ms.author: krowley
author: kccross
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
description: No dia 15 de agosto de 2018, iremos remover o aplicativo móvel do Visualizador de criptografia de mensagens do Office 365 (OME) do Android e dos repositórios da Apple. O aplicativo móvel Office 365 Message Encryption Viewer era necessário para ler mensagens de email e anexos que foram criptografados com a versão anterior do OME em telefones Apple e Android. Além de remover o aplicativo OME Viewer, não estamos fazendo outras alterações na versão anterior do OME.
ms.openlocfilehash: 3b5c92d4fa700a1ae8d7b104e33100301cf43506
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37071956"
---
# <a name="deprecating-office-365-message-encryption-viewer-app"></a>Reprovando o aplicativo visualizador de criptografia de mensagens do Office 365

No dia 15 de agosto de 2018, removemos o aplicativo móvel do Visualizador de criptografia de mensagens do Office 365 (OME) do Android e dos repositórios da Apple. O aplicativo móvel Office 365 Message Encryption Viewer era necessário para ler mensagens de email e anexos que foram criptografados com a versão anterior do OME em telefones Apple e Android. Além de remover o aplicativo OME Viewer, não estamos fazendo outras alterações na versão anterior do OME.
  
## <a name="changes-from-august-2018"></a>Alterações de agosto de 2018

Conforme anunciado em setembro de 2017, lançamos uma nova versão da [criptografia de mensagem do Office 365](https://aka.ms/ome2017) para que os usuários possam enviar mensagens criptografadas e protegidas para qualquer pessoa dentro ou fora da organização, sem a necessidade do aplicativo móvel. Desde então, adicionamos recursos adicionais:
  
- [Modelo somente criptografia](https://aka.ms/encryptonly)

- [Controle para descriptografar anexos](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
Com essa alteração, os usuários não poderão mais baixar o aplicativo móvel do Office 365 Message Encryption Viewer, começando em 1º de agosto. Como resultado, os destinatários de email podem não conseguir ler mensagens criptografadas com a versão anterior do OME em alguns dispositivos móveis Android e Apple. No entanto, eles ainda poderão ler essas mensagens em computadores pessoais (por meio de navegadores da área de trabalho). Os usuários que já baixaram o aplicativo continuarão a ser capazes de usá-lo.
  
## <a name="why-this-change-was-made"></a>Por que essa alteração foi feita

A nova versão do OME não requer mais um aplicativo móvel para ler mensagens de email e anexos protegidos. Os clientes do Office 365 que usam os novos recursos do OME podem exibir a mensagem protegida no Outlook Mobile e os clientes não-Office 365 podem exibir mensagens protegidas em um navegador.
  
Exigir que os usuários baixem um aplicativo móvel é outro obstáculo para os clientes exibirem mensagens protegidas. Os novos recursos de criptografia de mensagem do Office 365 oferecem uma experiência móvel melhor.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>Ainda posso usar a versão anterior da criptografia de mensagem do Office 365

A versão anterior da criptografia de mensagem do Office 365 não será preterida no momento, no entanto, fizemos melhorias significativas na nova versão da criptografia de mensagem do Office 365, o que facilita a criptografia e os direitos de proteção de dados confidenciais para qualquer pessoa e, em qualquer dispositivo, incluindo a capacidade de os usuários do Office 365 lerem mensagens protegidas diretamente no Outlook (desktop, Mobile e Web). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que eu preciso fazer para se preparar para essa alteração

Se sua organização envia atualmente anexos criptografados para destinatários que exigem o aplicativo visualizador do OME, você deve atualizar a documentação e os recursos de treinamento.
  
Recomendamos a atualização de regras de fluxo de emails existentes do Exchange para usar a versão atual do OME para que sua organização possa aproveitar os recursos novos e aprimorados. Depois de configurar os novos recursos do OME, os destinatários não precisarão que o aplicativo do OME Viewer Leia mensagens criptografadas em dispositivos móveis.
  
A Microsoft recomenda que você faça um plano para migrar para os novos recursos do OME assim que for razoável para sua organização. Para obter instruções, consulte [configurar novos recursos de criptografia de mensagem do Office 365](set-up-new-message-encryption-capabilities.md). Se quiser saber mais sobre como os novos recursos funcionam primeiro, confira criptografia de [mensagem do Office 365](ome.md).
  

