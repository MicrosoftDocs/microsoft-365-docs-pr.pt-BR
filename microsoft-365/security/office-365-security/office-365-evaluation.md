---
title: Avaliar o Microsoft defender para Office 365
description: O defender for Office 365 no modo de avaliação cria as políticas de email do defender for Office 365 que fazem o log de verdicts, como malware, mas não agem em mensagens.
keywords: Avalie o Office 365, Microsoft defender para Office 365, Office 365 Evaluation, experimente o Office 365, Microsoft defender, ATP
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: abb33b85717e63cb78a2b1edfd86584fd165a71f
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701010"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Avaliar o Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Avaliar o Microsoft defender para Office 365 em breve estará na visualização pública. Esta versão de visualização é fornecida sem um contrato de nível de serviço. Alguns recursos podem não ter suporte ou podem ter recursos restritos.

A condução de uma avaliação de produto de segurança abrangente pode ajudar a fornecer decisões informadas sobre atualizações e compras. Ele ajuda a experimentar os recursos do produto de segurança para avaliar como ele pode ajudar sua equipe de operações de segurança em suas tarefas diárias.

A experiência de avaliação do [Microsoft defender for Office 365](office-365-atp.md) foi projetada para eliminar as complexidades da configuração de dispositivos e ambientes, de forma que você possa se concentrar na avaliação dos recursos da solução de segurança. Ele só se aplica a proteção de email e não a SharePoint, clientes do Office ou equipes.

Se você ainda não tiver uma licença que ofereça suporte ao Microsoft defender para Office 365, você poderá iniciar uma [avaliação gratuita de 30 dias](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) e testar os recursos do centro de conformidade do Office 365 Security & ( https://protection.office.com/homepage) . Você desfrutará da configuração rápida e poderá desativá-la facilmente, se necessário.

## <a name="how-the-evaluation-works"></a>Como a avaliação funciona

O defender for Office 365 no modo de avaliação cria as políticas de email do defender for Office 365 que fazem o log de verdicts, como malware, mas não agem em mensagens. Não é necessário alterar sua configuração de registro MX.

Com o modo de avaliação, [anexos seguros](atp-safe-attachments.md), [links seguros](atp-safe-links.md)e [políticas de personificação](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) anti-phishing são configurados em seu nome. Todas as políticas do defender for Office 365 são criadas no modo não cumprimento em segundo plano e não são visíveis para você.

Como parte da configuração, o modo de avaliação também configura [a filtragem avançada de conectores](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors). Ele melhora a precisão da filtragem ao preservar as informações de endereço IP e de remetente, que são perdidas quando o email passa por um gateway de segurança de email (ESG) na frente do defender para Office 365. A filtragem avançada também melhora a precisão da filtragem de suas políticas antispam e antispam do Exchange Online Protection (EOP).

Para minimizar o impacto em potencial da produção em alguns cenários sem suporte, você pode ignorar a filtragem de EOP criando uma regra de transporte para definir o SCL (nível de confiança de spam) como-1. Consulte [usar o Eat para criar uma regra de fluxo de emails que define o SCL de uma mensagem](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)   para obter detalhes.

Quando o modo de avaliação estiver configurado, você terá um relatório atualizado diariamente com até 90 dias de dados quantificando as mensagens que seriam bloqueadas se as políticas foram implementadas (por exemplo, excluir, enviar para lixo eletrônico, quarentena). Os relatórios são gerados para todas as detecções do defender for Office 365 e EOP. Eles são agregados por tecnologia de detecção (por exemplo, representação) e podem ser filtrados por intervalo de tempo. Além disso, os relatórios de mensagens podem ser criados sob demanda para criar pivôs personalizados ou para aprofundar mensagens usando o explorador de ameaças.

Com a experiência de configuração simplificada, você pode se concentrar em:

- Executando a avaliação
- Obtendo um relatório detalhado
- Analisando o relatório para ação
- Apresentando o resultado da avaliação

## <a name="before-you-begin"></a>Antes de começar

### <a name="licensing"></a>Licenças

Para acessar a avaliação, você precisa atender aos requisitos de licenciamento. Qualquer uma das seguintes licenças funcionará:

- Plano 1 do Microsoft Defender para Office 365
- Plano 2 do Microsoft Defender para Office 365
- Microsoft 365 e5, Microsoft 365 E5 segurança
- Office 365 E5

Se você não tiver uma dessas licenças, será necessário obter uma licença de avaliação.

#### <a name="trial"></a>Teste

Para obter uma licença de avaliação do Microsoft defender para o Office 365, você precisa ter a função de **administrador de cobrança** ou a **função de administrador global**. Solicitar permissão de alguém que tenha a função de administrador global. [Saiba mais sobre assinaturas e licenças](https://docs.microsoft.com/microsoft-365/commerce/licenses/subscriptions-and-licenses)

Assim que você tiver a função apropriada, o caminho recomendado é obter uma licença de avaliação do Microsoft defender para Office 365 (plano 2) no centro de administração do Microsoft 365 acessando os serviços de cobrança > compra. A avaliação inclui uma avaliação gratuita de 30 dias para 25 licenças. [Obtenha uma versão de avaliação do Microsoft defender para Office 365 (plano 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Você terá uma janela de 30 dias com a avaliação para monitorar e relatar ameaças avançadas. Você também terá a opção de comprar uma assinatura paga se quiser obter os recursos completos do defender for Office 365.

### <a name="roles"></a>Funções

As funções do Exchange Online são necessárias para configurar o defender para Office 365 no modo de avaliação.

- [Saiba mais sobre permissões no Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)
- [Saiba como atribuir funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

As seguintes funções são necessárias:

|Tarefas|Role|
|---|---|
|Obter uma avaliação gratuita ou comprar o Microsoft defender para Office 365 (plano 2)|Função de administrador de cobrança ou função de administrador global|
|Criar política de avaliação|Função de domínios remotos e aceitos; Função de administrador de segurança|
|Editar política de avaliação|Função de domínios remotos e aceitos; Função de administrador de segurança|
|Excluir política de avaliação|Função de domínios remotos e aceitos; Função de administrador de segurança |
|Exibir relatório de avaliação|Função de administrador de segurança ou de leitor de segurança|
|


### <a name="enhanced-filtering"></a>Filtragem avançada

Suas políticas de proteção do Exchange Online, como proteção em massa e spam, permanecerão as mesmas. A entrega de mensagens também permanecerá a mesma. No entanto, a avaliação ativa a filtragem avançada para conectores, o que afeta o fluxo de email e as políticas de proteção do Exchange Online, a menos que seja ignorado.

A filtragem avançada para conectores permitirá que os locatários usem a proteção contra falsificação. A antifalsificação não é suportada se você estiver usando um portal de segurança de email (ESG) sem ter ativado a filtragem avançada para conectores.

### <a name="urls"></a>URLs

As URLs serão destruído durante o fluxo de emails. Se você não quiser URLs específicas destruído, gerencie a lista de URLs permitidas apropriadamente. Consulte [Manage URLs na lista de permissões/bloqueios de locatário](tenant-allow-block-list.md) para obter detalhes.

Links de URL nos corpos de mensagens de email não serão quebrados, para reduzir o impacto do cliente.

### <a name="email-routing"></a>Roteamento de email

Prepare os detalhes correspondentes que você precisará para configurar a forma como seu email é roteado no momento, incluindo o nome do conector de entrada que roteia seus emails. Se você estiver usando o Exchange Online Protection, não terá um conector.  [Saiba mais sobre o fluxo de email e o roteamento de email](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Os cenários de roteamento de email suportados incluem:

- **Parceiro de terceiros e/ou provedor de serviços no local**: o conector de entrada que você deseja avaliar usa um provedor de terceiros e/ou você está usando uma solução para segurança de email local.
- **Microsoft Exchange Online Protection somente**: o locatário que você deseja avaliar usa o Office 365 para segurança de email e os pontos de registro de troca de email (MX) para a Microsoft.

### <a name="email-security-gateway"></a>Gateway de segurança de email

Se você estiver usando um gateway de segurança de email de terceiros (ESG), precisará saber o nome do provedor. Se você estiver usando um ESG local ou não suportado fornecedores, precisará saber o (s) endereço (es) de IP público dos dispositivos.

Os parceiros de terceiros suportados incluem:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Escopo

Você poderá criar um escopo de avaliação para um conector de entrada. Se não houver um conector configurado, o escopo de avaliação permitirá que os administradores coletem dados de qualquer usuário em seu locatário para avaliar o defender para Office 365.

## <a name="get-started-with-the-evaluation"></a>Introdução à avaliação

Encontre o cartão de configuração de avaliação do Microsoft defender para Office 365 no centro de conformidade & segurança do Office 365 ( https://protection.office.com/homepage) de três pontos de acesso:

- Painel de > de gerenciamento de ameaças
- Política de > de gerenciamento de ameaças
- Relatórios > painel

## <a name="setting-up-the-evaluation"></a>Configurando a avaliação

Depois de iniciar o fluxo de configuração para sua avaliação, você receberá duas opções de roteamento. Dependendo da configuração de roteamento de email e das necessidades de avaliação da sua organização, você poderá selecionar se estiver usando um provedor de serviços local ou de terceiros ou apenas o Microsoft Exchange Online.

- Se você estiver usando um parceiro de terceiros e/ou provedor de serviços no local, precisará selecionar o nome do fornecedor no menu suspenso. Forneça os outros detalhes relacionados ao conector.

- Selecione Microsoft Exchange Online se o registro MX apontar para a Microsoft e se você tiver uma caixa de correio do Exchange Online.

Revise suas configurações e edite-as se necessário. Em seguida, selecione **criar avaliação**. Você deve receber uma mensagem de confirmação para indicar que a configuração foi concluída.

Seu relatório de avaliação do Microsoft defender para Office 365 é gerado uma vez por dia. Pode levar até 24 horas para que os dados sejam preenchidos.

### <a name="exchange-rules-optional"></a>Regras do Exchange (opcional)

Se você tiver um gateway existente, convém ignorar a filtragem porque ele ativará a filtragem avançada para conectores e alterará o endereço IP do remetente de entrada. Para ignorar, navegue até o centro de administração do Exchange e crie uma política de SCL-1 (se você ainda não tiver um). Para obter detalhes sobre os componentes de regra e como eles funcionam, consulte regras de fluxo de emails (regras de transporte) no Exchange Online.

## <a name="evaluate-capabilities"></a>Avaliar as funcionalidades

Após a geração do relatório de avaliação, confira quantos links avançados de ameaça, anexos avançados de ameaças e possíveis inpersonas foram identificados nos espaços de trabalho de email e colaboração em sua organização.

Quando a avaliação expirar, você poderá continuar a acessar o relatório por 90 dias. No entanto, não coletaremos mais informações. Se você quiser continuar usando o Microsoft defender para Office 365 após a expiração do teste, certifique-se [de comprar uma assinatura paga do Microsoft defender para Office 365 (plano 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Você pode acessar **as configurações** para atualizar seu roteamento ou desativar a avaliação a qualquer momento. No entanto, você precisa passar pelo mesmo processo de configuração novamente se decidir continuar a avaliação depois de desativá-la.

## <a name="provide-feedback"></a>Faça comentários

Seus comentários nos ajudam a melhorar a proteção do ambiente contra ataques avançados. Compartilhe sua experiência e impressões dos recursos do produto e dos resultados de avaliação.

Selecione **enviar comentários** para nos dizer o que você pensa.
