---
title: Recursos de criptografia gerenciada pelo cliente
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
description: 'Resumo: entenda a resiliência de dados no Microsoft 365.'
ms.openlocfilehash: 365cde7137247e20bb4fd2b57039057398deafd5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637337"
---
# <a name="customer-managed-encryption-features"></a>Recursos de criptografia gerenciada pelo cliente

Juntamente com as tecnologias de criptografia do Microsoft 365 gerenciadas pela Microsoft, a Microsoft 365 também funciona com tecnologias de criptografia adicionais que podem ser gerenciadas e configuradas, como:

- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [Secure Multipurpose Internet Mail Extension](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Criptografia de mensagem do Office 365](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Fluxo de email seguro com uma organização de parceiro](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Para obter mais informações sobre essas tecnologias, consulte as [descrições de serviço do Microsoft 365](https://technet.microsoft.com/library/office-365-service-descriptions.aspx).

## <a name="azure-rights-management"></a>Azure Rights Management

O [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) (Azure RMS) é a tecnologia de proteção usada pela [proteção de informações do Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection). Ele usa políticas de criptografia, identidade e autorização para ajudar a proteger seus arquivos e emails entre várias plataformas e dispositivos — telefones, tablets e PCs. As informações podem ser protegidas dentro e fora da sua organização, pois a proteção permanece com os dados. O Azure RMS fornece proteção persistente de todos os tipos de arquivo, protege arquivos em qualquer lugar, oferece suporte à colaboração entre empresas e uma ampla variedade de dispositivos Windows e não Windows. A proteção do Azure RMS também pode aumentar [as políticas de prevenção contra perda de dados (DLP)](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention). Para obter mais informações sobre quais aplicativos e serviços podem usar o Azure Rights Management Service da proteção de informações do Azure, consulte [How Applications support the Azure Rights Management Service](https://docs.microsoft.com/information-protection/understand-explore/applications-support).

O Azure RMS está integrado ao Microsoft 365 e está disponível para todos os clientes. Para configurar o Microsoft 365 para usar o Azure RMS, confira [Configurar o IRM para usar o Azure Rights Management e configurar o gerenciamento de direitos de informação (IRM) no centro de administração do SharePoint](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx). Se você operar o servidor RMS do Active Directory (AD) no local, você também pode [Configurar o IRM para usar um servidor AD RMS local](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server), mas é altamente recomendável [migrar para o Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) para usar novos recursos, como colaboração segura com outras organizações.

Quando você protege os dados do cliente com o Azure RMS, o Azure RMS usa uma chave assimétrica RSA de 2048 bits com algoritmo de hash SHA-256 para integridade para criptografar os dados. A chave simétrica para documentos do Office e email é AES 128 bits (modo CBC com preenchimento PKCS # 7). Para cada documento ou email protegido pelo Azure RMS, o Azure RMS cria uma única chave AES (a "chave de conteúdo") e essa chave é inserida no documento e persiste pelas edições do documento. A chave de conteúdo é protegida com a chave RSA da organização (a "chave de locatário de proteção de informações do Azure") como parte da política no documento, e a política também é assinada pelo autor do documento. Essa chave de locatário é comum a todos os documentos e emails protegidos pelo Azure RMS para a organização, e essa chave só pode ser alterada por um administrador de proteção de informações do Azure se a organização estiver usando uma chave de locatário gerenciada pelo cliente. Para obter mais informações sobre os controles de criptografia usados pelo Azure RMS, confira [como funciona o Azure RMS? Nos bastidores](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work).

Em uma implementação padrão do Azure RMS, a Microsoft gera e gerencia a chave raiz exclusiva para cada locatário. Os clientes podem gerenciar o ciclo de vida da chave raiz no Azure RMS com os serviços de compartimento de chave do Azure usando um método de gerenciamento de chave chamado [traga sua chave (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) , que permite gerar sua chave em HSMs locais (módulos de segurança de hardware) e permanecer no controle dessa chave após a transferência para o HSMs do FIPS 140-2 nível 2 validado da Microsoft. O acesso à chave raiz não é fornecido a nenhum pessoal, pois as chaves não podem ser exportadas ou extraídas dos HSMs que as protegem. Além disso, você pode acessar um log quase em tempo real, mostrando todos os acessos à chave raiz a qualquer momento. Para obter mais informações, consulte [Logging and analizating Azure Rights Management Usage](https://docs.microsoft.com/azure/information-protection/log-analyze-usage).

O Azure Rights Management ajuda a reduzir as ameaças, como ataques de toque e de interceptação, roubo de dados e violações involuntárias das políticas de compartilhamento organizacional. Ao mesmo tempo, qualquer acesso não garantido dos dados do cliente em trânsito ou em repouso por um usuário não autorizado que não tenha as permissões apropriadas é impedido por meio de políticas que seguem esses dados, reduzindo assim o risco de que os dados caiam nas mãos erradas ou sem saber muito, o que oferece funções de prevenção de perda de dados. Se usado como parte da proteção de informações do Azure, o Azure RMS também fornecerá recursos de classificação e rotulação de dados, marcação de conteúdo, controle de acesso a documentos e recursos de revogação de acesso. Para saber mais sobre esses recursos, confira [o que é proteção de informações do Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection), [roteiro de implantação do Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)e [tutorial de início rápido para a proteção de informações do Azure](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial).

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

Secure/Multipurpose Internet Mail Extensions (S/MIME) é um padrão para criptografia de chave pública e assinatura digital de dados MIME. O S/MIME é definido nas RFCs 3369, 3370, 3850, 3851 e outros. Permite que o usuário criptografe um email e assine digitalmente um email. Um email criptografado usando S/MIME só pode ser descriptografado pelo destinatário do email usando sua chave privada, o que está disponível somente para esse destinatário. Como tal, os emails não podem ser descriptografados por qualquer pessoa além do destinatário do email.

A [Microsoft oferece suporte a S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). Os certificados públicos são distribuídos para o Active Directory local do cliente e armazenados em atributos que podem ser replicados para um locatário do Microsoft 365. As chaves privadas que correspondem às chaves públicas permanecem no local e nunca são transmitidas para o Office 365. Os usuários podem redigir, criptografar, descriptografar, ler e assinar digitalmente os emails entre dois usuários em uma organização usando o Outlook, o Outlook na Web e clientes do Exchange ActiveSync. Para obter mais informações, consulte [criptografia S/MIME agora no Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Criptografia de Mensagem do Office 365

A [criptografia de mensagens do Office 365](https://products.office.com/exchange/office-365-message-encryption) (ome) construída sobre a [proteção de informações do Azure](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) (AIP) permite que você envie emails criptografados e protegidos por direitos para qualquer pessoa. O OME atenua ameaças como ataques de toque e sem interrupções, e outras ameaças, como o acesso não garantido de dados por um usuário não autorizado que não tenha as permissões corretas. Fizemos investimentos que oferecem uma experiência de email mais simples, mais intuitiva e segura criada sobre a proteção de informações do Azure. Você pode proteger as mensagens enviadas do Microsoft 365 para qualquer pessoa dentro ou fora da sua organização. Essas mensagens podem ser exibidas em um conjunto variado de clientes de email usando qualquer identidade, incluindo o Azure Active Directory, a conta da Microsoft e o Google IDs. Para obter mais informações sobre como sua organização pode usar mensagens criptografadas, consulte [Office 365 Message Encryption](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A).

## <a name="transport-layer-security"></a>Protocolo TLS   

Se quiser garantir uma comunicação segura com um parceiro, você pode usar conectores de entrada e de saída para fornecer segurança e integridade da mensagem. Você pode configurar o TLS de entrada e saída forçado em cada conector, usando um certificado. O uso de um canal SMTP criptografado pode evitar que os dados sejam roubados por meio de um ataque man-in-the-Middle. Para obter mais informações, consulte [como o Exchange Online usa o TLS para proteger conexões de email](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F).

## <a name="domain-keys-identified-mail"></a>Chaves de domínio identificadas por email

O Exchange Online Protection (EOP) e o Exchange Online suportam validação de entrada de mensagens de Email Identificado por Chaves de Domínio (DKIM). DKIM é um método para validar que uma mensagem foi enviada do domínio que ela diz ter originado e que não foi falsificada por qualquer outra pessoa. Ele vincula uma mensagem de email à organização responsável por enviá-la e faz parte de um paradigma maior de criptografia de email. Para obter mais informações sobre as três partes desse paradigma, consulte:

- [Configurar o SPF para ajudar a evitar a falsificação](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Usar DKIM para validar emails de saída enviados do seu domínio personalizado](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Usar DMARC para validar emails](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
