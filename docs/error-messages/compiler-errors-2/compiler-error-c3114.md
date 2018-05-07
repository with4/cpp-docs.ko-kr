---
title: 컴파일러 오류 C3114 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3114
dev_langs:
- C++
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69001d415167f976d0f30c2dd5a0181cc032d0d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3114"></a>컴파일러 오류 C3114
'argument': 잘못 명명 된 특성 인수입니다.  
  
 명명 된 인수는 유효한 특성 클래스 데이터 멤버를이 표시 되 면 안 `static`, `const`, 또는 `literal`합니다. 속성을 속성 되지 않아야 `static` 해야 get 및 set 접근자입니다.  
  
 자세한 내용은 참조 [속성](../../windows/property-cpp-component-extensions.md) 및 [사용자 정의 특성](../../windows/user-defined-attributes-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3114 오류가 발생 합니다.  
  
```  
// C3114.cpp  
// compile with: /clr /c  
public ref class A : System::Attribute {  
public:  
   static property int StaticProp {  
      int get();  
   }  
  
   property int Prop2 {  
      int get();  
      void set(int i);  
   }  
};  
  
[A(StaticProp=123)]   // C3114  
public ref class R {};  
  
[A(Prop2=123)]   // OK  
public ref class S {};  
```