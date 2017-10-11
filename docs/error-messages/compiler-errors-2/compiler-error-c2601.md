---
title: "컴파일러 오류 C2601 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2601
dev_langs:
- C++
helpviewer_keywords:
- C2601
ms.assetid: 88275582-5f37-45d7-807d-05f06ba00965
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cdffa40b751232525920d1d92affd9e3778d2f61
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2601"></a>컴파일러 오류 C2601
'function': 지역 함수 정의가 적합 하지 않습니다.  
  
 코드는 함수 내에서 함수를 정의 하려고 시도 합니다.  
  
 또는 C2601 오류가 발생 한 위치 하기 전에 소스 코드에서는 추가로 중괄호 있을 수 있습니다.  
  
 다음 샘플에서는 C2601 오류가 생성 됩니다.  
  
```  
// C2601.cpp  
int main() {  
   int i = 0;  
  
   void funcname(int j) {   // C2601  
      j++;  
   }  
}  
```
