---
title: "컴파일러 경고 (수준 4) C4220 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4220
dev_langs: C++
helpviewer_keywords: C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fdcaeb5ec7e3b7258b9bb7b3edc188038e648c99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4220"></a>컴파일러 경고(수준 4) C4220
varargs는 나머지 매개 변수와 일치  
  
 기본 Microsoft 확장 (/Ze)에서는 함수에 대 한 포인터와 유사 하지만 변수, 인수를 갖는 함수에 대 한 포인터를 찾습니다.  
  
## <a name="example"></a>예  
  
```  
// C4220.c  
// compile with: /W4  
  
int ( *pFunc1) ( int a, ... );  
int ( *pFunc2) ( int a, int b);  
  
int main()  
{  
   if ( pFunc1 != pFunc2 ) {};  // C4220  
}  
```  
  
 이러한 포인터 ANSI 규격 일치 하지 않습니다 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).