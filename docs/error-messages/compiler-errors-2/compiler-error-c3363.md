---
title: "컴파일러 오류 C3363 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3363
dev_langs: C++
helpviewer_keywords: C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dbdd31f9ecdc6f458f09d0561465cdf21cdde250
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3363"></a>컴파일러 오류 C3363
'type': 'typeid'는 형식에만 적용될 수 있습니다.  
  
 [typeid](../../windows/typeid-cpp-component-extensions.md) 연산자를 잘못 사용했습니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C3363을 생성합니다.  
  
```  
// C3363.cpp  
// compile with: /clr  
int main() {  
   System::typeid;   // C3363  
}  
```