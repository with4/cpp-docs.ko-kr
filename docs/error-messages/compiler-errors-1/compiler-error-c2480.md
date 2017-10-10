---
title: "컴파일러 오류 C2480 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 06f6c536d5756a19e28df7060373512e3e883a41
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2480"></a>컴파일러 오류 C2480
'identifier': 't h'는 정적 범위의 데이터 항목에만 유효  
  
 사용할 수 없습니다는 `thread` 는 자동 변수, 비정적 데이터 멤버, 함수 매개 변수 또는 함수 선언 또는 정의에 특성입니다.  
  
 사용 하 여는 `thread` 전역 변수, 정적 데이터 멤버 및 지역 정적 변수에에 대 한 특성입니다.  
  
 다음 샘플에서는 C2480 오류가 생성 됩니다.  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```
