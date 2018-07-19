---
title: 컴파일러 오류 C2140 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2140
dev_langs:
- C++
helpviewer_keywords:
- C2140
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1634e2a61ed9ee22bdfde619f8710226b74e48a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169688"
---
# <a name="compiler-error-c2140"></a>컴파일러 오류 C2140
'type': 제네릭 형식 매개 변수에 종속 되는 형식의 컴파일러 내장 형식 특성 '특성'에 대 한 인수로 사용할 수 없습니다  
  
 잘못 된 유형 지정자는 형식 특성에 전달 되었습니다.  
  
 자세한 내용은 참조 [형식 특성에 대 한 컴파일러 지원](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2140 오류가 발생 합니다.  
  
```  
// C2140.cpp  
// compile with: /clr /c  
template <class T>  
  
struct is_polymorphic {  
   static const bool value = __is_polymorphic(T);  
};  
  
class x {};  
  
generic <class T>  
ref class C {  
   void f() {  
      System::Console::WriteLine(__is_polymorphic(T));   // C2140  
      System::Console::WriteLine(is_polymorphic<T>::value);   // C2140  
  
      System::Console::WriteLine(__is_polymorphic(x));   // OK  
      System::Console::WriteLine(is_polymorphic<x>::value);   // OK  
   }  
};  
```