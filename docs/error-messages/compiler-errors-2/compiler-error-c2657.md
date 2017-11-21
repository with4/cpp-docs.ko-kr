---
title: "컴파일러 오류 C2657 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2657
dev_langs: C++
helpviewer_keywords: C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e0e06104458961297a4d0a3de8b7cda756d16ab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
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