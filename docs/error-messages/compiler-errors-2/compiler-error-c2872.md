---
title: "컴파일러 오류 c&2872; | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: d53dbd9429ba3c1a525b85a3ef9f2e70152ddfa2
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2872"></a>컴파일러 오류 C2872
'symbol': 모호한 기호  
  
컴파일러는 참조 하는 기호를 확인할 수 없습니다.  
  
C&2872; 헤더 파일을 포함 하는 경우에 발생할 수 있습니다는 [지시문을 사용 하 여](../../cpp/namespaces-cpp.md#using_directives), 이후의 헤더 파일은 포함 되어 있으며에 지정 된 네임 스페이스에도 사용 되는 형식을 포함 하 고는 `using` 지시문입니다. 지정 된 `using` 헤더 파일 지정 하는 모든 후에 지시문 `#include`합니다.  
  
 C 2872에 대 한 자세한 내용은 기술 자료 문서를 참조 하십시오. [PRB: 컴파일러 오류 수를 사용 하 여 #import Visual c + +.NET에서의 XML](http://support.microsoft.com/kb/316317) 및 ["오류 c 2872: '플랫폼': 모호한 기호" Windows::Foundation::Metadata 네임 스페이스를 사용 하 여 Visual Studio 2013의 경우 오류 메시지](https://support.microsoft.com/kb/2890859)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 c&2872; 오류가 생성 됩니다.  
  
```cpp  
// C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok  
   A::i++;   // ok  
   i++;   // C2872 ::i or A::i?  
}  
```
