---
title: Preterindo o aplicativo Visualizador de Criptografia de Mensagens
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: O aplicativo Visualizador de Criptografia de Mensagens do Office 365 (OME) foi removido das lojas Android e Apple em 2018.
ms.openlocfilehash: 9aca6fa2c0e9b276b666ffa187e3d18f061e7224
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817860"
---
# <a name="deprecating-message-encryption-viewer-app"></a>Preterindo o aplicativo Visualizador de Criptografia de Mensagens

Em 15 de agosto de 2018, removemos o aplicativo móvel Visualizador de Criptografia de Mensagens (OME) do Office 365 das lojas Android e Apple. O aplicativo móvel Visualizador de Criptografia de Mensagens do Office 365 era necessário para ler mensagens de email e anexos que eram criptografados com a versão anterior do OME em telefones Apple e Android. Além de remover o aplicativo Visualizador OME, não estamos fazendo outras alterações na versão anterior do OME.
  
## <a name="changes-from-august-2018"></a>Alterações de agosto de 2018

Conforme anunciado em setembro de 2017, lançamos uma nova versão da Criptografia de Mensagens do [Office 365](https://aka.ms/ome2017) para que os usuários possam enviar mensagens criptografadas e protegidas para qualquer pessoa dentro ou fora da organização sem a necessidade do aplicativo móvel. Desde então, adicionamos recursos adicionais:
  
- [Modelo somente criptografar](https://aka.ms/encryptonly)

- [Controle para descriptografar anexos](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)
    
Com essa alteração, os usuários não poderão mais baixar o aplicativo móvel Visualizador de Criptografia de Mensagens do Office 365 a partir de 1º de agosto. Como resultado, os destinatários de email podem não conseguir ler mensagens criptografadas com a versão anterior do OME em alguns dispositivos móveis Android e Apple. No entanto, eles ainda poderão ler essas mensagens em computadores pessoais (por meio de navegadores da área de trabalho). Os usuários que já baixaram o aplicativo continuarão a usá-lo.
  
## <a name="why-this-change-was-made"></a>Por que essa alteração foi feita

A nova versão do OME não exige mais que um aplicativo móvel leia anexos e mensagens de email protegidas. Os clientes que usam os novos recursos do OME podem exibir a mensagem protegida no Outlook Mobile e os não clientes podem exibir mensagens protegidas em um navegador.
  
Exigir que os usuários baixem um aplicativo móvel é outro obstáculo para os clientes exibirem mensagens protegidas. Os novos recursos de Criptografia de Mensagens do Office 365 proporcionam uma melhor experiência móvel.
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>Ainda posso usar a versão anterior da Criptografia de Mensagem do Office 365

No entanto, a versão anterior da Criptografia de Mensagens do Office 365 não será preterida no momento, no entanto, fizemos melhorias significativas na nova versão da Criptografia de Mensagens do Office 365, o que facilita a criptografia e os direitos de proteção de dados confidenciais para qualquer pessoa e em qualquer dispositivo, incluindo a capacidade dos usuários lerem mensagens protegidas diretamente no Outlook (área de trabalho, dispositivos móveis e web). 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>O que preciso fazer para me preparar para essa alteração

Se sua organização atualmente envia anexos criptografados para destinatários que exigem o aplicativo Visualizador OME, você deve atualizar seus recursos de documentação e treinamento.
  
É recomendável atualizar as regras de fluxo de emails existentes do Exchange para usar a versão atual do OME para que sua organização possa aproveitar os recursos novos e aprimorados. Depois de configurar os novos recursos do OME, os destinatários não precisarão do aplicativo Visualizador do OME para ler mensagens criptografadas em dispositivos móveis.
  
A Microsoft recomenda que você faça um plano para mudar para os novos recursos do OME assim que for razoável para sua organização. Para obter instruções, confira Configurar novos recursos de Criptografia de Mensagem do [Office 365.](set-up-new-message-encryption-capabilities.md) Se você quiser saber mais sobre como os novos recursos funcionam primeiro, confira a Criptografia de Mensagem do [Office 365.](ome.md)
  

