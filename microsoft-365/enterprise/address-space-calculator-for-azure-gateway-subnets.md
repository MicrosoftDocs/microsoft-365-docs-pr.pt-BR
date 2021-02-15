---
title: Calculadora de espaço de endereço para sub-redes de gateway do Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/07/2021
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
description: 'Resumo: Calcule o espaço de endereço de uma sub-rede de gateway do Azure com C3, Python ou PowerShell.'
ms.openlocfilehash: d92bea5c36fde6277154d19365ed0bdaa5df4254
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780563"
---
# <a name="address-space-calculator-for-azure-gateway-subnets"></a><span data-ttu-id="da564-103">Calculadora de espaço de endereço para sub-redes de gateway do Azure</span><span class="sxs-lookup"><span data-stu-id="da564-103">Address space calculator for Azure gateway subnets</span></span>

<span data-ttu-id="da564-104">Uma rede virtual (VNet) nos serviços de infraestrutura do Azure que está conectada a outras redes deve ter uma sub-rede de gateway.</span><span class="sxs-lookup"><span data-stu-id="da564-104">A virtual network (VNet) in Azure infrastructure services that is connected to other networks must have a gateway subnet.</span></span> <span data-ttu-id="da564-105">As práticas recomendadas para definir a sub-rede do gateway são:</span><span class="sxs-lookup"><span data-stu-id="da564-105">The best practices for defining the gateway subnet are:</span></span>

- <span data-ttu-id="da564-106">O comprimento do prefixo da sub-rede do gateway pode ter um comprimento máximo de prefixo de 29 (por exemplo, 10.119.255.248/29), mas a recomendação atual é que você use um comprimento de prefixo de 27 (por exemplo, 10.119.255.224/27).</span><span class="sxs-lookup"><span data-stu-id="da564-106">The prefix length of the gateway subnet can have a maximum prefix length of 29 (for example, 10.119.255.248/29), but the current recommendation is that you use a prefix length of 27 (for example, 10.119.255.224/27).</span></span>
- <span data-ttu-id="da564-107">Ao definir o espaço de endereço da sub-rede do gateway, use a última parte do espaço de endereço VNet.</span><span class="sxs-lookup"><span data-stu-id="da564-107">When defining the address space of the gateway subnet, use the last part of the VNet address space.</span></span>

<span data-ttu-id="da564-108">Para a segunda recomendação, você pode determinar o espaço de endereço da sub-rede do gateway definindo os bits usados para a sub-rede do gateway como 0 e os bits restantes no espaço de endereço VNet como 1.</span><span class="sxs-lookup"><span data-stu-id="da564-108">For the second recommendation, you can determine the address space of the gateway subnet by setting the bits used for the gateway subnet to 0 and the remaining bits in the VNet address space to 1.</span></span> <span data-ttu-id="da564-109">Para calcular rapidamente o espaço de endereço da sub-rede do gateway sem precisar ser convertido em binário e de volta para decimal, você pode usar um aplicativo de console escrito em C# ou Python ou com um bloco de comandos do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da564-109">To quickly calculate the gateway subnet address space without having to convert to binary and back to decimal, you can use a console application written in C# or Python or with a PowerShell command block.</span></span>

<span data-ttu-id="da564-110">Este artigo contém blocos de código C#, Python e PowerShell que calculam o espaço de endereço da sub-rede do gateway com base nos valores de w.x.y.z/n para o prefixo de endereço VNet e o comprimento do prefixo da sub-rede do gateway.</span><span class="sxs-lookup"><span data-stu-id="da564-110">This article contains C#, Python, and PowerShell code blocks that calculate the gateway subnet address space based on the values of w.x.y.z/n for the VNet address prefix and the gateway subnet prefix length.</span></span>

## <a name="c-code-block"></a><span data-ttu-id="da564-111">Bloco de código C#</span><span class="sxs-lookup"><span data-stu-id="da564-111">C# code block</span></span>

<span data-ttu-id="da564-112">Use esse bloco de código para criar um aplicativo de console em C#.</span><span class="sxs-lookup"><span data-stu-id="da564-112">Use this code block to create a console app in C#.</span></span>

```c#
using System; 
using System.Collections.Generic; 
using System.Linq; 
using System.Text; 
using System.Threading.Tasks; 
 
namespace ConsoleApplication1 
{ 
    class Program 
    { 
        static void Main(string[] args) 
        { 
            // Declare variables. 
            const long wOctet = 16777216;  
            const long xOctet = 65536; 
            const long yOctet = 256; 
            double D; 
            int w, x, y, z, vnetPrefLen, gwPrefLen; 
            long d, w2, x2, y2, z2; 
             
 
            // Get the five values needed from the keyboard. 
            Console.WriteLine("**************************************************************************"); 
            Console.WriteLine("**_ Gateway subnet address space calculator for Azure virtual networks _*_");             
            Console.WriteLine("_*************************************************************************");  
            Console.WriteLine(); 
            Console.WriteLine("Please supply your virtual network address space in the form of w.x.y.z/n."); 
            Console.WriteLine(); 
            Console.WriteLine("w="); 
            w = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("x="); 
            x = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("y="); 
            y = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("z="); 
            z = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("n="); 
            vnetPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
            Console.WriteLine("Now supply the prefix length of your gateway subnet:"); 
            gwPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
 
            // Perform the calculation. 
            D = w * wOctet + x * xOctet + y * yOctet + z; 
            for (int i = vnetPrefLen + 1; i < gwPrefLen + 1; i++) 
            { 
                D = D + Math.Pow(2, 32 - i); 
            } 
            d = Convert.ToInt64(D); 
            w2 = d / wOctet; 
            x2 = (d - w2 * wOctet) / xOctet;  
            y2 = (d - w2 * wOctet - x2 * xOctet) / yOctet; 
            z2 = d - w2 * wOctet - x2 * xOctet - y2 * yOctet; 
             
            // Display the result.             
            Console.WriteLine("**************************************************************************");  
            Console.WriteLine("For the Azure virtual address space {0}.{1}.{2}.{3}/{4}", w, x, y, z, vnetPrefLen); 
            Console.WriteLine("and gateway prefix length of {0}, the gateway subnet address space is:", gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("{0}.{1}.{2}.{3}/{4}", w2, x2, y2, z2, gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("Press ENTER to quit."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## <a name="python-code-block"></a><span data-ttu-id="da564-113">Bloco de código python</span><span class="sxs-lookup"><span data-stu-id="da564-113">Python code block</span></span>

<span data-ttu-id="da564-114">Use esse bloco de código para criar um aplicativo de console no Python.</span><span class="sxs-lookup"><span data-stu-id="da564-114">Use this code block to create a console app in Python.</span></span>

```python
import math 
# Collect the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet 
print("**************************************************************************")  
print("**_ Gateway subnet address space calculator for Azure virtual networks _*_")  
print("_*************************************************************************\n")   
print("Please supply your virtual network address space in the form of w.x.y.z/n.");  
w=int(input("w = ")) 
x=int(input("x = ")) 
y=int(input("y = ")) 
z=int(input("z = ")) 
n=int(input("n = ")) 
print("")  
g=int(input("Now supply the prefix length of your gateway subnet: ")) 
print("")  
 
# Calculate  
wOctet = 16777216  
xOctet = 65536  
yOctet = 256  
D = w * wOctet + x * xOctet + y * yOctet + z 
for index in range(n + 1,g + 1): 
    D += 2**(32 - index)  
 
w2 = math.floor(D / wOctet)  
x2 = math.floor((D - w2 * wOctet) / xOctet) 
y2 = math.floor((D - w2 * wOctet - x2 * xOctet) / yOctet) 
z2 = D - w2 * wOctet - x2 * xOctet - y2 * yOctet  
 
# Display the result  
gwAddrPref= "Your gateway address prefix is: " + str(w2) + "." + str(x2) + "." + str(y2) + "." + str(z2) + "/" + str(g)  
print(gwAddrPref) 
```


## <a name="powershell-command-block"></a><span data-ttu-id="da564-115">Bloco de comandos do PowerShell</span><span class="sxs-lookup"><span data-stu-id="da564-115">PowerShell command block</span></span>

<span data-ttu-id="da564-116">Preencha os valores e execute o bloco de comando resultante em uma janela do PowerShell ou no ISE (Ambiente de Script Integrado) do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="da564-116">Fill in the values and run the resulting command block in a PowerShell window or in the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
# Specify the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet: 
$w= 
$x= 
$y= 
$z= 
$n= 
$g= 
# Calculate 
$wOctet = 16777216 
$xOctet = 65536 
$yOctet = 256 
[long]$D = $w * $wOctet + $x * $xOctet + $y * $yOctet + $z; 
for ($i = $n + 1; $i -lt $g + 1; $i++) 
{ 
$D = $D + [math]::pow(2, 32 - $i) 
} 
$w2 = [math]::floor($D / $wOctet) 
$x2 = [math]::floor( ($D - $w2 * $wOctet) / $xOctet ) 
$y2 = [math]::floor( ($D - $w2 * $wOctet - $x2 * $xOctet) / $yOctet ) 
$z2 = $D - $w2 * $wOctet - $x2 * $xOctet - $y2 * $yOctet 
# Display the result 
$dx= [string]$w2 + "." + [string]$x2 + "." + [string]$y2 + "." + [string]$z2 + "/" + [string]$g 
Write-Host "Your gateway address prefix is: " $dx
```
    
## <a name="related-topics"></a><span data-ttu-id="da564-117">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="da564-117">Related topics</span></span>

[<span data-ttu-id="da564-118">Gerenciar o Microsoft 365 com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="da564-118">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)