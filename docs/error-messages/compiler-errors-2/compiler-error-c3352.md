---
title: "컴파일러 오류 C3352 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3352
dev_langs:
- C++
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 65643abc883cfd0674dbb908c8ab26f274f65cd4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3352"></a>컴파일러 오류 C3352
'function': 지정한 함수가 'type' 대리자 형식이 일치 하지 않습니다  
  
 에 대 한 매개 변수 목록이 `function` / 대리자 일치 하지 않습니다.  
  
 자세한 내용은 참조 [대리자 (c + + 구성 요소 확장명)](../../windows/delegate-cpp-component-extensions.md)합니다.  
  
 다음 샘플에서는 C3352 오류가 생성 됩니다.  
  
```  
// C3352.cpp  
// compile with: /clr  
delegate int D( int, int );  
ref class C {  
public:  
   int mf( int ) {  
      return 1;  
   }  
  
   // Uncomment the following line to resolve.  
   // int mf(int, int) { return 1; }  
};  
  
int main() {  
   C^ pC = gcnew C;  
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352  
}  
```  

