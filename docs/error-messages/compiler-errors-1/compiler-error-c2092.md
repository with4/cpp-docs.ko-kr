---
title: "컴파일러 오류 C2092 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2092
dev_langs: C++
helpviewer_keywords: C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 45178f653871aea85071aa5df643ebd579f05419
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2092"></a>컴파일러 오류 C2092
'배열 이름' 배열 요소 형식은 함수 일 수 없습니다.  
  
 함수의 배열은 허용 되지 않습니다. 함수 포인터의 배열을 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2092 오류가 생성 됩니다.  
  
```  
// C2092.cpp  
typedef void (F) ();  
typedef F AT[10];   // C2092  
```  
  
## <a name="example"></a>예제  
 해결 방법:  
  
```  
// C2092b.cpp  
// compile with: /c  
typedef void (F) ();  
typedef F * AT[10];  
```