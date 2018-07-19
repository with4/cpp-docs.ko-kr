---
title: 컴파일러 오류 C2736 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2736
dev_langs:
- C++
helpviewer_keywords:
- C2736
ms.assetid: 95a6bc28-c0cb-49dc-87e6-e993dbbba881
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e3a7ad6d4259a5df0d85fd1f208df6d322430ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230679"
---
# <a name="compiler-error-c2736"></a>컴파일러 오류 C2736
캐스트에는 'keyword' 키워드를 사용할 수 없습니다.  
  
 키워드는 캐스트에 사용할 수 없습니다.  
  
 다음 샘플에서는 C2736 오류가 생성 됩니다.  
  
```  
// C2736.cpp  
int main() {  
   return (virtual) 0;   // C2736  
   // try the following line instead  
   // return 0;  
}  
```