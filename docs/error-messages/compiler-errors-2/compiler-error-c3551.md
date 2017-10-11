---
title: "컴파일러 오류 C3551 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3551
dev_langs:
- C++
helpviewer_keywords:
- C3551
ms.assetid: c8ee23da-6568-40db-93a6-3ddb7ac47712
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 450bd97efc9cfbf07eac84a3e6a693af698fc64f
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3551"></a>컴파일러 오류 C3551
"런타임에 지정된 반환 형식이 필요합니다."  
  
 `auto` 키워드를 함수 반환 형식에 대한 자리 표시자로 사용하는 경우 컴파일하면 지정되는 반환 형식을 제공해야 합니다. 다음 예제에서는 런타임에 지정된 `myFunction` 함수의 반환 형식이 `int`형식의 네 요소 배열에 대한 포인터입니다.  
  
```  
auto myFunction()->int(*)[4];   
```  
  
## <a name="see-also"></a>참고 항목  
 [auto](../../cpp/auto-cpp.md)
