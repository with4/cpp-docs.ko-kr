---
title: "컴파일러 오류 C2774 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2774
dev_langs: C++
helpviewer_keywords: C2774
ms.assetid: 10f428c6-7f49-489a-92ba-6ef978b7caaf
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8b5b8b898dead7d08795e25d87f66a2c24214fc3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2774"></a>컴파일러 오류 C2774
'identifier':이 속성을 통해 연결 된 'put' 메서드가 없습니다  
  
 데이터 멤버를 사용 하 여 선언 [속성](../../cpp/property-cpp.md) 아무런 `put` 함수가 있지만 식에서 해당 값을 설정 하려고 합니다.  
  
 다음 샘플에서는 C2774 오류가 생성 됩니다.  
  
```  
// C2774.cpp  
struct A {  
   __declspec(property(get=GetProp)) int prop;  
   int GetProp(void);  
  
   __declspec(property(get=GetProp2, put=PutProp2)) int prop2;  
   int GetProp2(void);  
   void PutProp2(int);  
};  
  
int main() {  
   A* pa = new A;  
   int val = 0;  
   pa->prop = val;   // C2774  
   pa->prop++;   // C2774  
}  
```