---
title: "컴파일러 오류 C3114 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3114
dev_langs: C++
helpviewer_keywords: C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 509c0dd1d85187871e78cfa93a66bc4ef385bbb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3114"></a>컴파일러 오류 C3114
'argument': 잘못 명명 된 특성 인수입니다.  
  
 명명 된 인수는 유효한 특성 클래스 데이터 멤버를이 표시 되 면 안 `static`, `const`, 또는 `literal`합니다. 속성을 속성 되지 않아야 `static` 해야 get 및 set 접근자입니다.  
  
 자세한 내용은 참조 [속성](../../windows/property-cpp-component-extensions.md) 및 [사용자 정의 특성](../../windows/user-defined-attributes-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예  
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