---
title: Exchange Multigeográfico
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Saiba mais sobre as funcionalidades multi-geográficas no Exchange Online, como limitações de recursos e posicionamento da caixa de correio.
ms.openlocfilehash: ca7203c72f23fd03512bf23eaa5a4687e4bac1b5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687236"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a>Recursos multigeográficos no Exchange Online

Em um ambiente multigeográfico, você pode selecionar o local do conteúdo da caixa de correio do Exchange Online (dados em repouso) por usuário.

Você pode colocar caixas de correio em localização geográfica do satélite por:

- Criar uma nova caixa de correio do Exchange Online diretamente em uma localização geográfica do satélite.

- Mover uma caixa de correio do Exchange Online existente para um local geográfico do satélite, alterando o local de dados preferencial do usuário.

- Integração de uma caixa de correio de uma organização de um local da organização Exchange diretamente para uma localização geográfica do satélite.

## <a name="mailbox-placement-and-moves"></a>Colocação e movimentações de caixa de correio

Depois que a Microsoft concluir as etapas de configuração pré-requisito multigeográfica, o Exchange online segue o atributo **PreferredDataLocation** em objetos de usuário no Azure AD.

O Exchange Online sincroniza a propriedade **PreferredDataLocation** do Azure ad na propriedade **MailboxRegion** no serviço do diretório do Exchange Online. O valor de **MailboxRegion** determina a localização geográfica em que as caixas de correio do usuário e quaisquer caixas de correio de arquivo morto associadas serão colocadas. Não é possível configurar a caixa de correio principal do usuário e as caixas de correio de arquivo morto para residirem em diferentes localizações geográficas. Só é possível configurar uma localização geográfica por objeto do usuário.

- Quando o **PreferredDataLocation** está configurado em um usuário com uma caixa de correio existente, a caixa de correio será inserida em uma fila de realocação e será movida automaticamente para a localização geográfica especificada.

- Quando o **PreferredDataLocation** está configurado em um usuário com uma caixa de correio existente, quando você fornece a caixa de correio, ela será fornecida para a localização geográfica especificada.

- Quando o **PreferredDataLocation** não está especificado em um usuário, quando você fornece a caixa de correio, ela será fornecida para a localização geográfica central.

- Se o código **PreferredDataLocation** estiver incorreto (por exemplo, um tipo de NAN, em vez de NAM), a caixa de correio será provisionada na localização geográfica central.

**Observação**: os recursos multigeográficos e as reuniões hospedadas regionalmente do Skype for Business Online usam a propriedade **PreferredDataLocation** em objetos de usuário para localizar os serviços. Se você configurar os valores **PreferredDataLocation** nos objetos de usuário das reuniões hospedadas regionalmente, a caixa de correio desses usuários será automaticamente movida ao local geográfico especificado após a habilitação múltipla ser ativada no locatário do Microsoft 365.

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Limitações de recursos para a funcionalidade multigeográfica no Exchange Online

- Os recursos de segurança e de conformidade (por exemplo, auditoria e a descoberta eletrônica) que estão disponíveis no centro de administração do Exchange (EAC) não estão disponíveis em organizações multigeográficas. Em vez disso, você precisa usar o [Centro de Conformidade e Segurança do Microsoft 365](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) para configurar recursos de segurança e de conformidade.

- Os usuários do Outlook para Mac podem perder temporariamente o acesso à pasta de arquivo morto online enquanto você move caixa de correio para uma nova localização geográfica. Isso ocorre quando as caixas de correio principal e de arquivo morto do usuário estão em localizações geográficas diferentes, porque as movimentações de caixas de correio geográficas cruzadas podem ser concluídas em diferentes horários.

- Os usuários não podem compartilhar *pastas da caixa de correio* em localizações geográficas no Outlook na Web (conhecido anteriormente como Outlook Web App ou OWA). Por exemplo, um usuário na União Europeia não pode usar o Outlook na Web para abrir uma pasta compartilhada em uma caixa de correio localizada nos Estados Unidos. No entanto, o Outlook na Web pode abrir *outras caixas de correio* em diferentes localizações geográficas usando uma janela separada do navegador, conforme descrito em [Abrir a caixa de correio de outra pessoa em uma janela separada do navegador no Outlook Web App](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362).

  **Observação**: o compartilhamento de pastas de caixa de correio multigeográfica tem suporte no Outlook no Windows.

- As pastas públicas têm suporte nas organizações multigeográficas. No entanto, as pastas públicas devem permanecer na localização multigeográfica central. Você não pode mover pastas públicas para locais geográficos de satélite.

- Em um ambiente de várias regiões, não há suporte para a auditoria de caixas de correio de várias regiões. Por exemplo, se um usuário receber permissões para acessar uma caixa de correio compartilhada em um local geográfico diferente, as ações de caixa de correio executadas por esse usuário não serão registradas no log de auditoria da caixa de correio da caixa de correio compartilhada. Para saber mais, consulte [Gerenciar a auditoria da caixa de correio](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing?view=o365-worldwide).
