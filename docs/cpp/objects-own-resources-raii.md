---
title: 개체가 리소스 소유 (RAII) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 265eccc4c1a9f51a03e5a84433a9f7e9cc6d6a92
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402138"
---
# <a name="objects-own-resources-raii"></a>개체가 리소스 소유(RAII)
고유한 리소스 개체는 있는지 확인 합니다. 이 원칙은 라고도 하며 "resource acquisition is 초기화" 또는 "RAII."  
  
## <a name="example"></a>예제  
 생성자 인수로 (거의 항상 unique_ptr) 소유 하는 다른 명명 된 개체에 "새" 모든 개체를 전달 합니다.  
  
```cpp  
void f() {  
    unique_ptr<widget> p( new widget() );  
    my_class x( new widget() );  
    // ...  
} // automatic destruction and deallocation for both widget objects  
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"  
```  
  
 소유 하는 다른 개체에 새 리소스를 항상 즉시 전달 합니다.  
  
```cpp  
void g() {  
    other_class y( OpenFile() );  
    // ...  
} // automatic closing and release for file resource  
  // automatic exception safety, as if "finally { y.file.dispose(); }"  
```  
  
## <a name="see-also"></a>참고자료  
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)