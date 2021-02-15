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
description: Com o Office 365, seu conteúdo é criptografado em repouso e em trânsito com a criptografia, protocolos e tecnologias mais fortes disponíveis. Obter uma visão geral da criptografia no Office 365.
ms.openlocfilehash: 1aee9d401891e807f572c1eed2bc22a54f39e534
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709562"
---
# <a name="encryption"></a>Criptografia

A criptografia é uma parte importante da estratégia de proteção de arquivos e informações. Este artigo fornece uma visão geral da criptografia do Office 365. Obter ajuda com tarefas de criptografia, como configurar a criptografia para sua organização e como proteger documentos do Office com senha.
  
- Para saber mais sobre certificados e tecnologias como TLS, confira Detalhes de referência técnica sobre criptografia [no Office 365.](technical-reference-details-about-encryption.md)

- Para obter informações sobre como configurar ou configurar a criptografia para sua organização, consulte [Configurar a criptografia no Office 365 Enterprise.](set-up-encryption.md)

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>O que é criptografia e como ela funciona no Office 365?

O processo de criptografia codifica seus dados (chamados de texto sem formatação) em texto cifrado. Ao contrário de texto sem formatação, o texto cifrado não pode ser usado por pessoas ou computadores, a menos e até que o texto cifrado seja descriptografado. A descriptografia requer uma chave de criptografia que somente usuários autorizados tenham. A criptografia ajuda a garantir que apenas destinatários autorizados possam descriptografar seu conteúdo. O conteúdo inclui arquivos, mensagens de email, entradas de calendário e assim por diante.
  
A criptografia por si só não impede a interceptação de conteúdo. A criptografia faz parte de uma estratégia de proteção de informações maior para sua organização. Usando a criptografia, você ajuda a garantir que somente as partes autorizadas possam usar os dados criptografados.
  
Você pode ter várias camadas de criptografia ao mesmo tempo. Por exemplo, você pode criptografar mensagens de email e também os canais de comunicação por meio dos quais seus emails fluem. Com o Office 365, seus dados são criptografados em repouso e em trânsito, usando vários protocolos de criptografia fortes e tecnologias que incluem TLS/SSL (Transport Layer Security/Secure Sockets Layer), IPSec (Internet Protocol Security) e Advanced Encryption Standard (AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Criptografia de dados em repouso e dados em trânsito

 **Exemplos** de dados em repouso incluem arquivos que você carregou em uma biblioteca do SharePoint, dados do Project Online, documentos que você carregou em uma reunião do Skype for Business, mensagens de email e anexos que você armazenou em pastas em sua caixa de correio e arquivos que você carregou no OneDrive for Business.
  
 **Exemplos de dados em trânsito** incluem mensagens de email que estão sendo entregues ou conversas que estão ocorrendo em uma reunião online. No Office 365, os dados estão em trânsito sempre que o dispositivo do usuário está se comunicando com um servidor da Microsoft ou quando um servidor da Microsoft está se comunicando com outro servidor.
  
Com o Office 365, várias camadas e tipos de criptografia trabalham juntos para proteger seus dados. A tabela a seguir inclui alguns exemplos, com links para informações adicionais.
  
|**Tipos de conteúdo**|**Tecnologias de criptografia**|**Recursos para saber mais**|
|:-----|:-----|:-----|
|Arquivos em um dispositivo. Esses arquivos podem incluir mensagens de email salvas em uma pasta, documentos do Office salvos em um computador, tablet ou telefone ou dados salvos na nuvem da Microsoft.  <br/> |BitLocker em datacenters da Microsoft. O BitLocker também pode ser usado em computadores cliente, como computadores Windows e tablets  <br/> Distributed Key Manager (DKM) em datacenters da Microsoft  <br/> Chave do cliente do Microsoft 365  <br/> |[Centro de IT do Windows: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Central de Confiações da Microsoft: Criptografia](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Série de controles de segurança na nuvem: Criptografando Dados em Repouso](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Como o Exchange Online protege seus segredos de email](exchange-online-secures-email-secrets.md) <br/> [Criptografia do serviço com a Chave de Cliente](customer-key-overview.md) <br/> |
|Arquivos em trânsito entre usuários. Esses arquivos podem incluir documentos do Office ou itens de lista do SharePoint compartilhados entre usuários.  <br/> |TLS para arquivos em trânsito  <br/> |[Criptografia de dados no OneDrive for Business e no SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online: Segurança e Arquivamento](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|Email em trânsito entre destinatários. Esse email inclui emails hospedados pelo Exchange Online.  <br/> |Criptografia de Mensagens do Office 365 com Azure Rights Management, S/MIME e TLS para email em trânsito  <br/> |[Criptografia de Mensagens do Office 365 (OME)](ome.md) <br/> [Criptografia de email no Office 365](email-encryption.md) <br/> [Como o Exchange Online usa o TLS para proteger conexões de email no Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chats, mensagens e arquivos em trânsito entre destinatários usando o Microsoft Teams. <br/> |O Teams usa TLS e MTLS para criptografar mensagens instantâneas. O tráfego de mídia é criptografado usando SRTP (Secure RTP). O Teams usa algoritmos compatíveis com FIPS (Federal Information Processing Standard) para trocas de chaves de criptografia. <br/> |[Criptografia para o Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>E se eu precisar de mais controle sobre criptografia para atender aos requisitos de segurança e conformidade?

O Microsoft 365 fornece soluções gerenciadas pela Microsoft para criptografia de volume, criptografia de arquivo e criptografia de caixa de correio no Office 365. Além disso, a Microsoft fornece soluções de criptografia que você pode gerenciar e controlar. Essas soluções de criptografia são criadas no Azure.
  
Para saber mais, confira os seguintes recursos:
  
- [ O que é o Azure Rights Management? ](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [Ativar o Gerenciamento de Direitos no centro de administração](https://docs.microsoft.com/microsoft-365/enterprise/activate-rms-in-microsoft-365)

- [Configurar o IRM (Gerenciamento de Direitos de Informação) no centro de administração do SharePoint](set-up-irm-in-sp-admin-center.md)

- [Criptografia de serviço com Chave de Cliente no Office 365](customer-key-overview.md)

- [Criptografia de Chave Dupla para o Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>Como...

|**Para fazer esta tarefa**|**Consulte estes recursos**|
|:-----|:-----|
|Configurar a criptografia para minha organização  <br/> |[Configure a criptografia no Office 365 Enterprise](set-up-encryption.md) <br/> |
|Exibir detalhes sobre certificados, tecnologias e pacote de codificação TLS <br/> |[Detalhes técnicos sobre criptografia](technical-reference-details-about-encryption.md) <br/> |
|Trabalhar com mensagens criptografadas em um dispositivo móvel  <br/> |[Exibir mensagens criptografadas em seu dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Exibir mensagens criptografadas em seu iPhone ou iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Criptografar um documento usando proteção por senha  <br/><br/>  A proteção por senha não é suportada em um navegador. Use versões da área de trabalho do Word, Excel e PowerPoint para proteção por senha. |[Adicionar ou remover proteção em seu documento, a agenda ou a apresentação](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Escolha uma **seção Adicionar proteção** e consulte **Criptografar com Senha.**  |
|Remover a criptografia de um documento  <br/> |[Adicionar ou remover proteção em seu documento, a agenda ou a apresentação](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Choose a **Remove protection** section, and then see Remove **password encryption**.  |


## <a name="related-topics"></a>Tópicos relacionados

[Planejar recursos de proteção de informações e segurança do Microsoft 365](plan-for-security-and-compliance.md)

[10 principais maneiras de proteger os planos do Microsoft 365 para empresas](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)

[Fluxo de reprodução e criptografia de nível de vídeo do Microsoft Stream](https://docs.microsoft.com/stream/network-overview#video-level-encryption-and-playback-flow)
