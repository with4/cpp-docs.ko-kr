---
title: 컴파일 시간 캡슐화 (최신 c + +)에 대 한 Pimpl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2e80c4bd86cd4c7400e3937fcb8d164fe6b14106
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404657"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>컴파일 시간 캡슐화에 대한 Pimpl(최신 C++)
합니다 *캡슐화 pimpl 관용구* 숨기기 결합을 최소화 하 고 분리 인터페이스를 구현 하는 최신 c + + 기술 됩니다. 캡슐화 Pimpl는 짧은 "포인터" 구현 합니다. 개념에 익숙할 수 있지만 명칭 또는 컴파일러 방화벽 관용구와 같은 다른 이름으로 알고 이미 있습니다.  
  
## <a name="why-use-pimpl"></a>캡슐화 pimpl를 사용 하는 이유는?  
 캡슐화 pimpl 관용구 소프트웨어 개발 수명 주기를 개선 하는 방법을 다음과 같습니다.  
  
-   컴파일 종속성 최소화 합니다.  
  
-   인터페이스와 구현을 분리 합니다.  
  
-   이식성입니다.  
  
## <a name="pimpl-header"></a>캡슐화 Pimpl 헤더  
  
```cpp  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
```  
  
 캡슐화 pimpl 관용구 rebuild 단계적 및 불안정 개체 레이아웃을 피할 수 있습니다. (전이적) 인기 있는 형식에 대 한 적합 합니다.  
  
## <a name="pimpl-implementation"></a>캡슐화 Pimpl 구현  
 정의 된 `impl` .cpp 파일에서 클래스입니다.  
  
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
 Throw 되지 않는 스왑 특수화에 대 한 지원을 추가할지 여부를 고려 합니다.  
  
## <a name="see-also"></a>참고자료  
 [C + +의 진화](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ 언어 참조](../cpp/cpp-language-reference.md)   
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)