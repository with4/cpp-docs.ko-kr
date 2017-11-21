---
title: "컴파일러 오류 C2718 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2718
dev_langs: C++
helpviewer_keywords: C2718
ms.assetid: 78cc71f8-c142-46fc-9aed-970635d74f0c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5e3243d75f6bf1b389d624a85d04625f9bf0d368
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2718"></a>컴파일러 오류 C2718
'parameter': __declspec(align('#')) 인 실제 매개 변수는 맞춰지지 않습니다  
  
 [맞춤](../../cpp/align-cpp.md) `__declspec` 한정자 함수 매개 변수에서 허용 되지 않습니다.  
  
 다음 샘플에서는 C2718 오류가 생성 됩니다.  
  
```  
// C2718.cpp  
typedef struct __declspec(align(32)) AlignedStruct  {   
   int i;   
} AlignedStruct;  
  
void f2(int i, ...);  
  
void f4() {  
   AlignedStruct as;  
  
   f2(0, as);   // C2718, actual parameter is aligned  
}  
```