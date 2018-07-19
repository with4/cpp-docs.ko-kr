---
title: 컴파일러 오류 C2061 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2061
dev_langs:
- C++
helpviewer_keywords:
- C2061
ms.assetid: b0e61c0c-a205-4820-b9aa-301d6c6fe6eb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d4d4b018dbab16e8e376a3331a85d0f1b1004f5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167381"
---
# <a name="compiler-error-c2061"></a>컴파일러 오류 C2061
구문 오류: 'identifier' 식별자  
  
 컴파일러가 예기치 못했던 식별자를 찾았습니다. 다음 사항을 확인 `identifier` 사용 하기 전에 선언 합니다.  
  
 이니셜라이저는 괄호로 묶을 수 있습니다. 이 문제를 방지 하려면 괄호로 묶거나 하거나 쉽게는 `typedef`합니다.  
  
 컴파일러는 클래스 템플릿 인수로; 식을 검색 하는 경우이 오류가 발생할 수 또한 사용 하 여 [typename](../../cpp/typename.md) 형식이 컴파일러에 지시 합니다.  
  
 다음 샘플에서는 C2061 오류가 생성 됩니다.  
  
```  
// C2061.cpp  
// compile with: /c  
template < A a >   // C2061  
// try the following line instead  
// template < typename b >  
class c{};  
```  
  
 C2061 인스턴스 이름을 전달 하는 경우 발생할 수 있습니다 [typeid](../../windows/typeid-cpp-component-extensions.md):  
  
```  
// C2061b.cpp  
// compile with: /clr  
ref struct G {  
   int i;  
};  
  
int main() {  
   G ^ pG = gcnew G;  
   System::Type ^ pType = typeid<pG>;   // C2061  
   System::Type ^ pType2 = typeid<G>;   // OK  
}  
```