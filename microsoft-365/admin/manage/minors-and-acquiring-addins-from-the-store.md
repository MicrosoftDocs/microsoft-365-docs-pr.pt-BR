---
title: Menores e aquisição de complementos da Loja
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
description: Saiba mais sobre os regulamentos do RGPD (Regulamento Geral sobre a Proteção de Dados) que regem os dados pessoais de menores.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306546"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Menores e aquisição de complementos da Loja

O RGPD (Regulamento Geral sobre a Proteção de Dados) é uma regulamentação da União Europeia que entra em vigor em 25 de maio de 2018. Ele concede aos usuários direitos e proteção de seus dados. Um dos aspectos do RGPD é que os menores não podem ter seus dados pessoais enviados às partes que seu pai ou responsável não aprovou. A idade específica definida como menor depende da região onde o indivíduo está localizado.
  
As regiões que têm regulamentações estatutuais sobre o consentimento dos pais incluem Estados Unidos, Coreia do Sul, Reino Unido e União Europeia. Nessas regiões, um menor de idade será impedido (por meio do Azure Active Directory) de obter novos complementos do Office da Loja e executar os complementos adquiridos anteriormente. Para países sem regulamentações estatutárias, não haverá restrições de download.
  
Um usuário é determinado como menor com base nos dados especificados no Azure Active Directory. O administrador da organização é responsável por declarar a faixa etária legal e o consentimento dos pais desse usuário.
  
Se o pai/responsável consentir com um menor usando um determinado complemento, o administrador da organização poderá usar a implantação centralizada para implantar esse complemento em todos os menores que tenham consentimento.
  
Para ser compatível com o RGPD para menores, você precisa garantir que um dos seguintes builds do Office seja implantado em sua escola/organização.
 
 **Para Word, Excel, PowerPoint e Project:** 

|**Plataforma** <br/> |**Número de compilação** <br/> |
|:-----|:-----|
|Aplicativos do Microsoft 365 para empresas (Canal Atual)  <br/> |9001.2138   <br/> |
|Aplicativos do Microsoft 365 para empresas (Canal Empresarial Semestais)  <br/> |8431.2159  <br/> |
|Office 2016 para Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 para Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 para Mac  <br/> |16.11.18020200  <br/> |
|Office na Web  <br/> |N/D  <br/> |
   
 **Para o Outlook**: 
  
|**Plataforma** <br/> |**Número de compilação** <br/> |
|:-----|:-----|
|Outlook 2016 para Windows (MSI)  <br/> |Build No TBD  <br/> |
|Outlook 2016 para Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 para Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile para iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile para Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/D  <br/> |

 **Requisitos do Office 2013**
  
O Word, o Excel e o PowerPoint 2013 para Windows darão suporte às mesmas verificações secundárias se a ADAL (Biblioteca de Autenticação do Active Directory) estiver habilitada. Há duas opções de conformidade, conforme explicado a seguir.
  
- **Habilitar ADAL**. Este artigo explica como habilitar a ADAL para Office 2013: usando a autenticação moderna do [Microsoft 365 com clientes do Office.](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016)<br/>Você também precisa definir as chaves do Registro para habilitar a ADAL, conforme explicado em Habilitar Autenticação Moderna para [Office 2013 em dispositivos Windows.](../security-and-compliance/enable-modern-authentication.md)<br/>Além disso, você precisa instalar as seguintes atualizações de abril para o Office 2013:
    
  - [Descrição da atualização de segurança do Office 2013: 10 de abril de 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 de abril de 2018, atualização para o Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Não habilitar a ADAL.** Se você não conseguir habilitar a ADAL no Office 2013, nossa recomendação é usar a Política de Grupo para desativar a Loja para os clientes do Office. As informações sobre como desativar o aplicativo para configurações do Office estão localizadas [aqui.](https://technet.microsoft.com/library/cc178992.aspx)

## <a name="related-articles"></a>Artigos relacionados

[Implantar suplementos no centro de administração](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Gerenciar suplementos no centro de administração](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
