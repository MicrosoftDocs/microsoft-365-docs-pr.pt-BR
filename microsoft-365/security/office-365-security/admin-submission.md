---
title: Envios de administradores no Office 365, envios do O365, problema do Office 365 spam, o O365 falso negativo, enviar phishing no Office 365, enviar email para verificação, email suspeito no Office 365, examinar um email, fazer com que a Microsoft examine o phishing, peça à Microsoft para spam, enviar email, enviar emails, emails do dodgy, email de ator ruim, email suspeito, não confiável, relatar emails de phishing para a Microsoft, relatar emails de phishing para a Microsoft, relatar emails mal-intencionados para a Microsoft, relatar emails de golpes à Microsoft, relatar malwares em email para a Microsoft, spam email na caixa de entrada Office 365, vírus no email do Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Saiba como enviar emails suspeitos, emails de phishing suspeitos, spam e outras mensagens, URLs e arquivos potencialmente nocivos do seu locatário do Office 365 para a Microsoft para verificação.
ms.openlocfilehash: a12981ee302ea72e112826104996fb775e4ac3fb
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599978"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a>Como enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para a verificação do Office 365

Os administradores podem enviar emails usando ID de mensagem de arquivo ou rede, URLs e arquivos para verificação da Microsoft no Office 365.
A seção de envios atualizados ainda inclui mensagens relatadas pelo usuário e estão disponíveis para todos os clientes que usam o EOP.

Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email. As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).

## <a name="how-to-direct-suspicious-content-to-microsoft-for-office-365-scanning"></a>Como direcionar conteúdo suspeito para a Microsoft para a verificação do Office 365

Para enviar conteúdo à Microsoft, clique no botão **novo envio** no lado superior esquerdo da página envios. Um submenu no lado direito da página aparece com a opção de enviar um email, uma URL ou um arquivo.

### <a name="submit-a-questionable-email-to-microsoft"></a>Enviar um email questionável à Microsoft

![Exemplo de envio de email](../media/submission-flyout-email.PNG)

1. Para enviar um email, selecione **email** e ESPECIFIQUE a **ID da mensagem da rede** de email ou carregue o arquivo de email.

2. Especifique o (s) destinatário (s) em relação ao qual você gostaria de executar a verificação de política. A verificação de política determinará se o email ignorou a verificação devido a políticas de nível de usuário ou locatário.

3. Especifique se o email deve ter sido bloqueado ou não. Se o email tiver sido bloqueado, especifique se ele deve ter sido bloqueado como spam, phishing ou malware. Se você não tiver certeza de qual tipo pode ser, use a melhor Judgement.

   - Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.

   - Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos. Você verá informações adicionais sobre o envio clicando no link status. Isso inclui os resultados da verificação de política e a veredicto de nova verificação. Observação isso não executa o email por meio da pilha de filtragem completa do Office 365 ATP novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.

4. Clique no botão **Enviar** .

### <a name="send-a-suspect-url-to-microsoft"></a>Enviar uma URL suspeita para a Microsoft

![Exemplo de envio de email](../media/submission-url-flyout.png)

1. Para enviar **uma URL de seleção de** URL do submenu. Digite a URL completa incluindo o protocolo (**https://**).

   Se você tiver selecionado o **deve ter sido filtrado**, especifique se a URL é phishing ou malware.

2. Clique no botão **Enviar** .

### <a name="submit-a-suspected-file-to-microsoft"></a>Enviar um arquivo suspeito para a Microsoft

![Exemplo de envio de email](../media/submission-file-flyout.PNG)

1. Para enviar **um arquivo de seleção de** arquivo do submenu e carregar o arquivo que você deseja verificar.

2. Clique no botão **Enviar** .

## <a name="related-topics"></a>Tópicos relacionados

[Plano 2 de proteção avançada contra ameaças do Office 365](office-365-ti.md)

[Proteção contra ameaças no Office 365](protect-against-threats.md)

[Exibir relatórios para a proteção avançada contra ameaças do Office 365](view-reports-for-atp.md)
