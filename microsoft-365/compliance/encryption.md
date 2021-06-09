---
title: Criptografia no Microsoft 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
- m365solution-mip
- m365initiative-compliance
description: Com Office 365, seu conteúdo é criptografado em repouso e em trânsito com a criptografia, protocolos e tecnologias mais fortes disponíveis. Obter uma visão geral da criptografia em Office 365.
ms.openlocfilehash: c54508434c5ae5126a79eba1cb6dab3851d8f746
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926439"
---
# <a name="encryption"></a>Criptografia

A criptografia é uma parte importante da sua estratégia de proteção de arquivos e proteção de informações. Este artigo fornece uma visão geral da criptografia para Office 365. Obter ajuda com tarefas de criptografia, como como configurar a criptografia para sua organização e como proteger Office documentos.
  
- Para obter informações sobre certificados e tecnologias como TLS, consulte [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).

- Para obter informações sobre como configurar ou configurar a criptografia para sua organização, consulte [Set up encryption in Office 365 Enterprise](set-up-encryption.md).

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>O que é criptografia e como ela funciona Office 365?

O processo de criptografia codifica seus dados (chamado de texto sem formatação) em texto cifrado. Ao contrário do texto sem formatação, o texto cifrado não pode ser usado por pessoas ou computadores, a menos que e até que o texto cifrado seja descriptografado. A descriptografia requer uma chave de criptografia que somente usuários autorizados têm. A criptografia ajuda a garantir que somente destinatários autorizados possam descriptografar seu conteúdo. O conteúdo inclui arquivos, mensagens de email, entradas de calendário e assim por diante.
  
A criptografia por si só não impede a interceptação de conteúdo. A criptografia faz parte de uma estratégia de proteção de informações maior para sua organização. Ao usar a criptografia, você ajuda a garantir que somente as partes autorizadas possam usar os dados criptografados.
  
Você pode ter várias camadas de criptografia no local ao mesmo tempo. Por exemplo, você pode criptografar mensagens de email e também os canais de comunicação pelos quais seu email flui. Com o Office 365, seus dados são criptografados em repouso e em trânsito, usando vários protocolos de criptografia fortes e tecnologias que incluem Transport Layer Security/Secure Sockets Layer (TLS/SSL), IPSec (Internet Protocol Security) e Advanced Encryption Standard (AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Criptografia para dados em repouso e dados em trânsito

 **Exemplos** de dados em repouso incluem arquivos que você carregou em uma biblioteca do SharePoint, dados do Project Online, documentos que você carregou em uma reunião do Skype for Business, mensagens de email e anexos que você armazenou em pastas em sua caixa de correio e arquivos carregados no OneDrive for Business.
  
 **Exemplos de dados em trânsito** incluem mensagens de email que estão sendo entregues ou conversas que estão ocorrendo em uma reunião online. No Office 365, os dados estão em trânsito sempre que um dispositivo do usuário está se comunicando com um servidor Microsoft ou quando um servidor Microsoft está se comunicando com outro servidor.
  
Com Office 365, várias camadas e tipos de criptografia trabalham juntos para proteger seus dados. A tabela a seguir inclui alguns exemplos, com links para informações adicionais.
  
|**Tipos de conteúdo**|**Tecnologias de criptografia**|**Recursos para saber mais**|
|:-----|:-----|:-----|
|Arquivos em um dispositivo. Esses arquivos podem incluir mensagens de email salvas em uma pasta, Office documentos salvos em um computador, tablet ou telefone ou dados salvos na nuvem da Microsoft.  <br/> |BitLocker nos datacenters da Microsoft. BitLocker também pode ser usado em computadores cliente, como computadores Windows tablets e computadores  <br/> Distributed Key Manager (DKM) nos datacenters da Microsoft  <br/> Chave do cliente para Microsoft 365  <br/> |[Windows Centro de IT: BitLocker](/windows/device-security/bitlocker/bitlocker-overview) <br/> [Centro de Confiança da Microsoft: Criptografia](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Série de controles de segurança na nuvem: Criptografando dados em repouso](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Como o Exchange Online protege seus segredos de email](exchange-online-secures-email-secrets.md) <br/> [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md) <br/> |
|Arquivos em trânsito entre usuários. Esses arquivos podem incluir Office ou SharePoint de lista compartilhados entre os usuários.  <br/> |TLS para arquivos em trânsito  <br/> |[Criptografia de dados no OneDrive for Business e no SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online: Segurança e Arquivamento](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features) <br/> |
|Email em trânsito entre destinatários. Este email inclui emails hospedados por Exchange Online.  <br/> |Criptografia de Mensagens do Office 365 gerenciamento de direitos do Azure, S/MIME e TLS para email em trânsito  <br/> |[Criptografia de Mensagens do Office 365 (OME)](ome.md) <br/> [Criptografia de email no Office 365](email-encryption.md) <br/> [Como o Exchange Online usa o TLS para proteger conexões de email no Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chats, mensagens e arquivos em trânsito entre destinatários usando Microsoft Teams. <br/> |Teams usa TLS e MTLS para criptografar mensagens instantâneas. O tráfego de mídia é criptografado usando rtp seguro (SRTP). Teams usa algoritmos compatíveis com FIPS (Federal Information Processing Standard) para trocas de chaves de criptografia. <br/> |[Criptografia para Teams](/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>E se eu precisar de mais controle sobre criptografia para atender aos requisitos de segurança e conformidade?

Microsoft 365 fornece soluções gerenciadas pela Microsoft para criptografia de volume, criptografia de arquivo e criptografia de caixa de correio em Office 365. Além disso, a Microsoft fornece soluções de criptografia que você pode gerenciar e controlar. Essas soluções de criptografia são criadas no Azure.
  
Para saber mais, confira os seguintes recursos:
  
- [ O que é o Azure Rights Management? ](/information-protection/understand-explore/what-is-azure-rms)

- [Ativar o Gerenciamento de Direitos no centro de administração](../enterprise/activate-rms-in-microsoft-365.md)

- [Configurar o IRM (Gerenciamento de Direitos de Informação) no centro de administração do SharePoint](set-up-irm-in-sp-admin-center.md)

- [Criptografia de serviço com Chave de Cliente no Office 365](customer-key-overview.md)

- [Criptografia de Chave Dupla para Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>Como...

|**Para fazer essa tarefa**|**Consulte esses recursos**|
|:-----|:-----|
|Configurar criptografia para minha organização  <br/> |[Configure a criptografia no Office 365 Enterprise](set-up-encryption.md) <br/> |
|Exibir detalhes sobre certificados, tecnologias e pacote de codificação TLS <br/> |[Detalhes técnicos sobre criptografia](technical-reference-details-about-encryption.md) <br/> |
|Trabalhar com mensagens criptografadas em um dispositivo móvel  <br/> |[Exibir mensagens criptografadas em seu dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Exibir mensagens criptografadas em seu iPhone ou iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Criptografar um documento usando proteção de senha  <br/><br/>  A proteção por senha não é suportada em um navegador. Use versões da área de trabalho do Word, Excel e PowerPoint para proteção de senha. |[Adicionar ou remover proteção em seu documento, uma workbook ou uma apresentação](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Escolha uma **seção Adicionar proteção** e, em seguida, consulte Encrypt with **Password**.  |
|Remover criptografia de um documento  <br/> |[Adicionar ou remover proteção em seu documento, uma workbook ou uma apresentação](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Escolha uma **seção Remover proteção** e, em seguida, consulte Remover criptografia de **senha**.  |


## <a name="related-topics"></a>Tópicos relacionados

[Planejar recursos Microsoft 365 segurança e proteção de informações](plan-for-security-and-compliance.md)

[Top 10 maneiras de proteger Microsoft 365 para planos de negócios](/office365/admin/security-and-compliance/secure-your-business-data)

[Microsoft Stream Video level encryption and playback flow](/stream/network-overview#video-level-encryption-and-playback-flow)