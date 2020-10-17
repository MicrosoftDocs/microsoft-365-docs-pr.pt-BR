---
title: Cadeias de criptografia do Microsoft 365-DOD e GCC alta
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/16/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Veja uma lista completa de certificados raiz e CAs (autoridades de certificação) principais de DOD e GCC no Microsoft 365.
ms.openlocfilehash: a933acc14f0984e4935ff6e56ccccd3aed1f16cf
ms.sourcegitcommit: 705915f8bf9b7c082d12a009523d8aa0670a74a1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48493648"
---
# <a name="microsoft-365-encryption-chains---dod-and-gcc-high"></a>Cadeias de criptografia do Microsoft 365-DOD e GCC alta

A Microsoft 365 utiliza vários provedores de certificado diferentes. Veja a seguir a lista completa de certificados raiz conhecidos do Microsoft 365 que **os clientes de baixo e gcc** podem encontrar ao acessar o Microsoft 365. Para obter informações sobre os certificados que podem ser instalados em sua própria infraestrutura, consulte [Plan for de certificados SSL de terceiros para o Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/plan-for-third-party-ssl-certificates).

As seguintes informações de certificado aplicam-se a **todos os clientes DOD e gcc elevado**.

Última atualização: **10/16/2020**

>[!NOTE]
>Para obter informações de certificado que se aplicam a **clientes em todo o mundo**, consulte [Microsoft 365 Encryption encadeations](encryption-office-365-certificate-chains.md).

| **Tipo de certificado** | **Download de P7b** | **Pontos de extremidade da CRL** | **Pontos de extremidade OCSP** |
| --- | --- | --- | --- | --- |
| Certificados raiz e intermediário confiáveis publicamente | [Pacote de certificados do ITAR da Microsoft 365 (P7B)](https://download.microsoft.com/download/b/3/a/b3ae08a2-516c-46a9-8723-6256e4fd6383/m365_chain_certs_itar20201012.p7b) | crl.entrust.net<br>crl3.digicert.com<br>crl4.digicert.com | ocsp.digicert.com<br>ocsp.entrust.net |

Expanda as seções raiz e intermediária abaixo para ver detalhes adicionais sobre os provedores de certificado.

## <a name="microsoft-365-certificate-details"></a>**Detalhes do certificado Microsoft 365**

### <a name="baltimore-cybertrust-root"></a>**Baltimore CyberTrust Root**

| **Subject** | CN = Baltimore CyberTrust raiz<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| --- | --- |
| **Número de série** | 02:00:00: B9 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | Maio de 12 18:46:00 2000 UTC |
| **Validade não após** | Maio de 12 23:59:00 2025 UTC |
| **Identificador de chave de assunto** | E5:9d: 59-30:82:47: (em inglês): (em inglês). (! em inglês): 08:36. |
| **Impressão digital (SHA-1)** | D4DE20D05E66FC53FE1A50882C78DB2852CAE474 |
| **Impressão digital (SHA-256)** | 16AF57A9F676B0AB126095AA5EBADEF22AB31119D644AC95CD4B93DBF3F26AEB |
| **PIN (SHA-256)** | Y9mvm0exBk1JoQ57f9Vm28jKo5lFm/woKcVxrYxu80o = |

### <a name="digicert-cloud-services-ca-1"></a>**AC de serviços de nuvem do DigiCert-1**

| **Subject** | CN = autoridade de certificação dos serviços de nuvem DigiCert-1<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz global DigiCert<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| **Número de série** | 01:9E: C1: C6: O BD: 3F: 59:7B: B2:0C: 33:.. |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Ago 04 12:00:00 2015 UTC |
| **Validade não após** | Ago 04 12:00:00 2030 UTC |
| **Identificador de chave de assunto** | DD: 51: D0: a2: a2:31:73: A9: (em inglês): (em inglês): [!... 7e: 5D: 8F: 57: |
| **Identificador de chave de autoridade** | keyid: 03: de: 50:35:-D1:4C: BB: 66: (em inglês): a3: E2: (em inglês). 1b: 1b:. |
| **Impressão digital (SHA-1)** | 81B68D6CD2F221F8F534E677523BB236BBA1DC56 |
| **Impressão digital (SHA-256)** | 2F6889961A7CA7067E8BA103C2CF9B9A924F8CA293F11178E23A1978D2F133D3 |
| **PIN (SHA-256)** | UgpUVparimk8QCjtWQaUQ7EGrtrykc/L8N66EhFY3VE = |
| **URLs de CRL** | http://crl4.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl3.digicert.com/DigiCertGlobalRootCA.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="digicert-cloud-services-ca-1"></a>**AC de serviços de nuvem do DigiCert-1**

| **Subject** | CN = autoridade de certificação dos serviços de nuvem DigiCert-1<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz global DigiCert, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Número de série** | 0F: 17:1A: 48: C6: (EM INGLÊS) (EM INGLÊS): 18:92:92:, CD: 2E: |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Quinta-feira, 24 de setembro de 2020 5:00 PM |
| **Validade não até** | Terça-feira, 24 de setembro de 2030 4:59 PM |
| **Identificador de chave de assunto** | DD51D0A23173A973AE8FB4017E5D8C57CB9FF0F7 |
| **Identificador de chave de autoridade** | KeyID: 03: de: 50:35:-D1:4C: BB: 66: (em inglês): a3: E2: (em inglês). 1b: 1b:. |
| **Impressão digital (SHA-1)** | B3F6B64A07BB9611F47174407841F564FB991F29 |
| **Impressão digital (SHA-256)** | 5F88694615E4C61686E106B84C3338C6720C535F60D36F61282ED15E1977DD44 |
| **URLs de CRL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="digicert-global-root-ca"></a>**Autoridade de certificação raiz global do DigiCert**

| **Subject** | CN = autoridade de certificação raiz global DigiCert<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Número de série** | 08:3B: E0:56:90:42: (EM INGLÊS): B1: (A1: A). |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | UTC de novembro de 10 00:00:00 2006 |
| **Validade não após** | UTC de novembro de 10 00:00:00 2031 |
| **Identificador de chave de assunto** | 03: de: 50:35:56: (em inglês):%Name: 66:66: F0: a3:, (em inglês.) |
| **Identificador de chave de autoridade** | keyid: 03: de: 50:35:-D1:4C: BB: 66: (em inglês): a3: E2: (em inglês). 1b: 1b:. |
| **Impressão digital (SHA-1)** | A8985D3A65E5E5C4B2D7D66D40C6DD2FB19C5436 |
| **Impressão digital (SHA-256)** | 4348A0E9444C78CB265E058D5E8944B4D84F9662BD26DB257F8934A443C70161 |
| **PIN (SHA-256)** | r/mIkG3eEpVdm + u/ko/cwxzOMo1bk4TyHIlByibiA5E = |

### <a name="digicert-global-root-g2"></a>**DigiCert raiz G2 global**

| **Subject** | CN = DigiCert global raiz G2<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Emissor** | CN = DigiCert global root G2, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Número de série** | 03:3A: F1: E6: A7:11: A9: A0: BB: 28: A: B1:-1D: 09. |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Quinta-feira, 1 de agosto de 2013 5:00 AM |
| **Validade não até** | Sexta-feira, 15 de janeiro de 2038 4:00 AM |
| **Identificador de chave de assunto** | 4E2254201895E6E36EE60FFAFAB912ED06178F39 |
| **Identificador de chave de autoridade** | KeyID: 4e: 22:54: cerca de 20:18:95: E6: E3:6e: E6: a: (em inglês): o FA: FA: B9:. |
| **Impressão digital (SHA-1)** | DF3C24F9BFD666761B268073FE06D1CC8D4F82A4 |
| **Impressão digital (SHA-256)** | CB3CCBB76031E5E0138F8DD39A23F9DE47FFC35E43C1144CEA27D46A5AB1CB5F |

### <a name="digicert-high-assurance-ev-root-ca"></a>**AC raiz EV de alta garantia DigiCert**

| **Subject** | CN = DigiCert AC raiz EV de alta garantia<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Número de série** | 02: AC: 5C: 26:6A: 0B: 40:9B: 8F: 0B: 79: (EM INGLÊS). |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | UTC de novembro de 10 00:00:00 2006 |
| **Validade não após** | UTC de novembro de 10 00:00:00 2031 |
| **Identificador de chave de assunto** | B1:3E: C3:69:...: (em inglês): 47:01:0,01: o (a) a BF: 08:08:02: |
| **Identificador de chave de autoridade** | keyid: B1:3E: C3: (em inglês) (em inglês):-BF: 47:47-01:0,01:1a: 1Uma: 08:02:. |
| **Impressão digital (SHA-1)** | 5FB7EE0633E259DBAD0C4C9AE6D38F1A61C7DC25 |
| **Impressão digital (SHA-256)** | 7431E5F4C3C1CE4690774F0B61E05440883BA9A01ED00BA6ABD7806ED3B118CF |
| **PIN (SHA-256)** | WoiWRyIOVNa9ihaBciRSC7XHjliYS9VwUGOIud4PB18 = |

### <a name="digicert-sha2-extended-validation-server-ca"></a>**Autoridade de certificação do servidor de validação estendida do DigiCert SHA2**

| **Subject** | CN = DigiCert SHA2 servidor de validação estendida<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Número de série** | 0C: 79: A9:44: B0: O 8C: 11: O QUE É 20:92:61:5F: E2, 6B: 1D. |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Oct 22 00:00:00 2013 UTC |
| **Validade não após** | Oct 22 00:00:00 2028 UTC |
| **Identificador de chave de assunto** | 3D: D3:50: A5: (EM INGLÊS): (EM INGLÊS): (EM INGLÊS): [!: 0A: 65: (EM INGLÊS): |
| **Identificador de chave de autoridade** | keyID: B1:3E: C3: (em inglês) (em inglês):-BF: 47:47-01:0,01:1a: 1Uma: 08:02:. |
| **Impressão digital (SHA-1)** | 7E2F3A4F8FE8FA8A5730AECA029696637E986F3F |
| **Impressão digital (SHA-256)** | 403E062A2653059113285BAF80A0D4AE422C848C9F78FAD01FC94BC5B87FEF1A |

### <a name="digicert-sha2-secure-server-ca"></a>**Autoridade de certificação do servidor seguro do DigiCert SHA2**

| **Subject** | CN = DigiCert SHA2 servidor seguro AC<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz global DigiCert, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Número de série** | 01: FD: A3: EB: 6E: AUTORIDADE DE CERTIFICAÇÃO: 75: C8:88:43:8B: 72:4B: CF: |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Sexta-feira, 8 de março de 2013 4:00 AM |
| **Validade não até** | Quarta-feira, 8 de março de 2023 4:00 AM |
| **Identificador de chave de assunto** | 0F80611C823161D52F28E78D4638B42CE1C6D9E2 |
| **Identificador de chave de autoridade** | KeyID: 03: de: 50:35:-D1:4C: BB: 66: (em inglês): a3: E2: (em inglês). 1b: 1b:. |
| **Impressão digital (SHA-1)** | 1FB86B1168EC743154062E8C9CC5B171A4B7CCB4 |
| **Impressão digital (SHA-256)** | 154C433C491929C5EF686E838E323664A00E6A0D822CCC958FB4DAB03E49A08F |
| **URLs de CRL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="digicert-sha2-secure-server-ca"></a>**Autoridade de certificação do servidor seguro do DigiCert SHA2**

| **Subject** | CN = DigiCert SHA2 servidor seguro AC<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz global DigiCert, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Número de série** | 02:74:2E: O AA: 17: CA: 8E: 21: C7:17: (EM INGLÊS). |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Terça-feira, 22 de setembro de 2020 5:00 PM |
| **Validade não até** | Domingo, 22 de setembro de 2030 4:59 PM |
| **Identificador de chave de assunto** | 0F80611C823161D52F28E78D4638B42CE1C6D9E2 |
| **Identificador de chave de autoridade** | KeyID: 03: de: 50:35:-D1:4C: BB: 66: (em inglês): a3: E2: (em inglês). 1b: 1b:. |
| **Impressão digital (SHA-1)** | 626D44E704D1CEABE3BF0D53397464AC8080142C |
| **Impressão digital (SHA-256)** | C1AD7778796D20BCA65C889A2655021156528BB62FF5FA43E1B8E5A83E3D2EAA |
| **URLs de CRL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="digicert-tls-rsa-sha256-2020-ca1"></a>**DigiCert TLS RSA SHA256 2020 CA1**

| **Subject** | CN = DigiCert TLS RSA SHA256 2020 CA1<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz global DigiCert, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Número de série** | 0A: 35:08: D5:5C: (29:2: 2B: 7D:...:: 0F: |
| **Comprimento da chave pública** | Bits RSA 2048 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Quarta-feira, 23 de setembro de 2020 5:00 PM |
| **Validade não até** | Segunda-feira, 23 de setembro de 2030 4:59 PM |
| **Identificador de chave de assunto** | B76BA2EAA8AA848C79EAB4DA0F98B2C59576B9F4 |
| **Identificador de chave de autoridade** | KeyID: 03: de: 50:35:-D1:4C: BB: 66: (em inglês): a3: E2: (em inglês). 1b: 1b:. |
| **Impressão digital (SHA-1)** | 6938FD4D98BAB03FAADB97B34396831E3780AEA1 |
| **Impressão digital (SHA-256)** | 25768713D3B459F9382D2A594F85F34709FD2A8930731542A4146FFB246BEC69 |
| **URLs de CRL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="entrust-root-certification-authority"></a>**Autoridade de certificação raiz confiável**

| **Subject** | CN = autoridade de certificação raiz confiável<br>OU = "(c) 2006 Entrust, Inc."<br>OU = www. Entrust. net/CPS é incorporado por referência<br>OU = ver www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Número de série** | 45:6B: 50:54 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | UTC de novembro de 27 12:23:42 2006 |
| **Validade não após** | UTC de novembro de 27 12:53:42 2026 |
| **Identificador de chave de assunto** | 68:90: E4:67: (EM INGLÊS): (EM INGLÊS).-53: (EM INGLÊS): 86:--43: |
| **Identificador de chave de autoridade** | keyID: 68:90: E4:67: (...............:-4B: 43: (em inglês). |
| **Impressão digital (SHA-1)** | B31EB1B740E36C8402DADC37D44DF5D4674952F9 |
| **Impressão digital (SHA-256)** | 73C176434F1BC6D5ADF45B0E76E727287C8DE57616C1E6E6141A2B2CBC7D8E4C |

### <a name="entrust-root-certification-authority---g2"></a>**Autoridade de certificação raiz confiável-G2**

| **Subject** | CN = autoridade de certificação raiz Entrust-G2<br>OU = &quot; (c) 2009 Entrust, Inc.-for apenas para uso autorizado&quot;<br>OU = ver www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Número de série** | 4A: 53:8C: 28 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Jul 07 17:25:54 2009 UTC |
| **Validade não após** | Dec 07 17:55:54 2030 UTC |
| **Identificador de chave de assunto** | 6A: 72:26:7A: D0:1e: 3B: 7D: E7:3B: 69:. º da 6C: (em inglês). 8d: |
| **Impressão digital (SHA-1)** | 8CF427FD790C3AD166068DE81E57EFBB932272D4 |
| **Impressão digital (SHA-256)** | 43DF5774B03E7FEF5FE40D931A7BEDF1BB2E6B42738C4E6D3841103D3AA7F339 |
| **PIN (SHA-256)** | du6FkDdMcVQ3u8prumAo6t3i3G27uMP2EOhR8R0at/U = |

### <a name="entrustnet-certification-authority-2048"></a>**Entrust.net Certification Authority (2048)**

| **Subject** | CN = autoridade de certificação Entrust. net (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. net/CPS \_ 2048 incorp. por Ref. (limite s liab.)<br>O = Entrust. net |
| --- | --- |
| **Número de série** | 38:63: DE: F8 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | Dec 24 17:50:51 1999 UTC |
| **Validade não após** | Jul 24 14:15:12 2029 UTC |
| **Identificador de chave de assunto** | 55: E4:81: (11: D1): (em inglês): são: D8:89:: 08: o.... |
| **Impressão digital (SHA-1)** | 503006091D97D4F5AE39F7CBE7927D7D652D3431 |
| **Impressão digital (SHA-256)** | 6DC47172E01CBCB0BF62580D895FE2B8AC9AD4F873801E0C10B9C837D21EB177 |
| **PIN (SHA-256)** | HqPF5D7WbC2imDpCpKebHpBnhs6fG1hiFBmgBGOofTg = |

### <a name="entrust-certification-authority---l1c"></a>**Autoridade de certificação Entrust-L1C**

| **Subject** | CN = autoridade de certificação Entrust-L1C<br>OU = &quot; (c) 2009 Entrust, Inc.&quot;<br>OU = www. Entrust. net/RPA é incorporado por referência<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação Entrust. net (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. net/CPS \_ 2048 incorp. por Ref. (limita liab.)<br>O = Entrust. net |
| **Número de série** | 4C: 0E: 8C: 39 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | UTC de novembro de 11 15:40:40 2011 |
| **Validade não após** | UTC de novembro de 11 02:51:17 2021 |
| **Identificador de chave de assunto** | 1e: F1: AB: 89: a 06: F8:49: (em inglês): 28:140:140:14:7A:. ee: |
| **Identificador de chave de autoridade** | keyid: 55: E4:81:.. 11:11: a:: D8:89:89: o B9:08: o... º. |
| **Impressão digital (SHA-1)** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **Impressão digital (SHA-256)** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **PIN (SHA-256)** | VFv5NemtodoRftw8KsvFb8AoCWwOJL6bOJS + Ui0bQ94 = |
| **URLs de CRL** | http://crl.entrust.net/2048ca.crl |
| **URLs de OCSP** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1e"></a>**Autoridade de certificação Entrust-L1E**

| **Subject** | CN = autoridade de certificação Entrust-L1E<br>OU = &quot; (c) 2009 Entrust, Inc.&quot;<br>OU = www. Entrust. net/RPA é incorporado por referência<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação Entrust. net (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. net/CPS \_ 2048 incorp. por Ref. (limita liab.)<br>O = Entrust. net |
| **Número de série** | 4C: 0E: C9:18 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | UTC de novembro de 11 15:40:40 2011 |
| **Validade não após** | UTC de novembro de 11 02:51:17 2021 |
| **Identificador de chave de assunto** | 5B: 41:8A: B2: C4:43: C1: BD: BF: C8: (EM INGLÊS): 54:41:55:9D: |
| **Identificador de chave de autoridade** | keyid: 68:90: E4:67: (...............:-4B: 43: (em inglês). |
| **Impressão digital (SHA-1)** | 8A000CC056F7D17349F045BEB0319A3B91C9F979 |
| **Impressão digital (SHA-256)** | 3C7A634E5778A0F731972B702DAE24B2CF2060219F607E69878B164C61A06C41 |
| **URLs de CRL** | http://crl.entrust.net/rootca1.crl |
| **URLs de OCSP** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1k"></a>**Autoridade de certificação Entrust-L1K**

| **Subject** | CN = autoridade de certificação Entrust-L1K<br>OU = &quot; (c) 2012 Entrust, Inc.-for apenas para uso autorizado&quot;<br>OU = ver www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz Entrust-G2<br>OU = &quot; (c) 2009 Entrust, Inc.-for apenas para uso autorizado&quot;<br>OU = ver www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| **Número de série** | 0E: E9:4C: C3: A 00:00:00:00:51: |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Oct 05 19:13:56 2015 UTC |
| **Validade não após** | Dec 05 19:43:56 2030 UTC |
| **Identificador de chave de assunto** | 82: a2:70:74: (!...................... |
| **Identificador de chave de autoridade** | keyid: 6A: 72:26:7A: D0:1e: o EF: 7D:: 3B: 69:. º: (em inglês). 8d: |
| **Impressão digital (SHA-1)** | F21C12F46CDB6B2E16F09F9419CDFF328437B2D7 |
| **Impressão digital (SHA-256)** | 13EFB39A2F6654E8C67BD04F4C6D4C90CD6CAB5091BCEDC73787F6B77D3D3FE7 |
| **PIN (SHA-256)** | 980Ionqp3wkYtN9SZVgMzuWQzJta1nfxNPwTem1X0uc = |
| **URLs de CRL** | http://crl.entrust.net/g2ca.crl |
| **URLs de OCSP** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1m"></a>**Autoridade de certificação Entrust-L1M**

| **Subject** | CN = Entrust Certification Authority-L1M, OU = &quot; (c) 2014 Entrust, Inc.-para uso autorizado apenas&quot;<br>OU = ver www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz Entrust-G2<br>OU = &quot; (c) 2009 Entrust, Inc.-for apenas para uso autorizado&quot;<br>OU = ver www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| **Número de série** | 61: A1: E7: D2:00:00:00:00:51:, D3:66 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Dec 15 07:25:03 2014 UTC |
| **Validade não após** | Oct 15 08:55:03 2030 UTC |
| **Identificador de chave de assunto** | C3: (EM INGLÊS): D0: B5:2A: (EM INGLÊS): (EM INGLÊS): 91:91: º: 39: (EM INGLÊS): |
| **Identificador de chave de autoridade** | keyid: 6A: 72:26:7A: D0:1e: o EF: 7D:: 3B: 69:. º: (em inglês). 8d: |
| **Impressão digital (SHA-1)** | CC136695639065FAB47074D28C55314C66077E90 |
| **Impressão digital (SHA-256)** | 75C5B3F01FD1F51A2C447AB7C785D72E69FA9C472C08571E7EADF3B8EABAE70C |
| **URLs de CRL** | http://crl.entrust.net/g2ca.crl |
| **URLs de OCSP** | http://ocsp.entrust.net |

### <a name="microsoft-azure-tls-issuing-ca-01"></a>**CA de emissão do Microsoft Azure TLS 01**

| **Subject** | CN = CA de emissão do Microsoft Azure TLS 01<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Emissor** | CN = DigiCert global root G2, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Número de série** | 0A: AF: A6: C5: A AC: 63: O (A): 41: (!: 3B:). |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha384RSA |
| **Validade não antes** | Quarta-feira, 29 de julho de 2020 5:30 AM |
| **Validade não até** | Quinta-feira, 27 de junho de 2024 4:59 PM |
| **Identificador de chave de assunto** | 0F205DD7A15795DB92CF2BD0C7C27704CE728076 |
| **Identificador de chave de autoridade** | KeyID: 4e: 22:54: cerca de 20:18:95: E6: E3:6e: E6: a: (em inglês): o FA: FA: B9:. |
| **Impressão digital (SHA-1)** | 2F2877C5D778C31E0F29C7E371DF5471BD673173 |
| **Impressão digital (SHA-256)** | 24C7299864E0A2A6964F551C0E8DF2461532FA8C48E4DBBB6080716691F190E5 |
| **URLs de CRL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-02"></a>**CA de emissão do Microsoft Azure TLS 02**

| **Subject** | CN = CA de emissão do Microsoft Azure TLS 02<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Emissor** | CN = DigiCert global root G2, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Número de série** | 0C: 6A: E9:7C: (EM INGLÊS): CE: (EM INGLÊS).: 83:: |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha384RSA |
| **Validade não antes** | Quarta-feira, 29 de julho de 2020 5:30 AM |
| **Validade não até** | Quinta-feira, 27 de junho de 2024 4:59 PM |
| **Identificador de chave de assunto** | 00AB91FC216226979AA8791B61419060A96267FD |
| **Identificador de chave de autoridade** | KeyID: 4e: 22:54: cerca de 20:18:95: E6: E3:6e: E6: a: (em inglês): o FA: FA: B9:. |
| **Impressão digital (SHA-1)** | E7EEA674CA718E3BEFD90858E09F8372AD0AE2AA |
| **Impressão digital (SHA-256)** | 15A98761EBE011554DA3A46D206B0812CB2EB69AE87AAA11A6DD4CB84ED5142A |
| **URLs de CRL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-05"></a>**CA de emissão do Microsoft Azure TLS 05**

| **Subject** | CN = CA de emissão do Microsoft Azure TLS<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Emissor** | CN = DigiCert global root G2, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Número de série** | 0D: 7B: ED: E9:7D: 82:09:7A: 52:. º DA. º DE. |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha384RSA |
| **Validade não antes** | Quarta-feira, 29 de julho de 2020 5:30 AM |
| **Validade não até** | Quinta-feira, 27 de junho de 2024 4:59 PM |
| **Identificador de chave de assunto** | C7B29C7F1CE3B85AEFE9681AA85D94C126526A68 |
| **Identificador de chave de autoridade** | KeyID: 4e: 22:54: cerca de 20:18:95: E6: E3:6e: E6: a: (em inglês): o FA: FA: B9:. |
| **Impressão digital (SHA-1)** | 6C3AF02E7F269AA73AFD0EFF2A88A4A1F04ED1E5 |
| **Impressão digital (SHA-256)** | D6831BA43607F5AC19778D627531562AF55145F191CAB5EFAFA0E0005442B302 |
| **URLs de CRL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-06"></a>**CA de emissão do Microsoft Azure TLS 06**

| **Subject** | CN = CA de emissão do Microsoft Azure TLS 6<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Emissor** | CN = DigiCert global root G2, OU = www. DigiCert. com, O = DigiCert Inc, C = US |
| **Número de série** | 02: E7:91:71: SÃO: FB: 80: E9:3F: E2:-: E2:83:83: |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha384RSA |
| **Validade não antes** | Quarta-feira, 29 de julho de 2020 5:30 AM |
| **Validade não até** | Quinta-feira, 27 de junho de 2024 4:59 PM |
| **Identificador de chave de assunto** | D5C1673AC2A39DF477525B59123829E65568BBA5 |
| **Identificador de chave de autoridade** | KeyID: 4e: 22:54: cerca de 20:18:95: E6: E3:6e: E6: a: (em inglês): o FA: FA: B9:. |
| **Impressão digital (SHA-1)** | 30E01761AB97E59A06B41EF20AF6F2DE7EF4F7B0 |
| **Impressão digital (SHA-256)** | 48FF8B494668C752304B48BFE818758987DEF6582E5F09B921F4B60BB3D6A8DD |
| **URLs de CRL** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-1"></a>**AC 1 TLS da TI da Microsoft**

| **Subject** | CN = autoridade de certificação TLS da TI da Microsoft<br>OU = ti da Microsoft<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Emissor** | CN = Baltimore CyberTrust raiz<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **Número de série** | 08: B8:7A: 50:1B: DA: (EM INGLÊS): (EM INGLÊS):-0,50: |
| **Comprimento da chave pública** | RSA 4096 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Maio de 20 12:51:28 2016 UTC |
| **Validade não após** | Maio de 20 12:51:28 2024 UTC |
| **Identificador de chave de assunto** | 58:88:9F: (em inglês): (em inglês): (em inglês) (em inglês):-E8:22: (em inglês).: |
| **Identificador de chave de autoridade** | keyid: E5:9d: 59-30:/!: (em inglês): (em inglês): 4: (em inglês): 08:36: |
| **Impressão digital (SHA-1)** | 417E225037FBFAA4F95761D5AE729E1AEA7E3A42 |
| **Impressão digital (SHA-256)** | 4FF404F02E2CD00188F15D1C00F4B6D1E38B5A395CF85314EAEBA855B6A64B75 |
| **PIN (SHA-256)** | xjXxgkOYlag7jCtR5DreZm9b61iaIhd + J3 + b2LiybIw = |
| **URLs de CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-2"></a>**AC 2 do Microsoft IT TLS**

| **Subject** | CN = autoridade de certificação TLS de ti da Microsoft<br>OU = ti da Microsoft<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Emissor** | CN = Baltimore CyberTrust raiz<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **Número de série** | 0F: 2C: 10: C9:5B: 06: C0:93: O B8: D4: (... |
| **Comprimento da chave pública** | RSA 4096 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Maio de 20 12:51:57 2016 UTC |
| **Validade não após** | Maio de 20 12:51:57 2024 UTC |
| **Identificador de chave de assunto** | 91:9e: 3B: 44:, 6C: (em inglês): (em inglês): (em inglês).: (em inglês). |
| **Identificador de chave de autoridade** | keyid: E5:9d: 59-30:/!: (em inglês): (em inglês): 4: (em inglês): 08:36: |
| **Impressão digital (SHA-1)** | 54D9D20239080C32316ED9FF980A48988F4ADF2D |
| **Impressão digital (SHA-256)** | 4E107C981B42ACBE41C01067E16D44DB64814D4193E572317EA04B87C79C475F |
| **PIN (SHA-256)** | wBdPad95AU7OgLRs0FU/E6ILO1MSCM84kJ9y0H + TT7s = |
| **URLs de CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-4"></a>**AC 4 TLS da TI da Microsoft**

| **Subject** | CN = AC do Microsoft IT TLS 4<br>OU = ti da Microsoft<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Emissor** | CN = Baltimore CyberTrust raiz<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **Número de série** | 0B. 6A: B3: B0: (EM INGLÊS): (EM INGLÊS): B1: (EM INGLÊS): |
| **Comprimento da chave pública** | RSA 4096 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Maio de 20 12:52:38 2016 UTC |
| **Validade não após** | Maio de 20 12:52:38 2024 UTC |
| **Identificador de chave de assunto** | 7a: 7B: 8C: C1: FC: E7: a0: autoridade de certificação: 1C: (! de..........: C3: |
| **Identificador de chave de autoridade** | keyid: E5:9d: 59-30:/!: (em inglês): (em inglês): 4: (em inglês): 08:36: |
| **Impressão digital (SHA-1)** | 8A38755D0996823FE8FA3116A277CE446EAC4E99 |
| **Impressão digital (SHA-256)** | 5FFAC43E0DDC5B4AF2B696F6BC4DB7E91DF314BB8FE0D0713A0B1A7AD2A68FAC |
| **PIN (SHA-256)** | wUY9EOTJmS7Aj4fDVCu/KeE + + mV7FgIcbn4WhMz1I2k = |
| **URLs de CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-5"></a>**AC do Microsoft IT TLS 5**

| **Subject** | CN = AC do Microsoft IT TLS 5<br>OU = ti da Microsoft<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Emissor** | CN = Baltimore CyberTrust raiz<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **Número de série** | 08:88: CD: 52:5F:-16:44: (EM INGLÊS), 14: A5:82: |
| **Comprimento da chave pública** | RSA 4096 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Maio de 20 12:53:03 2016 UTC |
| **Validade não após** | Maio de 20 12:53:03 2024 UTC |
| **Identificador de chave de assunto** | 08: Fe: 25:9F: 74: (em inglês) (em inglês): a:% 8E: A8: (em inglês).: |
| **Identificador de chave de autoridade** | keyid: E5:9d: 59-30:/!: (em inglês): (em inglês): 4: (em inglês): 08:36: |
| **Impressão digital (SHA-1)** | AD898AC73DF333EB60AC1F5FC6C4B2219DDB79B7 |
| **Impressão digital (SHA-256)** | F0EE5914ED94C7252D058B4E39808AEE6FA8F62CF0974FB7D6D2A9DF16E3A87F |
| **PIN (SHA-256)** | RCbqB + W8nwjznTeP4O6VjqcwdxIgI79eBpnBKRr32gc = |
| **URLs de CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-rsa-tls-ca-01"></a>**AC do Microsoft RSA TLS 01**

| **Subject** | CN = AC do Microsoft RSA TLS 01<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Emissor** | CN = Baltimore CyberTrust root, OU = CyberTrust, O = Baltimore, C = IE |
| **Número de série** | 0F: 14:96:5F: 20: A 20:69:99:4F: D5: (EM INGLÊS). |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Terça-feira, 21 de julho de 2020 4:00 PM |
| **Validade não até** | Terça-feira, 8 de outubro de 2024 12:00 AM |
| **Identificador de chave de assunto** | B5760C3011CEC792424D4CC75C2CC8A90CE80B64 |
| **Identificador de chave de autoridade** | KeyID: E5:9d: 59-30:/!: (em inglês): (em inglês): 4: (em inglês): 08:36: |
| **Impressão digital (SHA-1)** | 703D7A8F0EBF55AAA59F98EAF4A206004EB2516A |
| **Impressão digital (SHA-256)** | 04EEEA8E50B4775B3C24797262917EE50002EC4C75B56CDF3EE1C18CFCA5BA52 |
| **URLs de CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="microsoft-rsa-tls-ca-02"></a>**AC do Microsoft RSA TLS 02**

| **Subject** | CN = Microsoft RSA TLS AC 02<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Emissor** | CN = Baltimore CyberTrust root, OU = CyberTrust, O = Baltimore, C = IE |
| **Número de série** | 0F: A7:47:22: (EM INGLÊS): C5: C8:0F: 58:9E: FB: |
| **Comprimento da chave pública** | Bits RSA 4096 |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Terça-feira, 21 de julho de 2020 4:00 PM |
| **Validade não até** | Terça-feira, 8 de outubro de 2024 12:00 AM |
| **Identificador de chave de assunto** | FF2F7FE106F438F32DED258D98C2FE0EF66CFCFA |
| **Identificador de chave de autoridade** | KeyID: E5:9d: 59-30:/!: (em inglês): (em inglês): 4: (em inglês): 08:36: |
| **Impressão digital (SHA-1)** | B0C2D2D13CDD56CDAA6AB6E2C04440BE4A429C75 |
| **Impressão digital (SHA-256)** | 05E4005DB0C382F3BD66B47729E9011577601BF6F7B287E9A52CED710D258346 |
| **URLs de CRL** | http://crl3.digicert.com/Omniroot2025.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |
