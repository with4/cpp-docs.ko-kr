---
title: "main 함수 제한 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Main
dev_langs: C++
helpviewer_keywords: main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c444fe53719aea5c78477aa9d9f35134c44d99a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="main-function-restrictions"></a>main 함수 제한
에 몇 가지 제한이 적용 된 **주** 다른 모든 c + + 함수에 적용 되지 않는 함수입니다. **주** 함수:  
  
-   오버 로드할 수 없습니다 (참조 [함수 오버 로드](function-overloading.md)).  
  
-   로 선언할 수 없습니다 **인라인**합니다.  
  
-   로 선언할 수 없습니다 **정적**합니다.  
  
-   주소를 사용할 수 없습니다.  
  
-   호출할 수 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [main: 프로그램 시작](../cpp/main-program-startup.md)