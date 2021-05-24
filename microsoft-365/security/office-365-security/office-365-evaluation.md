---
title: Avaliar o Microsoft Defender para Office 365
description: O Defender para Office 365 no modo de avaliação cria o Defender para Office 365 de email que registram vereditos, como malware, mas não agem em mensagens.
keywords: evaluate Office 365, Microsoft Defender for Office 365, office 365 evaluation, try office 365, Microsoft Defender, Microsoft Defender for Endpoint
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 04/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab0f05c45afa6a4ad66c9fc1bf58e69505632171
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624988"
---
# <a name="evaluate-microsoft-defender-for-office-365"></a>Avaliar o Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> O Microsoft Defender para Office 365 está em visualização pública. Esta versão de visualização é fornecida sem um contrato de nível de serviço. Determinados recursos podem não ser suportados ou podem ter recursos restritos.

A realização de uma avaliação completa do produto de segurança pode ajudar a tomar decisões informadas sobre atualizações e compras. Ele ajuda a experimentar os recursos do produto de segurança para avaliar como ele pode ajudar sua equipe de operações de segurança em suas tarefas diárias.

A [experiência de avaliação](defender-for-office-365.md) do Microsoft Defender para Office 365 foi projetada para eliminar as complexidades da configuração de dispositivo e ambiente para que você possa se concentrar na avaliação dos recursos do Microsoft Defender para Office 365. Com o modo de avaliação, todas as mensagens enviadas Exchange Online caixas de correio podem ser avaliadas sem apontar registros MX para a Microsoft. O recurso só se aplica à proteção de email e não Office clientes como Word, SharePoint ou Teams.

Se você ainda não tiver uma licença compatível com o Microsoft Defender para Office 365, poderá iniciar uma avaliação gratuita de [30](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA) dias e testar os recursos no centro de Conformidade Office 365 Segurança & Segurança ( https://protection.office.com/homepage) . Você aproveitará a configuração rápida e poderá desativar facilmente, se necessário.

> [!NOTE]
> Se você estiver no portal de segurança unificado do Microsoft 365 (security.microsoft.com) pode iniciar um Defender para avaliação de Office 365 aqui: & Políticas de > de colaboração de email & Regras > Políticas de Ameaças > Políticas Adicionais.

## <a name="how-the-evaluation-works"></a>Como funciona a avaliação

O Defender para Office 365 no modo de avaliação cria o Defender para Office 365 de email que registram vereditos, como malware, mas não agem em mensagens. Não é necessário alterar a configuração do registro MX.

Com o modo de [avaliação, Cofre anexos,](safe-attachments.md) [](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)  [Cofre links](safe-links.md)e políticas de representação baseadas em inteligência de caixa de correio são configuradas em seu nome. Todas as políticas do Defender Office 365 são criadas no modo não impositivo em segundo plano e não ficam visíveis para você.

Como parte da instalação, o modo de avaliação também configura [a Filtragem Aprimorada para Conectores.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) Ele melhora a precisão de filtragem preservando o endereço IP e as informações do remetente, que são perdidas quando o email passa por um gateway de segurança de email (ESG) na frente do Defender para Office 365. A filtragem aprimorada para conectores também melhora a precisão de filtragem para suas políticas anti-spam e anti-phishing (EOP) existentes Proteção do Exchange Online (EOP).

A Filtragem Aprimorada Habilitada para Conectores melhora a precisão de filtragem, mas pode alterar a entrega de determinadas mensagens se você tiver um ESG na frente do Defender para Office 365 e, no momento, não ignorar a filtragem EOP. O impacto é limitado às políticas do EOP; As políticas MDO configuradas como parte da avaliação são criadas no modo não impositivo. Para minimizar o impacto potencial de produção, você pode ignorar toda a filtragem do EOP criando uma regra de transporte para definir o Nível de Confiança de Spam (SCL) como -1. Consulte [Usar o EAC para criar uma regra de fluxo](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message)de emails que define a SCL de uma mensagem para obter   detalhes.

Quando o modo de avaliação estiver definido, você terá um relatório atualizado diariamente com até 90 dias de dados quantificando as mensagens que seriam bloqueadas se as políticas fossem implementadas (por exemplo, excluir, enviar para lixo eletrônico, quarentena). Os relatórios são gerados para todas as detecções Office 365 e EOP do Defender. Eles são agregados por tecnologia de detecção (por exemplo, representação) e podem ser filtrados por intervalo de tempo. Além disso, os relatórios de mensagens podem ser criados sob demanda para criar pivôs personalizados ou para enviar mensagens de profundidade usando o Explorador de Ameaças.

Com a experiência de configuração simplificada, você pode se concentrar em:

- Executando a avaliação
- Obter um relatório detalhado
- Analisando o relatório para ação
- Apresentando o resultado da avaliação

## <a name="before-you-begin"></a>Antes de começar

### <a name="licensing"></a>Licenças

Para acessar a avaliação, você precisará atender aos requisitos de licenciamento. Qualquer uma das seguintes licenças funcionará:

- Plano 1 do Microsoft Defender para Office 365
- Plano 2 do Microsoft Defender para Office 365
- Microsoft 365 E5, Microsoft 365 E5 Security
- Office 365 E5

Se você não tiver uma dessas licenças, precisará obter uma licença de avaliação.

#### <a name="trial"></a>Teste

Para obter uma licença de avaliação para o Microsoft Defender para Office 365, você precisa ter a função de administrador de Cobrança **ou** a função de **administrador global**. Solicite permissão de alguém que tenha a função de administrador global. [Saiba mais sobre assinaturas e licenças](../../commerce/licenses/subscriptions-and-licenses.md)

Depois de ter a função adequada, o caminho recomendado é obter uma licença de avaliação para o Microsoft Defender para Office 365 (Plano 2) no centro de administração do Microsoft 365, indo para Cobrança > Serviços de Compra. A avaliação inclui uma avaliação gratuita de 30 dias para 25 licenças. [Obter uma avaliação do Microsoft Defender para Office 365 (Plano 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Você terá uma janela de 30 dias com a avaliação para monitorar e relatar ameaças avançadas. Você também terá a opção de comprar uma assinatura paga se quiser o Defender completo para Office 365 recursos.

### <a name="roles"></a>Funções

**Exchange Online funções são necessárias para** configurar o Defender para Office 365 no modo de avaliação. Atribuir uma Microsoft 365 de conformidade ou função de administrador de segurança não funcionará.

- [Saiba mais sobre permissões no Exchange Online](/exchange/permissions-exo/permissions-exo)
- [Saiba mais sobre a atribuição de funções de administrador](../../admin/add-users/assign-admin-roles.md)

As seguintes funções são necessárias:

|Tarefa|Função (em Exchange Online)|
|---|---|
|Obter uma avaliação gratuita ou comprar o Microsoft Defender para Office 365 (Plano 2)|Função de administrador de cobrança OU função de administrador global|
|Criar política de avaliação|Função Domínios Remotos e Aceitos; Função de administrador de segurança|
|Editar política de avaliação|Função Domínios Remotos e Aceitos; Função de administrador de segurança|
|Excluir política de avaliação|Função Domínios Remotos e Aceitos; Função de administrador de segurança |
|Exibir relatório de avaliação|Função de administrador de segurança OU Função de leitor de segurança|
|

### <a name="enhanced-filtering"></a>Filtragem aprimorada

Suas Proteção do Exchange Online políticas, como proteção em massa e spam, permanecerão as mesmas. No entanto, a avaliação liga a filtragem aprimorada para conectores, o que pode afetar o fluxo de emails e Proteção do Exchange Online políticas, a menos que seja ignorada.

A filtragem aprimorada para conectores permite que os locatários usem proteção anti-spoofing. Não há suporte para anti-spoofing se você estiver usando um gateway de segurança de email (ESG) sem ter ligado a filtragem aprimorada para conectores.

### <a name="urls"></a>URLs

AS URLs serão detonadas durante o fluxo de emails. Se você não quiser URLs específicas detonadas, gerencie sua lista de URLs permitidas adequadamente. Consulte [Gerenciar a lista de locatários permitir/bloquear](tenant-allow-block-list.md) para obter detalhes.

Links de URL nos corpos de mensagens de email não quebram, para diminuir o impacto do cliente.

### <a name="email-routing"></a>Roteamento de email

Prepare os detalhes correspondentes que você precisará configurar como seu email está roteado no momento, incluindo o nome do conector de entrada que roteia seu email. Se você estiver apenas usando Proteção do Exchange Online, não terá um conector.  [Saiba mais sobre o fluxo de emails e o roteamento de email](/office365/servicedescriptions/exchange-online-service-description/mail-flow)

Cenários de roteamento de email com suporte incluem:

- Parceiro de terceiros **e/ou** provedor de serviços local : O conector de entrada que você deseja avaliar usa um provedor de terceiros e/ou você está usando uma solução para segurança de email local.
- **Microsoft Exchange Online Proteção:** o locatário que você deseja avaliar usa Office 365 segurança de email e o registro de email Exchange (MX) aponta para a Microsoft.

### <a name="email-security-gateway"></a>Gateway de segurança de email

Se você estiver usando um gateway de segurança de email de terceiros (ESG), precisará saber o nome do provedor. Se você estiver usando um ESG local ou fornecedores não suportados, precisará saber o(es) endereço(es) público para os dispositivos.

Os parceiros de terceiros com suporte incluem:

- Barracuda
- IronPort
- Mimecast
- Proofpoint
- Sophos
- Symantec
- Trend Micro

### <a name="scoping"></a>Escopo

Você poderá escopo da avaliação para um conector de entrada. Se não houver nenhum conector configurado, o escopo de avaliação permitirá que os administradores reúnam dados de qualquer usuário em seu locatário para avaliar o Defender para Office 365.

## <a name="get-started-with-the-evaluation"></a>Começar com a avaliação

Encontre o microsoft Defender para Office 365 de configuração de avaliação no centro de conformidade Office 365 segurança & segurança ( a partir de https://protection.office.com/homepage) três pontos de acesso:

- Painel de gerenciamento de > ameaças
- Política de gerenciamento de > ameaças
- Relatórios > Painel

## <a name="setting-up-the-evaluation"></a>Configurando a avaliação

Depois de iniciar o fluxo de configuração para sua avaliação, você terá duas opções de roteamento. Dependendo da configuração e das necessidades de avaliação de roteamento de email da sua organização, você pode selecionar se está usando um provedor de serviços de terceiros e/ou local ou apenas Microsoft Exchange Online.

- Se você estiver usando um parceiro de terceiros e/ou um provedor de serviços local, será necessário selecionar o nome do fornecedor no menu suspenso. Forneça os outros detalhes relacionados ao conector.

- Selecione Microsoft Exchange Online se o registro MX aponta para a Microsoft e você tem uma caixa Exchange Online caixa de correio.

Revise suas configurações e edite-as, se necessário. Em seguida, selecione **Criar avaliação**. Você deve receber uma mensagem de confirmação para indicar que sua configuração está concluída.

Seu relatório de avaliação do Microsoft Defender para Office 365 é gerado uma vez por dia. Pode levar até 24 horas para os dados preencherem.

### <a name="exchange-rules-optional"></a>Exchange regras (opcional)

Se você tiver um gateway existente, a habilitação do modo de avaliação ativará a filtragem aprimorada para conectores. Isso melhora a precisão de filtragem alterando o endereço IP do remetente de entrada. Isso pode alterar os vereditos do filtro e, se você não estiver ignorando Proteção do Exchange Online isso pode alterar a capacidade de entrega de determinadas mensagens. Nesse caso, talvez você queira ignorar temporariamente a filtragem para analisar o impacto. Para ignorar, navegue até o centro de administração Exchange e crie uma política de SCL -1 (se você ainda não tiver uma). Para obter detalhes sobre os componentes de regra e como eles funcionam, consulte Mail flow rules (transport rules) in Exchange Online.

## <a name="evaluate-capabilities"></a>Avaliar as funcionalidades

Depois que o relatório de avaliação tiver sido gerado, confira quantos links avançados de ameaças, anexos avançados de ameaças e possíveis personificações foram identificados nos emails e nos espaços de trabalho de colaboração em sua organização.

Depois que a avaliação expirar, você poderá continuar a acessar o relatório por 90 dias. No entanto, ele não coletará mais informações. Se você quiser continuar usando o Microsoft Defender para Office 365 após sua avaliação expirar, certifique-se de comprar uma assinatura paga para o Microsoft Defender para Office 365 [(Plano 2)](https://admin.microsoft.com/AdminPortal/Home#/catalog/offer-details/microsoft-defender-for-office-365-plan-2-/223860DC-15D6-42D9-A861-AE05473069FA).

Você pode ir **para** Configurações atualizar seu roteamento ou desativar sua avaliação a qualquer momento. No entanto, você precisa passar pelo mesmo processo de configuração novamente caso decida continuar sua avaliação depois de ter desligado.

## <a name="provide-feedback"></a>Faça comentários

Seus comentários nos ajudam a melhorar a proteção do ambiente contra ataques avançados. Compartilhe sua experiência e impressões dos recursos do produto e dos resultados da avaliação.

Selecione **Dar comentários** para nos dizer o que você acha.