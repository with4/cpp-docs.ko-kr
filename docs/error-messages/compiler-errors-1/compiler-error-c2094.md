---
title: "컴파일러 오류 C2094 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2094
dev_langs: C++
helpviewer_keywords: C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d87846c5ea26ee9157f895f43b1f96fdc67602d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2094"></a>컴파일러 오류 C2094
'identifier' 레이블이 정의되지 않았습니다.  
  
[goto](../../cpp/goto-statement-cpp.md) 문에서 사용하는 레이블이 함수에 존재하지 않습니다.  
  
## <a name="example"></a>예  
다음 샘플에서는 C2094를 생성합니다.  
  
```cpp  
// C2094.c  
int main() {  
   goto test;  
}   // C2094  
```  
  
 해결 방법:  
  
```cpp  
// C2094b.c  
int main() {  
   goto test;  
   test:   
   {  
   }  
}  
```