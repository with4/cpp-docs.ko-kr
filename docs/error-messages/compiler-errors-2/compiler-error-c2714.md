---
title: "컴파일러 오류 C2714 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2714
dev_langs:
- C++
helpviewer_keywords:
- C2714
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f5c86d4f5081d035749218be8fccb14b846641f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2714"></a>컴파일러 오류 C2714
__alignof(void) 허용 되지 않습니다.  
  
 잘못 된 값은 운영자에 게 전달 되었습니다.  
  
 참조 [__alignof 연산자](../../cpp/alignof-operator.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C2714 오류가 발생 합니다.  
  
```  
// C2714.cpp  
int main() {  
   return __alignof(void);   // C2714  
   return __alignof(char);   // OK  
}  
```