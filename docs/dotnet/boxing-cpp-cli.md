---
title: Boxing (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3b9898b4a640d2f3aa4e38ceb621521ffb301fed
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105893"
---
# <a name="boxing-ccli"></a>Boxing(C++/CLI)
Boxing은 값 형식을 형식으로 변환 하는 프로세스 `object` 또는 값 형식에 의해 구현 된 임의의 인터페이스 형식으로. 공용 언어 런타임 (CLR) 값 형식 상자에 값 옵니다는 `System.Object` 하 고 관리 되는 힙에 저장 합니다. unboxing하면 개체에서 값 형식이 추출됩니다. Boxing은 암시적이며 unboxing은 명시적입니다.  
  
## <a name="related-articles"></a>관련 문서  
  
|제목|설명|  
|-----------|-----------------|  
|[방법: 명시적으로 boxing 요청](../dotnet/how-to-explicitly-request-boxing.md)|변수에 대 한 boxing을 명시적으로 요청 하는 방법을 설명 합니다.|  
|[방법: gcnew를 사용하여 값 형식 만들기 및 암시적 boxing 사용](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|사용 하는 방법을 보여 줍니다. `gcnew` boxed 값 형식인 관리 되 고, 가비지 수집 힙에 배치할 수 있는 키를 만들려고 합니다.|  
|[방법: Unbox](../dotnet/how-to-unbox.md)|Unbox 값을 수정 하는 방법을 보여 줍니다.|  
|[표준 변환 및 암시적 boxing](../dotnet/standard-conversions-and-implicit-boxing.md)|Boxing을 필요로 하는 변환을 통해 컴파일러에서 표준 변환이 선택 했는지 보여 줍니다.|  
|[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|Visual C++ 설명서에서 .NET 프로그래밍을 위한 최상위 문서입니다.|