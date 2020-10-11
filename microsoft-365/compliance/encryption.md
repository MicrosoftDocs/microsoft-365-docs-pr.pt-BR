---
title: Criptografia
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
description: Com o Office 365, seu conteúdo é criptografado em repouso e em trânsito com a criptografia, protocolos e tecnologias mais fortes disponíveis. Obtenha uma visão geral da criptografia no Office 365.
ms.openlocfilehash: 28a5b55e63c3b66725aaa4a21e5dc750105c7c5a
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408591"
---
# <a name="encryption"></a>Criptografia

A criptografia é uma parte importante da estratégia de proteção de arquivos e proteção de informações. Este artigo fornece uma visão geral da criptografia para o Office 365. Obtenha ajuda com tarefas de criptografia, como configurar a criptografia para sua organização e como proteger com senha documentos do Office.
  
- Para obter informações sobre certificados e tecnologias como TLS, consulte [Technical Reference Details about Encryption in Office 365](technical-reference-details-about-encryption.md).

- Para obter informações sobre como configurar ou configurar a criptografia para sua organização, consulte [set up Encryption in Office 365 Enterprise](set-up-encryption.md).

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>O que é criptografia e como ela funciona no Office 365?

O processo de criptografia codifica seus dados (chamados de texto sem formatação) em texto cifrado. Diferentemente de texto não criptografado, o texto cifrado não pode ser usado por pessoas ou computadores, a menos que e até que o texto cifrado A descriptografia requer uma chave de criptografia que apenas usuários autorizados têm. A criptografia ajuda a garantir que apenas destinatários autorizados possam descriptografar o conteúdo. O conteúdo inclui arquivos, mensagens de email, entradas de calendário e assim por diante.
  
A criptografia por si só não impede a interceptação de conteúdo. A criptografia faz parte de uma estratégia de proteção de informações maior para sua organização. Usando a criptografia, você ajuda a garantir que apenas partes autorizadas possam usar os dados criptografados.
  
Você pode ter várias camadas de criptografia no lugar ao mesmo tempo. Por exemplo, você pode criptografar mensagens de email e também os canais de comunicação através dos quais seu email flui. Com o Office 365, seus dados são criptografados em repouso e em trânsito, usando vários protocolos de criptografia fortes e tecnologias que incluem segurança da camada de transporte/camada de soquetes seguros (TLS/SSL), segurança do protocolo Internet (IPSec) e padrão de criptografia avançada (AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Criptografia de dados em repouso e dados em trânsito

 **Exemplos de dados em repouso** incluem arquivos que você carregou para uma biblioteca do SharePoint, dados do Project online, documentos que você carregou em uma reunião do Skype for Business, mensagens de email e anexos que você armazenou em pastas na sua caixa de correio e arquivos que você carregou para o onedrive for Business.
  
 **Exemplos de dados em trânsito** incluem mensagens de email que estão no processo de entrega ou conversas que estão ocorrendo em uma reunião online. No Office 365, os dados estão em trânsito sempre que o dispositivo de um usuário está se comunicando com um servidor Microsoft ou quando um servidor Microsoft está se comunicando com outro servidor.
  
Com o Office 365, várias camadas e tipos de criptografia funcionam juntos para proteger seus dados. A tabela a seguir inclui alguns exemplos, com links para informações adicionais.
  
|**Tipos de conteúdo**|**Tecnologias de criptografia**|**Recursos para saber mais**|
|:-----|:-----|:-----|
|Arquivos em um dispositivo. Esses arquivos podem incluir mensagens de email salvas em uma pasta, documentos do Office salvos em um computador, Tablet ou telefone ou dados salvos na nuvem da Microsoft.  <br/> |BitLocker nos datacenters da Microsoft. O BitLocker também pode ser usado em máquinas clientes, como computadores e tablets do Windows  <br/> Gerenciador de chaves distribuídas (DKM) nos datacenters da Microsoft  <br/> Chave do cliente para o Microsoft 365  <br/> |[Centro de ti do Windows: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Centro de confiança da Microsoft: criptografia](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Série de controles de segurança na nuvem: Criptografando dados em repouso](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Como o Exchange Online protege seus segredos de email](exchange-online-secures-email-secrets.md) <br/> [Criptografia de serviço com a chave do cliente](customer-key-overview.md) <br/> |
|Arquivos em trânsito entre usuários. Esses arquivos podem incluir documentos do Office ou itens de lista do SharePoint compartilhados entre usuários.  <br/> |TLS para arquivos em trânsito  <br/> |[Criptografia de dados no OneDrive for Business e no SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online: segurança e arquivamento](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|Email em trânsito entre destinatários. Este email inclui email hospedado pelo Exchange Online.  <br/> |Criptografia de mensagem do Office 365 com o Azure Rights Management, S/MIME e TLS para email em trânsito  <br/> |[Criptografia de Mensagens do Office 365 (OME)](ome.md) <br/> [Criptografia de email no Office 365](email-encryption.md) <br/> [Como o Exchange Online usa o TLS para proteger conexões de email no Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chats, mensagens e arquivos em trânsito entre destinatários usando o Microsoft Teams. <br/> |O Microsoft Teams usa TLS e MTLS para criptografar mensagens instantâneas. O tráfego de mídia é criptografado usando o protocolo SRTP (Secure RTP). O Microsoft Teams usa algoritmos compatíveis com FIPS (Federal Information Processing Standard) para trocas de chave de criptografia. <br/> |[Criptografia para o Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>E se eu precisar de mais controle sobre a criptografia para atender aos requisitos de segurança e conformidade?

A Microsoft 365 fornece soluções gerenciadas pela Microsoft para criptografia de volume, criptografia de arquivo e criptografia de caixa de correio no Office 365. Além disso, a Microsoft oferece soluções de criptografia que podem ser gerenciadas e controladas. Essas soluções de criptografia são criadas no Azure.
  
Para saber mais, confira os seguintes recursos:
  
- [ O que é o Azure Rights Management? ](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [Ativar o gerenciamento de direitos no centro de administração](https://docs.microsoft.com/microsoft-365/enterprise/activate-rms-in-microsoft-365)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

- [Criptografia de serviço com Chave de Cliente no Office 365](customer-key-overview.md)

- [Criptografia de chave dupla para o Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>Como...

|**Para executar esta tarefa**|**Confira estes recursos**|
|:-----|:-----|
|Configurar a criptografia para minha organização  <br/> |[Configure a criptografia no Office 365 Enterprise](set-up-encryption.md) <br/> |
|Exibir detalhes sobre certificados, tecnologias e pacotes de criptografia TLS <br/> |[Detalhes técnicos sobre a criptografia](technical-reference-details-about-encryption.md) <br/> |
|Trabalhar com mensagens criptografadas em um dispositivo móvel  <br/> |[Exibir mensagens criptografadas no seu dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Exibir mensagens criptografadas no seu iPhone ou iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Criptografar um documento usando a proteção por senha  <br/><br/>  A proteção por senha não é suportada em um navegador. Use versões de área de trabalho do Word, Excel e PowerPoint para proteção por senha. |[Adicionar ou remover proteção em seu documento, pasta de trabalho ou apresentação](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Escolha uma seção **Adicionar proteção** e, em seguida, confira **criptografar com senha**.  |
|Remover a criptografia de um documento  <br/> |[Adicionar ou remover proteção em seu documento, pasta de trabalho ou apresentação](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Escolha uma seção **remover proteção** e, em seguida, consulte **remover criptografia de senha**.  |


## <a name="related-topics"></a>Tópicos relacionados

[Planejar os recursos de segurança e proteção de informações da Microsoft 365](plan-for-security-and-compliance.md)

[As 10 maneiras principais de proteger os planos do Microsoft 365 for Business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data?view=o365-worldwide)

[Fluxo de reprodução e criptografia no nível de vídeo do Microsoft Stream](https://docs.microsoft.com/stream/network-overview#video-level-encryption-and-playback-flow)
