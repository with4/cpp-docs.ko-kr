---
title: 컴파일러 오류 C2657 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2657
dev_langs:
- C++
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70814ce7423bee3147f68d6298babc10eeac56fb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231385"
---
# <a name="compiler-error-c2657"></a>컴파일러 오류 C2657
' 클래스:: *'에서 문의 시작 찾을 (했는지 확인 한 형식을 지정 하 시겠습니까?)  
  
 줄의 멤버 포인터를 식별자로 시작 합니다.  
  
 이 오류는 멤버에 대 한 포인터의 선언에서 누락 된 형식 지정자에 의해 발생할 수 있습니다.  
  
 다음 샘플에서는 C2657 오류가 생성 됩니다.  
  
```  
// C2657.cpp  
class C {};  
int main() {  
   C::* pmc1;        // C2657  
   int C::* pmc2;   // OK  
}  
```