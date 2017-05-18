---
title: "컴파일러 경고 (수준 1) C4190 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: bf45c0737f52da93f93c1f95d313771f0e92a10e
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4190"></a>컴파일러 경고 (수준 1) C4190
'identifier1'에 C 링크가 지정 하지만 C와 호환 되지 않는 ' identifier2' UDT를 반환 합니다.  
  
 반환 형식으로 함수 또는 함수 포인터에 UDT (사용자 정의 형식, 클래스, 구조체, 열거형 또는 공용 구조체는) 및 `extern` "C" 링크가 있습니다. 유효 하는 경우:  
  
-   C + +에서이 함수에 대 한 모든 호출이 발생합니다.  
  
-   C + +에서 함수 정의.  
  
## <a name="example"></a>예제  
  
```cpp  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```
