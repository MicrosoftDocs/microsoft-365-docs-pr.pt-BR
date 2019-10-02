---
title: 'Etapa 6: configurar criptografia de email'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Entenda e configure o gerenciamento de acesso privilegiado do Office 365.
ms.openlocfilehash: ef9da1d6aea20ef965b56006d91c4da3c0ad18ab
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370428"
---
# <a name="step-6-configure-email-encryption"></a>Etapa 6: configurar criptografia de email

*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*

![Fase 6: proteção de informações](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Há três tipos de criptografia de email no Microsoft 365.

|||
|:-------|:-----|
| Criptografia de Mensagem do Office (OME) | Criptografia para email do Exchange Online enviado fora da sua organização. |
| Gerenciamento de Direitos de Informação (IRM) | Criptografia e permissões que trafegam com o email. |
| S/MIME (Secure/Multipurpose Internet Mail Extensions) | Proteção de email com criptografia e assinaturas digitais. |
|||

## <a name="office-365-message-encryption"></a>Criptografia de Mensagem do Office 365

Com o OME, sua organização pode enviar e receber mensagens de email criptografadas entre pessoas dentro e fora da sua organização. O OME funciona com o Outlook.com, o Yahoo!, o Gmail e outros serviços de email. A criptografia de mensagens de email ajuda a garantir que apenas destinatários pretendidos possam exibir a mensagem.

![Criptografia OME de mensagens de email](./media/infoprotect-email-encryption/ome-encryption.png)

Você configura regras de transporte que definem as condições de criptografia. Quando um usuário envia uma mensagem que corresponde a uma regra, a criptografia é aplicada automaticamente.

Para exibir mensagens criptografadas, os destinatários podem obter uma senha de uso único, entrar com uma conta da Microsoft ou entrar com uma conta corporativa ou de estudante associada ao Microsoft 365. Os destinatários também podem enviar respostas criptografadas. Eles não precisam de sua própria assinatura do Microsoft 365 para exibir mensagens criptografadas ou enviar respostas criptografadas.

Para saber mais, veja [Criptografia de Mensagens do Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ome).

## <a name="irm"></a>IRM

O IRM no Microsoft 365 ajuda você a proteger suas informações com criptografia adicional e aplicando uma política inteligente que especifica quem tem acesso ao que eles podem fazer. Para mensagens de email, você pode usar o IRM para criptografia e aplicar restrições de uso. Por exemplo, você pode especificar que alguns destinatários tenham todos os recursos para gerenciar o email e alguns não tenham a capacidade de imprimir ou encaminhar o email. 

As políticas de IRM são configuradas no Microsoft 365 e podem ser aplicadas a documentos no SharePoint Online e mensagens de email. Um email protegido por IRM inclui as configurações de política aplicadas aplicadas e viajar com ela. 

![Proteção do IRM de mensagens de email](./media/infoprotect-email-encryption/irm-protection.png)

Quando o destinatário abre o email com a política incluída, as configurações de política são usadas para descriptografar a mensagem e determinar o que o destinatário pode fazer com ele. 

Confira mais informações em [Gerenciamento de Direitos de Informação no Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).

## <a name="smime"></a>S/MIME

O S/MIME é uma solução de proteção baseada em email digital baseada em certificado que permite criptografar e assinar digitalmente uma mensagem. A criptografia de mensagem ajuda a garantir que somente o destinatário pretendido poderá abrir e ler a mensagem. Uma assinatura digital ajuda o destinatário a validar a identidade do remetente e a determinar que apenas o remetente poderia enviá-lo.

![Proteção S/MIME de mensagens de email](./media/infoprotect-email-encryption/smime-protection.png)

O S/MIME pode ser usado para emails para outras caixas de correio em sua assinatura do Microsoft 365 ou para usuários externos.
Tanto a criptografia de mensagens quanto as assinaturas digitais são possibilitadas por meio do uso de certificados digitais que contenham as chaves pública e privada para criptografar ou descriptografar mensagens e criar e verificar assinaturas digitais.
Para usar S/MIME, você deve ter as chaves públicas para cada destinatário. Os destinatários mantêm suas próprias chaves privadas, o que deve permanecer seguro. Se sua chave privada estiver comprometida, você precisará obter um novo certificado digital e redistribuir as chaves públicas para todos os remetentes potenciais.

Para obter mais informações, consulte [S/MIME para assinatura e criptografia de mensagens](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).


Como um ponto de verificação provisório, confira o [Critério de saída](infoprotect-exit-criteria.md#crit-infoprotect-step6) correspondente desta etapa.

## <a name="next-step"></a>Próxima etapa

|||
|:-------|:-----|
|![Etapa 7](./media/stepnumbers/Step7.png)|[Configurar o gerenciamento de acesso privilegiado do Office 365](infoprotect-configure-privileged-access-management.md)|
