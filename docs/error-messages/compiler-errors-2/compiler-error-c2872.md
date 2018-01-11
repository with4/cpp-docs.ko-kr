---
title: "컴파일러 오류 C2872 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2872
dev_langs: C++
helpviewer_keywords: C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 88d770823efdad4f58431f20b5685dfbb6bfec3b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2872"></a>컴파일러 오류 C2872
'*기호*': 모호한 기호  
  
컴파일러가 참조 하는 기호를 확인할 수 없습니다. 범위에서 지정한 이름 가진 둘 이상의 기호를 합니다. 컴파일러에서 검색 모호한 기호에 대 한 다음과 같은 오류 메시지가 파일 위치 및 선언에 대 한 메모를 참조 하세요. 이 문제를 해결 하려면 수을 정규화 하면 모호한 기호 네임 스페이스, 예를 들어,를 사용 하 여 `std::byte` 또는 `::byte`합니다. 사용할 수도 있습니다는 [네임 스페이스 별칭](../../cpp/namespaces-cpp.md#namespace_aliases) 소스 코드에서 기호를 명확히 구분 하는 경우 포함된 된 네임 스페이스를 사용 하기 위해 편리한 짧은 이름을 지정 합니다.  
  
C2872 헤더 파일을 포함 하는 경우 발생할 수 있습니다는 [지시문을 사용 하 여](../../cpp/namespaces-cpp.md#using_directives), 후속 헤더 파일을 포함 하 고에 지정 된 네임 스페이스에도 사용 되는 형식을 포함 하는 `using` 지시문입니다. 지정 된 `using` 헤더 파일을 지정할 때 사용 하는 모든 후에 지시문 `#include`합니다.  
  
 C2872에 대 한 자세한 내용은 기술 자료 문서를 참조 하십시오. [PRB: 컴파일러 오류 때 하면 XML에서 사용 #import Visual c + +.net에서](http://support.microsoft.com/kb/316317) 및 ["오류 C2872: 'Platform': 모호한 기호" 사용 하는 경우 오류 메시지는 Visual Studio 2013에서 Windows::Foundation::Metadata 네임 스페이스](https://support.microsoft.com/kb/2890859)합니다.  
  
## <a name="example"></a>예  
 라는 변수가 모호한 참조 되기 때문에 다음 샘플에서는 C2872, `i`두; 이름이 같은 변수는 범위에:  
  
```cpp  
// C2872.cpp  
// compile with: cl /EHsc C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok, uses i from global namespace  
   A::i++;   // ok, uses i from namespace A  
   i++;   // C2872 ambiguous: ::i or A::i? 
   // To fix this issue, use the fully qualified name
   // for the intended variable. 
}  
```