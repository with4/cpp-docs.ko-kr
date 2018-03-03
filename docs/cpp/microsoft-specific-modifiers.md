---
title: "Microsoft 전용 한정자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f9533ffc2d21c3e8ee006fc97f7c61f4cb41115
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="microsoft-specific-modifiers"></a>Microsoft 전용 한정자
이 단원에서는 다음 영역의 Microsoft 전용 C++ 확장에 대해 설명합니다.  
  
-   [기반 주소 지정](../cpp/based-addressing.md), 다른 포인터가 오프셋 될 수 있는 기준으로 포인터를 사용 하는 방법  
  
-   [함수 호출 규칙](../cpp/calling-conventions.md)  
  
-   확장 저장소 클래스 특성을 사용 하 여 선언 된 [__declspec](../cpp/declspec.md) 키워드  
  
-   [__w64](../cpp/w64.md) 키워드  
  
 Microsoft 전용 키워드 중 대다수는 파생 형식을 형성하는 선언자를 수정하는 데 사용될 수 있습니다. 선언 자에 대 한 자세한 내용은 참조 [선언 자](http://msdn.microsoft.com/en-us/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838)합니다.  
  
### <a name="microsoft-specific-keywords"></a>Microsoft 전용 키워드  
  
|키워드|의미|파생 형식을 만드는 데 사용됩니까?|  
|-------------|-------------|---------------------------------|  
|[__based](../cpp/based-grammar.md)|뒤에 오는 이름이 32비트 오프셋을 선언에 포함된 32비트 기준으로 선언합니다.|예|  
|[__cdecl](../cpp/cdecl.md)|뒤에 오는 이름이 C 명명 및 호출 규칙을 사용합니다.|예|  
|[__declspec](../cpp/declspec.md)|뒤에 오는 이름이 Microsoft 전용 저장소 클래스 특성을 지정합니다.|아니요|  
|[__fastcall](../cpp/fastcall.md)|뒤에 오는 이름이 인수 전달 시 가능하면 스택 대신 레지스터를 사용하는 함수를 선언합니다.|예|  
|[__restrict](../cpp/extension-restrict.md)|__Declspec 비슷합니다 ([제한](../cpp/restrict.md)), 하지만 변수에서 사용 합니다.|아니요|  
|[__stdcall](../cpp/stdcall.md)|뒤에 오는 이름이 표준 호출 규칙을 준수하는 함수를 지정합니다.|예|  
|[__w64](../cpp/w64.md)|64비트 컴파일러에서 더 큰 형식으로 데이터 형식을 표시합니다.|아니요|  
|[__unaligned](../cpp/unaligned.md)|형식 또는 다른 데이터의 포인터가 정렬되지 않음을 지정합니다.|아니요|  
|[__vectorcall](../cpp/vectorcall.md)|뒤에 오는 이름이 인수 전달 시 가능하면 스택 대신 SSE 레지스터 등의 레지스터를 사용하는 함수를 선언합니다.|예|  
  
## <a name="see-also"></a>참고 항목  
 [C++ 언어 참조](../cpp/cpp-language-reference.md)