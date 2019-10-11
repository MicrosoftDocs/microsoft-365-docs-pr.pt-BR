---
title: Inteligência de fluxo de emails no Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: Os administradores podem saber mais sobre os códigos de erro associados à entrega de mensagens usando conectores no Office 365 (também conhecido como inteligência de fluxo de emails).
ms.openlocfilehash: 088af4b6924fde0277901a19437d17c4506ff22b
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441538"
---
# <a name="mail-flow-intelligence-in-office-365"></a>Inteligência de fluxo de emails no Office 365

Normalmente, você usa um conector para rotear mensagens de email da sua organização do Office 365 para seu ambiente de email local. Você também pode usar um conector para rotear mensagens do Office 365 para uma organização de parceiro. Quando o Office 365 não pode entregar essas mensagens por meio do conector, elas são enfileiradas no Office 365. O Office 365 continuará a tentar a entrega de cada mensagem por 48 horas. Após 48 horas, a mensagem na fila expirará, e a mensagem será retornada ao remetente original em uma notificação de falha na entrega (também conhecida como uma mensagem de erro NDR ou de retorno).

O Office 365 gera um erro quando uma mensagem não pode ser entregue usando um conector. Os erros mais comuns e suas soluções são descritos neste tópico. Coletivamente, os erros de enfileiramento e notificação para mensagens não entregues enviadas via conectores são conhecidos como _inteligência de fluxo de emails_.

## <a name="error-code-450-44312-dns-query-failed"></a>Código de erro: 450 4.4.312 de consulta DNS falhou

Normalmente, esse erro significa que o Office 365 tentou se conectar ao host inteligente especificado no conector, mas a consulta DNS para localizar os endereços IP do host inteligente falhou. As possíveis causas para esse erro são:

- Há um problema com o serviço de hospedagem DNS do seu domínio (o participante que mantém os servidores de nomes autoritativos para seu domínio).

- Seu domínio expirou recentemente, portanto, o registro MX não pode ser recuperado.

- O registro MX do seu domínio mudou recentemente e os servidores DNS do Office 365 ainda têm informações de DNS armazenadas em cache anteriormente para o seu domínio.

### <a name="how-do-i-fix-error-code-450-44312"></a>Como corrigir o código de erro 450 4.4.312?

- Trabalhe com seu serviço de hospedagem DNS para identificar e corrigir o problema com seu domínio.

- Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), entre em contato com seu parceiro para corrigir o problema.

## <a name="error-code-450-44315-connection-timed-out"></a>Código de erro: 450 conexão 4.4.315 atingiu o tempo limite

Normalmente, isso significa que o Office 365 não pode se conectar ao servidor de email de destino. Os detalhes do erro explicarão o problema. Por exemplo:

- Seu servidor de email local está inoperante.

- Há um erro nas configurações de host inteligente do conector, portanto, o Office 365 está tentando se conectar ao endereço IP errado.

### <a name="how-do-i-fix-error-code-450-44315"></a>Como corrigir o código de erro 450 4.4.315?

- Descubra qual cenário se aplica a você e faça as correções necessárias. Por exemplo, se o fluxo de emails estiver funcionando corretamente e você não tiver alterado as configurações do conector, você precisará verificar seu ambiente de email local para ver se o servidor está inoperante ou se houve alguma alteração na infraestrutura de rede (por exemplo, Você alterou provedores de serviços de Internet, portanto, agora tem endereços IP diferentes).

- Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), entre em contato com seu parceiro para corrigir o problema.

## <a name="error-code-450-44316-connection-refused"></a>Código de erro: 450 4.4.316 conexão recusada

Normalmente, esse erro significa que o Office 365 encontrou um erro de conexão ao tentar se conectar ao servidor de email de destino. Uma causa provável desse erro é o Firewall Bloquear conexões de endereços IP do Office 365. Ou, esse erro pode ser por design se você tiver migrado completamente seu sistema de email local para o Office 365 e desligar o ambiente de email local.

### <a name="how-do-i-fix-error-code-450-44316"></a>Como corrigir o código de erro 450 4.4.316?

- Se você tiver caixas de correio em seu ambiente local, precisará modificar suas configurações de firewall para permitir conexões de endereços IP 365 do Office na porta 25 TCP para seus servidores de email locais. Para obter uma lista dos endereços IP do Office 365, confira [URLs e intervalos de endereços IP do office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).

- Se não houver mais mensagens a serem entregues ao seu ambiente local, clique em **corrigir agora** no alerta para que o Office 365 possa rejeitar imediatamente as mensagens com destinatários inválidos. Isso reduzirá o risco de exceder a cota da organização para destinatários inválidos, o que pode afetar a entrega de mensagens normal. Ou você pode usar as seguintes instruções para corrigir manualmente o problema:

  - No [centro de administração do Exchange (Eat)](https://docs.microsoft.com/Exchange/exchange-admin-center) no Office 365, desabilite ou exclua o conector que entrega emails do Office 365 para seu ambiente de email local:

    1. No Eat, vá para \> **conectores**de **fluxo de emails** .

    2. Selecione o conector com o valor **de do** **Office 365** e o valor **para para** o **servidor de email da sua organização** e execute uma das seguintes etapas:

       - Exclua o conector clicando no ícone **excluir** ![remover](../media/adf01106-cc79-475c-8673-065371c1897b.gif)

       - Desabilite o conector clicando em **Editar** ![ícone](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) de edição e desmarcando **ativá-lo**.

  - Altere o domínio aceito no Office 365 associado ao seu ambiente de email local da **retransmissão interna** para **autoritativa**. Para obter instruções, consulte [gerenciar domínios aceitos no Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).

  **Observação**: normalmente, essas alterações levam entre 30 minutos e uma hora para entrar em vigor. Após uma hora, verifique se você não receberá mais o erro.

- Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a>Código de erro: 450 4.4.317 não pode se conectar ao servidor remoto

Normalmente, esse erro significa que o Office 365 está conectado ao servidor de email de destino, mas o servidor respondeu com um erro imediato ou não atende aos requisitos de conexão. Os detalhes do erro explicarão o problema. Por exemplo:

- O servidor de email de destino respondeu com um erro "serviço não disponível", que indica que o servidor não pode manter a comunicação com o Office 365.

- O conector é configurado para exigir TLS, mas o servidor de email de destino não dá suporte a TLS.

### <a name="how-do-i-fix-error-code-450-44317"></a>Como corrigir o código de erro 450 4.4.317?

- Verifique as configurações e os certificados de TLS nos seus servidores de email locais e as configurações de TLS no conector.

- Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a>Código de erro: 450 4.4.318 conexão foi fechada abruptamente

Normalmente, esse erro significa que o Office 365 está tendo dificuldade para se comunicar com seu ambiente de email local, portanto, a conexão foi interrompida. As possíveis causas para esse erro são:

- O firewall usa regras de exame de pacotes SMTP e essas regras não estão funcionando corretamente.

- Seu servidor de email local não está funcionando corretamente (por exemplo, bloqueios de serviço, panes ou recursos de sistema Baixos), que está causando o tempo limite do servidor e fecha a conexão com o Office 365.

- Há problemas de rede entre seu ambiente local e o Office 365.

### <a name="how-do-i-fix-error-code-450-44318"></a>Como corrigir o código de erro 450 4.4.318?

- Descubra qual cenário se aplica a você e faça as correções necessárias.

- Se o problema for causado por problemas de rede entre seu ambiente local e o Office 365, entre em contato com sua equipe de rede para solucionar o problema.

- Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.

## <a name="error-code-450-47320-certificate-validation-failed"></a>Código de erro: 450 falha na validação do certificado 4.7.320

Normalmente, esse erro significa que o Office 365 encontrou um erro ao tentar validar o certificado do servidor de email de destino. Os detalhes do erro explicarão o erro. Por exemplo:

- Certificado expirado

- Incompatibilidade de entidade do certificado

- O certificado não é mais válido

### <a name="how-do-i-fix-error-code-450-47320"></a>Como corrigir o código de erro 450 4.7.320?

- Corrija o certificado ou as configurações no conector para que as mensagens em fila no Office 365 possam ser entregues.

- Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.

## <a name="other-error-codes"></a>Outros códigos de erro

O Office 365 está com dificuldades para entregar mensagens ao seu servidor de email local ou de parceiro. Use as informações do **servidor de destino** no erro para examinar o problema no seu ambiente ou modifique o conector se houver um erro de configuração.

Se o erro for da organização de seu parceiro (por exemplo, um provedor de serviços de nuvem de terceiros), você precisará entrar em contato com seu parceiro para corrigir o problema.
