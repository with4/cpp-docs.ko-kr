---
title: "컴파일러 오류 C2813 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C2813
ms.assetid: 6cf2135f-7b82-42d1-909a-5e864308a09c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: fc5f5437751abf6bcb11299e8484a199275db970
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c2813"></a>컴파일러 오류 C2813
\#/MP와 가져오기가 지원 되지 않습니다.  
  
 C 2813 컴파일러 명령에서 지정 하는 경우에 내보내집니다는 **/MP** 컴파일러 옵션과 컴파일할 하나 이상의 파일에 두 개 이상의 파일에 포함 되어는[#import](../../preprocessor/hash-import-directive-cpp.md) 전처리기 지시문입니다. [#import](../../preprocessor/hash-import-directive-cpp.md) 지시문은 지정 된 형식 라이브러리의 형식에서 c + + 클래스를 생성 한 다음 두 개의 헤더 파일에 이러한 클래스를 씁니다. [#import](../../preprocessor/hash-import-directive-cpp.md) 지시문에는 동시에 동일한 헤더 파일에 쓰려고 할 때 해당 단위가 충돌 여러 컴파일 단위가 동일한 형식 라이브러리를 가져오는 경우 때문에 지원 되지 않습니다.  
  
 컴파일러 오류가 고 **/MP** 컴파일러 옵션은 2의 새로운 기능 [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)]합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2813을 생성합니다. "compile with:" 주석의 명령줄은 **/MP** 및 **/c** 컴파일러 옵션을 사용하여 여러 파일을 컴파일하도록 컴파일러에 알립니다. 파일 중 하나 이상 포함 된 [#import](../../preprocessor/hash-import-directive-cpp.md) 지시문입니다. 이 예제를 테스트하기 위해 동일한 파일을 두 번 사용합니다.  
  
```  
// C2813.cpp  
// compile with: /MP /c C2813.cpp C2813.cpp  
#import "C:\windows\system32\stdole2.tlb"   // C2813  
int main()   
{  
}  
```
