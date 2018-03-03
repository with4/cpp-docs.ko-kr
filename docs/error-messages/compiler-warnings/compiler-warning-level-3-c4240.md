---
title: "컴파일러 경고 (수준 3) C4240 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4240
dev_langs:
- C++
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 662aaeb3246fac20bd0ac9f3412424bfacac5698
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4240"></a>컴파일러 경고(수준 3) C4240
비표준 확장이 사용 됨: 이제 정의 됩니다. 이전에 ' 액세스 지정자', 'classname'에 대 한 액세스를 '액세스 지정자' 되도록 정의 되어 있습니다.  
  
 ANSI 호환성 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), 중첩된 클래스에 대 한 액세스를 변경할 수 없습니다. 기본 Microsoft 확장 (/Ze)에서는 할 수 있습니다, 이러한 경고.  
  
## <a name="example"></a>예  
  
```  
// C4240.cpp  
// compile with: /W3  
class X  
{  
private:  
   class N;  
public:  
   class N  
   {   // C4240  
   };  
};  
  
int main()  
{  
}  
```