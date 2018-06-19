---
title: 컴파일러 오류 C2246 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2246
dev_langs:
- C++
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6d4de93f964807003dbfcfb6717b8a858354c1c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169025"
---
# <a name="compiler-error-c2246"></a>컴파일러 오류 C2246
'identifier': 지역으로 정의된 클래스에 잘못된 정적 데이터 멤버가 있습니다.  
  
 로컬 범위를 가진 클래스, 구조체 또는 공용 구조체의 멤버가 `static`으로 선언되었습니다.  
  
 다음 샘플에서는 C2246을 생성합니다.  
  
```  
// C2246.cpp  
// compile with: /c  
void func( void ) {  
   class A { static int i; };   // C2246  i is local to func  
   static int j;   // OK  
};  
```