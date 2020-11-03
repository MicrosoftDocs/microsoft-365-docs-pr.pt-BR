---
title: Visão geral do Exchange Online Protection (EOP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 09/18/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Saiba como o Exchange Online Protection (EOP) pode ajudar a proteger sua organização de email local em ambientes autônomos e híbridos.
ms.openlocfilehash: a8b30a475e6865916c74f08c4d927662f658a096
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842399"
---
# <a name="exchange-online-protection-overview"></a>Visão geral do Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


O proteção do Exchange Online (EOP) é o serviço de filtragem baseado em nuvem que ajuda a proteger sua organização contra spam e malware. O EOP está incluído em todas as organizações do Microsoft 365 com caixas de correio do Exchange Online. No entanto, o EOP também está disponível nos seguintes cenários locais:

- **Em um cenário autônomo: o** EOP fornece proteção de email baseada em nuvem para sua organização local do Exchange ou para qualquer outra solução de email SMTP local.

- **Em uma implantação híbrida: o** EOP pode ser configurado para proteger seu ambiente de email e controlar o roteamento de email quando você tem uma combinação de caixas de correio locais e em nuvem.

Nesses cenários, o EOP pode simplificar o gerenciamento de seu ambiente de email e aliviar muitos dos ônus que acompanham a manutenção de hardware e software locais.

O restante deste tópico explica como o EOP funciona em ambientes autônomos e híbridos.

## <a name="how-eop-works"></a>Como o EOP funciona

Para entender como o EOP funciona, ele o ajuda a ver como processa o email de entrada:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Gráfico de email da Internet ou dos comentários do cliente transmitidos para o EOP e por meio da conexão, do anti-malware, da filtragem de política de barra de Tróia e da filtragem de conteúdo, antes do veredicto de lixo eletrônico ou quarentena ou entrega de email do usuário final.":::

- Quando uma mensagem de entrada entra EOP, ela inicialmente passa pela filtragem de conexão, que verifica a reputação do remetente. A maior parte do spam é interrompida neste ponto e rejeitada pelo EOP. Para obter mais informações, confira [Configurar a filtragem da conexão](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-connection-filter-policy?view=o365-worldwide).

- Em seguida, a mensagem é inspecionada em busca de sinais de malware. Se o malware for encontrado na mensagem ou no (s) anexo (s) a mensagem é roteada para um repositório de quarentena somente do administrador. Você pode saber mais sobre a configuração do anti-malware [aqui](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-malware-policies?view=o365-worldwide).

- As mensagens continuam por meio da filtragem de política, onde são avaliadas em relação às regras de fluxo de emails personalizadas (também conhecidas como regras de transporte) que você cria ou impõe de um modelo. Por exemplo, você pode ter uma regra que envia uma notificação a um gerente quando o email chega de um remetente específico. As verificações de prevenção de perda de dados (DLP) também ocorrem neste ponto (Exchange Enterprise CAL com serviços).

- Em seguida, a mensagem passa pela filtragem de conteúdo (também conhecida como anti-spam). Uma mensagem que este filtro determina ser spam *ou phishing* pode ser enviada para a quarentena ou para a pasta lixo eletrônico de um usuário, entre outras opções. Para obter mais informações, consulte [Configure anti-spam Policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies?view=o365-worldwide) e [Configure anti-phishing Policies](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-anti-phishing-policies-eop?view=o365-worldwide).

Qualquer mensagem que transmita todas essas camadas de proteção com êxito é entregue ao destinatário.

Para obter mais informações, consulte [ordem e precedência de proteção de email](how-policies-and-protections-are-combined.md).

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>Planos e recursos do EOP para organizações de email locais

Os planos de assinatura disponíveis do EOP são:

- **EOP autônomo** : você se inscreve no EOP para proteger sua organização de email local.

- **Recursos do EOP no Exchange Online** : qualquer assinatura que inclua o Exchange Online (autônomo ou como parte do Microsoft 365) usa o EOP para proteger suas caixas de correio do Exchange Online.

- **Exchange Enterprise CAL com serviços** : se você tiver uma organização do Exchange no local onde comprou o Exchange Enterprise CAL adicional com licenças de serviços, o EOP faz parte dos serviços incluídos.

Para obter informações sobre requisitos, limites importantes e disponibilidade de recursos em todos os planos de assinatura do EOP, consulte a [Descrição do serviço de proteção do Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Configurando o EOP para organizações de email locais

A configuração do EOP pode ser simples, especialmente no caso de uma pequena organização com um punhado de regras de conformidade. No entanto, se você tiver uma organização de grande porte com vários domínios, regras de conformidade personalizadas ou fluxo de email híbrido, a configuração pode precisar de mais planejamento e tempo.

Se você já comprou o EOP, consulte [Configurar seu serviço EOP](set-up-your-eop-service.md) para garantir a conclusão de todas as etapas necessárias de configuração do EOP, a fim de proteger seu ambiente de mensagens.

### <a name="eop-datacenters"></a>Datacenters EOP

O EOP é executado em uma rede mundial de data center projetados para fornecer a melhor disponibilidade. Por exemplo, se um data center ficar indisponível, mensagens de email são automaticamente roteadas para um outro data center sem qualquer interrupção no serviço. Os servidores em cada datacenter aceitam mensagens em seu nome, fornecendo uma camada de separação entre sua organização e a Internet, reduzindo assim a carga em seus servidores. Por meio dessa rede altamente disponível, a Microsoft pode assegurar que esse email chegue a sua organização pontualmente.

EOP realiza balanceamento de carga entre data centers, mas apenas dentro de uma região. Se você for aprovisionado em uma região, todas as suas mensagens serão processadas usando o roteamento de email para essa região. A lista a seguir mostra como o roteamento de email regional funciona para os data centers EOP:

- Na Europa, Oriente Médio e África (EMEA), todas as caixas de correio do Exchange Online são localizadas nos data centers da EMEA e todas as mensagens são roteadas através de data centers da EMEA para filtragem do EOP.

- No Asia-Pacific (na EOP), todas as caixas de correio do Exchange Online estão localizadas em datacenters da linha da Pacífico e as mensagens são roteadas por meio de datacenters da rota para filtragem do.

- Nas Américas, os serviços são distribuídos nos seguintes locais:

  - América do Sul: as caixas de correio do Exchange Online estão localizadas em datacenters no Brasil e no Chile. Todas as mensagens são roteadas através de datacenters locais para filtragem do EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.

  - Canadá: as caixas de correio do Exchange Online estão localizadas em datacenters no Canadá. Todas as mensagens são roteadas através de datacenters locais para filtragem do EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.

  - Estados Unidos: caixas de correio do Exchange Online estão localizadas em datacenters dos EUA. Todas as mensagens são roteadas através de datacenters locais para filtragem do EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.

- Para a Nuvem de Comunidade Governamental (GCC), todas as caixas de correio do Exchange Online localizadas em data centers dos EUA e todas as mensagens são roteadas através de data centers dos EUA para filtragem do EOP.

## <a name="eop-help-for-admins"></a>Ajuda do EOP para administradores

O conteúdo da Ajuda para administradores do EOP é composta pelas seguintes categorias de primeiro nível:

- [Configure o EOP, o dia 1, para administradores do Microsoft defender para Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide): Configurando as ferramentas de proteção e detecção do EOP no núcleo do Microsoft defender para Office 365.

- [Recursos do EOP](eop-features.md): fornece uma lista de recursos disponíveis no EOP.

- [Set up your EOP Service](set-up-your-eop-service.md): fornece etapas para configurar o seu serviço do EOP e links para informações adicionais.

- [Vá para EOP do Google Postini, firewall de vírus e spam de Barracuda ou Cisco IronPort](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md): descreve o processo para mudar para EOP de outro produto de proteção de email.

- [Gerenciar destinatários no EOP autônomo](manage-recipients-in-eop.md): descreve como gerenciar usuários e grupos de email no EOP.

- [Fluxo de email no EOP](mail-flow-in-eop.md): descreve como configurar cenários de fluxo de email personalizados usando conectores, como gerenciar domínios associados ao serviço e como habilitar o recurso bloqueio de borda baseado em diretório (DBEB).

- [Práticas recomendadas para a configuração do EOP](best-practices-for-configuring-eop.md): descreve as definições de configuração e considerações recomendadas para depois de configurar e provisionar o serviço.

- [Relatórios de auditoria em EOP autônomos](auditing-reports-in-eop.md): descreve como usar os relatórios de auditoria para rastrear as alterações de configuração para o serviço.

- [Proteção antispam e antimalware no EOP](anti-spam-and-anti-malware-protection.md): descreve a filtragem de spam e a filtragem de malware e mostra como personalizá-las para atender melhor às necessidades da sua organização. Descreve também as tarefas que os administradores e usuários finais podem realizar em mensagens em quarentena.

- [Relatórios e rastreamento de mensagens no Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md): descreve os relatórios e as ferramentas de solução de problemas disponíveis.

- [Centro de administração do Exchange em EOP autônomo](exchange-admin-center-in-exchange-online-protection-eop.md): descreve como acessar e navegar pela interface de gerenciamento do centro de administração do Exchange (Eat) para gerenciar seu serviço do EOP.

- [Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-protection-powershell): fornece informações sobre o PowerShell remoto, que permite gerenciar seu serviço do EOP a partir da linha de comando.

- [Ajuda e suporte para EOP](help-and-support-for-eop.md) Fornece informações sobre como obter ajuda e suporte técnico.
