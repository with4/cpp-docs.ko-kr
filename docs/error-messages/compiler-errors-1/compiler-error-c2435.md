---
title: "컴파일러 오류 C2435 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2435
dev_langs:
- C++
helpviewer_keywords:
- C2435
ms.assetid: be6aa8f8-579b-42ea-bdd8-2d01393646ad
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b70ebf347e2d5b6af8938e348a5e789412241256
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2435"></a>컴파일러 오류 C2435
'var': 동적 초기화는 관리 되는 CRT 필요, /clr: safe를 컴파일할 수 없습니다  
  
 **/clr:pure** 및 **/clr:safe** 컴파일러 옵션은 Visual Studio 2015에서는 더 이상 사용되지 않습니다.  
  
 응용 프로그램별 도메인 전역 변수는 초기화로 컴파일된 CRT가 필요 `/clr:pure`를 확인할 수 있는 이미지를 생성 하지 않는 합니다.  
  
 자세한 내용은 [appdomain](../../cpp/appdomain.md) 및 [process](../../cpp/process.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2435 오류가 생성 됩니다.  
  
```  
// C2435.cpp  
// compile with: /clr:safe /c  
int globalvar = 0;   // C2435  
  
__declspec(process)  
int globalvar2 = 0;  
```
