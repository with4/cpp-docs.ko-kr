---
title: "컴파일러 오류 C3797 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3797
dev_langs: C++
helpviewer_keywords: C3797
ms.assetid: ab27ff34-8c1d-4297-b004-9e39bd3a4f25
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5157e8b63bf15c2d972235e38f692e2ba356a629
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3797"></a>컴파일러 오류 C3797
'override': 이벤트 선언 (에 배치 해야 이벤트 추가/remove/raise 메서드에 대신) 하는 재정의 지정자를 사용할 수 없습니다  
  
 다른 trivial 이벤트와 trivial 이벤트 (명시적으로 정의 된 접근자 메서드 없이 이벤트)를 재정의할 수 없습니다. 재정의 하는 이벤트 접근자 함수로 동작을 정의 해야 합니다.  
  
 자세한 내용은 참조 [이벤트](../../windows/event-cpp-component-extensions.md)합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3797 오류가 발생 합니다.  
  
```  
// C3797.cpp  
// compile with: /clr /c  
delegate void MyDel();  
  
ref class Class1 {  
public:  
   virtual event MyDel ^ E;  
};  
  
ref class Class2 : public Class1 {  
public:  
   virtual event MyDel ^ E override;   // C3797  
};  
  
// OK  
ref class Class3 : public Class1 {  
public:  
   virtual event MyDel ^ E {  
      void add(MyDel ^ d) override {}  
      void remove(MyDel ^ d) override {}  
   }  
};  
```