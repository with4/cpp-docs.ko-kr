---
title: "컴파일러 오류 C3533 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e7bcd9c710ac5cdd50b966a72291918459d984be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3533"></a>컴파일러 오류 C3533
'type': 매개 변수는 'auto' 포함 하는 형식을 가질 수 없습니다  
  
 메서드 또는 템플릿 매개 변수를 선언할 수 없습니다는 `auto` 키워드 경우 기본 [/zc: auto](../../build/reference/zc-auto-deduce-variable-type.md) 컴파일러 옵션을 적용 합니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  제거는 `auto` 매개 변수 선언에서 키워드입니다.  
  
## <a name="example"></a>예  
 함수 매개 변수를 선언 하므로 다음 예제에서는 생성 C3535는 `auto` 키워드와 것은으로 컴파일된 **/zc: auto**합니다.  
  
```  
// C3533a.cpp  
// Compile with /Zc:auto  
void f(auto j){} // C3533  
```  
  
## <a name="example"></a>예  
 다음 예제는 템플릿 매개 변수를 선언 하므로 C3535 생성는 `auto` 키워드와 것은으로 컴파일된 **/zc: auto**합니다.  
  
```  
// C3533b.cpp  
// Compile with /Zc:auto  
template<auto T> class C{}; // C3533  
```  
  
## <a name="see-also"></a>참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)   
 [/Zc: auto (변수 형식 추론)](../../build/reference/zc-auto-deduce-variable-type.md)