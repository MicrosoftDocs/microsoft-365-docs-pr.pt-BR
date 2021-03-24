---
title: Inteligência de fluxo de emails
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Os administradores podem aprender sobre os códigos de erro associados à entrega de mensagens usando conectores (também conhecidos como inteligência de fluxo de emails).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2cb52e5865415440b3b2924a3ebcc96a7f8e17e5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053165"
---
# <a name="mail-flow-intelligence-in-eop"></a>Inteligência de fluxo de emails no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Em organizações do Microsoft 365 com caixas de correio no Exchange Online ou organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, normalmente você usa um conector para rotear mensagens de email do EOP para seu ambiente de email local. Você também pode usar um conector para rotear mensagens do Microsoft 365 para uma organização parceira. Quando o Microsoft 365 não pode entregar essas mensagens por meio do conector, elas estão na fila no Microsoft 365. O Microsoft 365 continuará a repetir a entrega para cada mensagem por 24 horas. Após 24 horas, a mensagem em fila expirará, e a mensagem será retornada para o remetente original em um relatório de não entrega (também conhecido como uma mensagem de NDR ou bounce).

O Microsoft 365 gera um erro quando uma mensagem não pode ser entregue usando um conector. Os erros mais comuns e suas soluções são descritos neste artigo. Coletivamente, erros de fila e notificação para mensagens não entregues enviadas por meio de conectores é conhecido como inteligência de _fluxo de emails._

## <a name="error-code-450-44312-dns-query-failed"></a>Código de erro: falha na consulta DNS 450 4.4.312

Normalmente, esse erro significa que o Microsoft 365 tentou se conectar ao host inteligente especificado no conector, mas a consulta DNS para encontrar os endereços IP do host inteligente falhou. As possíveis causas desse erro são:

- Há um problema com o serviço de hospedagem DNS do seu domínio (a parte que mantém os servidores de nomes autoritativos para seu domínio).

- Seu domínio expirou recentemente, portanto, o registro MX não pode ser recuperado.

- O registro MX do seu domínio foi alterado recentemente, e os servidores DNS ainda têm informações DNS armazenadas anteriormente em cache para seu domínio.

### <a name="how-do-i-fix-error-code-450-44312"></a>Como corrigir o código de erro 450 4.4.312?

- Trabalhe com seu serviço de hospedagem DNS para identificar e corrigir o problema com seu domínio.

- Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), contate seu parceiro para corrigir o problema.

## <a name="error-code-450-44315-connection-timed-out"></a>Código de erro: 450 4.4.315 Tempo de conexão

Normalmente, isso significa que o Microsoft 365 não pode se conectar ao servidor de email de destino. Os detalhes do erro explicarão o problema. Por exemplo:

- Seu servidor de email local está inoossado.

- Há um erro nas configurações de host inteligente do conector, portanto, o Microsoft 365 está tentando se conectar ao endereço IP errado.

### <a name="how-do-i-fix-error-code-450-44315"></a>Como corrigir o código de erro 450 4.4.315?

- Descubra qual cenário se aplica a você e faça as correções necessárias. Por exemplo, se o fluxo de emails estiver funcionando corretamente e você não tiver alterado as configurações do conector, você precisará verificar seu ambiente de email local para ver se o servidor está inoportu ou se houve alterações na infraestrutura de rede (por exemplo, você alterou provedores de serviços de Internet, portanto, agora tem endereços IP diferentes).

- Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), contate seu parceiro para corrigir o problema.

## <a name="error-code-450-44316-connection-refused"></a>Código de erro: 450 4.4.316 Conexão recusada

Normalmente, esse erro significa que o Microsoft 365 encontrou um erro de conexão ao tentar se conectar ao servidor de email de destino. Uma causa provável para esse erro é que o firewall está bloqueando conexões de endereços IP do Microsoft 365. Ou, esse erro pode ser por design se você tiver migrado completamente seu sistema de email local para o Microsoft 365 e desligado seu ambiente de email local.

### <a name="how-do-i-fix-error-code-450-44316"></a>Como corrigir o código de erro 450 4.4.316?

- Se você tiver caixas de correio em seu ambiente local, precisará modificar suas configurações de firewall para permitir conexões de endereços IP do Microsoft 365 na porta TCP 25 para seus servidores de email locais. Para ver uma lista dos endereços IP do Microsoft 365, consulte URLs e intervalos de [endereços IP do Microsoft 365.](../../enterprise/urls-and-ip-address-ranges.md)

- Se nenhuma mensagem mais deve ser entregue ao seu ambiente local, clique em **Corrigir** agora no alerta para que o Microsoft 365 possa rejeitar imediatamente as mensagens com destinatários inválidos. Isso reduzirá o risco de exceder a cota da sua organização para destinatários inválidos, o que pode afetar a entrega normal de mensagens. Ou você pode usar as instruções a seguir para corrigir manualmente o problema:

  - No Centro de administração do [Exchange (EAC),](/Exchange/exchange-admin-center)desabilite ou exclua o conector que entrega emails do Microsoft 365 para seu ambiente de email local:

    1. No EAC, vá para **Conectores de fluxo** \> **de emails.**

    2. Selecione o conector com o **valor De** do **Office 365** e o **servidor** de **email** da sua organização para valor e faça uma das seguintes etapas:

       - Excluir o conector clicando em **Excluir** ![ Ícone remover](../../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Desabilite o conector clicando em **Editar** ![ Ícone de Edição e ](../../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) desblicando **Abilitar**.

  - Altere o domínio aceito no Microsoft 365 associado ao seu ambiente de email local de **Retransmissão** Interna para **Autoritativa**. Para obter instruções, [consulte Gerenciar domínios aceitos no Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains).

  **Observação**: normalmente, essas alterações levam entre 30 minutos e uma hora para fazer efeito. Após uma hora, verifique se você não recebe mais o erro.

- Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Código de erro: 450 4.4.317 Não é possível se conectar ao servidor remoto

Normalmente, esse erro significa que o Microsoft 365 se conectou ao servidor de email de destino, mas o servidor respondeu com um erro imediato ou não responde aos requisitos de conexão. Os detalhes do erro explicarão o problema. Por exemplo:

- O servidor de email de destino respondeu com um erro "Serviço não disponível", que indica que o servidor não consegue manter a comunicação com o Microsoft 365.

- O conector é configurado para exigir TLS, mas o servidor de email de destino não dá suporte a TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Como corrigir o código de erro 450 4.4.317?

- Verifique as configurações e certificados TLS em seus servidores de email locais e as configurações TLS no conector.

- Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Código de erro: 450 4.4.318 A conexão foi fechada abruptamente

Normalmente, esse erro significa que o Microsoft 365 está tendo dificuldades para se comunicar com seu ambiente de email local, portanto, a conexão foi retirada. As possíveis causas desse erro são:

- O firewall usa regras de exame de pacotes SMTP e essas regras não estão funcionando corretamente.

- Seu servidor de email local não está funcionando corretamente (por exemplo, travamentos de serviço, falhas ou recursos de sistema baixos), o que está fazendo com que o servidor se desajuste e feche a conexão com o Microsoft 365.

- Há problemas de rede entre seu ambiente local e o Microsoft 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Como corrigir o código de erro 450 4.4.318?

- Descubra qual cenário se aplica a você e faça as correções necessárias.

- Se o problema for causado por problemas de rede entre seu ambiente local e o Microsoft 365, contate sua equipe de rede para solucionar o problema.

- Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Código de erro: falha na validação do certificado 450 4.7.320

Normalmente, esse erro significa que o Microsoft 365 encontrou um erro ao tentar validar o certificado do servidor de email de destino. Os detalhes do erro explicarão o erro. Por exemplo:

- Certificado expirado

- Incompatibilidade de assunto do certificado

- O certificado não é mais válido

### <a name="how-do-i-fix-error-code-450-47320"></a>Como corrigir o código de erro 450 4.7.320?

- Correção do certificado ou das configurações no conector para que as mensagens em fila no Microsoft 365 possam ser entregues.

- Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.

## <a name="other-error-codes"></a>Outros códigos de erro

O Microsoft 365 está com dificuldades para entregar mensagens ao servidor de email local ou parceiro. Use as **informações do servidor** de destino no erro para examinar o problema em seu ambiente ou modificar o conector se houver um erro de configuração.

Se o erro for da sua organização parceira (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.