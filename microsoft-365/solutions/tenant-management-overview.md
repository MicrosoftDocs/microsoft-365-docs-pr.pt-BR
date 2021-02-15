---
title: Gerenciamento de locatários do Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Uma visão geral do planejamento, implantação e operação contínua dos locatários do Microsoft 365.
ms.openlocfilehash: f7daeaed149b5b6199ac9012b3ffa3d811029099
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908451"
---
# <a name="tenant-management-for-microsoft-365-for-enterprise"></a>Gerenciamento de locatários do Microsoft 365 para empresas

Criar um caminho para a transformação digital da sua organização com a computação em nuvem requer uma base sólida na qual seus funcionários podem confiar em produtividade, colaboração, desempenho, privacidade, conformidade e segurança.

A configuração correta dos locatários do Microsoft 365 fornece essa base, deixando os funcionários focados na execução do trabalho e no departamento de TI a fim de se concentrar nas soluções de ponta a ponta que fornecem valor comercial adicional. 

Esta solução o leva até a configuração dessa base nestas etapas:

1. Determinar seus locatários
2. Otimizar sua rede
3. Sincronizar suas identidades e impor logins seguros
4. Migrar seus dispositivos Windows, clientes do Office e servidores e dados locais do Office
5. Implantar o gerenciamento de dispositivos e aplicativos

Mas primeiro, vamos dar um tempo para entender o que é um locatário e a aparência de um locatário que fornece uma base sólida.

## <a name="a-microsoft-365-tenant-defined"></a>Um locatário do Microsoft 365 definido

Um locatário do Microsoft 365 é uma instância dedicada dos serviços do Microsoft 365 e os dados da sua organização armazenados em um local padrão específico, como a Europa ou a América do Norte. Esse local é especificado quando você cria o locatário para sua organização. Cada locatário do Microsoft 365 é distinto, exclusivo e separado de todos os outros locatários do Microsoft 365. Você cria um locatário do Microsoft 365 quando compra um ou mais produtos da Microsoft, como o Microsoft 365 E3 ou E5, e um conjunto de licenças para cada um.

Seu locatário do Microsoft 365 também inclui um locatário do Azure Active Directory (Azure AD), que é uma instância dedicada do Azure AD para contas de usuário, grupos e outros objetos. Cada locatário do Azure AD é distinto, exclusivo e separado de todos os outros locatários do Azure AD. Embora sua organização possa ter vários locatários do Azure AD que você pode configurar com assinaturas do Azure, os locatários do Microsoft 365 só podem usar um único locatário do Azure AD, aquele que foi criado quando você criou o locatário. 

Veja um exemplo:

![Um exemplo de locatário do Microsoft 365 com seu locatário do Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

*O gerenciamento de* locatários é o planejamento, a implantação e a operação contínua dos locatários do Microsoft 365. 

## <a name="attributes-of-a-well-designed-and-operating-tenant"></a>Atributos de um locatário bem projetado e operacional

Além do nome e do local corretos para seu locatário, há elementos adicionais para planejar, implantar e gerenciar para garantir que suas experiências de usuário com aplicativos de produtividade na nuvem, como o Microsoft Teams e o Exchange Online, sejam eficazes, seguras e &mdash; &mdash; eficazes.

Aqui estão os elementos:

- Você tem o conjunto correto de produtos (assinaturas) e licenças.
  - O conjunto de produtos combina com suas necessidades comerciais, de IT e de segurança.
  - Há um número adequado de licenças para seus funcionários e alterações previstas no pessoal.
- Para rede:
  - Você configurou os nomes de domínio DNS corretos.
  - Para redes corporativas, você otimizou o tráfego de rede para a rede da Microsoft para funcionários no local.
  - Você otimizou o tráfego de rede para funcionários remotos que estão usando um cliente VPN.
- Você sincronizou suas contas, grupos e outros objetos do Active Directory Domain Services (AD DS).
  - Suas contas de locatário do Azure AD são mapeadas para caixas de correio do Exchange Online com os domínios DNS corretos para endereços de email.
  - Suas contas de usuário foram atribuídas com as licenças corretas dos produtos comprados corretos (como o Microsoft 365 E3 ou E5).
- Você configurou um gerenciamento forte de identidade e acesso.
  - Você está exigindo uma conexão de usuário segura com autenticação sem senha ou multifafação (MFA).
  - Você tem políticas de Acesso Condicional que impõem restrições e requisitos de entrada para níveis mais altos de segurança.
- Os servidores locais do Office e seus dados foram migrados para aplicativos de nuvem ou estão sendo usados em uma configuração híbrida.
- Você está fazendo o gerenciamento de dispositivos com o Intune ou o Basic Mobility and Security integrados ao Microsoft 365.
  - Os dispositivos de propriedade da sua organização são inscritos e gerenciados.
  - Os aplicativos para dispositivos pessoais são gerenciados.

Aqui está um exemplo de um locatário do Microsoft 365 com todos esses elementos no local.

![Um exemplo de locatário do Microsoft 365](../media/tenant-management-overview/tenant-management-tenant-config.png)

Nesta ilustração, o locatário do Microsoft 365 inclui:

- Produtos e licenças para o Microsoft 365 E3 e E5.
- Aplicativos de produtividade do Microsoft 365.
- Intune com dispositivos inscritos e políticas de dispositivos e aplicativos.
- Um locatário do Azure AD que sincronizou a conta de usuário (grupos e outros objetos de diretório não são mostrados), domínios e políticas de Acesso Condicional.

## <a name="tenant-capabilities-for-microsoft-365-for-enterprise"></a>Recursos de locatário do Microsoft 365 para empresas

As seções e tabelas a seguir listam os principais recursos e licenciamento para as etapas desta solução.

### <a name="tenant"></a>Tenant

| Capcidade ou recurso | Descrição | Licenças |
|:-------|:-----|:-------|
| Vários locatários | Cada locatário do Microsoft 365 é distinto, exclusivo e separado de todos os outros locatários do Microsoft 365. Com vários locatários, há restrições e considerações adicionais ao gerenciar e fornecer serviços aos usuários. | Microsoft 365 E3 ou E5 | 
| Migração de caixa de correio entre locatários | Os administradores de locatários podem mover caixas de correio entre locatários com dependências mínimas de infraestrutura em seus sistemas locais. Isso elimina a necessidade de remoção e integração de caixas de correio. | Microsoft 365 E3 ou E5 | 
| Multi-Geo | Seu locatário pode armazenar dados em repouso em outras localizações geográficas do datacenter que você escolheu para atender aos requisitos de residência de dados. | Microsoft 365 E3 ou E5 | 
| Mover os dados principais para um novo datacenter geo | À medida que a Microsoft adiciona novas áreas geográficas de datacenter para capacidade adicional e recursos de computação, você pode solicitar uma movimentação geográfica de datacenter para residência de dados na área geográfica dos dados principais do cliente. | Microsoft 365 E3 ou E5 | 
||||

### <a name="networking"></a>Rede

| Capcidade ou recurso | Descrição | Licenças |
|:-------|:-----|:-------|
| Network Insights | Métricas de desempenho de rede coletadas do locatário do Microsoft 365 para ajudá-lo a projetar perímetros de rede para seus locais de escritório. | Microsoft 365 E3 ou E5 | 
| Automatizar atualizações de ponto de extremidade | Automatize a configuração e as atualizações contínuas dos pontos de extremidade do Microsoft 365 em seus arquivos PAC do cliente e dispositivos e serviços de rede. | Microsoft 365 E3 ou E5 | 
||||

### <a name="identity"></a>Identidade

| Capcidade ou recurso | Descrição | Licenças |
|:-------|:-----|:-------|
| Sincronizar os Serviços de Domínio do Active Directory (AD DS) local com seu locatário do Azure AD    | Aproveite seu provedor de identidade local para contas de usuário, grupos e outros objetos. | Microsoft 365 E3 ou E5 |
| MFA imposta com padrões de segurança   | Proteja-se contra os dispositivos e identidades comprometidos exigindo uma segunda forma de autenticação para as entradas. O padrão de segurança exige MFA para todas as contas de usuário.   | Microsoft 365 E3 ou E5 |
| MFA imposta com Acesso Condicional| Exigir MFA com base nos atributos da entrada com políticas de Acesso Condicional.    | Microsoft 365 E3 ou E5 | 
| MFA imposta com Acesso Condicional baseado em risco   | Exija MFA com base no risco de o usuário entrar no Microsoft Defender para Identidade. | Microsoft 365 E5 ou E3 com as licenças do Azure AD Premium P2 | 
| Redefinição de Senha por autoatendimento (SSPR)    | Permita que os usuários redefinam ou desbloqueiem suas contas ou senhas.  | Microsoft 365 E3 ou E5 |
||||

### <a name="migration"></a>Migração

| Capcidade ou recurso | Descrição | Licenças |
|:-------|:-----|:-------|
| Migrar para o Windows 10 | Migre seus dispositivos que executem o Windows 7 ou o Windows 8.1 para o Windows 10 Enterprise. | Licenças do Windows 10 Enterprise incluídas no Microsoft 365 E3 ou E5 | 
| Migrar para o Microsoft 365 Apps para empresas | Migre seus aplicativos cliente do Office, como Word e PowerPoint, para as versões instaladas da nuvem que são atualizadas com novos recursos. | Microsoft 365 E3 ou E5 | 
| Migrar dados e servidores locais para o Microsoft 365 | Migre suas caixas de correio do Exchange, sites do SharePoint e Skype for Business Online para os serviços de nuvem do Microsoft 365. | Microsoft 365 E3 ou E5 | 
||||

### <a name="device-and-app-management"></a>Gerenciamento de aplicativo e dispositivo

| Capcidade ou recurso | Descrição | Licenças |
|:-------|:-----|:-------|
| Microsoft Intune | Um serviço baseado em nuvem que fornece gerenciamento de dispositivo móvel (MDM) e gerenciamento de aplicativo móvel (MAM) para controlar como o aplicativo da sua organização e os dispositivos são usados, incluindo celulares, tablets e laptops. | Microsoft 365 E3 ou E5 | 
| Mobilidade e Segurança Básica | Proteja e gerencie os dispositivos móveis dos usuários, como iPhones, iPads, Androids e telefones Windows com esse serviço integrado.  | Microsoft 365 E3 ou E5 | 
||||

## <a name="next-steps"></a>Próximas etapas

Use estas etapas para configurar e gerenciar seus locatários do Microsoft 365.

1. [Determinar seus locatários](tenant-management-tenants.md)
2. [Otimizar sua rede](tenant-management-networking.md)
3. [Sincronizar suas identidades e impor logins seguros](tenant-management-identity.md)
4. [Migrar seus dados e servidores do Office locais](tenant-management-migration.md)
5. [Implantar o gerenciamento de dispositivos e aplicativos](tenant-management-device-management.md)

[![As etapas para implantar e gerenciar um locatário do Microsoft 365](../media/tenant-management-overview/tenant-management-step-grid.png)](tenant-management-tenants.md)

Cada etapa descreve as opções de implantação, resume os resultados e tarefas contínuas de manutenção.

Para entender como uma organização multinacional fictícia, mas representativa, implantou os elementos de seu locatário do Microsoft 365, consulte o estudo de caso [da Contoso.](../enterprise/contoso-case-study.md)
