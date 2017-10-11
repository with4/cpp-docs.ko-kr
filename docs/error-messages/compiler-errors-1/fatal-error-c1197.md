---
title: "심각한 오류 C1197 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1197
dev_langs:
- C++
helpviewer_keywords:
- C1197
ms.assetid: 22b801b7-e792-41f6-a461-973c03c69f25
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d0eb3ab152e9299d47210a6d2c1eb58e3f92a925
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1197"></a>심각한 오류 C1197
프로그램에 이미 'mscorlib.dll_2'를 참조 하는 대로 'mscorlib.dll_1'를 참조할 수 없습니다.  
  
 공용 언어 런타임의 버전은 컴파일러와 일치 합니다.  그러나 이전 버전에서 공용 언어 런타임 파일의 버전을 참조 하도록 시도가.  
  
 이 오류를 해결 하려면만 사용 하 여 컴파일하는 Visual c + +의 버전과 함께 제공 되는 공용 언어 런타임의 버전에서 파일을 참조 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C1197 오류가 생성 됩니다.  
  
```  
// C1197.cpp  
// compile with: /clr /c  
// processor: x86  
#using "C:\Windows\Microsoft.NET\Framework\v1.1.4322\mscorlib.dll"   // C1197  
// try the following line instead  
// #using "mscorlib.dll"  
```
