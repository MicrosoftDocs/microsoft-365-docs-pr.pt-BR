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
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
ms.custom:
- seo-marvel-apr2020
description: Saiba como a Proteção do Exchange Online (EOP) pode ajudar a proteger sua organização de email local em ambientes autônomos e híbridos.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9aa2925ed5a9a6088fab81a09754b479740411cc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910829"
---
# <a name="exchange-online-protection-overview"></a>Visão geral do Exchange Online Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

O Exchange Online Protection (EOP) é o serviço de filtragem baseado em nuvem que ajuda a proteger sua organização contra spam e malware. O EOP está incluído em todas as organizações do Microsoft 365 com caixas de correio do Exchange Online. No entanto, o EOP também está disponível nos seguintes cenários locais:

- **Em um cenário** autônomo: o EOP fornece proteção de email baseada em nuvem para sua organização local do Exchange ou para qualquer outra solução de email SMTP local.

- **Em uma implantação** híbrida : o EOP pode ser configurado para proteger seu ambiente de email e controlar o roteamento de emails quando você tem uma combinação de caixas de correio locais e na nuvem.

Nesses cenários, o EOP pode simplificar o gerenciamento do seu ambiente de email e aliviar muitos dos encargos que vêm com a manutenção de hardware e software local.

O restante deste tópico explica como o EOP funciona em ambientes autônomos e híbridos.

## <a name="how-eop-works"></a>Como o EOP funciona

Para entender como o EOP funciona, ele o ajuda a ver como processa o email de entrada:

:::image type="content" source="../../media/tp_emailprocessingineopt3.png" alt-text="Gráfico de emails da Internet ou comentários do cliente que passam para o EOP e por meio do Connection, Anti-malware, Mailflow Rules-slash-Policy Filtering e Filtragem de Conteúdo, antes do veredito de lixo eletrônico ou quarentena ou entrega de email do usuário final.":::

- Quando uma mensagem de entrada entra no EOP, ela passa inicialmente pela filtragem de conexão, que verifica a reputação do remetente. A maioria dos spams é interrompida neste ponto e rejeitada pelo EOP. Para obter mais informações, confira [Configurar a filtragem da conexão](configure-the-connection-filter-policy.md).

- Em seguida, a mensagem é inspecionada para ver se há sinais de malware. Se o malware for encontrado na mensagem ou nos anexos, a mensagem será roteada para um armazenamento de quarentena somente de administrador. Você pode saber mais sobre como configurar o anti-malware [aqui](configure-anti-malware-policies.md).

- As mensagens continuam por meio da filtragem de política, onde são avaliadas em relação às regras de fluxo de emails personalizadas (também conhecidas como regras de transporte) que você cria ou impõe a partir de um modelo. Por exemplo, você pode ter uma regra que envia uma notificação a um gerente quando o email chega de um remetente específico. Verificações de prevenção contra perda de dados (DLP) também ocorrem neste ponto (Exchange Enterprise CAL com Serviços).

- Em seguida, a mensagem passa pela filtragem de conteúdo (também conhecida como Anti-spam). Uma mensagem que esse filtro determina como spam ou *phishing* pode ser enviada para quarentena, ou a pasta Lixo Eletrônico do usuário, entre outras opções. Para obter mais informações, [consulte Configure anti-spam policies](configure-your-spam-filter-policies.md) and Configure [anti-phishing policies](configure-anti-phishing-policies-eop.md).

Qualquer mensagem que passa todas essas camadas de proteção com êxito é entregue ao destinatário.

Para obter mais informações, [consulte Order and precedence of email protection](how-policies-and-protections-are-combined.md).

## <a name="eop-plans-and-features-for-on-premises-email-organizations"></a>Planos e recursos do EOP para organizações de email locais

Os planos de assinatura do EOP disponíveis são:

- **Autônomo do EOP:** você se inscreva no EOP para proteger sua organização de email local.

- **Recursos do EOP** no Exchange Online : Qualquer assinatura que inclua o Exchange Online (autônomo ou como parte do Microsoft 365) usa o EOP para proteger suas caixas de correio do Exchange Online.

- **Exchange Enterprise CAL com Serviços**: Se você tiver uma organização local do Exchange onde comprou licenças adicionais do Exchange Enterprise CAL com Serviços, o EOP faz parte dos serviços incluídos.

Para obter informações sobre requisitos, limites importantes e disponibilidade de recursos em todos os planos de assinatura do EOP, consulte a descrição do [serviço de Proteção do Exchange Online](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

## <a name="setting-up-eop-for-on-premises-email-organizations"></a>Configuração do EOP para organizações de email locais

A configuração do EOP pode ser simples, especialmente no caso de uma pequena organização com um punhado de regras de conformidade. No entanto, se você tiver uma organização de grande porte com vários domínios, regras de conformidade personalizadas ou fluxo de email híbrido, a configuração pode precisar de mais planejamento e tempo.

Se você já comprou o EOP, consulte [Configurar seu serviço EOP](set-up-your-eop-service.md) para garantir a conclusão de todas as etapas necessárias de configuração do EOP, a fim de proteger seu ambiente de mensagens.

### <a name="eop-datacenters"></a>Datacenters EOP

O EOP é executado em uma rede mundial de data center projetados para fornecer a melhor disponibilidade. Por exemplo, se um data center ficar indisponível, mensagens de email são automaticamente roteadas para um outro data center sem qualquer interrupção no serviço. Os servidores em cada datacenter aceitam mensagens em seu nome, fornecendo uma camada de separação entre sua organização e a Internet, reduzindo assim a carga em seus servidores. Por meio dessa rede altamente disponível, a Microsoft pode assegurar que esse email chegue a sua organização pontualmente.

EOP realiza balanceamento de carga entre data centers, mas apenas dentro de uma região. Se você for aprovisionado em uma região, todas as suas mensagens serão processadas usando o roteamento de email para essa região. A lista a seguir mostra como o roteamento de email regional funciona para os data centers EOP:

- Na Europa, Oriente Médio e África (EMEA), todas as caixas de correio do Exchange Online são localizadas nos data centers da EMEA e todas as mensagens são roteadas através de data centers da EMEA para filtragem do EOP.

- No Asia-Pacific (APAC), todas as caixas de correio do Exchange Online estão localizadas em datacenters do APAC e as mensagens atualmente são roteadas por meio de datacenters APAC para filtragem de EOP.

- Nas Américas, os serviços são distribuídos nos seguintes locais:

  - América do Sul: as caixas de correio do Exchange Online estão localizadas em datacenters no Brasil e no Chile. Todas as mensagens são roteadas por datacenters locais para filtragem EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.

  - Canadá: as caixas de correio do Exchange Online estão localizadas em datacenters no Canadá. Todas as mensagens são roteadas por datacenters locais para filtragem EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.

  - Estados Unidos: as caixas de correio do Exchange Online estão localizadas em datacenters dos EUA. Todas as mensagens são roteadas por datacenters locais para filtragem EOP. As mensagens em quarentena são armazenadas no datacenter onde o locatário está localizado.

- Para a Nuvem de Comunidade Governamental (GCC), todas as caixas de correio do Exchange Online localizadas em data centers dos EUA e todas as mensagens são roteadas através de data centers dos EUA para filtragem do EOP.

## <a name="eop-help-for-admins"></a>Ajuda do EOP para administradores

O conteúdo da Ajuda para administradores do EOP é composta pelas seguintes categorias de primeiro nível:

- [Configure o EOP, Dia 1,](protect-against-threats.md)para administradores do Microsoft Defender para Office 365 : Configurando ferramentas de proteção e detecção do EOP no núcleo do Microsoft Defender para Office 365.

- [Recursos do EOP](eop-features.md): fornece uma lista de recursos que estão disponíveis no EOP.

- [Configurar seu serviço EOP:](set-up-your-eop-service.md)fornece etapas para configurar seu serviço EOP e links para informações adicionais.

- Alternar para o EOP do Google Postini, o Firewall de Spam e [Vírus barracuda](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md)ou Cisco IronPort : descreve o processo para alternar para o EOP de outro produto de proteção de email.

- [Gerenciar destinatários no EOP autônomo](manage-recipients-in-eop.md): descreve como gerenciar usuários de email e grupos no EOP.

- Fluxo de emails no [EOP](mail-flow-in-eop.md): descreve como configurar cenários de fluxo de emails personalizados usando conectores, como gerenciar domínios associados ao serviço e como habilitar o recurso DbEB (Bloqueio de Borda Baseado em Diretório).

- [Práticas recomendadas para configurar o EOP](best-practices-for-configuring-eop.md): descreve as configurações recomendadas e considerações para depois de configurar e provisionar seu serviço.

- [Relatórios de auditoria no EOP autônomo](auditing-reports-in-eop.md): descreve como usar relatórios de auditoria para controlar as alterações de configuração no serviço.

- [Proteção anti-spam e anti-malware](anti-spam-and-anti-malware-protection.md)no EOP : descreve a filtragem de spam e a filtragem de malware e mostra como personalizá-los para atender melhor às necessidades da sua organização. Descreve também as tarefas que os administradores e usuários finais podem realizar em mensagens em quarentena.

- [Relatórios e rastreamento de mensagens na Proteção do Exchange Online](reporting-and-message-trace-in-exchange-online-protection.md): descreve os relatórios e as ferramentas de solução de problemas disponíveis.

- Centro de administração do [Exchange no EOP](exchange-admin-center-in-exchange-online-protection-eop.md)autônomo : descreve como acessar e navegar pela interface de gerenciamento do Centro de administração do Exchange (EAC) para gerenciar seu serviço EOP.

- [Proteção do Exchange Online PowerShell](/powershell/exchange/exchange-online-protection-powershell): fornece informações sobre o PowerShell remoto, que permite gerenciar seu serviço EOP a partir da linha de comando.

- [Ajuda e suporte para EOP](help-and-support-for-eop.md) Fornece informações sobre como obter ajuda e suporte técnico.