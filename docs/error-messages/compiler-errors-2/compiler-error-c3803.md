---
title: 컴파일러 오류 C3803 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3803
dev_langs:
- C++
helpviewer_keywords:
- C3803
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d720e2f94cc4a480122413e31b897ec1718ebc15
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3803"></a>컴파일러 오류 C3803
'property': 속성에는 해당 접근자 'accessor' 중 하 나와 호환 되지 않는 형식  
  
 정의 된 속성의 형식은 [속성](../../cpp/property-cpp.md) 해당 접근자 함수 중 하나에 대 한 반환 형식과 일치 하지 않습니다.  
  
 다음 샘플에서는 C3803 오류가 생성 됩니다.  
  
```  
// C3803.cpp  
struct A  
{  
   __declspec(property(get=GetIt)) int i;  
   char GetIt()  
   {  
      return 0;  
   }  
  
   /*  
   // try the following definition instead  
   int GetIt()  
   {  
      return 0;  
   }  
   */  
}; // C3803  
  
int main()  
{  
}  
```