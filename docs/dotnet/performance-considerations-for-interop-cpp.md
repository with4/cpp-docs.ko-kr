---
title: Interop (c + +)에 대 한 성능 고려 사항 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- /clr compiler option [C++], interop performance considerations
- platform invoke [C++], interoperability
- interop [C++], performance consideraitons
- mixed assemblies [C++], performance considerations
- interoperability [C++], performance considerations
ms.assetid: bb9a282e-c3f8-40eb-a2fa-45d80d578932
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9223c52e4ef831a9a1ff657db1a0d7859dd6ce6c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="performance-considerations-for-interop-c"></a>Interop에 대한 성능 고려 사항(C++)
이 항목에서는 관리 되 는/관리 되지 않는 interop 전환이 런타임 성능에 영향을 줄이기 위한 지침을 제공 합니다.  
  
 Visual c + +에서는 Visual Basic 및 C# P/Invoke (), 같은 다른.NET 언어와 동일한 상호 운용성 메커니즘을 지원 하지만 Visual c + + (c + + interop) 관련 된 interop 지원 기능을 제공 합니다. 성능이 중요 한 응용 프로그램은 interop 각 기술의 성능에 미치는 영향을 이해 하는 것이 중요 합니다.  
  
 Interop 기술을 사용 썽크를 호출 하는 특별 한 전환 시퀀스가 필요한에 관계 없이 관리 되는 함수는 관리 되지 않는 함수 그 반대의 경우도 마찬가지를 호출할 때마다 합니다. 이 썽크는 Visual c + + 컴파일러에서 자동으로 삽입 있지만 이러한 전환과 누적 되므로 성능이 저하 될 수 있다는 점을 염두에 중요 합니다.  
  
## <a name="reducing-transitions"></a>전환 줄이기  
 방지 하거나 interop 썽크의 비용을 줄일 가지 방법은 관리 되 는/관리 되지 않는 전이 최소화 하기 위해 관련 된 인터페이스를 리팩터링 하는 것입니다. 수 다 스러운 인터페이스는 관리 되 는/관리 되지 않는 경계를 넘어 자주 호출을 포함 하는 대상으로 하 여 성능을 크게 향상을 만들 수 있습니다. 예를 들어, 루프에서 관리 되지 않는 함수를 호출 하는 관리 되는 함수 리팩터링에 대 한 좋은 후보를입니다. 루프 자체 관리 되지 않는 쪽으로 이동 또는 관리 되지 않는 호출을 만들 경우 관리 되는 대신 사용할 수 있는 경우 (아마도 관리 되는 쪽에서 데이터를 큐를 대기 하 고 다음 루프 후 한 번에 관리 되지 않는 API에 마샬링), 전환 수 감소 기호 ificantly 합니다.  
  
## <a name="pinvoke-vs-c-interop"></a>P/Invoke vs입니다. C++ Interop  
 Visual Basic 및 C# 같은.NET 언어에 대 한 기본 구성 요소와의 상호 운용 앞에서 설명한 방법 P/Invoke 됩니다. P/Invoke는.NET Framework에서 지원 되므로 Visual c + +도 지원 하지만 Visual c + + c + + Interop 라고 하는 자체 상호 운용성 지원을 제공 합니다. C + + Interop은 것이 좋습니다 P/Invoke를 통해 P/Invoke 형식 안전 하지 않습니다. 결과적으로, 실행 시 오류가 보고 주로 c + + Interop 뿐만 아니라 있습니다 P/Invoke를 통해 성능상의 이점이 있습니다.  
  
 두 가지 방법을 모두 여러 단계를 관리 되는 함수는 관리 되지 않는 함수를 호출할 때마다이 필요 합니다.  
  
-   네이티브 형식으로 CLR에서 함수 호출 인수가 마샬링됩니다.  
  
-   관리 되는-관리 썽크 실행 됩니다.  
  
-   관리 되지 않는 함수 (기본 버전의 인수를 사용 하 여) 라고 합니다.  
  
-   관리 되지 않는 리소스에서 관리로 썽크 실행 됩니다.  
  
-   반환 형식 및 "out" 또는 "에, out" 인수는 CLR 형식으로 네이티브 코드에서 마샬링됩니다.  
  
 관리 되 는/관리 되지 않는 썽크 interop 전혀 작동 필요 하지만 필요한 데이터 마샬링을 관련 된 데이터 형식, 함수 서명 및 데이터 사용 방법에 따라 다릅니다.  
  
 가장 간단한 형태는 c + + Interop를 수행한 데이터 마샬링을: 매개 변수는 비트 방식에서 관리 되 는/관리 되지 않는 경계를 넘어 복사 됩니다 변환이 전혀 수행 됩니다. P/Invoke에 대 한 경우에 모든 매개 변수는 단순, blittable 형식입니다. P/Invoke에서 관리 되는 각 매개 변수에 해당 네이티브 형식으로 변환할 매우 강력 단계를 수행 하는 그렇지 않은 경우 인수는 "out"로 표시 하는 경우에 그 반대로 또는 "에, out"입니다.  
  
 즉, c + + Interop P/Invoke 가장 강력한 방법을 사용 하는 반면 데이터 마샬링을의 가장 빠른 가능한 메서드를 사용 합니다. 즉, c + + Interop (한 시간 내에 c + +에 대 한 일반적인) 기본적으로 최적의 성능을 제공 프로그래머는이 동작이 없는 경우 안전 하거나 적절 한 주소를 지정 하는 일을 담당 합니다.  
  
 따라서 c + + Interop 있어야 데이터 마샬링을 제공 해야 명시적으로 하지만 장점은 프로그래머가 무료 제공 되는 데이터의 특성을 적절 한 란 무엇이 고 사용 하는 방법 결정 된다는 점입니다. 또한 P/Invoke 데이터 마샬링 동작 수를 수정할 수도 있지만에 어느 정도에 맞게 사용자 지정 c + + Interop 데이터를 마샬링 호출 별로 별로 사용자 지정할 수 있습니다. P/Invoke 불가능 아닙니다.  
  
 C + + Interop에 대 한 자세한 내용은 참조 [c + + Interop를 사용 하 여 (암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [혼합형(네이티브 및 관리) 어셈블리](../dotnet/mixed-native-and-managed-assemblies.md)