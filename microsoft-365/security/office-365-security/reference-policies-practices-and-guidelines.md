---
title: Políticas de referência, práticas e diretrizes
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ff3f140b-b005-445f-bfe0-7bc3f328aaf0
ms.collection:
- M365-security-compliance
description: A Microsoft desenvolveu várias políticas, procedimentos e adotou várias práticas recomendadas do setor para ajudar a proteger os usuários de emails ofensivos, indesejados ou mal-intencionados.
ms.openlocfilehash: 0957e34008f4e05693218970c458656d73d9c0fe
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031806"
---
# <a name="reference-policies-practices-and-guidelines"></a>Referência: políticas, práticas e diretrizes

A Microsoft é dedicada a ajudar a fornecer a experiência de usuário mais confiável na Web. Portanto, a Microsoft desenvolveu várias políticas, procedimentos e adotou várias práticas recomendadas do setor para ajudar a proteger os usuários de emails ofensivos, indesejados ou mal-intencionados. Os remetentes que tentam enviar emails para os usuários do Office 365 devem garantir que eles compreendam e estejam seguindo as orientações deste artigo para ajudar nesse esforço e para ajudar a evitar possíveis problemas de entrega.

Se você não estiver em conformidade com essas políticas e diretrizes, talvez não seja possível que a nossa equipe de suporte o ajude. Se você estiver seguindo as diretrizes, as práticas e as políticas apresentadas neste artigo e ainda estiver tendo problemas de entrega com base no seu endereço IP de envio, siga as etapas para enviar uma solicitação de deslistação. Para obter instruções, confira [usar o portal de remoção da lista para ser removido da lista de remetentes bloqueados do Office 365](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).

## <a name="general-microsoft-policies"></a>Políticas gerais da Microsoft

Os emails enviados para os usuários do Office 365 devem estar em conformidade com todas as políticas da Microsoft que regem a transmissão de email e o uso do Office 365.

- Termos de serviços aplicáveis ao Office 365; em particular, a proibição contra o uso do serviço para spam ou distribuição de malware

- [Contrato de serviços Microsoft](https://www.microsoft.com/servicesagreement/)

## <a name="governmental-regulations"></a>Normas governamentais

Os emails enviados para os usuários do Office 365 devem aderir a todas as leis e regulamentos aplicáveis que regem as comunicações de email na jurisdição aplicável.

- [Lei CAN-SPAM: um guia de conformidade para empresas](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business)

- ["Remover" as respostas e responsabilidades: os marketing de emails devem honrar as declarações "cancelar assinatura"](https://www.lawpublish.com/ftc-emai-marketers-unsubscribe-claims.mdl)

## <a name="technical-guidelines"></a>Orientações técnicas

Os emails enviados para o Office 365 devem estar em conformidade com as recomendações aplicáveis listadas nos documentos abaixo (alguns links estão disponíveis apenas em inglês).

- [RFC 2505: recomendações de antispam para SMTP MTAs](https://www.ietf.org/rfc/rfc2505.txt)

- [RFC 2920: extensão de serviço SMTP para pipeline de comando](https://www.ietf.org/rfc/rfc2920.txt)

Além disso, os servidores de email que se conectam ao Office 365 devem aderir aos seguintes requisitos:

- O remetente deve estar em conformidade com todos os padrões técnicos para a transmissão de emails da Internet, conforme publicado pela IETF (Internet Engineering Task Force) da Internet Society, incluindo RFC 5321, RFC 5322 e outros.

- Após receber um código de resposta de erro SMTP numérico entre 500 e 599 (também conhecido como uma resposta ou NDR permanente de falha na entrega), o remetente não deve tentar retransmitir essa mensagem para esse destinatário.

- Após várias respostas de não entrega, o remetente deve cessar outras tentativas de envio de email para esse destinatário.

- As mensagens não devem ser transmitidas por meio de servidores proxy ou de retransmissão de emails não seguros.

- O mecanismo de cancelamento de desconexão, de listas individuais ou de todas as listas hospedadas pelo remetente, deve ser claramente documentado e fácil para os destinatários encontrarem e usarem.

- As conexões do espaço IP dinâmico podem não ser aceitas.

- Os servidores de email devem ter registros DNS reversos válidos.

## <a name="reputation-management"></a>Gerenciamento de reputação

Remetentes, ISPs e outros provedores de serviços devem gerenciar ativamente a reputação dos endereços IP de saída.

## <a name="office-365-limits"></a>Limites do Office 365

Os remetentes devem aderir aos limites do Office 365 listados nos [limites do Exchange Online Protection](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx).

## <a name="email-delivery-resources-and-organizations"></a>Recursos de entrega de email e organizações

A Microsoft trabalha ativamente com órgãos de mercado e provedores de serviços para melhorar a Internet e o ecossistema de email. Essas organizações publicaram documentos de práticas recomendadas que suportamos e recomendamos que os remetentes sigam. Isso melhora a capacidade de entregar emails entre vários provedores de serviço de email em todo o mundo.

- [Grupo de trabalho de antiabuso móvel de malware de mensagens](https://www.m3aawg.org/)

- [Aliança de confiança online](https://www.otalliance.org/resources)

- [Coalition de &amp; provedor de remetente de email](https://www.espcoalition.org/)

## <a name="abuse-and-spam-reporting"></a>Relatórios de abuso e spam

Para relatar um email ilegal, abusivo, indesejado ou mal-intencionado, [denuncie o lixo eletrônico e golpes de phishing no Outlook na Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). O envio desses tipos de comunicação é uma violação da política da Microsoft e a ação apropriada será realizada nos relatórios confirmados.

## <a name="law-enforcement"></a>Aplicação de leis

Se você for membro da imposição de leis e quiser atender à Microsoft Corporation com a documentação legal sobre o Office 365, ou se tiver dúvidas sobre a documentação legal que você enviou à Microsoft, ligue para (1) (425) 722-1299.
