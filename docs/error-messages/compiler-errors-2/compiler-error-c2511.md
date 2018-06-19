---
title: 컴파일러 오류 c 2511을 발생 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2511
dev_langs:
- C++
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d97cbbd75d3b39b55ff640ed99e261ba349043d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199630"
---
# <a name="compiler-error-c2511"></a>컴파일러 오류 C2511
'identifier': 오버 로드 된 멤버 함수 'class'에서 찾을 수 없습니다  
  
 지정된 된 매개 변수 없는 버전의 함수 선언 됩니다.  가능한 원인:  
  
1.  잘못 된 매개 변수는 함수에 전달 합니다.  
  
2.  잘못 된 순서로 매개 변수 전달.  
  
3.  매개 변수 이름의 철자가 잘못 되었습니다.  
  
 다음 샘플에서는 c 2511을 발생 합니다.  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```