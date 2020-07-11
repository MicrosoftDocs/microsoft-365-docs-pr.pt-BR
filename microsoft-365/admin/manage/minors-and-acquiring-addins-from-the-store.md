---
title: Menores e aquisição de suplementos da loja
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Saiba mais sobre as normas gerais de RGPD (regulamentação de proteção de dados) que governam os dados pessoais dos menores.
ms.openlocfilehash: dcf2c98906830e0007747e2dd90e67b9dc85a5bb
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103085"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Menores e aquisição de suplementos da loja

A regulamentação geral de proteção de dados (RGPD) é uma regulamentação de União Européia que se torna efetiva 25 de maio de 2018. Ele fornece direitos e proteção de seus dados aos usuários. Um dos aspectos do RGPD é que os menores não podem ter seus dados pessoais enviados a partes que seu pai ou guardião não aprovou. A idade específica definida como um secundário depende da região onde o indivíduo está localizado.
  
Regiões que têm regulamentações estatutárias sobre o consentimento dos pais incluem Estados Unidos, Coréia do Sul, Reino Unido e União Européia. Para essas regiões, um pequeno será bloqueado (por meio do Azure Active Directory) para obter qualquer suplemento novo do Office a partir da loja e executar suplementos que foram adquiridos anteriormente. Para países sem regulamentações legais, não haverá restrições de download.
  
Um usuário é determinado como um secundário com base nos dados especificados no Azure Active Directory. O administrador da organização é responsável por declarar o grupo de idades legais e o consentimento do responsável para esse usuário.
  
Se o pai/guardião for enviado a um secundário usando um suplemento específico, o administrador da organização poderá usar a implantação centralizada para implantar esse suplemento em todos os menores que tiverem consentimento.
  
Ser compatível com o RGPD para menores que você precisa para garantir que uma das seguintes versões do Office seja implantada em sua escola/organização.
 
 **Para Word, Excel, PowerPoint e Project**: 

|**Plataforma** <br/> |**Número de compilação** <br/> |
|:-----|:-----|
|Microsoft 365 aplicativos para empresas (canal atual)  <br/> |9001,2138   <br/> |
|Microsoft 365 aplicativos para empresas (canal empresarial semestral)  <br/> |8431,2159  <br/> |
|Office 2016 para Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 para Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 para Mac  <br/> |16.11.18020200  <br/> |
|Office para a Web  <br/> |N/D  <br/> |
   
 **Para o Outlook**: 
  
|**Plataforma** <br/> |**Número de compilação** <br/> |
|:-----|:-----|
|Outlook 2016 para Windows (MSI)  <br/> |Compilação não TBD  <br/> |
|Outlook 2016 para Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 para Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile para iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile para Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/D  <br/> |

 **Requisitos do Office 2013**
  
O Word, o Excel e o PowerPoint 2013 para Windows oferecerão suporte às mesmas verificações secundárias se a biblioteca de autenticação do Active Directory (ADAL) estiver habilitada. Há duas opções de conformidade, conforme explicado a seguir.
  
- **Habilitar Adal**. Este artigo explica como habilitar a ADAL para o Office 2013: [usando a autenticação moderna da Microsoft 365 com clientes do Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).<br/>Você também precisa definir as chaves do registro para habilitar a ADAL, conforme explicado em [habilitar a autenticação moderna para o Office 2013 em dispositivos Windows](../security-and-compliance/enable-modern-authentication.md).<br/>Além disso, você precisa instalar as seguintes atualizações de abril para o Office 2013:
    
  - [Descrição da atualização de segurança para o Office 2013:10 de abril de 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 de abril de 2018, atualização para o Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Não habilite a Adal**. Se você não conseguir habilitar a ADAL no Office 2013, nossa recomendação é usar a política de grupo para desativar o repositório para os clientes do Office. As informações sobre como desativar as configurações de aplicativo para Office estão localizadas [aqui](https://technet.microsoft.com/library/cc178992.aspx).

## <a name="related-articles"></a>Artigos relacionados

[Implantar suplementos no centro de administração](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Gerenciar suplementos no centro de administração](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
