---
title: 컴파일러 오류 C2433 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2433
dev_langs:
- C++
helpviewer_keywords:
- C2433
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8445e35b929dc3fa2d9d6507f0b6469df26130db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2433"></a>컴파일러 오류 C2433
'identifier': 'modifier' 데이터 선언에 사용할 수 없습니다  
  
 `friend`, `virtual`, 및 `inline` 데이터 선언에 대 한 한정자를 사용할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C2433 오류가 발생 합니다.  
  
```  
// C2433.cpp  
class C{};  
  
int main() {  
   inline C c;   // C2433  
}  
```