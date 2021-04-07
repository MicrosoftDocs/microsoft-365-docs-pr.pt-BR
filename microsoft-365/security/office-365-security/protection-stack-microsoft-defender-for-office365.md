---
title: Pilha de proteção contra ameaças passo a passo no Microsoft Defender para Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
ms.reviewer: gigarrub
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
description: Siga o caminho de uma mensagem de entrada através da pilha de filtragem de ameaças no Microsoft Defender para Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0760bd7a67f175e4af114324ccc729355ad5f593
ms.sourcegitcommit: 4e05f19c00e172b65f637f19ca461db5b21dff4e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51601359"
---
# <a name="step-by-step-threat-protection-in-microsoft-defender-for-office-365"></a>Proteção passo a passo contra ameaças no Microsoft Defender para Office 365

A pilha de proteção ou filtragem do Microsoft Defender para Office 365 pode ser dividida em 4 fases, como neste artigo. De modo geral, os emails de entrada passam por todas essas fases antes da entrega, mas o caminho real que o email leva está sujeito à configuração do Defender for Office 365 de uma organização.

> [!TIP]
> Fique atento até o final  deste artigo para um gráfico unificado de todas as 4 fases da proteção do Defender para Office 365!

## <a name="phase-1---edge-protection"></a>Fase 1 - Proteção de Borda

Infelizmente, os blocos de borda que antes *eram críticos* agora são relativamente simples para os atores ruins superarem. Com o tempo, menos tráfego é bloqueado aqui, mas ele permanece uma parte importante da pilha.  

Os blocos de borda são projetados para serem automáticos. No caso de falso positivo, os remetentes serão notificados e avisados sobre como resolver o problema. Conectores de parceiros confiáveis com reputação limitada podem garantir a entrega, ou substituições temporárias podem ser colocadas em lugar, ao integrar novos pontos de extremidade.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase1.png" alt-text="A fase 1 da filtragem no Defender para Office 365 é a Proteção de Borda.":::

1. **A limitação** de rede protege a infraestrutura do Office 365 e os clientes contra ataques de Negação de Serviço (DOS) limitando o número de mensagens que podem ser enviadas por um conjunto específico de infraestrutura.

2. **A reputação e a throttling** de IP bloquearão as mensagens enviadas de endereços IP de conexão ruins conhecidos. Se um IP específico enviar muitas mensagens em um curto período de tempo, elas serão aceleradas.

3. **A reputação do** domínio bloqueará todas as mensagens enviadas de um domínio mal conhecido.

4. **Os blocos de filtragem de** borda baseados em diretório tenta coletar informações de diretório de uma organização por meio de SMTP.

5. **A detecção de backscatter** impede que uma organização seja atacada por meio de NDRs (relatórios de não entrega) inválidos.

6. **A filtragem aprimorada para conectores** preserva informações de autenticação mesmo quando o tráfego passa por outro dispositivo antes de atingir o Office 365. Isso melhora a precisão da pilha de filtragem, incluindo clustering heurístico, anti-spoofing e modelos de aprendizado de máquina anti-phishing, mesmo quando em cenários de roteamento complexos ou híbridos.

## <a name="phase-2---sender-intelligence"></a>Fase 2 - Inteligência de Remetente

Os recursos na inteligência de remetente são essenciais para capturar spam, massa, representação e mensagens falsas não autorizadas e também fator para a detecção de phishing. A maioria desses recursos é configurável individualmente.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase2.png" alt-text="A fase 2 da filtragem no MDO é Inteligência de Remetente.":::

1. **Os gatilhos e** alertas de detecção de comprometimento de conta são acionados quando uma conta tem comportamento anômalo, consistente com comprometimento. Em alguns casos, a conta de usuário é bloqueada e impedida de enviar outras mensagens de email até que o problema seja resolvido pela equipe de operações de segurança de uma organização.

2. **A Autenticação** de Email envolve os métodos configurados pelo cliente e os métodos configurados na Nuvem, destinados a garantir que os envios sejam autorizados, mailers autênticos. Esses métodos resistem à spoofing.
    - **O SPF** pode rejeitar emails com base em registros TXT DNS que listam endereços IP e servidores permitidos para enviar emails em nome da organização.
    - **O DKIM** fornece uma assinatura criptografada que autentica o remetente.
    - **O DMARC** permite que os administradores marquem sPF e DKIM conforme necessário em seu domínio e impõe o alinhamento entre os resultados dessas duas tecnologias.
    - **O ARC** não é configurado pelo cliente, mas é baseado no DMARC para trabalhar com o encaminhamento em listas de email, enquanto grava uma cadeia de autenticação.

3. A inteligência de **spoof** é capaz de filtrar aqueles permitidos para 'spoof' (ou seja, aqueles que enviam emails em nome de outra conta ou encaminham para uma lista de emails) de spoofers mal-intencionados imitando um domínio externo organizacional ou conhecido. Ele separa emails legítimos "em nome" de remetentes de spoofing para entregar mensagens de spam e phishing. 

    **A inteligência de spoof intra-org** detecta e bloqueia tentativas de spoof de um domínio dentro da organização.

4. **A inteligência de spoof entre domínios** detecta e bloqueia tentativas de spoof de um domínio fora da organização.

5. **A filtragem em** massa permite que os administradores configurem um nível de confiança em massa (BCL) indicando se a mensagem foi enviada de um remetente em massa. Os administradores podem usar o Controle Deslizante em Massa na política Antispam para decidir qual nível de email em massa tratar como spam.

6. **A inteligência de caixa** de correio aprende com comportamentos padrão de email do usuário. Ele aproveita o gráfico de comunicação de um usuário para detectar quando um remetente parece ser apenas alguém com quem o usuário geralmente se comunica, mas é realmente mal-intencionado. Esse método detecta a representação.

7. **A representação de inteligência de caixa** de correio habilita ou desabilita resultados de representação aprimorados com base no mapa de remetente individual de cada usuário. Quando habilitado, esse recurso ajuda a identificar a representação.

8. **A representação do usuário** permite que um administrador crie uma lista de destinos de alto valor que provavelmente serão personificados. Se um email chegar onde o remetente parece ter apenas o mesmo nome e endereço que a conta de alto valor protegido, o email será marcado ou marcado. (Por exemplo, *trα cye@contoso.com* para *tracye@contoso.com*).

9. **A representação de domínio** detecta domínios semelhantes ao domínio do destinatário e que tentam parecer com um domínio interno. Por exemplo, essa representação *tracye@liw α re.com* para *tracye@litware.com*.

## <a name="phase-3---content-filtering"></a>Fase 3 - Filtragem de Conteúdo

Nesta fase, a pilha de filtragem começa a manipular o conteúdo específico do email, incluindo seus hiperlinks e anexos.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase3.png" alt-text="A fase 3 da filtragem no MDO é Filtragem de Conteúdo.":::

1. **As regras de** transporte (também conhecidas como regras de fluxo de emails ou regras de transporte do Exchange) permitem que um administrador tome uma ampla gama de ações quando uma ampla variedade de condições é atendida para uma mensagem. Todas as mensagens que fluem pela sua organização são avaliadas em relação às regras de fluxo de emails/regras de transporte habilitadas.

2. **O Microsoft Defender Antivírus** e dois mecanismos *antivírus* de terceiros são usados para detectar todos os malwares conhecidos em anexos.

3. Os mecanismos anti-vírus (AV) também são usados para digitar  todos os anexos de forma que o bloqueio de tipo possa bloquear todos os anexos de tipos especificados pelo administrador.

4. Sempre que o Microsoft Defender for Office 365 detecta um anexo mal-intencionado, o hash do arquivo e um hash de seu conteúdo ativo são adicionados à reputação do Exchange Online Protection (EOP). **O bloqueio de reputação de** anexo bloqueará esse arquivo em todos os office 365 e nos pontos de extremidade, por meio de chamadas de nuvem do MSAV.

5. **O cluster heurístico** pode determinar que um arquivo é suspeito com base na heurística de entrega. Quando um anexo suspeito é encontrado, toda a campanha é pausada e o arquivo é área desconfiado. Se o arquivo for considerado mal-intencionado, toda a campanha será bloqueada.

6. **Os modelos de aprendizado** de máquina atuam no header, no conteúdo do corpo e nas URLs de uma mensagem para detectar tentativas de phishing.

7. A Microsoft usa uma determinação da reputação da área de segurança de URL, bem como a reputação da URL de feeds de terceiros no bloqueio de reputação da **URL,** para bloquear qualquer mensagem com uma URL mal-intencionada conhecida.

8. **A heurística de conteúdo** pode detectar mensagens suspeitas com base na estrutura e na frequência de palavras no corpo da mensagem, usando modelos de aprendizado de máquina.

9. **Os Anexos Seguros** são áreas de segurança em todos os anexos para clientes do Defender para Office 365, usando a análise dinâmica para detectar ameaças nunca vistas.

10. **A detonação de** conteúdo vinculado trata cada URL vinculando a um arquivo em um email como um anexo, de forma assíncrona em áreas de segurança do arquivo no momento da entrega.

11. **A detonação** de URL acontece quando a tecnologia anti-phishing upstream encontra uma mensagem ou URL suspeita. A detonação de URL ressaliza as URLs na mensagem no momento da entrega.

## <a name="phase-4---post-delivery-protection"></a>Fase 4 - Proteção pós-entrega

O último estágio ocorre após a entrega de emails ou arquivos, atuando em emails que estão em várias caixas de correio e arquivos e links que aparecem em clientes como o Microsoft Teams.

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase4.png" alt-text="A fase 4 da filtragem no Defender para Office 365 é Proteção pós-entrega.":::

1. **Links seguros** é a proteção de hora de clique do MDO. Cada URL em cada mensagem é empacotada para apontar para os servidores de Links Seguros da Microsoft. Quando uma URL é clicada, ela é verificada em relação à reputação mais recente, antes que o usuário seja redirecionado para o site de destino. A URL é assíncrona em áreas de segurança para atualizar sua reputação.

2. Phish Zero-Hour limpeza automática **(ZAP)** detecta e neutraliza mensagens de phishing mal-intencionadas que já foram entregues às caixas de correio do Exchange Online.

3. **Malware O ZAP** detecta e neutraliza retroativamente mensagens de malware mal-intencionadas que já foram entregues às caixas de correio do Exchange Online.

4. **Spam O ZAP** detecta e neutraliza retroativamente mensagens de spam mal-intencionadas que já foram entregues às caixas de correio do Exchange Online.

5. **Os Exibições** de Campanha permitem que os administradores vejam a imagem geral de um ataque, mais rápido e mais completo, do que qualquer equipe poderia sem automação. A Microsoft aproveita as grandes quantidades de dados anti-phishing, anti-spam e anti-malware em todo o serviço para ajudar a identificar campanhas e permite que os administradores as investiguem do início ao fim, incluindo destinos, impactos e fluxos, que também estão disponíveis em um write-up de campanha baixável.

6. **Os complementos** de Mensagem de Relatório permitem que as pessoas reportem facilmente falsos positivos (emails bons, marcados erroneamente como *ruins)* ou falsos negativos (email ruim marcado como bom *)* para a Microsoft para análise mais detalhada.

7. **Links seguros para clientes do Office** oferece a mesma proteção de hora de clique em Links Seguros, na verdade, dentro de clientes do Office, como Word, PowerPoint e Excel.

8. **A proteção para OneDrive, SharePoint** e Teams oferece a mesma proteção de Anexos Seguros contra arquivos mal-intencionados, na verdade, dentro do OneDrive, do SharePoint e do Microsoft Teams.

9. Quando uma URL que aponta para um arquivo é selecionada após a **entrega,** a detonação de conteúdo vinculado exibe uma página de aviso até que a área de segurança do arquivo seja concluída e a URL seja encontrada como segura.


## <a name="the-filtering-stack-diagram"></a>O diagrama de pilha de filtragem

O diagrama final (como com todas as partes do diagrama que o compõe) está sujeito a alterações à medida que o produto cresce *e desenvolve*. Reserve esta página e use a opção **comentários** que você encontrará na parte inferior se precisar perguntar após as atualizações. Para seus registros, essa é a pilha com todas as fases em ordem:

:::image type="content" source="../../media/mdo-filtering-stack/mdo-filter-stack-phase5.png" alt-text="Todas as fases de filtragem no MDO em ordem, 1 a 4.":::

## <a name="more-information"></a>Mais informações

Você precisa configurar o Microsoft Defender para Office 365 ***agora** mesmo _? Use essa pilha, _now*, com este passo [a passo](protect-against-threats.md) para começar a proteger sua organização.

*Agradecimentos especiais do MSFTTracyP e* da equipe de escrita de documentos para a Equipe de Escrita de Giulian Garruba por esse conteúdo.
