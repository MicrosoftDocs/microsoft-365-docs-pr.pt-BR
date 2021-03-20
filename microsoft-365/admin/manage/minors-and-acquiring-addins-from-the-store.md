---
title: Secundárias e aquisição de complementos da Loja
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
description: Saiba mais sobre os regulamentos do RGPD (Regulamento Geral de Proteção de Dados) que regem os dados pessoais de menores.
ms.openlocfilehash: c49ea719bc85166cc8082200eb833273b0ab5835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915249"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Secundárias e aquisição de complementos da Loja

O RGPD (Regulamento Geral de Proteção de Dados) é uma regulamentação da União Europeia que entra em vigor em 25 de maio de 2018. Ele dá aos usuários direitos e proteção de seus dados. Um dos aspectos do RGPD é que os menores não podem ter seus dados pessoais enviados às partes que seu pai ou responsável não aprovou. A idade específica definida como secundária depende da região onde o indivíduo está localizado.
  
As regiões que têm regulamentos estatutários sobre o consentimento dos pais incluem os Estados Unidos, a Coreia do Sul, o Reino Unido e a União Europeia. Para essas regiões, um secundário será bloqueado (por meio do Azure Active Directory) de obter novos complementos do Office na Loja e executar os complementos que foram adquiridos anteriormente. Para países sem regulamentos estatutários, não haverá restrições de download.
  
Um usuário é determinado como um secundário com base nos dados especificados no Azure Active Directory. O administrador da organização é responsável por declarar a faixa etária legal e o consentimento dos pais para esse usuário.
  
Se o pai/responsável consentir com um menor usando um complemento específico, o administrador da organização poderá usar a implantação centralizada para implantar esse complemento em todos os menores que tenham consentimento.
  
Para ser compatível com o RGPD para menores, você precisa garantir que uma das seguintes builds do Office seja implantada em sua escola/organização.
 
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
|Outlook mobile para iOS  <br/> |2.75.0  <br/> |
|Outlook mobile para Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/D  <br/> |

 **Requisitos do Office 2013**
  
Word, Excel e PowerPoint 2013 para Windows darão suporte às mesmas verificações secundárias se a Biblioteca de Autenticação do Active Directory (ADAL) estiver habilitada. Há duas opções de conformidade, conforme explicado em seguida.
  
- **Habilitar a ADAL**. Este artigo explica como habilitar o ADAL para o Office 2013: usando a autenticação moderna do [Microsoft 365 com clientes do Office.](../../enterprise/modern-auth-for-office-2013-and-2016.md)<br/>Você também precisa definir as chaves do Registro para habilitar o ADAL conforme explicado em Habilitar Autenticação Moderna para [Office 2013 em dispositivos Windows](../security-and-compliance/enable-modern-authentication.md).<br/>Além disso, você precisa instalar as seguintes atualizações de abril para o Office 2013:
    
  - [Descrição da atualização de segurança do Office 2013: 10 de abril de 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 de abril de 2018, atualização para o Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Não habilita o ADAL**. Se você não conseguir habilitar o ADAL no Office 2013, nossa recomendação é usar a Política de Grupo para desativar a Loja para os clientes do Office. Informações sobre como desativar o aplicativo para configurações do Office estão localizadas [aqui](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).

## <a name="related-articles"></a>Artigos relacionados

[Implantar suplementos no centro de administração](./manage-deployment-of-add-ins.md)

[Gerenciar suplementos no centro de administração](./manage-addins-in-the-admin-center.md)
