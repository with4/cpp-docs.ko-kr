---
title: 컴파일러 오류 C3533 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: faaf53d08512559b86c95148bc93e7b3367d2b01
ms.sourcegitcommit: 3bb7c1c0ceeb8012418e2fff9ae5a7db0fff3877
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34458916"
---
# <a name="compiler-error-c3533"></a>컴파일러 오류 C3533
'type': 매개 변수는 'auto' 포함 하는 형식을 가질 수 없습니다  
  
 메서드 또는 템플릿 매개 변수를 선언할 수 없습니다는 `auto` 키워드 경우 기본 [/zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션을 적용 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  제거는 `auto` 매개 변수 선언에서 키워드입니다.  
  
## <a name="example"></a>예제  
 함수 매개 변수를 선언 하므로 다음 예제에서는 생성 C3533는 `auto` 키워드와 것은으로 컴파일된 **/zc: auto**합니다.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j) {} // C3533  
```  
  
## <a name="example"></a>예제  
 다음 예제는 템플릿 매개 변수를 선언 하므로 C + + 14 모드에서 C3533 생성는 `auto` 키워드와 것은으로 컴파일된 **/zc: auto**합니다. (C + + 17,이 유효한 템플릿 정의의 클래스 형식이 추론 됩니다 단일 비형식 템플릿 매개 변수를 사용 합니다.)
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C {}; // C3533  
```  
  
## <a name="see-also"></a>참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)   
 [/Zc:auto(변수 형식 추론)](../../build/reference/zc-auto-deduce-variable-type.md)
