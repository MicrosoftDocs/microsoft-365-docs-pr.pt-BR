---
title: Políticas de referência, práticas e diretrizes
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: A Microsoft desenvolveu várias políticas, procedimentos e adotou várias práticas recomendadas do setor para ajudar a proteger nossos usuários contra emails ofensivos, indesejados ou mal-intencionados.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1065fdef5f804214ca48f7ca54170e6e417490d7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289192"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referência: políticas, práticas e diretrizes

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

A Microsoft se dedica a ajudar a fornecer a experiência de usuário mais confiável na Web. Portanto, a Microsoft desenvolveu várias políticas, procedimentos e adotou várias práticas recomendadas do setor para ajudar a proteger nossos usuários contra emails ofensivos, indesejados ou mal-intencionados. Os envios que tentam enviar emails aos usuários devem garantir que eles entendam totalmente e estão seguindo as orientações neste artigo para ajudar nesse esforço e para ajudar a evitar possíveis problemas de entrega.

Se você não estiver em conformidade com essas políticas e diretrizes, talvez não seja possível que nossa equipe de suporte ajude você. Se você estiver aderindo às diretrizes, práticas e políticas apresentadas neste artigo e ainda estiver enfrentando problemas de entrega com base no seu endereço IP de envio, siga as etapas para enviar uma solicitação de relistagem. Para obter instruções, [confira Usar o portal de remoção da lista para se remover da lista de envios bloqueados.](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)

## <a name="general-microsoft-policies"></a>Políticas gerais da Microsoft

Os emails enviados aos usuários do Microsoft 365 devem estar em conformidade com todas as políticas da Microsoft que regem a transmissão de emails e o uso do Microsoft 365.

- Termos de Serviços aplicáveis ao Microsoft 365; em particular, a proibição de usar o serviço para spam ou distribuir malware.

- [Contrato de Serviços Microsoft](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Regulamentações governamentais

Os emails enviados aos usuários do Microsoft 365 devem cumprir todas as leis e regulamentos aplicáveis que regem as comunicações por email na jurisdição aplicável.

- [CAN-SPAM Act: Um Guia de Conformidade para Empresas](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- [Respostas e responsabilidades "Remover-me" : os mercados de email devem honrar as declarações "Cancelar assinatura"](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.html)

## <a name="technical-guidelines"></a>Diretrizes técnicas

Os emails enviados para o Microsoft 365 devem estar em conformidade com as recomendações aplicáveis listadas nos documentos abaixo (alguns links estão disponíveis apenas em inglês).

- [RFC 2505: Recomendações anti-spam para MTAs SMTP](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: Extensão de serviço SMTP para pipelining de comando](https://www.ietf.org/rfc/rfc2920.txt)

Além disso, os servidores de email que se conectam ao Microsoft 365 devem cumprir os seguintes requisitos:

- Espera-se que o remetente cumpra todos os padrões técnicos para a transmissão de emails da Internet, conforme publicado pela IETF (Internet Engineering Task Force) da Internet, incluindo RFC 5321, RFC 5322 e outros.

- Depois de receber um código de resposta de erro SMTP numérico entre 500 e 599 (também conhecido como uma resposta permanente de falha na entrega ou NDR), o remetente não deve tentar retransmitir essa mensagem para esse destinatário.

- Após várias respostas de não entrega, o remetente deve parar de tentar enviar emails para esse destinatário.

- As mensagens não devem ser transmitidas por meio de retransmissão de email insegura ou servidores proxy.

- O mecanismo para cancelar a inscrição, seja de listas individuais ou de todas as listas hospedadas pelo remetente, deve ser claramente documentado e fácil para os destinatários encontrar e usar.

- Conexões de espaço IP dinâmico podem não ser aceitas.

- Os servidores de email devem ter registros DNS reverso válidos.

## <a name="reputation-management"></a>Gerenciamento de reputação

Os fornecedores, ISP e outros provedores de serviços devem gerenciar ativamente a reputação de seus endereços IP de saída.

## <a name="microsoft-365-limits"></a>Limites do Microsoft 365

Os envios devem cumprir os limites do Microsoft 365 listados nos Limites [da Proteção do Exchange Online.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-limits)

## <a name="email-delivery-resources-and-organizations"></a>Organizações e recursos de entrega de email

A Microsoft trabalha ativamente com órgãos do setor e provedores de serviços para melhorar o ecossistema de internet e email. Essas organizações publicaram documentos de práticas recomendas aos que damos suporte e recomendamos que os envios aderem. Isso melhora sua capacidade de entregar emails entre vários provedores de serviços de email em todo o mundo.

- [Grupo de trabalho anti-abuso móvel de malware de mensagens](https://www.m3aawg.org/)

- [Online Trust Alliance](https://www.otalliance.org/resources)

- [Remetente de email & provedor de internet](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Relatórios de abusos e spam

Para relatar emails ilegais, ofensivos, indesejados ou mal-intencionados, confira [As mensagens e arquivos de relatório para a Microsoft.](report-junk-email-messages-to-microsoft.md) O envio desses tipos de comunicações é uma violação da política da Microsoft e a ação apropriada será tomada em relatórios confirmados.

## <a name="law-enforcement"></a>Aplicação da lei

Se você for membro das autoridades legais e quiser atender à Microsoft Corporation com documentação legal sobre o Office 365 ou se tiver dúvidas sobre a documentação legal enviada à Microsoft, ligue para (1) (425) 722-1299.
