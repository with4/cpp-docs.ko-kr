---
title: "(최신 c + +) 컴파일 시간 캡슐화에 대 한 Pimpl | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a109015f3d30b04eaf89e769e1265c49663599f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>컴파일 시간 캡슐화에 대한 Pimpl(최신 C++)
*pimpl 관용구* 은 최신 c + + 기술 구현, 결합, 최소화 하 고 분리 인터페이스를 숨기려면 합니다. Pimpl는 짧은 "포인터"를 구현 합니다. 이미 개념을 잘 알고 있어야 하지만 명칭 또는 컴파일러 방화벽 관용구와 같은 다른 이름으로 알 수 있습니다.  
  
## <a name="why-use-pimpl"></a>Pimpl를 사용 하는 이유는?  
 Pimpl 관용구 소프트웨어 개발 수명 주기를 개선할 수 있는 방법을 다음과 같습니다.  
  
-   컴파일 종속성 최소화 합니다.  
  
-   인터페이스와 구현을 분리 합니다.  
  
-   이식성 합니다.  
  
## <a name="pimpl-header"></a>Pimpl 헤더  
  
```cpp  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
  
```  
  
 Pimpl 관용구 다시 작성을 단계적 및 불안정 개체 레이아웃을 방지합니다. (전이적) 인기 있는 형식에 대 한 적합 합니다.  
  
## <a name="pimpl-implementation"></a>Pimpl 구현  
 정의 `impl` .cpp 파일에서 클래스입니다.  
  
```cpp  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## <a name="best-practices"></a>최선의 방법  
 Throw 되지 않는 스왑 특수화에 대 한 지원을 추가 하려면 사용할지 고려 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)