---
title: "심각한 오류 C1004 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1004
dev_langs:
- C++
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c6a9e74d7918e1cb2c9190c87f4f1ec75f89237b
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1004"></a>심각한 오류 C1004
예기치 않은 파일의 끝  
  
 구문을 확인 하지 않고 컴파일러에 소스 파일의 끝에 도달 합니다. 코드는 다음 요소 중 하나가 없을 수 있습니다.  
  
-   닫는 중괄호  
  
-   닫는 괄호  
  
-   닫는 주석 표식 (* /)  
  
-   세미콜론  
  
 이 오류를 해결 하려면 다음을 확인 합니다.  
  
-   기본 디스크 드라이브에 소스 파일로 배의 공간에 대 한 필요한 임시 파일에 대 한 공간이 부족 합니다.  
  
-   `#if` 닫는 false 인 계산 되는 지시문 `#endif` 지시문입니다.  
  
-   소스 파일은 캐리지 리턴 및 줄 바꿈으로 끝나지 않습니다.  
  
 다음 샘플에서는 C1004 오류가 생성 됩니다.  
  
```  
// C1004.cpp  
#if TEST  
int main() {}  
// C1004  
```  
  
 해결 방법:  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```
