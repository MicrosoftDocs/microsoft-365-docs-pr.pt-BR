---
title: Adicionar registros DNS para conectar seu domínio
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: Conectar um domínio em qualquer provedor de host DNS ao Microsoft 365, verificando seu domínio e atualizando os registros DNS na conta do seu registrador.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 62b6793dd97e146b703c82e0ba23f4d7414025b6
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623972"
---
# <a name="add-dns-records-to-connect-your-domain"></a>Adicionar registros DNS para conectar seu domínio

Caso tenha comprado um domínio de um provedor de hospedagem de terceiros, você poderá conectá-lo ao Microsoft 365 atualizando os registros DNS na conta do seu registrador.

Ao concluir essas etapas, seu domínio permanecerá registrado no host do qual você comprou o domínio, mas o Microsoft 365 poderá usá-lo para seus endereços de email (como user@yourdomain.com) e outros serviços.

Se você não adicionar um domínio, as pessoas da sua organização usarão o domínio onmicrosoft.com para os endereços de email deles até que você o faça. É importante adicionar seu domínio antes de adicionar usuários, para que você não precise configurá-los duas vezes.

[Verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml) se você não encontrar o que está procurando abaixo.

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a>Etapa 1: adicionar um registro TXT ou MX para verificar se você é proprietário do domínio

### <a name="recommended-verify-with-a-txt-record"></a>Recomendado: verificar com um registro TXT

Primeiro, você precisa provar que é o proprietário do domínio que deseja adicionar ao Microsoft 365.

1. Entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com/) e selecione **Mostrar tudo > ****Configurações** > **Domínios**.
2. Em uma nova janela ou guia do navegador, entre no seu provedor de hospedagem de DNS e, em seguida, localize o local em que você gerencia suas configurações de DNS (por exemplo, Configurações de Arquivo de Zona, Gerenciar Domínios, Gerenciador de Domínio, Gerenciador de DNS).
3. Vá para a página do Gerenciador DNS do seu provedor e adicione o registro TXT indicado no centro de administração ao seu domínio.

A adição desse registro não afetará o seu email existente ou outros serviços e você poderá removê-lo com segurança logo que o seu domínio esteja conectado ao Microsoft 365.

Exemplo:
- Nome do TXT: `@`
- Valor do TXT: MS=ms######## (ID exclusivo do centro de administração)
- TTL: `3600‎` (ou seu provedor padrão)

4. Salve o registro, volte para o centro de administração e, em seguida, selecione **Verificar**. Geralmente, leva cerca de 15 minutos para que as alterações de registro sejam registradas, mas, às vezes, pode ser mais demorado. Dê algum tempo e algumas tentativas para a mudança pegar.

Quando a Microsoft encontrar o registro TXT correto, seu domínio estará verificado.

### <a name="verify-with-an-mx-record"></a>Verificar com um registro MX

Se seu registrador não for compatível com a adição de registros TXT, é possível verificar adicionando um registro MX.

1. Entre no [Centro de administração do Microsoft 365](https://admin.microsoft.com/) e selecione **Mostrar tudo > ****Configurações** > **Domínios**.
2. Em uma nova janela ou guia do navegador, entre no seu provedor de hospedagem de DNS e, em seguida, localize o local em que você gerencia suas configurações de DNS (por exemplo, Configurações de Arquivo de Zona, Gerenciar Domínios, Gerenciador de Domínio, Gerenciador de DNS).
3. Vá para a página do Gerenciador DNS do seu provedor e adicione o registro MX indicado no centro de administração ao seu domínio.

A **Prioridade** do registro MX deve ser o maior de todos os registros MX existentes do domínio. Caso contrário, isso pode interferir no envio e recebimento de emails. Você deve excluir esses registros assim que a verificação de domínio concluir.

Verifique se os campos estão definidos para os seguintes valores:

- Tipo de Registro: `MX`
- Prioridade: definir para o maior valor disponível, geralmente `0`.
- Nome do Host: `@`
- Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.
- TTL: `3600‎` (ou seu provedor padrão)

Quando a Microsoft encontrar o registro MX correto, seu domínio será verificado.

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a>Etapa 2: adicionar registros DNS para conectar os serviços Microsoft

Em uma nova janela ou guia do navegador, entre no seu provedor de hospedagem de DNS e localize o local em que você gerencia suas configurações de DNS (por exemplo, Configurações de Arquivo de Zona, Gerenciar Domínios, Gerenciador de Domínio, Gerenciador de DNS).

Você adicionará vários tipos diferentes de registros DNS dependendo dos serviços que deseja habilitar. 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a>Adicionar um registro MX para email (Outlook, Exchange Online)
**Antes de começar:** se os usuários já têm um email com seu domínio (como user@yourdomain.com), crie suas contas no centro de administração antes de configurar seus registros MX. Dessa forma, eles continuarão a receber emails. Quando você atualiza o registro MX do domínio, todos os novos emails das pessoas que usam esse domínio agora vão para o Microsoft 365. Todos os e-mails existentes permanecem no organizador atual, a menos que você decida [migrar e-mails e contato para o Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)

Você obterá informações sobre o registro MX no assistente de configuração de domínio do centro de administração.

No site do provedor de hospedagem, crie um novo registro MX.
Verifique se os campos estão definidos para os seguintes valores:

- Tipo de Registro: `MX`
- Prioridade: definir para o maior valor disponível, geralmente `0`.
- Nome do Host: `@`
- Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.
- TTL: `3600‎` (ou seu provedor padrão)

Salve o registro e remova todos os outros registros MX.

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a>Adicionar registros CNAME para conectar outros serviços (Teams, Exchange Online, AAD, MDM)
Você obterá informações sobre os registros CNAME no assistente de configuração de domínio do centro de administração.

No site do seu provedor de hospedagem, adicione registros CNAME para cada serviço que você deseja conectar.
Verifique se os campos estão definidos para os seguintes valores para cada:

- Tipo de Registro: `CNAME (Alias)`
- Host: cole os valores copiados do centro de administração aqui.
- Pontos de endereçamento: copie o valor do centro de administração e cole-o aqui.
- TTL: `3600‎` (ou seu provedor padrão)


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a>Adicionar ou editar um registro SPF TXT para ajudar a evitar spam de email (Outlook, Exchange Online)
**Antes de começar:** se você já possui um registro SPF para seu domínio, não crie um novo para o Microsoft 365. Em vez disso, adicione os valores necessários do Microsoft 365 ao registro atual para que você tenha um *único* registro SPF que inclua os dois conjuntos de valores.

No site do seu host DNS, edite o registro SPF existente ou crie um.
Verifique se os campos estão definidos para os seguintes valores:

- Tipo de Registro: `TXT (Text)`
- Host: `@`
- Valor do TXT: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (ou seu provedor padrão)

Salve o registro.

Valide seu registro SPF usando uma destas [ferramentas de validação de SPF](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).

O SPF foi projetado para ajudar a evitar a falsificação, mas há técnicas de falsificação contra as quais o SPF não pode protegê-lo. Para se proteger contra isso, depois de configurar o SPF, você também deve configurar o DKIM e o DMARC para o Microsoft 365. 

Para começar, consulte [Usar DKIM para validar emails de saída enviados do seu domínio no Microsoft 365](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) e [Usar DMARC para validar emails no Microsoft 365](../../security/office-365-security/use-dmarc-to-validate-email.md).

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a>Adicionar registros SRV para serviços de communications (Teams, Skype for Business)

No site do seu provedor de hospedagem, adicione registros SRV para cada serviço que você deseja conectar.
Verifique se os campos estão definidos para os seguintes valores para cada:

- Tipo de Registro: `SRV (Service)`
- Nome: `@`
- Destino: copie o valor do centro de administração e cole-o aqui.
- Protocolo: copie o valor do centro de administração e cole-o aqui.
- Serviço: copie o valor do centro de administração e cole-o aqui.
- Prioridade: `100`
- Espessura: `1`
- Porta: copie o valor do centro de administração e cole-o aqui.
- TTL: `3600‎` (ou seu provedor padrão)

Salve o registro.

#### <a name="srv-record-field-restrictions-and-workarounds"></a>Restrições e soluções alternativas para campos de registro SRV
Alguns provedores de hospedagem impõem restrições aos valores dos campos dentro de registros SRV. Aqui estão algumas soluções alternativas comuns para essas restrições.

##### <a name="name"></a>Nome
Se o seu provedor de hospedagem não permitir a definição desse campo como **@**, deixe-o em branco. Use esta abordagem *apenas* quando o provedor de hospedagem tiver campos separados para os valores de Serviço e Protocolo. Caso contrário, consulte as observações a seguir sobre Serviço e Protocolo.

##### <a name="service-and-protocol"></a>Serviço e Protocolo
Caso seu provedor de hospedagem não forneça esses campos para registros SRV, você deve especificar os valores **Serviço** e **Protocolo** no campo **Nome** do registro. (Observação: dependendo do seu provedor de hospedagem, o campo **Nome** pode ser chamado de algo mais, como: **Host**, **Hostname** ou **Subdomínio**.) Para adicionar esses valores, crie uma única cadeia de caracteres e separe os valores com um ponto. 

Exemplo: `_sip._tls`

##### <a name="priority-weight-and-port-br"></a>Prioridade, Espessura e Porta <br>
Se o seu provedor de hospedagem não oferecer esses campos para registros SRV, você deve especificá-los no campo **Destino** do registro. (Observação: dependendo do seu provedor de hospedagem, o campo **Destino** pode ter outro nome, como: **Conteúdo**, **Endereço IP** ou **Host de Destino**.) 

Para adicionar esses valores, crie uma única cadeia de caracteres, separando os valores com espaços e *às vezes terminando com um ponto* (verifique com o seu provedor se não tiver certeza). Os valores devem ser incluídos nesta ordem: Prioridade, Peso, Porta, Destino. 

- Exemplo 1: `100 1 443 sipdir.online.lync.com.`
- Exemplo 2: `100 1 443 sipdir.online.lync.com`

## <a name="related-content"></a>Conteúdo relacionado

[Alterar os servidores de nomes para configurar o Microsoft 365 com qualquer registrador de domínio ](change-nameservers-at-any-domain-registrar.md) (artigo)\
[Localizar e corrigir problemas após adicionar seu domínio ou registros DNS ](find-and-fix-issues.md) (artigo)\
[Gerenciar domínios](index.yml) (página de link)