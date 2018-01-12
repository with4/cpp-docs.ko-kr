---
title: "컴파일러 경고 (수준 1) C4087 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4087
dev_langs: C++
helpviewer_keywords: C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ef21fc01fc6c756eb68f90bd58f9b18456e12fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4087"></a>컴파일러 경고(수준 1) C4087
'function': 'void' 매개 변수 목록을 사용하여 선언되었습니다.  
  
 함수 선언에 정식 매개 변수가 없지만 함수 호출에 실제 매개 변수가 있습니다. 추가 매개 변수는 함수 호출 규칙에 따라 전달됩니다.  
  
 이 경고는 C 컴파일러용입니다.  
  
## <a name="example"></a>예  
  
```  
// C4087.c  
// compile with: /W1  
int f1( void ) {  
}  
  
int main() {  
   f1( 10 );   // C4087  
}  
```