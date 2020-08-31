---
title: Cadeias de criptografia
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/3/2020
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
description: Exibir uma lista completa de certificados raiz e CAs (autoridades de certificação) no Office 365.
ms.openlocfilehash: c0f63f6e4ebc288f8b06d608af81a485e5f71e8a
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307440"
---
# <a name="encryption-chains"></a>Cadeias de criptografia

O Office 365 aproveita vários provedores de certificado diferentes. A seguir, a descrição da lista completa de certificados raiz conhecidos do Office 365 que os clientes podem encontrar ao acessar o Office 365. Para obter informações sobre os certificados que você pode precisar instalar em sua própria infraestrutura, consulte [Plan for de certificados SSL de terceiros para o Office 365](https://docs.microsoft.com/microsoft-365/enterprise/plan-for-third-party-ssl-certificates). As informações de certificado a seguir aplicam-se a todas as instâncias de nuvem do Office 365 em todo o mundo.

>[!NOTE]
>Para obter informações de certificado que se aplicam aos clientes **DOD e gcc altos** , consulte [Office 365 Encryption encadeations-DOD e gcc High](encryption-office-365-certificate-chains-itar.md).

| **Tipo de certificado** | **Download de P7b** | **Pontos de extremidade da CRL** | **Pontos de extremidade OCSP** | **Pontos de extremidade AIA** |
| --- | --- | --- | --- | --- |
| Certificados raiz confiáveis publicamente | [Pacote de certificados raiz do Office 365 (P7B)](https://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) | crl.globalsign.net<br>www.d-trust.net | N/D | N/D |
| Certificados intermediários confiáveis publicamente | [Pacote de certificados intermediário (P7B) do Office 365](https://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b) | cdp1.public-trust.com<br>crl.cnnic.cn<br>crl.entrust.net<br>crl.globalsign.com<br>crl.globalsign.net<br>crl.identrust.com<br>crl.thawte.com<br>crl3.digicert.com<br>crl4.digicert.com<br>s1.symcb.com<br>www.d-trust.net | isrg.trustid.ocsp.identrust.com<br>ocsp.digicert.com<br>ocsp.entrust.net<br>ocsp.globalsign.com<br>ocsp.omniroot.com<br>ocsp.startssl.com<br>ocsp.thawte.com<br>ocsp2.globalsign.com<br>ocspcnnicroot.cnnic.cn<br>root-c3-ca2-2009.ocsp.d-trust.net<br>root-c3-ca2-ev-2009.ocsp.d-trust.net<br>s2.symcb.com | aia.startssl.com<br>apps.identrust.com<br>cacert.omniroot.com<br>www.cnnic.cn |

Expanda as seções raiz e intermediária abaixo para ver detalhes adicionais sobre os provedores de certificado.

## <a name="office-365-root-certificate-details"></a>**Detalhes do certificado raiz do Office 365**

### <a name="baltimore-cybertrust-root"></a>**Baltimore CyberTrust Root**

| **Assunto** | CN = Baltimore CyberTrust raiz<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
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

### <a name="cnnic-root"></a>**RAIZ CNNIC**

| **Assunto** | CN = CNNIC RAIZ<br>O = CNNIC<br>C = CN |
| --- | --- |
| **Número de série** | 49:33:00:01 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | Abr 16 07:09:14 2007 UTC |
| **Validade não após** | Abr 16 07:09:14 2027 UTC |
| **Identificador de chave de assunto** | 65: F2:31: AD: 2A: (em inglês): 0A: 52:52:, 96:.:-02:... |
| **Identificador de chave de autoridade** | keyid: 65: F2: (em inglês)-1: AD: 2A: 1 a: (!: 0A: C7:02: (em inglês): |
| **Impressão digital (SHA-1)** | 8BAF4C9B1DF02A92F7DA128EB91BACF498604B6F |
| **Impressão digital (SHA-256)** | E28393773DA845A679F2080CC7FB44A3B7A1C3792CB7EB7729FDCB6A8D99AEA7 |
| **PIN (SHA-256)** | H0IkzshPyZztiB/2/P0 + IfjFGcVHqmpd094kcwLOUNE = |

### <a name="digicert-global-root-ca"></a>**Autoridade de certificação raiz global do DigiCert**

| **Assunto** | CN = autoridade de certificação raiz global DigiCert<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
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

### <a name="digicert-high-assurance-ev-root-ca"></a>**AC raiz EV de alta garantia DigiCert**

| **Assunto** | CN = DigiCert AC raiz EV de alta garantia<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
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

### <a name="d-trust-root-class-3-ca-2-2009"></a>**D-TRUST root classe 3 CA 2 2009**

| **Assunto** | CN = D-confiança da classe raiz 3 2 2009<br>O = D-Trust GmbH<br>C = DE |
| --- | --- |
| **Número de série** | 09:83: F3 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | UTC de novembro de 05 08:35:58 2009 |
| **Validade não após** | UTC de novembro de 05 08:35:58 2029 |
| **Identificador de chave de assunto** | FD: da: 14: C4:9F: (em inglês) (em inglês): 1e: 42: (em inglês) (em inglês). |
| **Impressão digital (SHA-1)** | 58E8ABB0361533FB80F79B1B6D29D3FF8D5F00F0 |
| **Impressão digital (SHA-256)** | 49E7A442ACF0EA6287050054B52564B650E4F49E42E348D6AA38E039E957B1C1 |
| **PIN (SHA-256)** | 7KDxgUAs56hlKzG00DbfJH46MLf0GlDZHsT5CwBrQ6E = |
| **URLs de CRL** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_2009.crl |

### <a name="d-trust-root-class-3-ca-2-ev-2009"></a>**D-confiança de classe raiz 3 AC 2 EV 2009**

| **Assunto** | CN = D-confiança classe raiz 3 AC 2 EV 2009<br>O = D-Trust GmbH<br>C = DE |
| --- | --- |
| **Número de série** | 09:83: F4 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | UTC de novembro de 05 08:50:46 2009 |
| **Validade não após** | UTC de novembro de 05 08:50:46 2029 |
| **Identificador de chave de assunto** | D3:94:8A: 4C: 62: (em inglês): a 2a: (em inglês): (em inglês): 7D:, 8a: 7D: 36: D7: |
| **Impressão digital (SHA-1)** | 96C91B0B95B4109842FAD0D82279FE60FAB91683 |
| **Impressão digital (SHA-256)** | EEC5496B988CE98625B934092EEC2908BED0B0F316C2D4730C84EAF1F3D34881 |
| **PIN (SHA-256)** | /zQvtsTIvTCkcG9zSJU58Z5uSMwF9GJUZU9mENvFQOk = |
| **URLs de CRL** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%20EV%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_ev\_2009.crl |

### <a name="dst-root-ca-x3"></a>**AC root de horário de verão**

| **Assunto** | CN = AC raiz de DST X3<br>O = confiança de assinatura digital co. |
| --- | --- |
| **Número de série** | 44.: B0: (EM INGLÊS): (EM INGLÊS): D6: A3:6B: (EM INGLÊS). |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | UTC de setembro de 30 21:12:19 2000 |
| **Validade não após** | UTC de setembro de 30 14:01:15 2021 |
| **Identificador de chave de assunto** | C4: A7: B1: A4: (em inglês): (em inglês).: (em inglês): 4B: 90:: (em inglês) |
| **Impressão digital (SHA-1)** | DAC9024F54D8F6DF94935FB1732638CA6AD77C13 |
| **Impressão digital (SHA-256)** | 0687260331A72403D909F105E69BCF0D32E1BD2493FFC6D9206D11BCD6770739 |
| **PIN (SHA-256)** | Vjs8r4z + 80wjNcr1YKepWQboSIRi63WsWXhIMN + eWys = |

### <a name="entrust-root-certification-authority---g2"></a>**Autoridade de certificação raiz confiável-G2**

| **Assunto** | CN = autoridade de certificação raiz Entrust-G2<br>OU = &quot; (c) 2009 Entrust, Inc.-for apenas para uso autorizado&quot;<br>OU = ver www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
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

| **Assunto** | CN = autoridade de certificação Entrust. net (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. net/CPS \_ 2048 incorp. por Ref. (limite s liab.)<br>O = Entrust. net |
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

### <a name="globalsign"></a>**GlobalSign**

| **Assunto** | CN = GlobalSign<br>O = GlobalSign<br>OU = GlobalSign raiz CA-R2 |
| --- | --- |
| **Número de série** | 04:00:00:00.00:86: (... |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | Dec 15 08:00:00 2006 UTC |
| **Validade não após** | Dec 15 08:00:00 2021 UTC |
| **Identificador de chave de assunto** | 9B: E2:07:57:67: (em inglês):: 6A: C0:6A: 06:. de: 59: o 9a: 2D: |
| **Identificador de chave de autoridade** | keyid: 9b: E2:07: são: a (em inglês),: 1e: 1e: 1e: C0:6A: (! de: 59): |
| **Impressão digital (SHA-1)** | 75E0ABB6138512271C04F85FDDDE38E4B7242EFE |
| **Impressão digital (SHA-256)** | CA42DD41745FD0B81EB902362CF9D8BF719DA1BD1B1EFC946F5B4C99F42C1B9E |
| **PIN (SHA-256)** | iie1VXtL7HzAMF +/PVPR9xzT80kQxdZeJ + zduCB3uj0 = |
| **URLs de CRL** | http://crl.globalsign.net/root-r2.crl |

### <a name="globalsign-root-ca"></a>**GlobalSign Root CA**

| **Assunto** | CN = autoridade de certificação raiz GlobalSign<br>OU = autoridade de certificação raiz<br>O = GlobalSign NV-SA<br>C = BE |
| --- | --- |
| **Número de série** | 04:00:00:00: A (EM INGLÊS): 4B: 5A: C3 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | UTC de setembro de 01 12:00:00 1998 |
| **Validade não após** | Jan 28 12:00:00 2028 UTC |
| **Identificador de chave de assunto** | 60:7B: 66:1a: 1a:............: 89:89:4B: 2F-7D:. |
| **Impressão digital (SHA-1)** | B1BC968BD4F49D622AA89A81F2150152A41D829C |
| **Impressão digital (SHA-256)** | EBD41040E4BB3EC742C9E381D31EF2A41A48B6685C96E7CEF3C1DF6CD4331C99 |
| **PIN (SHA-256)** | K87oWBWM9UZfyddvDfoxL + 8lpNyoUB2ptGtn0fv6G2Q = |

### <a name="thawte-primary-root-ca---g3"></a>**AC raiz principal da Thawte-G3**

| **Assunto** | CN = AC raiz primária da Thawte-G3<br>OU = &quot; (c) 2008 Thawte, Inc.-for Authorized use only&quot;<br>OU = divisão de serviços de certificação<br>O = &quot; Thawte, Inc.&quot;<br>C = US |
| --- | --- |
| **Número de série** | 60:01:97:-B7:46: A7:9A: O (A) (EM INGLÊS): [!: 2F: |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Abr 02 00:00:00 2008 UTC |
| **Validade não após** | Dec 01 23:59:59 2037 UTC |
| **Identificador de chave de assunto** | AD: 6C: AA: 94: (em inglês) (em inglês): a E4: FF: FA: (em inglês): (em inglês). |
| **Impressão digital (SHA-1)** | F18B538D1BE903B6A6F056435B171589CAF36BF2 |
| **Impressão digital (SHA-256)** | 4B03F45807AD70F21BFC2CAE71C9FDE4604C064CF5FFB686BAE5DBAAD7FDD34C |
| **PIN (SHA-256)** | GQbGEk27Q4V40A4GbVBUxsN/D6YCjAVUXgmU7drshik = |

### <a name="verisign-class-3-public-primary-certification-authority---g5"></a>**Autoridade de certificação principal pública da classe VeriSign 3-G5**

| **Assunto** | CN = autoridade de certificação primária pública de classe 3 da VeriSign-G5<br>OU = &quot; (c) 2006 Verisign, Inc.-for Authorized use only&quot;<br>OU = rede de confiança VeriSign<br>O = &quot; Verisign, Inc.&quot;<br>C = US |
| --- | --- |
| **Número de série** | 18: DA: D1:9E: 26:7D: E8: BB: 4A: 21: (EM INGLÊS:. |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | UTC de novembro de 08 00:00:00 2006 |
| **Validade não após** | Jul 16 23:59:59 2036 UTC |
| **Identificador de chave de assunto** | 7F: D3:65: A7: o (a) (a) (em inglês)-% b: %2:09:,... |
| **Impressão digital (SHA-1)** | 4EB6D578499B1CCF5F581EAD56BE3D9B6744A5E5 |
| **Impressão digital (SHA-256)** | 9ACFAB7E43C8D880D06B262A94DEEEE4B4659989C3D0CAF19BAF6405E41AB7DF |
| **PIN (SHA-256)** | JbQbUG5JMJUoI6brnx0x3vZF6jilxsapbXGVfjhN8Fg = |

## <a name="office-365-intermediate-certificate-details"></a>**Detalhes do certificado intermediário do Office 365**

### <a name="cnnic-sha256-ssl"></a>**SSL CNNIC SHA256**

| **Assunto** | CN = SSL CNNIC SHA256 <br>O = CNNIC SHA256 (SSL) <br>C = CN |
| --- | --- |
| **Emissor** | CN = CNNIC RAIZ <br>O = CNNIC <br>C = CN |
| **Número de série** | 49:33:00:7C |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Dec 18 12:32:18 2014 UTC |
| **Validade não após** | Dec 18 12:32:18 2024 UTC |
| **Identificador de chave de assunto** | B7: D1:59: (em inglês): 8C: (em inglês): (são: 06:28:47:23:... |
| **Identificador de chave de autoridade** | keyid: 65: F2: (em inglês)-1: AD: 2A: 1 a: (!: 0A: C7:02: (em inglês): |
| **Impressão digital (SHA-1)** | FC844648FC708433921BE88B18C48787A3E2813E |
| **Impressão digital (SHA-256)** | FA8B9F99DBB94E7B772AA9190846E777047C15C7A3BF4A1AF9C0CA984A689511 |
| **PIN (SHA-256)** | dKZRcLDh7hBNZTmTIHOGJ6C2Om/ITjUCPkOnLTnrZXk = |
| **URLs AIA** | http://www.cnnic.cn/download/cert/CNNICROOT.cer |
| **URLs de CRL** | ldap:///CN=crl1,%20OU=crl,%20O=CNNIC,%20C=CN?certificateRevocationList;binary,authorityRevocationList;binary,deltaRevocationList;binary<br>http://crl.cnnic.cn/download/rootsha2crl/CRL1.crl |
| **URLs de OCSP** | <http://ocspcnnicroot.cnnic.cn> |

### <a name="d-trust-ssl-class-3-ca-1-2009"></a>**D-confiança da classe 3 SSL 1 2009**

| **Assunto** | CN = D-TRUST SSL classe 3 CA 1 2009<br>O = D-Trust GmbH<br>C = DE |
| --- | --- |
| **Emissor** | CN = D-confiança da classe raiz 3 2 2009<br>O = D-Trust GmbH<br>C = DE |
| **Nome alternativo da entidade** | RFC822 Name=info@d-trust.net<br>URL =http://www.d-trust.net |
| **Número de série** | 09:90:63 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | UTC de novembro de 12 12:46:55 2009 |
| **Validade não após** | UTC de novembro de 05 08:35:58 2029 |
| **Identificador de chave de assunto** | 50:19:32:94: (em inglês), 9A: C4: B5:04: (em inglês) (em inglês): 83: |
| **Identificador de chave de autoridade** | keyid: FD: da: 14: C4: o (a): 21: o BD: 1e: 42:39: (em inglês) (em inglês). |
| **Impressão digital (SHA-1)** | 2FC5DE6528CDBE50A14C382FC1DE524FAABF95FC |
| **Impressão digital (SHA-256)** | 6AC159B4C2BC8E729F3B84642EF1286BCC80D775FE278C740ADA468D59439025 |
| **PIN (SHA-256)** | 9w0QP9HzLXkfs + 4zENaUFq2XKcQON1oyksoJ + Gg2AZE = |
| **URLs de CRL** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_2009.crl |
| **URLs de OCSP** | http://root-c3-ca2-2009.ocsp.d-trust.net |

### <a name="d-trust-ssl-class-3-ca-1-ev-2009"></a>**D-confiança da classe 3 da AC 1 EV 2009**

| **Assunto** | CN = D-confiança SSL classe 3 AC 1 EV 2009<br>O = D-Trust GmbH<br>C = DE |
| --- | --- |
| **Emissor** | CN = D-confiança classe raiz 3 AC 2 EV 2009<br>O = D-Trust GmbH<br>C = DE |
| **Nome alternativo da entidade** | RFC822 Name=info@d-trust.net<br>URL =http://www.d-trust.net |
| **Número de série** | 09:90:64 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | UTC de novembro de 12 12:52:43 2009 |
| **Validade não após** | UTC de novembro de 05 08:50:46 2029 |
| **Identificador de chave de assunto** | AC: Ed: a5:9d: 7A: a2: [!: F1: F1:8A: (em inglês): (em inglês): B1:. |
| **Identificador de chave de autoridade** | keyid:, D3:94:8A: (em inglês), 4C: 62: a 2a: (em inglês):-7D: (em inglês):. |
| **Impressão digital (SHA-1)** | 1069423D308D0FC54575059638560FC7556E32B3 |
| **Impressão digital (SHA-256)** | B0935DC04B4E60C0C42DEF7EC57A1B1D8F958D17988E71CC80A8CF5E635BA5B4 |
| **PIN (SHA-256)** | lv5BNZ5aWd27ooolULDolFTwIaaWjHvG4yyH3rss4X8 = |
| **URLs de CRL** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%20EV%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_ev\_2009.crl |
| **URLs de OCSP** | http://root-c3-ca2-ev-2009.ocsp.d-trust.net |

### <a name="digicert-cloud-services-ca-1"></a>**AC de serviços de nuvem do DigiCert-1**

| **Assunto** | CN = autoridade de certificação dos serviços de nuvem DigiCert-1<br>O = DigiCert Inc<br>C = US |
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

### <a name="digicert-sha2-high-assurance-server-ca"></a>**Autoridade de certificação do servidor de alta garantia DigiCert SHA2**

| **Assunto** | CN = DigiCert SHA2 AC de servidor de alta garantia<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Emissor** | CN = DigiCert AC raiz EV de alta garantia<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| **Número de série** | 04: E1: E7: A4: DC: 5C: F2: F3:6D: C0:2B: 42:2: 5D: |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Oct 22 12:00:00 2013 UTC |
| **Validade não após** | Oct 22 12:00:00 2028 UTC |
| **Identificador de chave de assunto** | 51:68: FF: 90: AF: 02::%:: (!.............. |
| **Identificador de chave de autoridade** | keyid: B1:3E: C3: (em inglês) (em inglês):-BF: 47:47-01:0,01:1a: 1Uma: 08:02:. |
| **Impressão digital (SHA-1)** | A031C46782E6E6C662C2C87C76DA9AA62CCABD8E |
| **Impressão digital (SHA-256)** | 19400BE5B7A31FB733917700789D2F0A2471C0C9D506C0E504C06C16D7CB17C0 |
| **PIN (SHA-256)** | k2v657xBsOVe1PQRwOsHsw3bsGT2VzIqz5K + 59sNQws = |
| **URLs de CRL** | http://crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="digicert-sha2-secure-server-ca"></a>**Autoridade de certificação do servidor seguro do DigiCert SHA2**

| **Assunto** | CN = DigiCert SHA2 servidor seguro AC<br>O = DigiCert Inc<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz global DigiCert<br>OU = www. DigiCert. com<br>O = DigiCert Inc<br>C = US |
| **Número de série** | 01: FD: A3: EB: 6E: AUTORIDADE DE CERTIFICAÇÃO: 75: C8:88:43:8B: 72:4B: CF: |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Mar 08 12:00:00 2013 UTC |
| **Validade não após** | Mar 08 12:00:00 2023 UTC |
| **Identificador de chave de assunto** | 0F: (80:61: a 1C: 82: o E7:61: (em inglês). ~: ~:: 8D: 46: |
| **Identificador de chave de autoridade** | keyid: 03: de: 50:35:-D1:4C: BB: 66: (em inglês): a3: E2: (em inglês). 1b: 1b:. |
| **Impressão digital (SHA-1)** | 1FB86B1168EC743154062E8C9CC5B171A4B7CCB4 |
| **Impressão digital (SHA-256)** | 154C433C491929C5EF686E838E323664A00E6A0D822CCC958FB4DAB03E49A08F |
| **PIN (SHA-256)** | 5kJvNEMw0KjrCAu7eXY5HZdvyCS13BbA0VJG1RSP91w = |
| **URLs de CRL** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **URLs de OCSP** | http://ocsp.digicert.com |

### <a name="entrust-certification-authority---l1c"></a>**Autoridade de certificação Entrust-L1C**

| **Assunto** | CN = autoridade de certificação Entrust-L1C<br>OU = &quot; (c) 2009 Entrust, Inc.&quot;<br>OU = www. Entrust. net/RPA é incorporado por referência<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação Entrust. net (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. net/CPS \_ 2048 incorp. por Ref. (limita liab.)<br>O = Entrust. net |
| **Número de série** | 4C: 0E: 8C: 39 |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha1RSA |
| **Validade não antes** | UTC de novembro de 11 15:40:40 2011 |
| **Validade não após** | UTC de novembro de 12 02:51:17 2021 |
| **Identificador de chave de assunto** | 1e: F1: AB: 89: a 06: F8:49: (em inglês): 28:140:140:14:7A:. ee: |
| **Identificador de chave de autoridade** | keyid: 55: E4:81:.. 11:11: a:: D8:89:89: o B9:08: o... º. |
| **Impressão digital (SHA-1)** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **Impressão digital (SHA-256)** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **PIN (SHA-256)** | VFv5NemtodoRftw8KsvFb8AoCWwOJL6bOJS + Ui0bQ94 = |
| **URLs de CRL** | http://crl.entrust.net/2048ca.crl |
| **URLs de OCSP** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1k"></a>**Autoridade de certificação Entrust-L1K**

| **Assunto** | CN = autoridade de certificação Entrust-L1K<br>OU = &quot; (c) 2012 Entrust, Inc.-for apenas para uso autorizado&quot;<br>OU = ver www.entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
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

### <a name="globalsign"></a>**GlobalSign**

| **Assunto** | CN = GlobalSign<br>O = GlobalSign<br>OU = GlobalSign raiz CA-R3 |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz GlobalSign<br>OU = root CAO = GlobalSign NV-SA<br>C = BE |
| **Número de série** | 04:00:00:00:00:01:04:07:1D: |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | UTC de novembro de 18 10:00:00 2009 |
| **Validade não após** | Mar 18 10:00:00 2019 UTC |
| **Identificador de chave de assunto** | 8F: F0:4B: 7F: A8:2e: (em inglês): (em inglês): AE: 4D:: 8B:, de: |
| **Identificador de chave de autoridade** | keyid: 60:7B: 0,50:66:1a:-4B: 97: autoridade de certificação: 89: (em inglês) (em inglês): 2f: |
| **Impressão digital (SHA-1)** | 4765557AF418C68A641199146A7E556AA8242996 |
| **Impressão digital (SHA-256)** | FDFC6560B09C237F468B8130EB90996FF85FA13FA266239B8D5863798D6AB898 |
| **PIN (SHA-256)** | cGuxAXyFXFkWm61cF4HPWX8S0srS9j0aSqN0k4AP + 4A = |
| **URLs de CRL** | http://crl.globalsign.net/root.crl |
| **URLs de OCSP** | http://ocsp.globalsign.com/ExtendedSSLSHA256CACross |

### <a name="globalsign-extended-validation-ca---sha256---g2"></a>**AC de validação estendida do GlobalSign-SHA256-G2**

| **Assunto** | CN = GlobalSign validação estendida AC-SHA256-G2<br>O = GlobalSign NV-SA<br>C = BE |
| --- | --- |
| **Emissor** | CN = GlobalSign<br>O = GlobalSign<br>OU = GlobalSign raiz CA-R2 |
| **Número de série** | 04:00:00:00:00: A-4E: F0: |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Fev 20 10:00:00 2014 UTC |
| **Validade não após** | Dec 15 08:00:00 2021 UTC |
| **Identificador de chave de assunto** | da: 40:77:43://///////////!: A7: (...-3E: |
| **Identificador de chave de autoridade** | keyid: 9b: E2:07: são: a (em inglês),: 1e: 1e: 1e: C0:6A: (! de: 59): |
| **Impressão digital (SHA-1)** | 65BE102BE26928650E0EF54DC8F4F15AF5F98E8B |
| **Impressão digital (SHA-256)** | 24F91C0705A0A5338641B365FB0D9D9709B56297CFF1857E73C02C1636D486AA |
| **PIN (SHA-256)** | LvRiGEjRqfzurezaWuj8Wie2gyHMrW5Q06LspMnox7A = |
| **URLs de CRL** | http://crl.globalsign.net/root-r2.crl |
| **URLs de OCSP** | http://ocsp.globalsign.com/rootr2 |

### <a name="globalsign-extended-validation-ca---sha256---g3"></a>**AC de validação estendida do GlobalSign-SHA256-G3**

| **Assunto** | CN = GlobalSign validação estendida AC-SHA256-G3<br>O = GlobalSign NV-SA<br>C = BE |
| --- | --- |
| **Emissor** | CN = GlobalSign<br>O = GlobalSign<br>OU = GlobalSign raiz CA-R3 |
| **Número de série** | 48: A4:02: DD: 27:92: SÃO: A2:2008:34:9D |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | UTC de setembro de 21 00:00:00 2016 |
| **Validade não após** | UTC de setembro de 21 00:00:00 2026 |
| **Identificador de chave de assunto** | DD: B3: E7:6D: A8:2e: o E8: C5:4e: 6e: CF: (em inglês): o... |
| **Identificador de chave de autoridade** | keyid: 8F: F0:4B. 7F: A8:2e: 45:/!: AE: (em inglês): (em inglês): 0,50:: 8B: de: |
| **Impressão digital (SHA-1)** | 6023192FE7B59D2789130A9FE4094F9B5570D4A2 |
| **Impressão digital (SHA-256)** | AED5DD9A5339685DFB029F6D89A14335A96512C3CACC52B2994AF8B6B37FA4D2 |
| **PIN (SHA-256)** | 86fLIetopQLDNxFZ0uMI66Xpl1pFgLlHHn9v6kT0i4I = |
| **URLs de CRL** | http://crl.globalsign.com/root-r3.crl |
| **URLs de OCSP** | http://ocsp2.globalsign.com/rootr3 |

### <a name="globalsign-organization-validation-ca---sha256---g2"></a>**AC de validação de organização do GlobalSign-SHA256-G2**

| **Assunto** | CN = GlobalSign da organização de validação de empresa-SHA256-G2<br>O = GlobalSign NV-SA<br>C = BE |
| --- | --- |
| **Emissor** | CN = GlobalSign<br>O = GlobalSign<br>OU = GlobalSign raiz CA-R3 |
| **Número de série** | 04:00:00:00:00: A-89:. |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Ago 02 10:00:00 2011 UTC |
| **Validade não após** | Ago 02 10:00:00 2022 UTC |
| **Identificador de chave de assunto** | 96: de: 61: F1: o BD: (!...........: 7D: 53:... |
| **Identificador de chave de autoridade** | keyid: 8F: F0:4B. 7F: A8:2e: 45:/!: AE: (em inglês): (em inglês): 0,50:: 8B: de: |
| **Impressão digital (SHA-1)** | EF90B2B86F4756EBE7D36FF3015D63523A0076E9 |
| **Impressão digital (SHA-256)** | 0B339212D7CFF17A2C59E35669B58E77350133750A78DA9404770EDD470DEF76 |
| **PIN (SHA-256)** | IQBnNBEiFuhj + 8x6X8XLgh01V9Ic5/V3IRQLNFFc7v4 = |
| **URLs de CRL** | http://crl.globalsign.net/root-r3.crl |
| **URLs de OCSP** | http://ocsp2.globalsign.com/rootr3 |

### <a name="globalsign-organization-validation-ca---sha256---g2"></a>**AC de validação de organização do GlobalSign-SHA256-G2**

| **Assunto** | CN = GlobalSign da organização de validação de empresa-SHA256-G2<br>O = GlobalSign NV-SA<br>C = BE |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz GlobalSign<br>OU = autoridade de certificação raiz<br>O = GlobalSign NV-SA<br>C = BE |
| **Número de série** | 04:00:00:00:00:: 0,01:44: |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Fev 20 10:00:00 2014 UTC |
| **Validade não após** | Fev 20 10:00:00 2024 UTC |
| **Identificador de chave de assunto** | 96: de: 61: F1: o BD: (!...........: 7D: 53:... |
| **Identificador de chave de autoridade** | keyid: 60:7B: 0,50:66:1a:-4B: 97: autoridade de certificação: 89: (em inglês) (em inglês): 2f: |
| **Impressão digital (SHA-1)** | 902EF2DEEB3C5B13EA4C3D5193629309E231AE55 |
| **Impressão digital (SHA-256)** | 74EF335E5E18788307FB9D89CB704BEC112ABD23487DBFF41C4DED5070F241D9 |
| **PIN (SHA-256)** | IQBnNBEiFuhj + 8x6X8XLgh01V9Ic5/V3IRQLNFFc7v4 = |
| **URLs de CRL** | http://crl.globalsign.net/root.crl |
| **URLs de OCSP** | http://ocsp.globalsign.com/rootr1 |

### <a name="globalsign-organization-validation-ca---sha256---g2"></a>**AC de validação de organização do GlobalSign-SHA256-G2**

| **Assunto** | CN = GlobalSign da organização de validação de empresa-SHA256-G2<br>O = GlobalSign NV-SA<br>C = BE |
| --- | --- |
| **Emissor** | CN = autoridade de certificação raiz GlobalSign<br>OU = autoridade de certificação raiz<br>O = GlobalSign NV-SA<br>C = BE |
| **Número de série** | 04:00:00:00:00:: 0,01:44: |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Fev 20 10:00:00 2014 UTC |
| **Validade não após** | Fev 20 10:00:00 2024 UTC |
| **Identificador de chave de assunto** | 96: de: 61: F1: o BD: (!...........: 7D: 53:... |
| **Identificador de chave de autoridade** | keyid: 60:7B: 0,50:66:1a:-4B: 97: autoridade de certificação: 89: (em inglês) (em inglês): 2f: |
| **Impressão digital (SHA-1)** | 902EF2DEEB3C5B13EA4C3D5193629309E231AE55 |
| **Impressão digital (SHA-256)** | 74EF335E5E18788307FB9D89CB704BEC112ABD23487DBFF41C4DED5070F241D9 |
| **PIN (SHA-256)** | IQBnNBEiFuhj + 8x6X8XLgh01V9Ic5/V3IRQLNFFc7v4 = |
| **URLs de CRL** | http://crl.globalsign.net/root.crl |
| **URLs de OCSP** | http://ocsp.globalsign.com/rootr1 |

### <a name="lets-encrypt-authority-x3"></a>**Vamos criptografar a autoridade de certificação X3**

| **Assunto** | CN = vamos criptografar Authority X3<br>O = vamos criptografar<br>C = US |
| --- | --- |
| **Emissor** | CN = AC raiz de DST X3<br>O = confiança de assinatura digital co. |
| **Número de série** | 0A: 01:41:42:42:00:0,01-53:85::, 0B: 85: |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Mar 17 16:40:46 2016 UTC |
| **Validade não após** | Mar 17 16:40:46 2021 UTC |
| **Identificador de chave de assunto** | A8:4A: 6A: 63://////////////////!: D1:39: |
| **Identificador de chave de autoridade** | keyid: C4: A7: são: [!.............: 4B: (em inglês): 15:0,75: |
| **Impressão digital (SHA-1)** | E6A3B45B062D509B3382282D196EFE97D5956CCB |
| **Impressão digital (SHA-256)** | 25847D668EB4F04FDD40B12B6B0740C567DA7D024308EB6C2C96FE41D9DE218D |
| **PIN (SHA-256)** | YLh1dUR9y6Kja30RrAn7JKnbQG/uEtLMkBgFF2Fuihg = |
| **URLs AIA** | http://apps.identrust.com/roots/dstrootcax3.p7c |
| **URLs de CRL** | http://crl.identrust.com/DSTROOTCAX3CRL.crl |
| **URLs de OCSP** | http://isrg.trustid.ocsp.identrust.com |

### <a name="microsoft-it-ssl-sha2"></a>**SHA2 SSL de ti da Microsoft**

| **Assunto** | CN = SHA2 de SSL de ti da Microsoft<br>OU = ti da Microsoft<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Emissor** | CN = Baltimore CyberTrust raiz<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **Número de série** | 07:27:9A: A9 |
| **Comprimento da chave pública** | RSA 4096 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Dec 19 20:07:32 2013 UTC |
| **Validade não após** | Dec 19 20:06:55 2017 UTC |
| **Identificador de chave de assunto** | 51: AF: 24:26: (em inglês): (em inglês): (em inglês): 57: (16:26:2B: 3B: 46: |
| **Identificador de chave de autoridade** | keyid: E5:9d: 59-30:/!: (em inglês): (em inglês): 4: (em inglês): 08:36: |
| **Impressão digital (SHA-1)** | 948E1652586240D453287AB69CAEB8F2F4F02117 |
| **Impressão digital (SHA-256)** | 34BD941A06ED10E2FAC8459F79E4748C1EA08F142C6DE5E557884D0D3CE249FA |
| **PIN (SHA-256)** | CzdPous1hY3sIkO55pUH7vklXyIHVZAl/UnprSQvpEI = |
| **URLs de CRL** | http://cdp1.public-trust.com/CRL/Omniroot2025.crl |

### <a name="microsoft-it-ssl-sha2"></a>**SHA2 SSL de ti da Microsoft**

| **Assunto** | CN = SHA2 de SSL de ti da Microsoft<br>OU = ti da Microsoft<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Emissor** | CN = Baltimore CyberTrust raiz<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **Número de série** | 07:27: AA: 47 |
| **Comprimento da chave pública** | RSA 4096 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Maio de 07 17:04:09 2014 UTC |
| **Validade não após** | Maio de 07 17:03:30 2018 UTC |
| **Identificador de chave de assunto** | 51: AF: 24:26: (em inglês): (em inglês): (em inglês): 57: (16:26:2B: 3B: 46: |
| **Identificador de chave de autoridade** | keyid: E5:9d: 59-30:/!: (em inglês): (em inglês): 4: (em inglês): 08:36: |
| **Impressão digital (SHA-1)** | 97EFF3028677894BDD4F9AC53F789BEE5DF4AD86 |
| **Impressão digital (SHA-256)** | 2399983E99703EBD01CEA466C10799810C4BA62A8D61B88170A334DCD61BB20F |
| **PIN (SHA-256)** | CzdPous1hY3sIkO55pUH7vklXyIHVZAl/UnprSQvpEI = |
| **URLs de CRL** | http://cdp1.public-trust.com/CRL/Omniroot2025.crl |
| **URLs de OCSP** | http://ocsp.omniroot.com/baltimoreroot |

### <a name="microsoft-it-tls-ca-1"></a>**AC 1 TLS da TI da Microsoft**

| **Assunto** | CN = autoridade de certificação TLS da TI da Microsoft<br>OU = ti da Microsoft<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
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

| **Assunto** | CN = autoridade de certificação TLS de ti da Microsoft<br>OU = ti da Microsoft<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
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

| **Assunto** | CN = AC do Microsoft IT TLS 4<br>OU = ti da Microsoft<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
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

| **Assunto** | CN = AC do Microsoft IT TLS 5<br>OU = ti da Microsoft<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
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

### <a name="symantec-class-3-ev-ssl-ca---g3"></a>**AC SSL EV-G3 da Symantec classe 3**

| **Assunto** | CN = Symantec classe 3 EV SSL AC-G3<br>OU = rede de confiança da Symantec<br>O = Symantec Corporation<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação primária pública de classe 3 da VeriSign-G5<br>OU = &quot; (c) 2006 Verisign, Inc.-for Authorized use only&quot;<br>OU = rede de confiança VeriSign<br>O = &quot; Verisign, Inc.&quot;<br>C = US |
| **Nome alternativo da entidade** | Endereço do diretório: CN = SymantecPKI-1-533 |
| **Número de série** | 7E: E1:4A: 6F: 6F: EF: O (A) (EM INGLÊS): [!:. |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Oct 31 00:00:00 2013 UTC |
| **Validade não após** | Oct 30 23:59:59 2023 UTC |
| **Identificador de chave de assunto** | 01:59: o E7: (em inglês): (em inglês): 59: (em inglês): 59: (em inglês).: |
| **Identificador de chave de autoridade** | keyid: 7F: D3:///////////////!: b:/BB:,...:. º:. |
| **Impressão digital (SHA-1)** | E3FC0AD84F2F5A83ED6F86F567F8B14B40DCBF12 |
| **Impressão digital (SHA-256)** | 9E6BC5F9ECC52460E8EDC02C644D1BE1CB9F2316F41DAF3B616A0B2058294B31 |
| **PIN (SHA-256)** | gMxWOrX4PMQesK9qFNbYBxjBfjUvlkn/vN1n + L9lE5E = |
| **URLs de CRL** | http://s1.symcb.com/pca3-g5.crl |
| **URLs de OCSP** | http://s2.symcb.com |

### <a name="symantec-class-3-secure-server-ca---g4"></a>**Symantec classe 3 AC do servidor seguro-G4**

| **Assunto** | CN = autoridade de certificação do servidor seguro do Symantec Class 3-G4<br>OU = rede de confiança da Symantec<br>O = Symantec Corporation<br>C = US |
| --- | --- |
| **Emissor** | CN = autoridade de certificação primária pública de classe 3 da VeriSign-G5<br>OU = &quot; (c) 2006 Verisign, Inc.-for Authorized use only&quot;<br>OU = rede de confiança VeriSign<br>O = &quot; Verisign, Inc.&quot;<br>C = US |
| **Nome alternativo da entidade** | Endereço do diretório: CN = SymantecPKI-1-534 |
| **Número de série** | 51:3F: B9:74: (EM INGLÊS). \: (EM INGLÊS): (EM INGLÊS). |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Oct 31 00:00:00 2013 UTC |
| **Validade não após** | Oct 30 23:59:59 2023 UTC |
| **Identificador de chave de assunto** | 5F: 60: CF: 61:90:55: (em inglês)-84:43:: 2A: (em inglês): a. |
| **Identificador de chave de autoridade** | keyid: 7F: D3:///////////////!: b:/BB:,...:. º:. |
| **Impressão digital (SHA-1)** | FF67367C5CD4DE4AE18BCCE1D70FDABD7C866135 |
| **Impressão digital (SHA-256)** | EAE72EB454BF6C3977EBD289E970B2F5282949190093D0D26F98D0F0D6A9CF17 |
| **PIN (SHA-256)** | 9n0izTnSRF + W4W4JTq51avSXkWhQB8duS2bxVLfzXsY = |
| **URLs de CRL** | http://s1.symcb.com/pca3-g5.crl |
| **URLs de OCSP** | http://s2.symcb.com |

### <a name="thawte-sha256-ssl-ca"></a>**AC com autoridade de certificação do Thaw SHA256**

| **Assunto** | CN = AC de SSL de Thaw SHA256<br>O = &quot; Thawte, Inc.&quot;<br>C = US |
| --- | --- |
| **Emissor** | CN = AC raiz primária da Thawte-G3<br>OU = &quot; (c) 2008 Thawte, Inc.-for Authorized use only&quot;<br>OU = divisão de serviços de certificação<br>O = &quot; Thawte, Inc.&quot;<br>C = US |
| **Nome alternativo da entidade** | Endereço do diretório: CN = VeriSignMPKI-2-415 |
| **Número de série** | 36:34:9E: 18: O////////!: (!: 69:): |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Maio de 23 00:00:00 2013 UTC |
| **Validade não após** | Maio de 22 23:59:59 2023 UTC |
| **Identificador de chave de assunto** | 2 2B: 9A: 35: AE: 01:18:2B: (em inglês): a 7a: 05:...... º. |
| **Identificador de chave de autoridade** | keyid: AD: 6C: AA: (em inglês): [!:............ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @ @: |
| **Impressão digital (SHA-1)** | 67D147D5DAB7F28D663CA5B7A9568F087427B9F7 |
| **Impressão digital (SHA-256)** | 3F3AF9C9CC2C7599EF8F6DD7CA516CFC1797D7D12002254F3BFD0D4D0FE9DE86 |
| **PIN (SHA-256)** | /36ymPAVaJl3QDyB1lUkVf9GqJNug0R8JJPDN6348p8 = |
| **URLs de CRL** | http://crl.thawte.com/ThawtePCA-G3.crl |
| **URLs de OCSP** | http://ocsp.thawte.com |

### <a name="verizon-akamai-sureserver-ca-g14-sha2"></a>**Verizon Akamai SureServer AC G14-SHA2**

| **Assunto** | CN = Verizon Akamai SureServer AC G14-SHA2<br>OU = Cybertrust<br>O = Verizon Enterprise Solutions<br>L = Amsterdã<br>C = NL |
| --- | --- |
| **Emissor** | CN = Baltimore CyberTrust raiz<br>OU = CyberTrust<br>O = Baltimore<br>C = IE |
| **Número de série** | 07:27: A4:6B |
| **Comprimento da chave pública** | RSA 2048 bits (e 65537) |
| **Algoritmo de assinatura** | sha256RSA |
| **Validade não antes** | Abr 02 14:36:10 2014 UTC |
| **Validade não após** | Abr 02 14:35:52 2021 UTC |
| **Identificador de chave de assunto** | F8: BD: FA: AF: (em inglês): (em inglês) (em inglês): 1b: 1 a 12: (em inglês). |
| **Identificador de chave de autoridade** | keyid: E5:9d: 59-30:/!: (em inglês): (em inglês): 4: (em inglês): 08:36: |
| **Impressão digital (SHA-1)** | 6AD2B04E2196E48BF685752890E811CD2ED60606 |
| **Impressão digital (SHA-256)** | 7373D219B42547E41BCB752BCBCBE93F592FF6F99C340CE57B73D38C3EC0BA98 |
| **PIN (SHA-256)** | 8XFPrRr4VxmEIYKUu35QtR3oGbduX1AlrBzaBUHgp7c = |
| **URLs AIA** | https://cacert.omniroot.com/baltimoreroot.crt<br>https://cacert.omniroot.com/baltimoreroot.der |
| **URLs de CRL** | http://cdp1.public-trust.com/CRL/Omniroot2025.crl |
| **URLs de OCSP** | http://ocsp.omniroot.com/baltimoreroot |

## <a name="additional-certificate-paths"></a>**Caminhos de certificado adicionais**

A lista a seguir inclui certificados herdados que não estão incluídos acima e serão mesclados com a lista acima ao longo do tempo.

evsecure-aia.verisign.com<br>
sa.symcb.com<br>
sd.symcb.com<br>
\*. omniroot.com<br>
\*. verisign.com<br>
\*. symcb.com<br>
\*. symcd.com<br>
\*. verisign.net<br>
\*. geotrust.com<br>
\*. entrust.net<br>
\*. public-trust.com<br>
EVIntl-ocsp.verisign.com<br>
EVSecure-ocsp.verisign.com<br>
isrg.trustid.ocsp.identrust.com<br>
ocsp.digicert.com<br>
ocsp.entrust.net<br>
ocsp.globalsign.com/ExtendedSSLSHA256CACross<br>
ocsp.globalsign.com/rootr1<br>
ocsp.globalsign.com/rootr2<br>
ocsp2.globalsign.com/rootr3<br>
ocsp.int-x3.letsencrypt.org/<br>
ocsp.msocsp.com<br>
ocsp.omniroot.com/baltimoreroot<br>
ocsp2.globalsign.com/gsextendvalsha2g3r3<br>
ocsp2.globalsign.com/gsorganizationvalsha2g2<br>
ocsp2.globalsign.com/gsorganizationvalsha2g3<br>
ocsp2.globalsign.com/rootr3<br>
ocspx.digicert.com<br>
s2.symcb.com<br>
sr.symcd.com<br>
su.symcd.com<br>
vassg142.ocsp.omniroot.com<br>
cdp1.public-trust.com/CRL/Omniroot2025.crl<br>
crl.entrust.net/2048ca.crl<br>
crl.entrust.net/g2ca.crl<br>
crl.entrust.net/level1k.crl<br>
crl.entrust.net/rootca1.crl<br>
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl<br>
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl<br>
crl.globalsign.com/gsorganizationvalsha2g3.crl<br>
crl.globalsign.com/root.crl<br>
crl.globalsign.net/root-r2.crl<br>
crl.globalsign.com/root-r3.crl<br>
crl.globalsign.net/root.crl<br>
crl.identrust.com/DSTROOTCAX3CRL.crl<br>
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl<br>
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl<br>
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl<br>
crl3.digicert.com/DigiCertGlobalRootCA.crl<br>
crl3.digicert.com/sha2-ev-server-g1.crl<br>
crl3.digicert.com/sha2-ha-server-g5.crl<br>
crl3.digicert.com/ssca-sha2-g5.crl<br>
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl<br>
crl4.digicert.com/DigiCertGlobalRootCA.crl<br>
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl<br>
crl4.digicert.com/sha2-ev-server-g1.crl<br>
crl4.digicert.com/sha2-ha-server-g5.crl<br>
crl4.digicert.com/ssca-sha2-g5.crl<br>
EVIntl-crl.verisign.com/EVIntl2006.crl<br>
EVSecure-crl.verisign.com/pca3-g5.crl<br>
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl<br>
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl<br>
s1.symcb.com/pca3-g5.crl<br>
sr.symcb.com/sr.crl<br>
su.symcb.com/su.crl<br>
vassg142.crl.omniroot.com/vassg142.crl<br>
aia.entrust.net/l1k-chain256.cer<br>
apps.identrust.com/roots/dstrootcax3.p7c<br>
<https://cacert.a.omniroot.com/vassg142.crt><br>
<https://cacert.a.omniroot.com/vassg142.der><br>
<https://cacert.omniroot.com/baltimoreroot.crt><br>
<https://cacert.omniroot.com/baltimoreroot.der><br>
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt<br>
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt<br>
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt<br>
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt<br>
cert.int-x3.letsencrypt.org/<br>
EVIntl-aia.verisign.com/EVIntl2006.cer<br>
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt<br>
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt<br>
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt<br>
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt<br>
sr.symcb.com/sr.crt<br>
su.symcb.com/su.crt<br>
<https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt><br>
<https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt><br>
<https://www.microsoft.com/pki/mscorp/msitwww1.crt><br>
<https://www.microsoft.com/pki/mscorp/msitwww2.crt><br>