---
title: Entrega dinâmica e visualização com anexos seguros de ATP do Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 04/19/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: f16c9928-8e3d-4219-b994-271dc9a16272
ms.collection:
- M365-security-compliance
description: Ao configurar as políticas de anexos seguros de ATP, você escolhe a entrega dinâmica para evitar atrasos de mensagens e permite que as pessoas visualizem os anexos que estão sendo examinados.
ms.openlocfilehash: 755a5a317710946a3a03004482a6b48c8947c1a7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599418"
---
# <a name="dynamic-delivery-and-previewing-with-office-365-atp-safe-attachments"></a>Entrega dinâmica e visualização com anexos seguros de ATP do Office 365

## <a name="overview"></a>Visão Geral

A entrega dinâmica é uma opção que pode ser selecionada para [anexos seguros de ATP](atp-safe-attachments.md). Leia este artigo para saber mais sobre a entrega dinâmica e recursos de visualização de anexos nos [anexos seguros de ATP no Office 365](atp-safe-attachments.md).

Quando [as políticas de anexos seguros de ATP estão configuradas](set-up-atp-safe-attachments-policies.md) para sua organização, há várias opções de como os anexos de email são tratados. Eles incluem **bloqueio**, **substituição**e **entrega dinâmica**. Dependendo de como as políticas de anexos seguros de ATP estão configuradas, os destinatários de email podem enfrentar um atraso secundário na entrega de emails enquanto seus anexos são verificados. Para evitar atrasos de mensagens, escolha **entrega dinâmica**.

## <a name="how-dynamic-delivery-works"></a>Como a entrega dinâmica funciona

A entrega dinâmica elimina os atrasos de email enviando o corpo de uma mensagem de email para o destinatário com um espaço reservado para cada anexo de email. O espaço reservado permanece até que uma cópia do anexo seja verificada e determinada como sendo segura por [anexos seguros de ATP](atp-safe-attachments.md).

- Como cada anexo é limpo, ele está disponível para ser aberto ou baixado.

- Se um anexo for considerado mal-intencionado, ele será enviado para a quarentena, onde alguém da equipe de segurança da sua organização (como um administrador global do Office 365 ou administrador de segurança) pode [gerenciar mensagens em quarentena no Office 365](manage-quarantined-messages-and-files.md).

A maioria dos documentos PDFs e do Office pode ser visualizada no modo de segurança enquanto a verificação ATP está em andamento. Se um anexo não for compatível com o modo de exibição de entrega dinâmica, os destinatários de email verão um espaço reservado de anexo até que a verificação de anexos seguros de ATP esteja concluída.

> [!TIP]
> Se você estiver usando um dispositivo móvel e os PDFs não estiverem sendo renderizados no primeiro Visualizador de entrega dinâmica, tente entrar no Office 365 usando seu navegador móvel.

Com a entrega dinâmica, as pessoas podem ler e responder às mensagens de email imediatamente, enquanto seus anexos estão sendo analisados.

A verificação de anexos seguros de ATP ocorre na mesma região onde seus dados do Office 365 residem. Para obter mais informações sobre a geografia do Data Center, confira [onde estão seus dados?](https://products.office.com/where-is-your-data-located?geo=All)

## <a name="what-happens-when-someone-forwards-an-email-that-contains-an-attachment"></a>O que acontece quando alguém encaminha um email que contém um anexo?

Suponha que uma organização esteja usando a entrega dinâmica para a [política de anexos seguros de ATP](set-up-atp-safe-attachments-policies.md)e alguém receba um email que contenha um anexo. Agora, suponha que a pessoa encaminhe a mensagem de email para outra pessoa. O que acontece? Depende de os destinatários adicionais estarem incluídos nas políticas de anexos seguros de ATP.

- Se um destinatário for coberto por uma política de anexos seguros de ATP usando a opção de entrega dinâmica, o destinatário verá o espaço reservado, com a capacidade de visualizar arquivos compatíveis.

- Se um destinatário não for coberto por uma política de anexos seguros de ATP, o email e o anexo serão percorrendo, sem nenhum marcador de verificação de anexos seguros de ATP.

## <a name="whats-required-for-dynamic-delivery-to-work"></a>O que é necessário para que a entrega dinâmica funcione?

- Sua organização deve ter a [proteção avançada contra ameaças do Office 365](office-365-atp.md)

- As políticas devem ser definidas para anexos seguros de ATP usando a opção de entrega dinâmica (consulte [Configurar políticas de anexos seguros de ATP no Office 365](set-up-atp-safe-attachments-policies.md))

- O email da sua organização deve estar hospedado no Office 365. Embora a [proteção avançada contra ameaças do Office 365 possa ser usada com qualquer agente de transferência de email SMTP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#requirements-for-office-365-advanced-threat-protection-atp) (como o Exchange Server), a opção de entrega dinâmica para anexos seguros de ATP requer que o email da sua organização seja hospedado no Office 365. Se seu email não estiver hospedado no Office 365, escolha uma [opção de política de anexos seguros de ATP](set-up-atp-safe-attachments-policies.md#step-3-learn-about-atp-safe-attachments-policy-options)diferente, como **Bloquear**.

## <a name="additional-considerations"></a>Considerações adicionais

Há determinados cenários em que a entrega dinâmica não é suportada. Elas incluem o seguinte:

- Mensagens de email que estão em pastas públicas

- Mensagens de email que são roteadas de e de volta para a caixa de correio do usuário usando regras personalizadas

- Mensagens de email que são movidas (automática ou manualmente) da caixa de correio hospedada e em outros locais, incluindo pastas de arquivos mortos

- Mensagens de email excluídas

- Uma pasta de pesquisa de caixa de correio do usuário que está em um estado de erro

- Ambientes nos quais um administrador do Exchange Online habilitou o Exclaimer. Para resolver isso, confira [mensagens com anexos não são entregues quando a entrega dinâmica e o Exclaimer da ATP são usados](https://support.microsoft.com/help/4014438/messages-with-attachments-are-not-delivered-when-atp-dynamic-delivery)

- Mensagens criptografadas com [S/MIME (Secure/Multipurpose Internet Mail Extensions)](s-mime-for-message-signing-and-encryption.md))

- Nos casos em que a entrega dinâmica não é suportada, os anexos seguros de ATP não verificam as mensagens de email. No entanto, a entrega de mensagens de email com anexos que contenham URLs será verificada, dependendo de como as [políticas de links seguros de ATP](set-up-atp-safe-links-policies.md) estão configuradas. Nesses casos, as URLs em mensagens de email e arquivos do Office são verificadas.
