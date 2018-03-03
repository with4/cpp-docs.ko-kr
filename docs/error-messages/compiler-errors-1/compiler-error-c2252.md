---
title: "컴파일러 오류 C2252 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2252
dev_langs:
- C++
helpviewer_keywords:
- C2252
ms.assetid: fee74ab9-1997-4615-82fe-e6d1fe3aacd9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 60326d37e4c672487161abc53bf649056a2c4a52
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2252"></a>컴파일러 오류 C2252
현재 범위에 템플릿이 명시적으로 인스턴스화할 수 없습니다.  
  
 컴파일러에 문제가 템플릿의 명시적 인스턴스화를 발견 했습니다.  예를 들어 함수에 대 한 서식 파일을 명시적으로 인스턴스화할 수 없습니다.  
  
 다음 샘플에서는 C2252 오류가 생성 됩니다.  
  
```  
// C2252.cpp  
class A {  
public:  
   template <class T>  
   int getit(int i , T * it ) {  
      return i;  
   }  
   template int A::getit<double>(int i, double * it);   // C2252  
   // try the following line instead  
   // template <> int A::getit<double>(int i, double * it);  
  
};  
  
int main() {  
   // cannot explicitly instantiate in function  
   template int A::getit<long>(int i, long * it);   // C2252  
}  
```