---
title: "컴파일러 경고 (수준 1) C4087 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4087
dev_langs:
- C++
helpviewer_keywords:
- C4087
ms.assetid: 546e4d57-5c8e-422c-8ef1-92657336dad5
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 8c1ef0f7bc9badfc8ddd5f2cf0420568d4f524fb
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4087"></a>컴파일러 경고(수준 1) C4087
'function': 'void' 매개 변수 목록을 사용하여 선언되었습니다.  
  
 함수 선언에 정식 매개 변수가 없지만 함수 호출에 실제 매개 변수가 있습니다. 추가 매개 변수는 함수 호출 규칙에 따라 전달됩니다.  
  
 이 경고는 C 컴파일러용입니다.  
  
## <a name="example"></a>예제  
  
```  
// C4087.c  
// compile with: /W1  
int f1( void ) {  
}  
  
int main() {  
   f1( 10 );   // C4087  
}  
```
