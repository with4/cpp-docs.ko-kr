---
title: "컴파일러 오류 C2144 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2144
dev_langs:
- C++
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0f541465009dcc137b8853351d10ceb9d5db4d05
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2144"></a>컴파일러 오류 C2144
구문 오류: 'type' 앞에 있어야 '토큰이 있습니다.  
  
 예상 컴파일러 `token` 발견 `type` 대신 합니다.  
  
 이 오류는 누락 된 닫는 중괄호, 닫는 괄호 또는 세미콜론이으로 발생할 수 있습니다.  
  
 C2144 공백 문자를 포함 하는 CLR 키워드에서 매크로를 만들려고 할 때에 발생할 수 있습니다.  
  
 C2144는 형식을 전달 하려는 경우에 나타날 수 있습니다. 참조 [형식 전달 (C + + /cli CLI)](../../windows/type-forwarding-cpp-cli.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2144 오류가 발생 합니다.  
  
```  
// C2144.cpp  
// compile with: /clr /c  
#define REF ref  
REF struct MyStruct0;   // C2144  
  
// OK  
#define REF1 ref struct  
REF1 MyStruct1;  
```  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2144 오류가 발생 합니다.  
  
```  
// C2144_2.cpp  
// compile with: /clr /c  
ref struct X {  
  
   property double MultiDimProp[,,] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp[int , int, int] {  
      double get(int, int, int) { return 1; }  
      void set(int i, int j, int k, double l) {}  
   }  
  
   property double MultiDimProp2[] {   // C2144  
   // try the following line instead  
   // property double MultiDimProp2[int] {  
      double get(int) { return 1; }  
      void set(int i, double l) {}  
   }  
};  
```
