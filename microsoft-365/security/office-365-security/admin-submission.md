---
title: Envios de administradores, envios, problemas de spam, falso negativo, enviar phishing, enviar email para verificação, email suspeito no Office 365, examinar um email, fazer com que a Microsoft examine o phishing, peça à Microsoft para spam, enviar emails, enviar emails, emails do dodgy, email de ator ruim, email suspeito e não confiável, relatar emails de Phish para a Microsoft, relatar emails de phishing para a Microsoft , relatar malware em email para a Microsoft, email de spam na caixa de entrada, vírus em email
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Saiba como enviar emails suspeitos, emails de phishing, spam e outras mensagens, URLs e arquivos potencialmente nocivos da sua empresa para a Microsoft para verificação.
ms.openlocfilehash: 2d86555854f9babd202764f1bad8b548daf52c70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631376"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usar o Envio do Administrador para enviar spam, phishing, URLs e arquivos à Microsoft

Se você for um administrador em uma organização do Microsoft 365 com caixas de correio no Exchange Online, você pode usar o portal de envios no centro de conformidade de & de segurança para enviar mensagens de email, URLs e anexos para a Microsoft para verificação.

Ao enviar um email, você receberá informações sobre qualquer política que possa ter permitido o email de entrada em seu locatário, bem como o exame de qualquer URL e anexo no email. As políticas que podem ter permitido um email incluem a lista de remetentes confiáveis de um usuário individual, bem como políticas de nível de locatário, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte).

Para obter outras maneiras de enviar mensagens de email, URLs e anexos para a Microsoft, consulte 

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Abra o Centro de Conformidade e Segurança em <https://protection.office.com/>. Para ir diretamente para a página de **envio** , <https://protection.office.com/reportsubmission>use.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para se conectar ao PowerShell da Proteção do Exchange Online autônoma, confira [Conectar ao PowerShell da Proteção do Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Você precisa receber permissões para executar esses procedimentos. Para adicionar, modificar e excluir políticas antispam, você precisa ser membro dos grupos de função de gerenciamento da **organização**, **administrador de segurança**ou **leitor de segurança** . Para obter mais informações sobre grupos de função no centro de conformidade de & de segurança, consulte [permissões no centro de conformidade de & de segurança](permissions-in-the-security-and-compliance-center.md).

- Para obter mais informações sobre como os usuários podem enviar mensagens e arquivos para a Microsoft, consulte [relatar mensagens e arquivos para a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="how-to-direct-suspicious-content-to-microsoft-scanning"></a>Como direcionar conteúdo suspeito para a verificação da Microsoft

Para enviar conteúdo à Microsoft, clique no botão **novo envio** no lado superior esquerdo da página envios. Um submenu no lado direito da página aparece com a opção de enviar um email, uma URL ou um arquivo.

### <a name="submit-a-questionable-email-to-microsoft"></a>Enviar um email questionável à Microsoft

![Exemplo de envio de email](../../media/submission-flyout-email.PNG)

1. Para enviar um email, selecione **email** e ESPECIFIQUE a **ID da mensagem da rede** de email ou carregue o arquivo de email.

2. Especifique o (s) destinatário (s) em relação ao qual você gostaria de executar a verificação de política. A verificação de política determinará se o email ignorou a verificação devido a políticas de nível de usuário ou locatário.

3. Especifique se o email deve ter sido bloqueado ou não. Se o email tiver sido bloqueado, especifique se ele deve ter sido bloqueado como spam, phishing ou malware. Se você não tiver certeza de qual tipo pode ser, use o melhor julgamento.

   - Se o filtro tiver sido ignorado devido às políticas após o envio, você verá informações sobre essa política.

   - Se o filtro não tiver sido ignorado devido a uma ou mais políticas, a verificação será concluída em vários minutos. Você verá informações adicionais sobre o envio clicando no link status. Isso inclui os resultados da verificação de política e a veredicto de nova verificação. Observação isso não executa o email por meio da pilha de filtragem completa do Office 365 ATP novamente, mas executa uma verificação parcial com base em determinados atributos do email, da URL ou do arquivo.

4. Clique no botão **Enviar** .

### <a name="send-a-suspect-url-to-microsoft"></a>Enviar uma URL suspeita para a Microsoft

![Exemplo de envio de email](../../media/submission-url-flyout.png)

1. Para enviar **uma URL de seleção de** URL do submenu. Digite a URL completa incluindo o protocolo (**https://**).

   Se você tiver selecionado o **deve ter sido filtrado**, especifique se a URL é phishing ou malware.

2. Clique no botão **Enviar** .

### <a name="submit-a-suspected-file-to-microsoft"></a>Enviar um arquivo suspeito para a Microsoft

![Exemplo de envio de email](../../media/submission-file-flyout.PNG)

1. Para enviar **um arquivo de seleção de** arquivo do submenu e carregar o arquivo que você deseja verificar.

2. Clique no botão **Enviar** .
