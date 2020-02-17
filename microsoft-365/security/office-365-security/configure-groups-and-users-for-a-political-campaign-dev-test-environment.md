---
title: Defina grupos e usuários para um ambiente de desenvolvimento/teste de uma campanha política
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: 'Resumo: Crie assinaturas de teste do Office 365 e Enterprise Mobility + Security (EMS) com usuários e grupos para um ambiente de desenvolvimento/teste de campanha política.'
ms.openlocfilehash: a61cc21b67cafd213d47076698929d0aa2644d08
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083480"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a>Defina grupos e usuários para um ambiente de desenvolvimento/teste de uma campanha política

 **Resumo:** Crie assinaturas de teste do Office 365 e Enterprise Mobility + Security (EMS) com usuários e grupos para um ambiente de desenvolvimento/teste de campanha política.

Use as instruções deste artigo para criar um ambiente de desenvolvimento/de teste que inclui grupos e contas de usuário simplificadas para a solução [Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md).

## <a name="phase-1-create-your-office-365-devtest-environment"></a>Fase 1: Criar seu ambiente de desenvolvimento/teste do Office 365

Nesta fase, você deve obter assinaturas de avaliação do Office 365 E5 e do Enterprise Mobility + Security (EMS) E5 para uma organização fictícia que representa uma campanha política.

Primeiro, siga as instruções na **Fase 2** do [ambiente de desenvolvimento/de teste do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).

Em seguida, inscreva-se para a assinatura de avaliação do EMS E5 e adicione-a à mesma organização de sua assinatura de avaliação do Office 365.

1. Se necessário, entre no centro de administração com as credenciais da conta do administrador global da sua assinatura de avaliação. Para obter ajuda, confira [Como entrar no Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Clique no bloco de **Administração**.

3. Na guia **centro de administração do Microsoft 365** em seu navegador, na navegação à esquerda, clique em **Cobrança > Comprar serviços**.

4. Na página **Comprar serviços**, encontre o item **Enterprise Mobility + Security E5**. Passe o ponteiro do mouse sobre ele e clique em **Iniciar avaliação gratuita**.

5. Na página **Confirmar seu pedido**, clique em **Experimentar agora**.

6. Na página **Recibo do pedido**, clique em **Continuar**.

Em seguida, habilite a licença do EMS E5 para a sua conta de administrador global.

1. Na guia **centro de administração do Microsoft 365** no navegador, na navegação à esquerda, clique em **Usuários > Usuários ativos**.

2. Clique em sua conta de administrador global e, em seguida, clique em **Editar** para **Licenças de produto**.

3. No painel **Licenças de produto**, mude a licença de produto de **Enterprise Mobility + Security E5** para **Ativada**, clique em **Salvar** e clique em **Fechar** duas vezes.

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a>Fase 2: Criar e configurar seus grupos do Azure Active Directory (AD) (Active Directory)

Nesta fase, você cria e configura os grupos do Azure AD para a sua empresa.

Primeiro, crie um conjunto de grupos para uma campanha política com o Portal do Azure.

1. Em uma guia separada no navegador, vá ao Portal do Azure em [https://portal.azure.com](https://portal.azure.com). Se necessário, entre com as credenciais da conta de administrador global da sua assinatura de avaliação do Office 365 E5.

2. No Portal do Azure, clique em **Azure Active Directory > Usuários e grupos > Todos os grupos**.

3. Siga as seguintes etapas para cada nome do grupo nesta lista:

   - Equipe estratégica e sênior

   - Equipe de TI

   - Equipe de análise

   - Equipe principal regular

   - Equipe de operações

   - Equipe de campo

1. Na folha **Todos os grupos**, clique em **+ Novo grupo**.

2. Digite o nome do grupo na lista em **Nome**.

3. Selecione **Usuário dinâmico** em **Associação**.

4. Selecione **Sim** para **Habilitar recursos do Office**.

5. Clique em **Adicionar consulta dinâmica**.

6. Em **Adicionar usuários onde**, selecione **departamento**.

7. No campo seguinte, selecione **Igual a**.

8. No campo seguinte, digite o nome do grupo na lista.

9. Clique em **Adicionar consulta** e, em seguida, clique em **Criar**.

10. Clique em **Usuários e grupos – Todos os grupos**.

Em seguida, configure os grupos para que os membros tenham licenças do Office 365 E5 e EMS E5 atribuídas automaticamente.

1. No Portal do Azure, clique em **Azure Active Directory > Licenças > Todos os produtos**.

2. Na lista, selecione **Enterprise Mobility + Security E5** e **Office 365 Enterprise E5** e clique em **Atribuir+**.

3. Na folha **Atribuir licença**, clique em **Usuários e grupos**.

4. Na lista de grupos, selecione o seguinte:

   - Equipe de análise

   - Equipe de campo

   - Equipe de TI

   - Equipe de operações

   - Equipe principal regular

   - Equipe estratégica e sênior

5. Clique em **Selecionar** e clique em **Atribuir**.

6. Feche a guia do Portal do Azure no navegador.

## <a name="phase-3-add-your-user-accounts"></a>Fase 3: Adicionar as suas conta de usuário

Nesta fase, adicione exemplos de contas de usuário para a sua campanha política.

Primeiro, conecte-se ao módulo [PowerShell do Azure Active Directory para Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).

Em seguida, preencha o nome de sua organização, o local e uma senha comum e, em seguida, execute esses comandos desde o prompt de comando do PowerShell ou Ambiente de Script Integrado (ISE):

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> O uso de uma senha comum aqui serve para a automação e a facilidade da configuração para um ambiente de desenvolvimento/de teste. Isso não é recomendável para assinaturas de produção. Ao entrar com cada uma dessas novas contas de usuário, você deverá alterar a senha.

Use estas etapas para verificar se a associação de grupo dinâmico e o licenciamento com base em grupo estão funcionando corretamente.

1. Na guia **Microsoft Office Home** do navegador, clique no bloco **Administração**.

2. Na nova guia **Centro de administração do Microsoft 365** do seu navegador, clique em **Usuários**.

3. Na lista de usuários, clique em **Candidato**.

4. No painel que lista as propriedades da conta de usuário **Candidato**, verifique se:

   - É um membro do grupo **Equipe estratégica e sênior** (em **Associações de grupo**).

   - Foram-lhe atribuídas as licenças do **Enterprise Mobility + Security E5** e do **Office 365 Enterprise E5** (nas **Licenças de produto**).

5. Feche o painel da conta de usuário do **Candidato**.

## <a name="record-values-for-future-reference"></a>Valores de registro para referência futura

Grave esses valores para trabalhar com as assinaturas de avaliação do Office 365 e do EMS para o ambiente de desenvolvimento/de teste:

- Nome da sua organização de assinatura de avaliação:  ![Sublinhado](../../media/Common-Images/TableLine.png)

  Por exemplo, para o nome de domínio de assinatura de avaliação contoso.onmicrosoft.com, o nome da organização é "contoso".

- O nome do administrador global do Office 365: ![Sublinhado](../../media/Common-Images/TableLine.png).onmicrosoft.com

  Grave a senha dessa conta e a senha inicial comum das outras contas de usuário em um local seguro.

## <a name="next-step"></a>Próxima etapa

Criar os quatro diferentes tipos de sites de equipe do SharePoint Online neste ambiente de desenvolvimento/de teste com [Criar sites de equipe em um ambiente de desenvolvimento/de teste de campanha política](create-team-sites-in-a-political-campaign-dev-test-environment.md).

## <a name="see-also"></a>Confira também

[Diretrizes de segurança da Microsoft para campanhas políticas, instituições sem fins lucrativos e outras organizações Agile](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[Criar sites de equipe em um ambiente de desenvolvimento/teste de campanha política](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[Guias do Laboratório de Teste (TLGs) para adoção de nuvem](https://docs.microsoft.com/office365/enterprise/cloud-adoption-test-lab-guides-tlgs)

[Adoção da nuvem e de soluções híbridas](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
