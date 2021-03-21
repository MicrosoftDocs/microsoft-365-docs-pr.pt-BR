---
title: Recursos de criptografia de gerenciamento de cliente
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
ms.custom:
- seo-marvel-mar2020
description: Neste artigo, você aprenderá sobre tecnologias de criptografia que você pode gerenciar e configurar no Microsoft 365.
ms.openlocfilehash: 6a693c512100c59eef47414fdd6eab4a2924e835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926229"
---
# <a name="customer-managed-encryption-features"></a>Recursos de criptografia de gerenciamento de cliente

Juntamente com as tecnologias de criptografia no Microsoft 365 gerenciadas pela Microsoft, o Microsoft 365 também funciona com tecnologias de criptografia adicionais que você pode gerenciar e configurar, como:

- [Azure Rights Management](/azure/information-protection/what-is-azure-rms)

- [Secure Multipurpose Internet Mail Extension](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Criptografia de mensagem do Office 365](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Fluxo de email seguro com uma organização parceira](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Para obter informações adicionais sobre essas tecnologias, consulte as descrições de serviço [do Microsoft 365.](/office365/servicedescriptions/office-365-service-descriptions-technet-library)

## <a name="azure-rights-management"></a>Azure Rights Management

[O Azure Rights Management](/azure/information-protection/what-is-azure-rms) (Azure RMS) é a tecnologia de proteção usada pela [Proteção de Informações do Azure.](/information-protection/understand-explore/what-is-information-protection) Ele usa políticas de criptografia, identidade e autorização para ajudar a proteger seus arquivos e emails em várias plataformas e dispositivos — telefones, tablets e computadores. As informações podem ser protegidas dentro e fora da sua organização porque a proteção permanece com os dados. O Azure RMS fornece proteção persistente de todos os tipos de arquivo, protege arquivos em qualquer lugar, dá suporte à colaboração entre empresas e uma ampla variedade de dispositivos Windows e não Windows. A proteção do Azure RMS também pode aumentar as políticas de prevenção contra perda de [dados (DLP).](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) Para obter mais informações sobre quais aplicativos e serviços podem usar o serviço de Gerenciamento de Direitos do Azure da Proteção de Informações do Azure, consulte Como os aplicativos suportam o serviço de Gerenciamento de Direitos do [Azure.](/information-protection/understand-explore/applications-support)

O Azure RMS é integrado ao Microsoft 365 e está disponível para todos os clientes. Para configurar o Microsoft 365 para usar o Azure RMS, consulte [Configure IRM to use Azure Rights Management and Set up Information Rights Management (IRM) in SharePoint admin center](../enterprise/activate-rms-in-microsoft-365.md). Se você operar o servidor RMS do Active Directory (AD) local, também poderá configurar o IRM para usar um servidor [AD RMS](/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)local, mas recomendamos que você migre para o [Azure RMS](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) para usar novos recursos, como colaboração segura com outras organizações.

Quando você protege os dados do cliente com o Azure RMS, o Azure RMS usa uma chave assimétrica RSA de 2048 bits com algoritmo de hash SHA-256 para integridade para criptografar os dados. A chave simétrica para documentos e emails do Office é AES de 128 bits. Para cada documento ou email protegido pelo Azure RMS, o Azure RMS cria uma única chave do AES (a "chave de conteúdo") e essa chave é inserida no documento e persiste por meio de edições do documento. A chave de conteúdo é protegida com a chave RSA da organização (a "chave de locatário da Proteção de Informações do Azure") como parte da política no documento, e a política também é assinada pelo autor do documento. Essa chave de locatário é comum a todos os documentos e emails protegidos pelo Azure RMS para a organização e essa chave só poderá ser alterada por um administrador da Proteção de Informações do Azure se a organização estiver usando uma chave de locatário gerenciada pelo cliente. Para obter mais informações sobre os controles criptográficos usados pelo Azure RMS, consulte [How does Azure RMS work? Sob o hood](/information-protection/understand-explore/how-does-it-work).

Em uma implementação padrão do Azure RMS, a Microsoft gera e gerencia a chave raiz exclusiva para cada locatário. Os clientes podem gerenciar o ciclo de vida de sua chave raiz no Azure RMS com o Azure Key Vault Services usando um método de gerenciamento de chave chamado [Bring Your Own Key (BYOK)](/azure/information-protection/plan-implement-tenant-key) que permite que você gerencie sua chave em HSMs locais (módulos de segurança de hardware) e mantenha o controle dessa chave após a transferência para os HSMs do Nível 2 do FIPS 140-2 da Microsoft. O acesso à chave raiz não é dado a nenhuma equipe, pois as chaves não podem ser exportadas ou extraídas das HSMs que as protegem. Além disso, você pode acessar um log quase em tempo real mostrando todo o acesso à chave raiz a qualquer momento. Para obter mais informações, consulte [Logging and Analyzing Azure Rights Management Usage](/azure/information-protection/log-analyze-usage).

O Gerenciamento de Direitos do Azure ajuda a reduzir ameaças, como escuta telefônica, ataques man-in-the-middle, roubo de dados e violações não intencional de políticas de compartilhamento organizacional. Ao mesmo tempo, qualquer acesso injustificável de dados do cliente em trânsito ou em repouso por um usuário não autorizado que não tenha permissões apropriadas é impedido por meio de políticas que seguem esses dados, atenuando assim o risco de que esses dados caiam em mãos erradas, de forma consciente ou não, e fornecendo funções de prevenção contra perda de dados. Se usado como parte da Proteção de Informações do Azure, o Azure RMS também fornece recursos de Classificação de Dados e rotulagem, marcação de conteúdo, controle de acesso a documentos e recursos de revogação de acesso. Para saber mais sobre esses recursos, consulte O que é a Proteção de Informações do [Azure,](/information-protection/understand-explore/what-is-information-protection)o roteiro de implantação da Proteção de Informações do [Azure](/information-protection/plan-design/deployment-roadmap)e o tutorial de início rápido para a Proteção de Informações [do Azure.](/information-protection/get-started/infoprotect-quick-start-tutorial)

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

Secure/Multipurpose Internet Mail Extensions (S/MIME) é um padrão para criptografia de chave pública e assinatura digital de dados MIME. S/MIME é definido nos RFCs 3369, 3370, 3850, 3851 e outros. Ele permite que um usuário criptografe um email e assine digitalmente um email. Um email criptografado usando S/MIME só pode ser descriptografado pelo destinatário do email usando sua chave privada, que só está disponível para esse destinatário. Dessa forma, os emails não podem ser descriptografados por qualquer pessoa que não seja o destinatário do email.

[A Microsoft dá suporte a S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). Os certificados públicos são distribuídos para o Active Directory local do cliente e armazenados em atributos que podem ser replicados para um locatário do Microsoft 365. As chaves privadas que correspondem às chaves públicas permanecem no local e nunca são transmitidas para o Office 365. Os usuários podem compor, criptografar, descriptografar, ler e assinar digitalmente emails entre dois usuários em uma organização usando o Outlook, o Outlook na Web e Exchange ActiveSync clientes. Para obter mais informações, consulte [Criptografia S/MIME agora no Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Criptografia de Mensagem do Office 365

A Criptografia de Mensagens do [Office 365](https://products.office.com/exchange/office-365-message-encryption) (OME) criada sobre a Proteção de Informações do [Azure](/information-protection/understand-explore/what-is-information-protection) (AIP) permite que você envie emails criptografados e protegidos por direitos para qualquer pessoa. O OME atenua ameaças como escutas telefônicas e ataques de homem no meio e outras ameaças, como o acesso injustificável de dados por um usuário não autorizado que não tem permissões apropriadas. Fizemos investimentos que oferecem uma experiência de email mais simples, mais intuitiva e segura, criada em cima da Proteção de Informações do Azure. Você pode proteger mensagens enviadas do Microsoft 365 para qualquer pessoa dentro ou fora da sua organização. Essas mensagens podem ser exibidas em um conjunto diversificado de clientes de email usando qualquer identidade, incluindo o Azure Active Directory, a Conta da Microsoft e as IDs do Google. Para obter mais informações sobre como sua organização pode usar mensagens criptografadas, consulte Criptografia de Mensagem [do Office 365.](./ome.md)

## <a name="transport-layer-security"></a>Protocolo TLS   

Se quiser garantir uma comunicação segura com um parceiro, você pode usar conectores de entrada e de saída para fornecer integridade de mensagens e segurança. Você pode configurar TLS de entrada e saída forçadas em cada conector, usando um certificado. O uso de um canal SMTP criptografado pode impedir que os dados são roubados por meio de um ataque de homem no meio. Para obter mais informações, consulte [Como o Exchange Online usa o TLS para proteger conexões de email.](./exchange-online-uses-tls-to-secure-email-connections.md)

## <a name="domain-keys-identified-mail"></a>Mensagens identificadas por Chaves de Domínio

O Exchange Online Protection (EOP) e o Exchange Online suportam validação de entrada de mensagens de Email Identificado por Chaves de Domínio (DKIM). DKIM é um método para validar que uma mensagem foi enviada do domínio que ela diz ter originado e que não foi falsificada por qualquer outra pessoa. Ela vincula uma mensagem de email à organização responsável por enviá-la e faz parte de um paradigma maior da criptografia de email. Para obter mais informações sobre as três partes deste paradigma, consulte:

- [Configurar o SPF para ajudar a prevenir falsificação](/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Usar o DKIM para validar emails enviados de seu domínio personalizado](/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Usar DMARC para validar emails](/office365/SecurityCompliance/use-dmarc-to-validate-email)